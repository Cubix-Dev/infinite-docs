# finite_render_find_queue_families

<div class="alert alert-info part text-info">
❔  finite_render_find_queue_families was last modified in <b>v0.6.0</b>.
</div>

```c
//function
```

The ` finite_render_get_shader_code` attempts to get shader code and convert it into bytes.

# Parameters

| Type                        | Decription                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| `char *fileName` | The file to get shader code from. |
| `uint32_t *pShaderSize` | Size of the shader code |

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
`finite_render_get_shader_code` requires precompiled shaders in order to work.

## Standard Usage

This function requires you to get the shader's file size.

## Related Docs

[`FiniteShaderType`](../../enums/FiniteShaderType.md)
