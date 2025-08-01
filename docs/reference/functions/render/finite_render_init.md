# finite_render_init

<div class="alert alert-info part text-info">
❔  finite_render_init was last modified in <b>v0.6.0</b>.
</div>

```c
FiniteRender *finite_render_init(FiniteShell *shell, char **extensions, char **layers, uint32_t _exts, uint32_t _layers
```

The `finite_render_init` attempts to get shader code and convert it into bytes.

# Parameters

| Type                 | Decription                                                                           |
| -------------------- | ------------------------------------------------------------------------------------ |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) to be linked to the Render instance. |
| `char **extensions`  | An array of Instance level extension strings.                                        |
| `char **layers`      | An array of extension layer strings.                                                 |
| `_exts`              | The number of items in the extensions array                                          |
| `_layers`            | The number of items in extension layer string                                        |

## Code Example

```c
#include <finite/render.h>
#include <finite/log.h>

// load shaders
uint32_t vertSize;
char *vertCode = finite_render_get_shader_code("vert.spv", &vertSize);
bool success = finite_render_get_shader_module(render, vertCode, vertSize);

if (!success) {
    FINITE_LOG_ERROR("Unable to create Vertex Shader Module");
    return -1;
}

uint32_t fragSize;
char *fragCode = finite_render_get_shader_code("frag.spv", &fragSize);
success = finite_render_get_shader_module(render, fragCode, fragSize);

if (!success) {
    FINITE_LOG_ERROR("Unable to create Fragment Shader Module");
    return -1;
}
```

## Notes

`finite_render_init` requires precompiled shaders in order to work.

## Standard Usage

This function requires you to get the shader's file size.

## Related Docs

[`FiniteShaderType`](../../enums/FiniteShaderType.md)
