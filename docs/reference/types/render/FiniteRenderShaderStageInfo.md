# FiniteRenderShaderStageInfo

<div class="alert alert-info part text-info">
❔  FiniteRenderShaderStageInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderShaderStageInfo FiniteRenderShaderStageInfo;

struct FiniteRenderShaderStageInfo {
    const void *next;
    VkPipelineShaderStageCreateFlags flags;
    FiniteShaderType stage;
    VkShaderModule shader;
    const char *name;
    const VkSpecializationInfo *specializationInfo;    
};
```

The `FiniteRenderShaderStageInfo` struct contains param information for creating a VkShaderStage.

## Properties

| Type | Decription |
| ---- | ---------- |
|`const void *next`| An extension of the VkShaderStageInfo or NULL|
|`VkPipelineShaderStageCreateFlags flags`| The Shader Stage Flags. |
|`FiniteShaderType stage`| The [`FiniteShaderType`](../FiniteShaderType) of Shader stage |
|`VkShaderModule shader`| The VkShaderModule |
|`const char *name`| The name of entry function for the shader.|
|`const VkSpecializationInfo *specializationInfo`| Additional specizialization info for the VkShaderModule. |

## Standard Usage

All _values must **always** be defined.

This struct should be created manually and used as a param to [`finite_render_add_shader_stage`](../../functions/render/finite_render_add_shader_stage)
