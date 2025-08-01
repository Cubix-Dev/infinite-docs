# FiniteRenderVertexInputInfo

<div class="alert alert-info part text-info">
❔  FiniteRenderVertexInputInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderVertexInputInfo FiniteRenderVertexInputInfo;
struct FiniteRenderVertexInputInfo {
    const void *next;
    VkPipelineVertexInputStateCreateFlags flags;
    uint32_t _vertexBindings;
    const VkVertexInputBindingDescription *vertexBindingDescriptions;
    uint32_t _vertexAtributes;
    const VkVertexInputAttributeDescription *vertexAttributeDescriptions;
};
```

The `FiniteRenderVertexInputInfo` struct contains param information for creating a VkVertexInputState.

## Properties

| Type | Decription |
| ---- | ---------- |
|`const void *next`| An extension of the VKVertexInputStateInfo or NULL|
|`VkPipelineVertexInputStateCreateFlags flags`| The Vertex Input State Flags. |
|`uint32_t _vertexBinding`| The number of Vertex Binding Descriptions |
|`const VkVertexInputBindingDescription *vertexBindingDescriptions`| The Vertex Binding Descriptions |
|`uint32_t _vertexAtributes`| The number of Vertex Attribute Descriptions |
|`const VkVertexInputAttributeDescription *vertexAttributeDescriptions`| The Vertex Attribute Descriptions. |

## Standard Usage

All _values must **always** be defined.

This struct should be created manually and used as a param to [`finite_render_create_vertex_input`](../../functions/render/finite_render_create_vertex_input)
