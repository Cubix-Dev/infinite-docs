# finite_render_destroy_pixels

<div class="alert alert-info part text-info">
❔  `finite_render_destroy_pixels` was last modified in <b>v0.6.0</b>.
</div>

```c
void finite_render_destroy_pixels(FiniteRenderTextureInfo *image);
```

This function frees memory previously allocated to raw texture pixel data in a given [`FiniteRenderTextureInfo`](../../../types/FiniteRenderTextureInfo).

# Parameters

| Type                       | Description                                                             |
| -------------------------- | ----------------------------------------------------------------------- |
| `FiniteRenderTextureInfo *image` | Pointer to a texture info structure whose pixel buffer should be freed. |

## Code Example

```c
    #include <finite/render.h>
    #include <finite/log.h>

    FiniteRenderTextureInfo texture_info;
    // populate texture_info
    finite_render_create_texture("texture.png", &texture_info, true);

    // free the texture pixels
    finite_render_destroy_pixels(&texture_info);
```

## Notes

## Standard Usage

## Related Docs
