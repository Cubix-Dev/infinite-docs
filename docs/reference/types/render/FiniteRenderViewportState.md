# FiniteRenderViewportState

<div class="alert alert-info part text-info">
❔  FiniteRenderViewportState was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderViewportState FiniteRenderViewportState;
struct FiniteRenderViewportState {
    const void* next;
    VkPipelineViewportStateCreateFlags flags;
    uint32_t _viewports;
    const VkViewport *viewports;
    uint32_t _scissors;
    const VkRect2D *scissors;
};
```

The `FiniteRenderViewportState` struct contains param information for creating a VkPipelineViewportStateCreateInfo.

## Properties

| Type | Decription |
| ---- | ---------- |
|`const void *next`| An extension of the VkPipelineViewportStateCreateInfo   or NULL|
|`VkPipelineInputAssemblyStateCreateFlags flags`| The Assembly Flags. |
|`VkPrimitiveTopology toplogy`| The VKTopology data |
|`bool primitiveRestartEnable`| The Vertex Binding Descriptions |

## Standard Usage

This struct should be created manually and used as a param to [`finite_render_create_viewport_state`](../../functions/render/finite_render_create_viewport_state)
