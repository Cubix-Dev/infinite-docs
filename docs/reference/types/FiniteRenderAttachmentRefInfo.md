# FiniteRenderAttachmentRefInfo 

<div class="alert alert-info part text-info">
❔  FiniteRenderAttachmentRefInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderAttachmentRefInfo  FiniteRenderAttachmentRefInfo
:;

struct FiniteRenderAttachmentRefInfo {
    uint32_t _attachment;
    VkImageLayout layout;
    FiniteAttachmentDescriptor type;
};


```

The `FiniteRenderAttachmentRefInfo` struct param information for creating a VkAttachmenReference.

## Properties

| Type | Decription |
| ---- | ---------- |
|`uint32_t _attachment`| The number of attachments. |
|`VkImageLayout layout`| The layout the attachment is currently at. |
|`FiniteAttachmentDescriptor`| The type of descriptor the FintiteRenderAttachmentRef is.|

## Standard Usage

This struct should be created manually and used as a params [`finite_render_create_render_pass`](../../functions/render/finite_render_create_render_pass)
