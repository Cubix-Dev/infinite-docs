# FiniteRenderFramebufferInfo 

<div class="alert alert-info part text-info">
❔  FiniteRenderFramebufferInfo  was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderFramebufferInfo  FiniteRenderFramebufferInfo;
struct FiniteRenderFramebufferInfo {
    const void *next;
    VkFramebufferCreateFlags flags;
    uint32_t _attachments;
    VkImageView *attachments;
    uint32_t width;
    uint32_t height;
    uint32_t layers;
};
```

The `FiniteRenderFramebufferInfo ` struct contains param information for creating a VkFramebuffer.

## Properties

| Type | Decription |
| ---- | ---------- |
|`const void *next`| An extension of the VkRenderFrameBufferInfo or NULL|
|`VkFramebufferCreateFlags flags`|The VkFramebuffer flags|
|`uint32_t _attachments`| The number of attachments |
|`VkImageView *attachments`| The VkImageView attachments.|
|`uint32_t width`| The width of the framebuffer.|
|`uint32_t height`| The height of the framebuffer.|
|`uint32_t layer`| The depth of the framebuffer.|

## Standard Usage

This struct should be created manually and used as a params [`finite_render_create_framebuffers`](../../functions/render/finite_render_create_framebuffers)
