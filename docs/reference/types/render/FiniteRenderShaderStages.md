# FiniteRenderShaderStages 

<div class="alert alert-info part text-info">
❔  FiniteRenderShaderStages  was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderShaderStages FiniteRenderShaderStages ;
struct FiniteRenderShaderStages {
    uint32_t _stages;
    VkPipelineShaderStageCreateInfo *infos;
};
```

The `FiniteRenderSwapchainInfo` struct contains param information for creating a VkSwapchain.

## Properties

| Type | Decription |
| ---- | ---------- |
|`uint32_t _stage`| The number of Pipelines Shader stages |
|`VkPipelineShaderStageCreateInfo *infos`| An array of Pipeline Shader Stages |

## Standard Usage

This struct should be created manually and used as a param to [`finite_render_add_shader_stage`](../../functions/render/finite_render_add_shader_stage)
