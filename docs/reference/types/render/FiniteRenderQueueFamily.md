# FiniteRenderQueueFamilies

<div class="alert alert-info part text-info">
❔  FiniteRenderQueueFamilies was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderQueueFamilies FiniteRenderQueueFamilies;

struct FiniteRenderQueueFamilies {
    uint32_t graphicsFamily;
    uint32_t presentFamily;
    uint32_t _unique;
};
```

The `FiniteRenderQueueFamilies` struct refers to where the graphicsFamily and presentFamily are on the GPU.

## Properties

| Type | Decription |
| ---- | ---------- |
|`uint32_t graphicsFamily`|The location of the graphicsFamily|
|`uint32_t presentFamily`|The location of the presentFamily|
|`uint32_t _unique`|The how many unique addresses there are.|

## Standard Usage

This struct should be created with [`finite_render_find_queue_families`](../../functions/render/finite_render_find_queue_families).
