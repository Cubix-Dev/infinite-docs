# finite_render_init

<div class="alert alert-info part text-info">
❔  finite_render_init was last modified in <b>v0.6.0</b>.
</div>

```c
FiniteRender *finite_render_init(FiniteShell *shell, char **extensions, char **layers, uint32_t _exts, uint32_t _layers);
```

Creates a Vulkan instance and surface using the provided shell and configuration data.

# Parameters

| Type                        | Description                                                                                         |
| ---------------------------| --------------------------------------------------------------------------------------------------- |
| `FiniteShell *shell`       | Shell that holds the surface and display needed for surface creation.                              |
| `char **extensions`        | Optional array of Vulkan instance extensions to enable.                                             |
| `char **layers`            | Optional array of Vulkan validation layers to enable.                                               |
| `uint32_t _exts`           | Number of Vulkan instance extensions in the extensions array.                                       |
| `uint32_t _layers`         | Number of Vulkan validation layers in the layers array.                                             |

## Code Example

```c
#include <finite/log.h>
#include <finite/render.h>

FiniteShell *shell = finite_shell_init("wayland-0");

char *extensions[] = {
    VK_KHR_SURFACE_EXTENSION_NAME,
    VK_EXT_DEBUG_UTILS_EXTENSION_NAME,
    VK_KHR_WAYLAND_SURFACE_EXTENSION_NAME
};
char *layers[] = {
    "VK_LAYER_KHRONOS_validation"
};

FiniteRender *render = finite_render_init(shell, extensions, layers, 3, 1);
```

## Standard Usage

This function must have a valid [`FiniteShell`](../../../types/FiniteShell).

Call this function after creating a shell. It sets up the Vulkan instance and prepares a surface for rendering.

```c
FiniteShell *shell = finite_shell_init("wayland-0");
FiniteRender *render = finite_render_init(shell, NULL, NULL, 0, 0);
```

## Related Docs
[`finite_render_create_physical_device`](../finite_render_create_physical_device)