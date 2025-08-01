# FiniteRenderRenderPassInfo

<div class="alert alert-info part text-info">
❔  FiniteRenderRenderPassInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderRenderPassInfo FiniteRenderRenderPassInfo;

struct FiniteRenderRenderPassInfo {
    const void *next;
    VkRenderPassCreateFlags flags;
    uint32_t _attachments;
    VkAttachmentDescription *attachments;
    uint32_t _subpasses;
    const VkSubpassDescription *subpasses;
    uint32_t _deps;
    const VkSubpassDependency *dependencies;
    uint32_t _refs;
};
```

The `FiniteRenderRenderPassInfo` struct contains param information for creating a VkRenderPass.

## Properties

| Type | Decription |
| ---- | ---------- |
|`const void *next`| An extension of the VkRenderPassInfo or NULL|
|`VkRenderPassCreateFlags flags`| Additional flags for creating the render pass. |
|`uint32_t _attachments`| The number of attachments there are.|
|`VkAttachmentDescription *attachments`| The attachments.|
|`uint32_t _subpasses`| The number of subpasses |
|`const VkSubpassDescription *subpasses`| The subpasses |
|`uint32_t _deps`| The numbers of subpass dependencies. |
|`const VkSubpassDependency *dependencies` | The subpass dependencies. |
|`uint32_t _refs`| The number of Color Attachment references|

## Standard Usage

All _values must **always** be defined.

This struct should be created manually and used as a params [`finite_render_create_render_pass`](../../functions/render/finite_render_create_render_pass)
