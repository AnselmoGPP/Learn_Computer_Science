# Vulkan API fundamentals

<br>![computer graphics image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/computer_graphics.jpg)

## Table of Contents
+ [Quick overview](#quick-overview)
+ [Basics](#basics)
+ [Fundamentals](#fundamentals)
+ [Synchronization](#synchronization)
+ [Particularities](#particularities)
+ [Glossary](#glossary)
+ [Links](#links)


## Quick overview

### Rendering environment:

Create a **window** (e.g. `GLFWwindow`) and a **Vulkan instance** (`VkInstance`). Create an abstraction of the window: **surface** (`VkSurfaceKHR`). To use validation layers, create a **debugMessenger** (`VkDebugUtilsMessengerEXT`) and a **callback** (outputs validation layers information). 

Choose a **physical device** (`VkPhysicalDevice`) and create a **logical device** from it (`VkDevice`). The device has to support:

- **Queues** (`VkQueue`). Most operations are (asynchronously) executed by submitting them to a queue. We will select the queues that support the commands we want to use (**graphics** and **presentations** to window surface).

- **Swap chain** (`VkSwapchainKHR`). It is a collection of render targets that ensures that we don’t render an image directly on the image in the screen. For each swap chain image we need to create the following: `VkImage`, `VkImageView`, `VkFramebuffer` (this one, later). But the `VkDeviceMemory` is already created inside the swap chain implicitly.

Typically, image objects involve 3 elements: 
- `VkImage`: Image object.
- `VkImageView`: Image handler. It references a part of the image to be used (subset of its pixels). Required for being able to access it.
- `VkDeviceMemory`: Handle to a device memory object.

After creating `VkQueue`and a `VkSwapchainKHR`, we create one or more **render passes** (`VkRenderPass`), each one containing one or more subpasses. This describes the order of execution during rendering, and the images (**attachments**) used (each one needs a `VkImage`, `VkImageView`, and `VkDeviceMemory`).

Create the swap chain’s **framebuffers** (`VkFramebuffer`), one per swap chain image. Each framebuffer references all the `VkRenderPasses` and their attachments (`VkImageViews`). The final attachment (where the final image is rendered) is the corresponding swap chain’s `VkImageView`.

Create a **command-pool** (`VkCommandPool`). It contains all the commands that we want to use in a single thread. Record the operations you want to perform here, and execute them in the render loop by packing them in a **command buffer** (`VkCommandBuffer`) and submitting it to a queue (graphics, presentation).

### Object to render:

Create **shaders** (`VkShaderModule`) and load **textures** (`VkImage`, `VkImageView`, `VkDeviceMemory`, `VkSampler`). A `VkSampler` is a wrapper around a textures that applies filtering and transformations, and shaders access image resources through sampler objects.

Create a `VkDescriptorSetLayout` (blueprint for descriptor sets creation). 

Create the **graphics pipeline** (`VkPipeline`), which describes all the operations for transforming our vertices and textures into pixels (vertex data, shaders, primitive type, viewport, rasterizer, multisampling, depth buffer, stencil buffer, color blending, dynamic states, descriptor set layout, ...).

Create buffers for the **vertex** data and the **indices** (each one requires a `VkBuffer` and `VkDeviceMemory`).

Create the **descriptor set**. Each descriptor is a handle/pointer into a resource (UBO, sampler, ...) the shader has access to. Steps:

- Create **descriptors** (`VkBuffer` + `VkDeviceMemory`).
- Create `VkDescriptorPool` (it specifies the total number of descriptors in a single thread).
- Create `VkDescriptorSet` (set of descriptors. One per swapchain image).

Save the drawing command for your object in the **command buffer**. 

### Drawing:

Drawing commands (`vkCmdDraw()`) are explicitly recorded to a `VkCommandBuffer` (which is allocated from a `VkCommandPool`). This requires binding some elements: render pass, subpass, vertex buffer, index buffer, descriptor sets.

To render to one of the swapchain images we call `vkAcquireNextImageKHR()` to get the index of the next image in the chain. Then, we submit our `VkCommandBuffer` to the `VkQueue` (via `vkQueueSubmit()`), which passes the commands to the GPU and executes them. Then, we call `vkQueuePresentKHR()` to present the rendered image to the display.

### Others:

Synchronize things using synchronization objects: **Semaphores** (wait inside Vulkan), **fences** (wait in our own code), **barriers** (synchronize GPU operations) and **external synchronization** (this is up to us).

- Image available (`VkSemaphore`)
- Render finished (`VkSemaphore`)
- Frames in flight (`VkFence`)
- Images in flight (`VkFence`)

Optional: For real time rendering, run a render loop.

- Check for events
- Wait (frames in flight) for command buffer to execute
- Acquire image from swap chain
- If that image is used, wait (images in flight) until not used
- User updates: Check for events, update descriptor sets data, etc.
- Command buffer: Update (if necessary) and submit
- Presentation of image to swap chain

Optional: For better performance, run a parallel thread for loading/unloading resources (meshes, textures, shaders).

Shaders get data from:

- Vertex buffer (`VkBuffer`, `VkDeviceMemory`)
- Index buffer (`VkBuffer`, `VkDeviceMemory`)
- Descriptor set (`VkDescriptorSet`)
  - Uniform buffers (`VkBuffer`, `VkDeviceMemory`)
  - Textures (`VkImage`, `VkImageView`, `VkDeviceMemory`, `VkSampler`)
- Input attachments (input from a previous subpass)


## Basics

### Starting

Vulkan is a C API for computer graphics and computing on GPUs. It's heavily typed (each enum is separate, and returned handles are opaque 64-bit handles so they are typed on 64-bit). Most functions take big structures as parameters instead of basic types. 

First, create a `VkInstance` (Vulkan instances don't know about each other) and specify simple information (layers, extensions...). Use it to examine available GPUs,  with `VkEnumeratePhysicalDevices()` and check their properties (`vkGetPhysicalDeviceProperties()`) and features (`vkGetPhysicalDeviceFeatures()`). Then, take one `VkPhysicalDevice` and use it for creating a `VkDevice` (handle for the GPU you'll use). Note: A `VkInstance` can have many `VkPhysicalDevices`, while each one can have many `VkDevices`.

### Images and buffers

We can use our `VkDevice` for creating pretty much every other resource type (`VkImage`, `VkBuffer`...). 

- When creating an **image**, you have to declare in advance how it will be used (color attachment, shader sampled image, image load/store...), and the tiling/swizzling layout of the image data in memory (`LINEAR`, `OPTIMAL` ...). Images aren't used directly, but via a `VkImageView`, which describes what array slices or mip levels are visible, and (optionally) a different (compatible) format (e.g. aliasing `UNORM` texture as `UINT`).

- When creating a **buffer** you have to specify its size and usage. Buffers are usually used directly since they're just a block of memory, but if you want to use it as a texel buffer in a shader, you need to provide a `VkBufferView`.

### Allocating GPU memory

Before using those images and buffers you have to allocate memory for them with `vkAllocateMemory()`, which returns a `VkDeviceMemory` handle.

Available memory is exposed via `vkGetPhysicalDeviceMemoryProperties()`, which reports one or more memory **heaps** of given sizes, each one providing one or more memory **types** with given properties (CPU visible or not, coherent GPU and CPU access, cached or uncached, ...). Example: a discrete GPU may have 2 heaps (one for system RAM and one for GPU RAM) and multiple memory types from each.

When calling `vkAllocateMemory()` we specify how much memory to allocate, and what memory type we want from which heap (e.g. images for rendering may prefer device local memory for optimal use, while staging resources need host visible memory). Host visible memory can be mapped for update with `vkMapMemory()` (returns a pointer) and `vkUnMapMemory()`. All these maps (pointers to memory) are persistent, and it's legal to have memory mapped while in use by the GPU as long as you synchronise.

Note: To allocate data that must be GPU visible only, we first create a CPU and GPU visible buffer (staging buffer) where we store our data (vertex data, indices...) from the CPU. Then, we make the GPU copy this data to a GPU visible only buffer and delete the staging buffer.

### Binding memory

Each `VkBuffer` or `VkImage`, depending on its properties (tiling mode, usage flags...) will report their memory requirements via `vkGetBufferMemoryRequirements` or `vkGetImageMemoryRequirements`. The reported size accounts for padding for alignment between mips, hidden meta-data, etc. The requirements also include a bitmask of the memory types that are compatible with this resouce. Once you have the right memory type, size, and alignment, you can bind it with `vkBindBufferMemory` or `vkBindImageMemory`. This bind is **immutable** and must happen before you start using this resource.

### Command buffers and submissions

Commands are explicitly recorded to a `VkCommandBuffer`, which is then submitted to a `VkQueue` via `vkQueueSubmit()`. These commands will be executed in turn (though Vulkan has very specific ordering guarantees, mostrly about what work can overlap rather than wholesale rearrangement). 

A `VkCommandBuffer` is allocated from a `VkCommandPool`. This allows better threading behaviour since command buffers and command pools must be externally synchronised. You can have a pool per thread and allocate (`vkAllocateCommandBuffers()`) or free (`vkFreeCommandBuffers()`) command buffers without heavy locking.

A `VkQueue` makes work serialised to be passed to the GPU. A `VkPhysicalDevice` can report a number of queue __families__ with different capabilities (graphics, compute...). When you create your device you ask for a certain number of queues from each family, and then you can enumerate them from the device after creation with `vkGetDeviceQueue()`. When using multiple queues, they must be synchronised against each other since they can run out of order or in parallel. Be aware that some implementations might require you to use a separate queue for swapchain presentation (most won't).

### Shaders and pipeline state objects (PSO)

A `VkPipeline` takes a lot of state, but allows specific parts of the fixed function pipeline to be set dynamically (viewport, stencil masks and refs, blend constants, ...) when calling `vkCreateGraphicsPipelines()`. Optionally, you can specify a `VkPipelineCache` at creation time, which allows to compile a bunch of pipelines and save it to disk (`vkGetPipelineCacheData()`).

A `VkShaderModule` is created from a SPIR-V module, which can contain several entry points, and you choose one of them at pipeline creation.

### Binding model

The base binding unit is a **descriptor** (opaque representation that stores 'one bind'). This can be an image, sampler, uniform/constant buffer, etc. It can be arrayed (you have an array of images that can be different sizes, etc. as long as they are all 2D floating point images). Descriptors aren't bound individually, but in blocks in a `VkDescriptorSet`. The types of individual bindings contained in a `VkDescriptorSet` are described in a `VkDescriptorSetLayout`. Imagine `VkDescriptorSetLayout` as a C struct type describing some opaque type members, the `VkDescriptorSet` as a specific instance of that type, and each member inside as a binding that can be updated with any resource you want. You allocate a `VkDescriptorSet` with a given layout from a `VkDescriptorPool` (used to allocate descriptors on different threads more efficiently by having a pool per thread).

You can update a descriptor set directly to put specific values in the bindings (descriptors). When creating a pipeline, we specify n `VkDescriptorSetLayouts` for use in a `VkPipelineLayout`. Then, when binding, we have to bind matching `VkDescriptorSets` of those layouts. The sets can update and be bound at different frequencies, which allows grouping all resources by frequency of update. Imagine the pipeline as a function that takes some number of structs as arguments, so when you create a pipeline you declare the type (`VkDescriptorSetLayouts`) of each parameters, and when binding the pipeline you pass specific instances (arguments) of those types (`VkDescriptorSets`).

In the shader, each resource says which descriptor set and bindings it pulls from (`layout(set = 0, binding = 1) uniform myUBtype {...} myUBinstantce;`), which matches your descriptor set layout.

### Synchronisation

Some object types have to be **externally synchronized**. Example: if you use the same `VkQueue` on two different threads, there's no internal locking so it will crash (it's up to you to synchronize this). Check the spec for knowing what objects must be externally synchronised. As a rule, you can use `VkDevice` for creation functions freely (it's locked for allocation sake), but recording and submitting commands must be synchronised.

Some other types have to be **internally synchronized**. `VkEvent`, `VkSemaphore`, and `VkFence` can be used for efficient CPU-GPU and GPU-GPU synchronization, but be careful since there are a few ordering guarantees in the spec.

**Pipeline barriers** are generally used for ensuring ordering of GPU-side operation where necessary (e.g. to ensure that results from one operation are completed before another operation starts, or to ensure that all work of one type  finishes on a resource before it's used for work of another type). Three types of barriers: `VkMemoryBarrier` (applies to memory globally), `VkBufferMemoryBarrier`, and `VkImageMemoryBarrier` (both apply to specific resources, and subsections of them). Barriers take a bit field of different memory access types to specify what operations on each side of the barrier should be synchronised against the other. Example: a `VkImageMemoryBarrier` containing `srcAccessMask = ACCESS_COLOR_ATTACHMENT_WRITE` and `dstAccessMask = ACCESS_SHADER_READ` indicates that all color writes should finish before any shader reads begin).

Images exist in states called __image layouts__. A `VkImageMemoryBarrier` can specify a transition from one layout to another. The layout must match how the image is used at any time. There's a `GENERAL` layout that can be used for anything but might not be optimal, and there optimal layouts for color attachment, depth attachment, shader sampling, etc.

You can choose the initial state of an image: `UNDEFINED` (undefined contents) or `PREINITIALIZED` (useful for populating an image with data before use). Transitioning from `UNDEFINED` to `GENERAL` may lose contents, but `PREINITIALIZED` to `GENERAL` won't. Neither initial layout is valid for use by the GPU, so after creation an image needs to be transitioned into some appropriate state.

### Render passes

A `VkFramebuffer` is a set of `VkImageViews`. A `VkRenderPass` describes how your rendering happens. It contains a series of __subpasses__. The subpass selects some of the framebuffer attachments as color attachments (output images) and maybe one as a depth-stencil attachment. If you have multiple subpasses, each one may use a different subset of attachments for input and output.

Drawing commands can only happen inside a `VkRenderPass`, some commands (copies clears, ...) can only happen outside, and some other commands (state binding, ...) can happen inside or outside at will.

Subpasses don't inherit state. Each time you start a `VkRenderPass` or move to a new subpass you have to bind/set all of the state. Subpasses also specify an action both for loading and storing each attachment (clear buffer, overwrite screen, ...). 

When creating a `VkRenderPass` and its subpasses you specify the format and use of all attachments. When creating a `VkFramebuffer` you must choose a compatible (same number and format of attachments) `VkRenderPass` that will be used with it. When creating a `VkPipeline` you have to specify a compatible `VkRenderPass` and subpass that will be used with. If your render pass has multiple subpasses, you have to declare barriers and dependencies between.

### Backbuffers and presentation

Create a `VkSurfaceKHR` from whatever native windowing information is needed (Vulkan exposes native window system integration via extensions). Then, create a `VkSwapchainKHR` for that surface. Get the actual images in the `VkSwapchainKHR` via `vkGetSwapchainImagesKHR()`. These are normal `VkImage` handles, but you don't control their creation or memory binding (this is done for you, although you do have to create a `vkImageView` for each one. To render to one of these images, call `vkAcquireNextImageKHR()` to get the index of the next image in the chain. Render to it and call `vkQueuePresentKHR()` to present it to the display.

### Basic pseudocode example

<pre>
#include <vulkan/vulkan.h>

void doRendering()
{
  VkInstance inst;
  const char extensionNames[] = { "VK_KHR_surface", "VK_KHR_win32_surface" };
  VkInstanceCreateInfo instanceCreateInfo = { ..., extensionNames };
  <b>vkCreateInstance</b>(&instanceCreateInfo, NULL, &inst);

  VkDevice dev;
  VkPhysicalDevice phys[4];
  vkEnumeratePhysicalDevices(inst, 4, phys);
  vkDeviceCreateInfo deviceCreateInfo = { ... };
  <b>vkCreateDevice</b>(phys[0}, &deviceCreateInfo, NULL, &dev);

  VkSurfaceKHR surf;
  VkWin32SurfaceCreateInfoKHR surfaceCreateInfo = { ... };
  <b>vkCreateWin32SurfaceKHR</b>(inst, &surfaceCreateInfo, NULL, &surf);
  
  VkSwapchainKHR swap;
  VkSwapchainCreateInfoKHR swapCreateInfo = { ... };
  <b>vkCreateSwapchainKHR</b>(dev, &swapCreateInfo, NULL, &swap);

  VkImage image[4];
  <b>vkGetSwapchainImagesKHR</b>(dev, swap, 4, images);

  uint32_t currentSwapImage;
  <b>vkAcquireNextImageKHR</b>(dev, swap, UINT64_MAX, presentCompleteSemaphore, NULL, &currentSwapImage);
  
  VkImageView backbufferView;
  <b>vkCreateImageView</b>(dev, &backbufferViewCreateInfo, NULL, &backbufferView);
  
  VkQueue queue;
  <b>vkGetDeviceQueue</b>(dev, 0, 0, &queue);

  VkRenderPass renderpass;
  VkRenderPassCreateInfo renderpassCreateInfo = { ... };
  <b>VkCreateRenderPass</b>(dev, &renderpassCreateInfo, NULL, &renderpass);

  VkFramebuffer framebuffer;
  VkFramebufferCreateInfo framebufferCreateInfo = { ... };
  <b>vkCreateFramebuffer</b>(dev, &framebufferCreateInfo, NULL, &framebuffer);

  VkDescriptorSetLayout descriptorSetLayout;
  VkDescriptorSetLayoutCreateInfo descriptorSetLayoutCreateInfo = { ... };
  <b>vkCreateDescriptorSetLayout</b>(dev, &descriptorSetLayoutCreateInfo, NULL, &descriptorSetLayout);

  VkPipelineLayout pipeLayout;
  VkPipelineCreateInfo pipeLayoutCreateInfo = { ... };
  <b>vkCreatePipelineLayout</b>(dev, &pipeLayoutCreateInfo, NULL, &pipeLayout);

  VkShaderModule vertModule, fragModule;
  <b>vkCreateShaderModule</b>(dev, &vertModuleInfoWithSPIRV, NULL, &vertModule);
  <b>vkCreateShaderModule</b>(dev, &fragModuleInfoWithSPIRV, NULL, &fragModule);

  VkPipeline pipeline;
  VkGraphicsPipelineCreateInfo pipeCreateInfo = { ... };
  <b>vkCreateGraphicsPipelines</b>(dev, NULL, 1, &pipeCreateInfo, NULL, &pipeline);

  VkDescriptorPool, descriptorPool;
  VkDescriptorPoolCreateInfo descriptorPoolCreateInfo = { ... };
  <b>ckCreateDescriptorPool</b>(dev, &descriptorPoolCreateInfo, NULL, &descriptorPool);

  VkDescriptorSet descriptorSet;
  VkDescriptorSetAllocateInfo descriptorAllocInfo = { ... };
  <b>vkAllocateDescriptorSets</b>(dev, &descriptorAllocInfo, &descriptorSet);

  VkBuffer buffer;
  VkBufferCreateInfo bufferCreateInfo = { ... };
  <b>vkCreateBuffer</b>(dev, &bufferCreateInfo, NULL, &buffer);

  VkDeviceMemory memory;
  VkMemoryAllocateInfo memAllocInfo = { ... };
  <b>vkAllocateMemory</b>(dev, &memAllocInfo, NULL, &memory);

  <b>vkBindBufferMemory</b>(dev, buffer, memory, 0);

  void *data = NULL;
  vkMapMemory(dev, memory, 0, VK_WHOLE_SIZE, 0, &data);
  // < __fill data pointer with some transformation data__
  vkUnmapMemory(dev, memory);

  VkWriteDescriptorSet descriptorWrite = { ... };
  vkUpdateDescriptorSets(dev, 1, &descriptorWrite, 0, NULL);

  VkCommandPool commandPool;
  VkCommandPoolCreateInfo commandPoolCreateInfo = { ... };
  <b>vkCreateCommandPool</b>(dev, &commandPoolCreateInfo, NULL, &commandPool);

  VkCommandBuffer cmd;
  VkCommandBufferAllocateInfo commandAllocInfo = { ... };
  <b>vkAllocateCommandBuffers</b>(dev, &commandAllocInfo, &cmd);

  // Rendering:
  vkBeginCommandBuffer(cmd, &cmdBeginInfo);
    vkCmdBeginRenderPass(cmd, &renderpassBeginInfo, VK_SUBPASS_CONTENTS_INLINE);
      vkCmdBindPipeline(cmd, VK_PIPELINE_BIND_POINT_GRAPHICS, pipeline);
      vkCmdBindDescriptorSets(cmd, VK_PIPELINE_BIND_POINTS_GRAPHICS, descriptorSetLayout, 1, &descriptorSet, 0, NULL);
      vkCmdSetViewport(cmd, 1, &viewport);
      <b>vkCmdDraw</b>(cmd, 3, 1, 0, 0);
    vkCmdEndRenderPass(cmd);
  vkEndCommandBuffer(cmd);

  VkSubmitInfo submitInfo = { ... };
  <b>vkQueueSubmit</b>(queue, 1, &submitInfo, NULL);

  VkPresentInfoKHR presentInfo = { ... };
  <b>vkQueuePresentKHR</b>(queue, &presentInfo);
}
</pre>


## Fundamentals

### Execution model

Vulkan exposes one or more **devices**, each of which exposes one or more **queues** (which may process work asynchronously to one another). Each queue belongs to a **family** of queues. Each family supports one or more types of functionality and may contain multiple queues with similar characteristics. Queues within a single family are compatible with one another, and work produced for a family of queues can be executed on any queue within that family. Types of functionality that queues support: graphics, compute, video decode, video encode, protected memory management, sparse memory management, and transfer.

Device memory is explicitly managed by the application. Each device advertise one or more heaps, representing different area of memory, which are either device-local or host-local. A heap is always visible to the device, but may or may not be visible by the host.

#### Queue operation

Vulkan queues provide an interface to the execution engines of a device. Command buffers, containing commands for these execution engines, are submitted to a queue for execution. Once submitted, command buffers will begin and complete execution without further application intervention. Work is submitted to queues using commands (e.g. `vkQueueSubmit`) that can take a list of semaphores upon which to wait before work begins and a list of semaphores to signal onece work has completed. Queue submission commands return control to the application once queue operations have been submitted (they don't wait for completion).

There are no implicit ordering constraints between queue operations on different queues, or between queues and the host, so these may operate in any order with respect to each other. Explicit ordering constraints between different queues or the host can be expressed with semaphores and fences.

Command buffer submissions to a single queue respect submission order and other implicit ordering guarantees. However, some types of batches and queue submissions against a single queue (e.g. sparse memory binding) have no implicit ordering constraints. Additional explicit ordering constraints between queue submissions and individual batches acan be expressed with semaphores and fences.

Before a fence or semaphore is signaled, it's guaranteed that any previously submitted queue operations have completed execution, that memory writes from those queue operations are available to future queue operations, and that previous writes that are available are also visible to subsequent commands.

Command buffer boundaries between command buffers (of the same or different batches or submissions), primary or secondary or both, don't introduce any additional ordering constraints. Explicit ordering ocnstraints can be expressed with explicit synchronization primitives.

There are a few implicit ordering guarantees between commands within a command buffer, but only covering a subset of execution. Additional explicit ordering constraints can be expressed with the various explicit synchronization primitives.

Commands recorded in command buffers can perform actions, set state that persist across commands, synchronize other commands, or indirectly launch other commands, with some commands fulfilling several of these roles.

Synchronization commands introduce explicit execution and memory dependencies between two sets of action commands, where the second set of commands depends on the first one. This enforces both that the execution of certain pipeline stages in the second set occurs after the execution of certain stages in the first set, and that the effects of memory accesses performed by certain pipeline stages occur in order and are visible to each other. Otherwise, action commands may overlap execution or execute out of order, and may not see the side effects of each other's memory accesses.

### Object model

Vulkan represents devices, queues, and other entities as Vulkan objects, which are referred to by handles. All objects created or allocated from a `VkDevice` are private and must not be used on other devices. Two classes of handles:
- **Dispatchable:** Pointer to an opaque type. Each dispatchable object must have a unique handle value during its lifetime.
- **Non-dispatchable:** It's a 64-bit integer whose meaning is implementation-dependent. If the `privateData` feature is enabled for a `VkDevice`, each non-dispatchable object must have a handle value unique among objects created on that device. Otherwise, it may enconde information directly in the handle rather than acting as a reference to an underlying object, and thus may not have a unique handle value. If handle values are not unique, then destroying one such handle must not cause other identical handles to become invalid.

#### Object lifetime

Obj




## Synchronization

Treat the GPU as a separate thread of execution conceptually. Treat memory you allocate as shared. Don't free or write to that memory when it's being used. Imagine the GPU as a fat thread that shares memory with you (in fact, consider the various graphics, transfer, and compute queues as separate "threads" within the GPU). You can use **fences** to know exactly when a particular command you issued to the GPU has finished, or **semaphores** if you have different GPU commands that depend on each other. You can articulate some dependencies with render subpasses. Use **barriers** for controlling access to memory when they change ownership, layouts, or visibility.

The **CPU** has multiple cores, each one with multiple threads, which let us run multithreaded applications, which requires synchronization. The **GPU** is a much more sophisticated multithreaded device that executes a lot of different stages and threads, so it needs a much more explicit synchronization. It can execute multiple **queues** (graphics, transfer, compute...), which are like separate "threads" that provide executable commands to the GPU. Some of these commands make the GPU run the **graphics pipeline** (multiple times in parallel), which has multiple [stages](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkPipelineStageFlagBits.html). To synchronize all this, Vulkan provides some tools:

- Single queue:
  - [**`VkMemoryBarrier`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkMemoryBarrier.html): For a single queue. Before doing operation A (read) from pipeline stage X, operation B (write) from pipeline stage Y must have completed.
- Multiple queues:
  - [**`VkSemaphore`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkSemaphore.html): Block all execution on queue A until all operations on queue B finish (e.g. finish all rendering on graphics queue before sending framebuffer to presentation queue). Submitted to the queue with `VkSubmitInfo`.
  - [**`VkBufferMemoryBarrier`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkBufferMemoryBarrier.html): For multiple queues.
  - [**`VkImageMemoryBarrier`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkImageMemoryBarrier.html): For multiple queues.
- Commands:
  - [**`vkCmdPipelineBarrier`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/vkCmdPipelineBarrier.html) (execution barrier): Enforce an ordering between commands submitted to a command buffer (e.g. execute compute command before draw command). Instructions submitted prior to the execution barrier occur before instructions submitted after. Usually submitted together with a `VkMemoryBarrier` (as an argument).
  - [**`VkEvent`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkEvent.html): It's like a more fine grained pipeline barrier. It's splitted in 2 parts: one emits a signal, the other waits for it (`vkCmdWaitEvents`).
- Render passes & subpasses:
  - [**`VkSubpassDependency`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkSubpassDependency.html): Memory barrier used by subpasses. It ensures that all relevant memory modified prior to the start of the pass is visible.
- GPU-CPU:
  - [**`vkDeviceWaitIdle`, `vkQueueWaitIdle`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/vkCmdWaitEvents.html) (GPU to CPU): It waits until the queue you submitted the commands to is idle. Not recommended: waiting for a queue to be idle means you cannot submit more work to that queue in the meantime.
  - [**`VkFence`**](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkFence.html) (GPU to CPU): It can be submitted along with a command buffer in `VkQueueSubmit()`. Later, this fence will be signaled on the CPU in a way that is visible and waitable via `vkWaitForFences`.

### Submitting to a single queue (`MemoryBarrier`)

**Barrier:** Given a pipeline stage and all the types of memory we care about, make sure we're finished with those writes before accessing this type of memory at these other stages.

<pre>
vk::MemoryBarrier barrier { B, A };   // { Src, Dst }

command_buffer.pipelineBarrier( Y, X, 1, &barrier );   // (Src, Dst, barriersCount, barriers)
</pre>

This means that, before trying to do operation A from pipeline stage X, operation B from pipeline stage Y must have completed.

<pre>
vk::MemoryBarrier barrier {
  vk::AccessFlagBits::eTransferWrite,       // Src
  vk::AccessFlagBits::eVertexAttributeRead  // Dst
};

command_buffer.pipelineBarrier(
  vk::PipelineStageFlagBits::eTransfer,     // Src
  vk::PipelineStageFlagBits::eVertexInput   // Dst
  1,
  &barrier
};
</pre>

This means that, before trying to read vertex attribute memory (`eVertexAttributeRead`) from the vertex input stage of the pipeline (`eVertexInput`), make sure that writes to transferred memory (`eTransferWrite`) from the transfer stage (`eTransfer`) have completed. So, `MemoryBarriers` have 2 dimensions: pipeline masks ([`vk::PipelineStageFlagBits`](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkPipelineStageFlagBits.html)) and access masks ([`vk::AccessFlagBits`](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkAccessFlagBits.html)).

This barrier applies to submissions that occur on the same queue. So, this applies to all commands submitted prior to the same command buffer, and all commands submitted in a different buffer earlier on the same queue.

### Multiple queue submission (`VkSemaphore`, `VkBufferMemoryBarrier`, `VkImageMemoryBarrier`)

GPUs have multiple queue types (graphics, compute, transfer...), and 0 or more queues of each type. Submitting to multiple queues means dealing with parallel submission. There're two ways of synchronizing work between queues:

- `VkSemaphore`: Semaphores to be signaled are submitted to one queue at submission time, and semaphores are submitted to a different queue to be waited on (also at submission time). It blocks all execution on the second queue until all operations on the first queue finish. This can be useful for finishing all rendering on a graphics queue before attempting to send the framebuffer to the presentation queue.

- `VkBufferMemoryBarrier` & `VkImageMemoryBarrier`: Both encode the source and destination queue families. Example 1: transfer job to submit buffers or images to the GPU that get consumed later by the graphics queue. Example 2: Interdependencies between the graphics queue and the compute queue or vice-versa. They can be used in a single queue since they let you encode a barrier on a sub-region of either the buffer or image, or an image format transition in addition to everything else in the case of an image barrier. When used to describe a queue transfer however, these barriers need to be submitted to both queues with the source and destination queue reversed. Depending on the queue they are submitted to, the barriers define a release or consume dependency between the queues. When these barriers are used to describe a queue ownership transfer, when a __release__ is defined, `dstStageMask` is ignored (after all, commands submitted afterwards in the same queue don't care about the barrier). Similarly, the `srcStageMask` is ignored in the consume operation on the other side for an analogous reason.

### Memory vs Execution barrier (`vkCmdPipelineBarrier`)

As we've seen, memory barriers (`MemoryBarrier`) are configured across 2 orthogonal dimensions: pipeline masks (`vk::PipelineStageFlagBits`) and access masks (`vk::AccessFlagBits`). So, prior to certain types of memory access from certain stages, we require that certain types of memory writes from certain stages were made visible or flushed.

Commands submitted to a command buffer can be executed in any order. To enforce an ordering between them, we need an **execution barrier** (`vkCmdPipelineBarrier`). It specifies that instructions submitted prior to the execution barrier occur before instructions submitted after. Example: to sequence the compute command after the draw command, we can invoke the `vkCmdPipelineBarrier` with the source stage mask set to `VK_PIPELINE_STAGE_ALL_GRAPHICS_BIT` and the destination stage mask set to `VK_PIPELINE_STAGE_COMPUTE_SHADER_BIT` and no memory barriers at all.

The barrier is just another command passed down the queue. If we submit only a **memory barrier**, a command submitted earlier may slip past the memory barrier, or viceversa. Therefore, we need to submit together both the **memory barrier** and execution barrier. The API considered this and allows memory barriers to be passed as arguments to the pipeline barrier. However, there a few use case where we want to submit a pipeline barrier whithout memory barriers: when we submit a command that simply reads a resource that must later be modified (WAR: Write-After-Read).

### Render passes & Subpasses

Consider a sequence of 3 draw calls for drawing 3 transparent objects that overlap one another. We need here a back-to-front drawing (Painter's algorithm) with blending. We can guarantee that the draw calls will execute in the same submission order by injecting a memory barrier between each draw call. But there's another way.

At the start of every subpass and render pass there's an image barrier that ensures that all relevant memory modified prior to the start of the pass is visible. Once entering the pass, the draws sequence is guaranteed not to violate the render-pipeline order. Then, the render pass executes the store command on its render targets, discards temporary buffers/memory, and prepares framebuffers for the next render pass.

`VkSubpassDependency` is, in fact, a memory barrier, but with better syntaxis for applications that use multiple render targets. You can pass some [flag bits](https://registry.khronos.org/vulkan/specs/1.3-extensions/man/html/VkDependencyFlagBits.html): 

- `VK_DEPENDENCY_BY_REGION_BIT`: Often, we issue draw calls and don't want to violate pipeline order (e.g. when blending), but a full barrier per pipeline stage of the entire framebuffer is too much. This flag allows modern GPU architectures that do tiled-rendering optimize this process (useful when the usage of the framebuffer is localized), preventing most intermediate render-targets to be fully synchronized and flushed for each draw.

### GPU to CPU synchronization

Pipeline barriers and memory barriers are submitted asynchronously (like any other command we submit to GPU). This means, for example, that if you record a series of commands to a buffer, submit the buffer, and then submit a pipeline barrier as well, you aren't actually free to free that buffer just yet. Just because you submitted the pipeline barrier, there's no guarantee that the barrier itself has made its way through the GPUs command queue. The pipeline barrier is only useful for sequencing actions that are submitted on the same queue, asynchronously to the GPU. 

The easiest way to solve this is by using a wait command to wait until the queue you submitted the commands to is idle (you'll often see this in tutorial code). But this is not a good way: waiting for a queue to be idle means you cannot submit more work to that queue in the meantime. A better way of dealing with GPU-to-CPU synchronization is with a **fence**. Fences can be submitted along with a command buffer as part of the `VkQueueSubmit()` function, and this fence will later be signaled on the CPU in a way that is visible and waitable via `vkWaitForFences`.

### GPU-to-GPU synchronization

This was described previously when describing a memory dependency across different queues. However, sometimes we need synchronization between different queues on the GPU for other reasons such as managing the rendering frame and its presentation on a different queue (if the graphics and present queues are different). This is described with a `VkSemaphore`, which works similarly to the `VkFence`. It's submitted to the queue as part of the `VkSubmitInfo` struct, but instead of waiting for it on the CPU, it's waited on by a different queue (specified in a different part of the `VkSubmitInfo` struct).

### Events

**Events** are like a pipeline barrier splitted in two parts: one emits a signal, the other waits for the signal with the appropriate masks to indicate which pipeline stages need to flush what memory. Example: we want to submit commands A, B, and C, where C is dependent on A; and A and B were recorded on a separate thread into a secondary command buffer. We can synchronize A and C by inserting a pipeline barrier between B and C to flush the memory written by A. But, if B also writes memory in this pipeline stage, you'll end up waiting longer to flush more than you might have otherwise. You like recording A/B and C independently on 2 separate threads on the host CPU, but you don't like that the barrier between B and C synchronizes too much. Alternatively, putting a barrier between A and B may prevent parallelism between A and B since they don't technically have any hard dependency between them. The solution is the `VkEvent` which is more granular. The thread recording A and B can insert an event signal using `vkCmdEventSignal` between A and B, while the thread recording C can insert a `vkCmdEventWaits` just before C.

Events are powerful, but it's recommended first leveraging the render pass and subpass abstractions first, since they map well to hardware. Additionally, fine grained events can occasionally perform worse than a single barrier, so consider a simpler architecture at first. 


## Particularities

...



## Glossary

### Glossary:

- **Window object** (such as `GLFWwindow*`). The window is not created by Vulkan, but by our native windowing system (we can use the OS API or a library like GLFW).

- **Vulkan instance** (`VkInstance`): Stores the state of the application (includes extensions and validation layers).

- **Surface** (`VkSurfaceKHR`): Abstract type of surface to present rendered images to. Interface for interacting with the window system.

- **Physical device** (`VkPhysicalDevice`): Choose a GPU with Vulkan support and use it for creating a logical device.

- **Logical device** (`VkDevice`): Abstraction of the physical device with some of its features such as:

  - **Queues** (`VkQueue`): The Vulkan commands to execute are submitted to a queue. There're different queue families, each one with different queue types (for graphics commands, for presenting images to the screen, etc.).

  - **Swap chain** (`VkSwapchainKHR`): Collection of render targets. Each one has a swapChainImage (`VkImage`), swapChainImageView (`VkImageView`) and swapChainFramebuffer (`VkFramebuffer`). Each render target has one swapChainFramebuffer per render pass, and references all the attachments in their render pass.

- **Render pass** (`VkRenderPass`): It describes a set of subpasses and their corresponding attachments (images). It describes the images that will be used during rendering and the operations performed during rendering. Each subpass represents the attachments used in the fragment shader. We can have multiple render passes where each one renders to some images that are used as input attachments by the next render pass (we have to include them as a descriptor to be able to access them from the fragment shader). Similarly, subsequent subpasses take inputs from previous subpasses. The final attachment is one image from the swap chain (render to screen). We have to create the attachments (images) of our render passes. For each render pass we also have to create a framebuffer (used during command buffer creation), which contains all the images in a render pass. Given some geometry, its graphics pipeline will determine to which framebuffer, render pass, and subpass it is rendered. Attachment types:

  - Input attachments: Input images
  - Color attachments: Output images
  - Depth/stencil attachment: Stores depth/stencil information
  - Resolve attachment: Used for resolving multisampled color images (MSAA).

- Fragment shader's access to images:

  - Pixel access: Subsequent subpasses take inputs from previous subpasses. In the fragment shader, these inputs just provide access to the exact same pixel location from the previous subpass.
  - Image access: If we use different render passes where each one renders to an off-screen framebuffer (render to a texture) which is used as input by the next render pass, we get access to the entire rendered image.

- **Command-pool** (`VkCommandPool`): Record all the operations (drawing commands suitable for the graphics queue family) you want to perform here. Later, execute these commands by submitting them to one of the device queues (graphics, presentation, …) (after recording them in a `command buffer`).

- **descriptorSetLayout (`VkDescriporSetLayout`): 

- **Graphics pipeline:**
  - **pipelineLayout** (`VkPipelineLayout`): Specify a number of layouts. Used for creating the pipeline.
  - **graphicsPipeline** (`VkPipeline`): Configure different operations that take vertices and textures of your meshes to pixels:
    - Shader: Types, SPIR-V code, format of the vertex data passed to vertex shader.
    - Primitive type (triangles, lines, points).
    - Viewport state: Region of framebuffer where to render, and scissors rectangle.
    - Rasterizer: Cull mode, line thickness, polygon fill mode, depth bias...
    - Multisampling: Enable sample shading, number of samples...
    - Depth and stencil testing: Enable depth testing...
    - Color blending: Enable blending, color components, implement alpha blending, global settings...
    - Dynamic states: Specify some states you want to be able to change dynamically (i.e., without recreating the whole graphics pipeline) (viewport, line width...).
    - Render pass: Specify render pass and subpass.
    - Reference another pipeline, if it exists.

- **Texture:** Stores textures and mipmaps (`VkImage`, `VkImageView`, `VkDeviceMemory`). The texture image view is used in a descriptor.

- **Texture sampler** (`VkSampler`): Applies filtering and transformations to images (texels interpolation, addressing mode, anisotropic filtering, texels coordinate system, mipmaps, texels comparisons…). Shaders can access an image resource through a sampler object. Used in a descriptor.

- **Vertex buffer** (`VkBuffer`, `VkDeviceMemory`)

- **Index buffer** (`VkBuffer`, `VkDeviceMemory`)

- **Uniform buffers** (`VkBuffer`, `VkDeviceMemory`): One per swap chain image. Empty when just created. Used in a descriptor.

- **Descriptor pool** (`VkDescriptorPool`): Specify the total number of descriptors of each type in our app, and maximum number of descriptor sets. One pool per swap chain image per thread.

- **Descriptor set** (`VkDescriptorSet`): One per swap chain image. Set of descriptors (pointer to a resource accessible for a shader): UBO, sampler, etc. Each descriptor set requires:

  - **Decriptor set layout:** Where to create our descriptor set on.
  - **Descriptor pool:** Stores the descriptors it will use.
  - **Uniform buffer:** If some descriptor is a uniform buffer.
  - **Texture sampler & Texture image view:** If some descriptor is a texture sampler.

- **Command buffer** (`VkCommandBuffer`): ONe pepr swap chain image. Requires:
  - Command pool: From where to take the commands.
  - Rendering data: Render pass, swap chain framebuffer, render area, depth range...
  - Drawing commands for each model: graphics pipeline, vertex buffer, index buffer, descriptor sets, draw command.

- **Synchronisation objects (`VkSemaphore` & `VkFence`): Fences can be used in our code.
  - An image can be acquired for rendering
  - Rendering finished and presentation can happen
  - A swap cahin image is not being used by any frame in flight


## Links
- [Vulkan specification](https://docs.vulkan.org/spec/latest/chapters/introduction.html)
- [Vulkan.org](https://www.vulkan.org/)
- [Vulkan in 30 minutes](https://renderdoc.org/vulkan-in-30-minutes.html)
- [Vulkan synchronisation primer](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/22/vulkan-synchronization-primer/)
- [Yet another blog explaining Vulkan synchronization](https://themaister.net/blog/2019/08/14/yet-another-blog-explaining-vulkan-synchronization/)
- [Khronos - Understanding Vulkan synchronization](https://www.khronos.org/blog/understanding-vulkan-synchronization)
- [AMD - Vulkan barriers explained](https://gpuopen.com/learn/vulkan-barriers-explained/)