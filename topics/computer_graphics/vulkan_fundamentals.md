# Vulkan API fundamentals

<br>![computer graphics image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/computer_graphics.jpg)

## Table of Contents
+ [Introduction](#introduction)
+ [Overview](#overview)
+ [Fundamentals](#vulkan-fundamentals)
+ [Links](#links)


## Introduction





## Overview

### Starting

Vulkan is a C API for computer graphics. It's heavily typed (each enum is separate, and returned handles are opaque 64-bit handles so they are typed on 64-bit). Most functions take big structures as parameters instead of basic types. 

First, create a `VkInstance` (Vulkan instances don't know about each other) and specify simple information (layers, extensions...). Use it to examine available GPUs,  with `VkEnumeratePhysicalDevices()` and check their properties (`vkGetPhysicalDeviceProperties()`) and features (`vkGetPhysicalDeviceFeatures()`). Then, take one `VkPhysicalDevice` and use it for creating a `VkDevice` (handle for the GPU you'll use). Note: A `VkInstance` can have many `VkPhysicalDevices`, while each one can have many `VkDevices`.

### Images and buffers

We can use our `VkDevice` for creating pretty much every other resource type (`VkImage`, `VkBuffer`...). 

- When creating an **image**, you have to declare in advance how it will be used (color attachment, shader sampled image, image load/store...), and the tiling/swizzling layout of the image data in memory (`LINEAR`, `OPTIMAL` ...). Images aren't used directly, but via a `VkImageView`, which describes what array slices or mip levels are visible, and (optionally) a different (compatible) format (e.g. aliasing `UNORM` texture as `UINT`).

- When creating a **buffer** you have to specify its size and usage. Buffers are usually used directly since they're just a block of memory, but if you want to use it as a texel buffer in a shader, you need to provide a `VkBufferView`.

### Allocating GPU memory

Before using those images and buffers you have to allocate memory for them with `vkAllocateMemory()`, which returns a `VkDeviceMemory` handle.

Available memory is exposed via `vkGetPhysicalDeviceMemoryProperties()`, which reports one or more memory **heaps** of given sizes, each one providing one or more memory **types** with given properties (CPU visible or not, coherent GPU and CPU access, cached or uncached, ...). Example: a discrete GPU may have 2 heaps (one for system RAM and one for GPU RAM) and multiple memory types from each.

When calling `vkAllocateMemory()` we specify how much memory to allocate, and what memory type we want from which heap (e.g. images for rendering may prefer device local memory for optimal use, while staging resources need host visible memory). Host visible memory can be mapped for update with `vkMapMemory()` (returns a pointer) and `vkUnMapMemory()`. All these maps (pointers to memory) are persistent, and it's legal to have memory mapped while in use by the GPU as long as you synchronise.

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

The base binding unit is a **descriptor** (opaque representation that stores 'one bind'). This can be an image, sampler, uniform/constant buffer, etc. It can be arrayed (you have an array of images that can be different sizes, etc. as long as they are all 2D floating point images). Descriptors aren't bound individually, but in blocks in a `VkDescriptorSet``. The types of individual bindings contained in a `VkDescriptorSet` are described in a `VkDescriptorSetLayout`. Imagine `VkDescriptorSetLayout` as a C struct type describing some opaque type members, the `VkDescriptorSet` as a specific instance of that type, and each member inside as a binding that can be updated with any resource you want. You allocate a `VkDescriptorSet` with a given layout from a `VkDescriptorPool` (used to allocate descriptors on different threads more efficiently by having a pool per thread).

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
  const char *extensionNames[] = { "VK_KHR_surface", "VK_KHR_win32_surface" };
  VkInstanceCreateInfo instanceCreateInfo = { ..., extensionNames };
  VkInstance inst;
  **vkCreateInstance**(&instanceCreateInfo, NULL, &inst);

  VkPhysicalDevice phys[4];
  vkEnumeratePhysicalDevices(inst, 4, phys);
  vkDeviceCreateInfo deviceCreateInfo = { ... };
  VkDevice dev;
  **vkCreateDevice**(phys[0}, &deviceCreateInfo, NULL, &dev);

  VkWin32SurfaceCreateInfoKHR surfaceCreateInfo = { ... };
  VkSurfaceKHR surf;
  **vkCreateWin32SurfaceKHR**(inst, &surfaceCreateInfo, NULL, &surf);
  
  VkSwapchainCreateInfoKHR swapCreateInfo = { ... };
  VkSwapchainKHR swap;
  **vkCreateSwapchainKHR**(dev, &swapCreateInfo, NULL, &swap);

  VkImage image[4];
  **vkGetSwapchainImagesKHR**(dev, swap, 4, images);

  uint32_t currentSwapImage;
  **vkAcquireNextImageKHR**(dev, swap, UINT64_MAX, presentCompleteSemaphore, NULL, &currentSwapImage);
  
  VkImageView backbufferView;
  **vkCreateImageView**(dev, &backbufferViewCreateInfo, NULL, &backbufferView);
  
  VkQueue queue;
  **vkGetDeviceQueue**(dev, 0, 0, &queue);

  VkRenderPass renderpass;
  VkRenderPassCreateInfo renderpassCreateInfo = { ... };
  **VkCreateRenderPass**(dev, &renderpassCreateInfo, NULL, &renderpass);

  VkFramebuffer framebuffer;
  VkFramebufferCreateInfo framebufferCreateInfo = { ... };
  **vkCreateFramebuffer(dev, &framebufferCreateInfo, NULL, &framebuffer);

  VkDescriptorSetLayout descriptorSetLayout;
  VkDescriptorSetLayoutCreateInfo descriptorSetLayoutCreateInfo = { ... };
  **vkCreateDescriptorSetLayout**(dev, &descriptorSetLayoutCreateInfo, NULL, &descriptorSetLayout);

  VkPipelineLayout pipeLayout;
  VkPipelineCreateInfo pipeLayoutCreateInfo = { ... };
  **vkCreatePipelineLayout**(dev, &pipeLayoutCreateInfo, NULL, &pipeLayout);

  VkShaderModule vertModule, fragModule;
  **vkCreateShaderModule**(dev, &vertModuleInfoWithSPIRV, NULL, &vertModule);
  **vkCreateShaderModule**(dev, &fragModuleInfoWithSPIRV, NULL, &fragModule);

  VkPipeline pipeline;
  VkGraphicsPipelineCreateInfo pipeCreateInfo = { ... };
  **vkCreateGraphicsPipelines**(dev, NULL, 1, &pipeCreateInfo, NULL, &pipeline);

  VkDescriptorPool, descriptorPool;
  VkDescriptorPoolCreateInfo descriptorPoolCreateInfo = { ... };
  **ckCreateDescriptorPool**(dev, &descriptorPoolCreateInfo, NULL, &descriptorPool);

  VkDescriptorSet descriptorSet;
  VkDescriptorSetAllocateInfo descriptorAllocInfo = { ... };
  **vkAllocateDescriptorSets**(dev, &descriptorAllocInfo, &descriptorSet);

  VkBuffer buffer;
  VkBufferCreateInfo bufferCreateInfo = { ... };
  **vkCreateBuffer**(dev, &bufferCreateInfo, NULL, &buffer);

  VkDeviceMemory memory;
  VkMemoryAllocateInfo memAllocInfo = { ... };
  **vkAllocateMemory**(dev, &memAllocInfo, NULL, &memory);

  **vkBindBufferMemory**(dev, buffer, memory, 0);

  void *data = NULL;
  vkMapMemory(dev, memory, 0, VK_WHOLE_SIZE, 0, &data);
  // < fill data pointer with some transformation data
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

## Vulkan fundamentals

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


## Links
- [Vulkan specification](https://docs.vulkan.org/spec/latest/chapters/introduction.html)
- [Vulkan.org](https://www.vulkan.org/)
- [Vulkan in 30 minutes](https://renderdoc.org/vulkan-in-30-minutes.html)