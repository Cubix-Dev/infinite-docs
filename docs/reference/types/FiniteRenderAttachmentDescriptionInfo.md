# FiniteRenderAttachmentDescriptionInfo

<div class="alert alert-info part text-info">
❔  FiniteRenderAttachmentDescriptionInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderAttachmentDescriptionInfo FiniteRenderAttachmentDescriptionInfo;

struct FiniteRenderAttachmentDescriptionInfo {
    VkAttachmentDescriptionFlags flags;
    VkFormat format;
    VkSampleCountFlagBits samples;
    VkAttachmentLoadOp loadOp;
    VkAttachmentStoreOp storeOp;
    VkAttachmentLoadOp stencilLoadOp;
    VkAttachmentStoreOp stencilStoreOp;
    VkImageLayout initialLayout;
    VkImageLayout finalLayout;
};

```

The `FiniteRenderAttachmentDescriptionInfo` struct param information for creating a VkAttachmentDecription.

## Properties

| Type | Decription |
| ---- | ---------- |
|`VkAttachmentDescriptionFlags flags`| Flags for the AttachmentDescription. |
|`VkFormat format`|The format of the image view.|
|`VkSampleCountFlagBits samples`|The number of VkSamples in the images.|
|`VkAttachmentLoadOp loadOp`| What to do when loading attachments |
|`VkAttachmentStoreOp storeOp`| What to do when storing attachments |
|`VkAttachmentLoadOp stencilLoadOp`| What to do with stencil data when loading attachments |
|`VkAttachmentStoreOp stencilStoreOp`| What to do with stencil data when storing attachments |
|`VkImageLayout initialLayout`| The layout the attachment is currently at. |
|`VkImageLayout finalLayout`| The layout the attachment should be at when finished.|

## Standard Usage

This struct should be created manually and used as a params [`finite_render_create_render_pass`](../../functions/render/finite_render_create_render_pass)
