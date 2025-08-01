# FiniteRenderSubpassDependencyInfo 

<div class="alert alert-info part text-info">
❔  FiniteRenderSubpassDependencyInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderSubpassDependencyInfo   FiniteRenderSubpassDependencyInfo ;

struct FiniteRenderSubpassDependencyInfo {
    uint32_t srcSubpass;
    uint32_t destSubpass;
    VkPipelineStageFlags srcStageMask;
    VkPipelineStageFlags destStageMask;
    VkAccessFlags srcAccessMask;
    VkAccessFlags destAccessMask;
    VkDependencyFlags dependencyFlags;
};
```

The `FiniteRenderSubpassDependencyInfo` struct contains param information for creating a VkSubpassDependency.

## Properties

| Type | Decription |
| ---- | ---------- |
|`uint32_t srcSubpass`|The index of the source subpass|
|`uint32_t destSubpass`| The index of the destination subpass. |
|`VkPipelineStageFlags srcStageMask`| The stage mask flags for the source depenency. |
|`VkPipelineStageFlags destStageMask`| The stage mask flags for the destination dependency.|
|`VkAccessFlags srcAccessMask`| The access mask flags of the source depenedencies. |
|`VkAccessFlags destAccessMask`| The access mask flags for destination dependency. |
|`VkDependencyFlags dependencyFlags`| Additional dependency flags.|

## Standard Usage

The value of pipelineBindPoint should be `VK_PIPELINE_BIND_POINT_GRAPHICS`.

This struct should be created manually and used as a params [`finite_render_create_render_pass`](../../functions/render/finite_render_create_render_pass)
