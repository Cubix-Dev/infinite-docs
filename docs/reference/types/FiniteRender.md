# FiniteRender

<div class="alert alert-info part text-info">
❔  FiniteRender was last modified in <b>v0.6.0</b>.
</div>

```c
#define MAX_FRAMES_IN_FLIGHT 2

struct FiniteRender {
    FiniteShell *shell;
    char **required_layers;
    char **required_extensions;  // required instance level extensions
    char **required_deviceExtensions;
    uint32_t _images;
    uint32_t _layers;
    uint32_t _exts;
    uint32_t _devExts;
    uint32_t _modules;
    uint32_t _signals;
    uint32_t _fences;
    uint32_t _buffers; // will rename but refers to the FiniteRenderBuffers
    uint32_t _vertexBufferSize;
    uint32_t _currentFrame;

    bool withDepth;

    FiniteRenderShaderStages stages;

    VkInstance vk_instance;
    VkPhysicalDevice vk_pDevice;
    VkDevice vk_device;
    VkSurfaceKHR vk_surface;
    VkQueue vk_graphicsQueue;
    VkQueue vk_presentQueue;

    VkSwapchainKHR vk_swapchain;

    VkImage *vk_image;
    VkSurfaceFormatKHR vk_imageForm;
    VkPresentModeKHR mode;
    VkExtent2D vk_extent;
    VkImageView *vk_view;
    VkPipelineLayout vk_layout;
    VkRenderPass vk_renderPass;
    VkPipeline vk_pipeline;
    VkShaderModule *modules; // array of shader modules
    VkFramebuffer *vk_frameBufs;
    VkCommandPool vk_pool;
    VkCommandBuffer *vk_buffer;

    FiniteRenderBuffer *buffers;
    VkBuffer vk_vertexBuf;
    VkBuffer *vk_uniformBuf;
    VkDeviceMemory vk_memory;
    VkDeviceMemory *vk_uniformMemory;
    VkDescriptorSetLayout vk_descriptorLayout;
    VkDescriptorSet *vk_descriptor;
    void **uniformData;

    VkDescriptorPool vk_descPool;

    VkSemaphore *signals;
    VkFence *fences;
};

```

The `FiniteRender` struct refers to a single Vulkan instance.

## Properties

| Type | Decription |
| ---- | ---------- |
|`FiniteShell *shell`|The `FiniteShell` to attach the Vulkan instance to|
|`char **required_layers`| An array of extension layers (usually just validation which is on by default) |
|`char **required_extensions`| An array of Instance level extensions|
|`char **required_deviceExtensions`| An array of Device level extensions.|
| `uint32_t _images` | The number of Swapchain Images |
| `uint32_t _layers` | The number of extension layers |
| `uint32_t _exts` | The number of instance level extensions|
| `uint32_t _devExts` | The number of device level extensions|
|`uint32_t _modules` | The number of shader modules|
| `uint32_t _signals` | The number of Semaphores (signals)|
| `uint32_t _fences` | The number of fences|
| `uint32_t _buffers` | The number of FiniteRenderBuffers |
| `uint32_t _vertexBufferSize` | Unused|
| `uint32_t _currentFrame`| The current Frame In Flight.|
| `bool withDepth`| Whether to use the v0.6.0 depth layer features. |
| `FiniteRenderShaderStages stages`| The `FiniteRenderShaderStages` for the Vulkan Instance|
| `VkInstance vk_instance`| The Vulkan Instance struct |
| `VkPhysicalDevice vk_pDevice`| The Physical Device for the Render instance |
| `VkDevice vk_device`| The logical device for the render instance |
| `VkSurfaceKHR vk_surface`| The Vulkan Surface for the render instance.|
| `VkQueue vk_graphicsQueue`| The Graphics Queue for the render instance |
| `VkQueue vk_presentQueue`| The Presentation Queue for the render instance|
| `VkSwapchainKHR vk_swapchain`| The Swapchain for the render instance|
|`VkImage *vk_image`| An array of VkImages for the Render Instance |
|`VkSurfaceFormatKHR vk_imageForm`| The Image Format for the render instance |
|`VkPresentModeKHR mode`| The [PresentMode](https://registry.khronos.org/vulkan/specs/latest/man/html/VkPresentModeKHR.html) of the Window. Defaults to FIFO |
|`VkExtent2D vk_extent`| The window scale. The value should be retrived from the FiniteShell. |
|`VkImageView *vk_view`| An array of VkImageViews for the render instance. |
|`VkPipelineLayout vk_layout`| The pipeline layout for the vk_pipeline. |
|`VkRenderPass vk_renderPass`| The render pass for the render instance. |
|`VkPipeline vk_pipeline`| The Graphics Pipeline for the render instance. |
|`VkShaderModule *modules`| An array of shader modules |
|`VkFramebuffer *vk_frameBufs`| An array of Framebuffers |
|`VkCommandPool vk_pool`| The **MAIN** command pool used by the render instance. |
|`VkCommandBuffer *vk_buffer;`| The Command buffer created from the vk_pool |
|`FiniteRenderBuffer *buffers`| An array of VkBuffer details|
|`VkBuffer vk_vertexBuf`| A set of VkBuffers for drawing vertexes. |
|`VkBuffer *vk_uniformBuf`| An array of VkBuffers for Uniform buffers |
|`VkDeviceMemory vk_memory`| A set of VkDeviceMemory for storing info related to drawing vertexes |
|`VkDeviceMemory *vk_uniformMemory`| An array of VkDeviceMemory for storing info related to memory buffers |
|`VkDescriptorSetLayout vk_descriptorLayout`| A VkDescriptorSetLayout for the render instance |
|`VkDescriptorSet *vk_descriptor`| An array of VkDescriptorSets for the render instance |
|`void **uniformData`| Data about the uniform buffers used to render them |
|`VkDescriptorPool vk_descPool`| The descriptor pool for the render instance|
|`VkSemaphore *signals`| An array of Semaphores (signals)|
|`VkFence *fences`| An array of VkFences |

## Notes
The vk_surface in `FiniteRender` should be attached to a Wayland Surface (not an xdg_surface).

The vk_graphicsQueue and vk_presentQueue in FiniteRender are derived from the Physical Device. You must use a GPU that supports both.

In order to use multiple swapchains, you'll need to manage the value of vk_swapchain.

The `vk_image` array contains production ready images. This should not be confused with the `FiniteRenderImage`

## Swaitandard Usage

When creating a FiniteRender instance you must have a valid [`FiniteShell`](../FiniteShell) to like to it.

This struct should be created with [`finite_render_init`](../../functions/render/finite_render_init) and destroyed with [`finite_render_cleanup`](../../functions/render/finite_render_cleanup)

## Related Docs
