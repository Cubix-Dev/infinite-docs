# finite_render_create_physical_device

<div class="alert alert-info part text-info">
❔  finite_render_create_physical_device was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_create_physical_device(FiniteRender *render);
```

Selects and stores a compatible physical device for the given render context.

## Parameters

| Type                   | Decription                                                |
| ---------------------- | --------------------------------------------------------- |
| `FiniteRender *render` | The render context to store the selected physical device. |

```c
    #include <finite/log.h>
    #include <finite/render.h>

    char *extensions[] = {
        VK_KHR_SURFACE_EXTENSION_NAME,
        VK_EXT_DEBUG_UTILS_EXTENSION_NAME,
        VK_KHR_WAYLAND_SURFACE_EXTENSION_NAME
    };
    char *layers[] = {
        "VK_LAYER_KHRONOS_validation"
    };


    FiniteRender *render = finite_render_init(shell, extensions, layers, 3, 1);
    finite_render_create_physical_device(render);
```

## Standard Usage

Call this after initializing the render context. It will choose a compatible device from the available hardware.

## Related Docs

[`finite_render_init`](../finite_render_init)