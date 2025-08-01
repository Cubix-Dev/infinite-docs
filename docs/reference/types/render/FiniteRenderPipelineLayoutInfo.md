# FiniteRenderPipelineLayoutInfo 

<div class="alert alert-info part text-info">
❔  FiniteRenderPipelineLayoutInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderPipelineLayoutInfo FiniteRenderPipelineLayoutInfo;

struct FiniteRenderPipelineLayoutInfo {
    VkPipelineLayoutCreateFlags flags;
    uint32_t _setConsts;
    VkDescriptorSetLayout *setConsts;
    uint32_t _pushRange;
    VkPushConstantRange *pushRange;
};
```

The `FiniteRenderSwapchainInfo` struct contains param information for creating a VkSwapchain.

## Properties

| Type | Decription |
| ---- | ---------- |
|`VkPipelineLayoutCreateFlags flags`| The Pipeline Layout Flags. |
|`uint32_t _setConsts`| The number of Set Constants |
|`VkDescriptorSetLayout *setConsts`| An array of the Set Constants.|
|`uint32_t _pushRange`| The number of push range constants.|
|`VkPushConstantRange *pushRange`| An array of the push range constants |

## Standard Usage

All _values must **always** be defined.

This struct should be created manually and used as a param to [`finite_render_create_swapchain`](../../functions/render/finite_render_create_swapchain)
