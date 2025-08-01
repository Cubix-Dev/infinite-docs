# finite_render_create_device

<div class="alert alert-info part text-info">
❔  finite_render_create_device was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_create_device(FiniteRender *render, FiniteRenderQueueFamilies fIndex, uint32_t *uniqueQueueFamilies, char **device_extentsions, uint32_t _ext);
```

reates a logical Vulkan device and stores device queues in the render context.

## Parameters
| Type                               | Description                                                 |
| ---------------------------------- | ----------------------------------------------------------- |
| `FiniteRender *render`             | The render context to store the created device and queues.  |
| `FiniteRenderQueueFamilies fIndex` | Contains indices for the graphics and presentation queues.  |
| `uint32_t *uniqueQueueFamilies`    | Array of unique queue family indices used to create queues. |
| `char **device_extentsions`        | Optional array of Vulkan device extension names to enable.  |
| `uint32_t _ext`                    | Number of device extensions in the array.                   |

## Code Example

```c
#include <finite/log.h>
#include <finite/render.h>

uint32_t uniqueQueues[] = { graphicsQueueIndex, presentQueueIndex };
FiniteRenderQueueFamilies families = {
    .graphicsFamily = graphicsQueueIndex,
    .presentFamily = presentQueueIndex,
    ._unique = 2
};

char *extensions[] = {
    VK_KHR_SWAPCHAIN_EXTENSION_NAME
};

finite_render_create_device(render, families, uniqueQueues, extensions, 1);
```

## Standard Usage

Call this after selecting a physical device. It will create a logical device and initialize queues needed for rendering.

## Related Docs
[`finite_render_create_physical_device`](../finite_render_create_physical_device)<br>
[`finite_render_init`](../finite_render_init)