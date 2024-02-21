# Vulkan API fundamentals

<br>![computer graphics image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/computer_graphics.jpg)

## Table of Contents
+ [Vulkan overview](#vulkan-overview)
+ [Vulkan fundamentals](#vulkan-fundamentals)
+ [Links](#links)

## Vulkan overview

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

### Shaders and pipeline state objects



### Binding model

### Synchronisation

### Render passes

### Backbuffers and presentation

### Pseudocode example










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