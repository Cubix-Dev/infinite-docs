# FiniteRenderSwapchainInfo

<div class="alert alert-info part text-info">
❔  FiniteRenderSwapchainInfo was last modified in <b>v0.6.0</b>.
</div>

```c
typedef struct FiniteRenderSwapchainInfo FiniteRenderSwapchainInfo;

struct FiniteRenderSwapchainInfo {
    VkSurfaceCapabilitiesKHR caps;
    uint32_t _forms;
    VkSurfaceFormatKHR *forms;
    uint32_t _modes;
    VkPresentModeKHR *modes;
};
```

The `FiniteRenderSwapchainInfo` struct contains param information for creating a VkSwapchain.

## Properties

| Type | Decription |
| ---- | ---------- |
|`VkSurfaceCapabilitiesKHR caps`| The swapchain capabilities. |
|`uint32_t _forms`| Additional flags for creating the render pass. |
|`VkSurfaceFormatKHR *forms`| The number of attachments there are.|
|`uint32_t _modes`| The number of possible present modes.|
|`VkPresentModeKHR *modes`| An array of possible present modes |

## Standard Usage

All _values must **always** be defined.

This struct should be created manually and used as a param to [`finite_render_create_swapchain`](../../functions/render/finite_render_create_swapchain)
