# finite_render_create_swapchain

<div class="alert alert-info part text-info">
❔  finite_render_create_swapchain was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_create_swapchain(FiniteRender *render, FiniteRenderSwapchainInfo info);
```
Creates a Vulkan swapchain using the provided capabilities and render configuration.

## Parameters

| Type                             | Description                                               |
| -------------------------------- | --------------------------------------------------------- |
| `FiniteRender *render`           | The render context to store the created swapchain.        |
| `FiniteRenderSwapchainInfo info` | Holds surface capabilities for configuring the swapchain. |

## Code Examples
```c
#include <finite/log.h>
#include <finite/render.h>

FiniteRenderSwapchainInfo info = {
    .caps = surfaceCapabilities
};

finite_render_create_swapchain(render, info);
```

## Standard Usage

Call this after configuring the render surface and selecting the image format and present mode. It will create the swapchain used for rendering frames

## Related Docs

[`finite_render_init`](../finite_render_init)