# FiniteShaderType

<div class="alert alert-info part text-info">
❔ FiniteShaderType was last modified in <b>0.4.0</b>
</div>

```c
typedef enum FiniteShaderType FiniteShaderType;
enum FiniteShaderType {
    FINITE_SHADER_TYPE_VERTEX,
    FINITE_SHADER_TYPE_FRAGMENT
};

```

The `FiniteShaderType` enum describes a type of shader to be used in [`FiniteRenderShaderStageInfo `](../../FiniteRenderShaderStageInfo)

## Standard Usage

When creating a [`FiniteRenderShaderStageInfo`](../../FiniteRenderShaderStageInfo) this enum is expected as a parameter.

## Related Docs

[`FiniteRenderShaderStageInfo`](../../../FiniteRenderShaderStageInfo)
