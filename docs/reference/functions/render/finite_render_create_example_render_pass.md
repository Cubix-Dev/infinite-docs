# finite_render_create_example_render_pass

<div class="alert alert-info part text-info">
❔  finite_render_create_example_render_pass was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_create_example_render_pass(FiniteRender *render);
```
Creates a basic Vulkan render pass and stores it in the render context.

## Parameters
| Type                   | Description                                          |
| ---------------------- | ---------------------------------------------------- |
| `FiniteRender *render` | The render context to store the created render pass. |

## Code Example

```c
#include <finite/log.h>
#include <finite/render.h>

finite_render_create_example_render_pass(render);
```

## Standard Usage

Call this after creating the swapchain and selecting an image format. It will set up a basic render pass for use with framebuffers.

## Related Pages

[`finite_render_create_swapchain`](../finite_render_create_swapchain)<br>
[`finite_render_init`](../finite_render_init)