# finite_render_create_swapchain_images

<div class="alert alert-info part text-info">
❔  finite_render_create_swapchain_images was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_create_swapchain_images(FiniteRender *render);
```

Retrieves swapchain images and creates image views for rendering.

## Parameters

| Type                   | Description                                                 |
| ---------------------- | ----------------------------------------------------------- |
| `FiniteRender *render` | The render context to store the retrieved images and views. |

## Code Examples

```c
#include <finite/log.h>
#include <finite/render.h>

finite_render_create_swapchain_images(render);
```

## Standard Usage

Call this after creating the swapchain. It will populate the render object with image handles and image views for each swapchain image.

## Related Docs

[`finite_render_create_swapchain`](../finite_render_create_swapchain)<br>
[`finite_render_init`](../finite_render_init)
