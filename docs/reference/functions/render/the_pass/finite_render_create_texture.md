# finite_render_create_texture

<div class="alert alert-info part text-info"> 
❔ `finite_render_create_texture` was last modified in <b>v0.6.0</b>. 
</div>

```c
void finite_render_create_texture(const char *file, FiniteRenderTextureInfo *info, bool forceAlpha);
```

This function takes a image file and populates a given [`FiniteRenderTextureInfo`](../../../types/FiniteRenderTextureInfo)

# Parameters

| Type                            | Description                                                                                 |
| ------------------------------- | ------------------------------------------------------------------------------------------- |
| `const char *file`              | Path to the image file to load.                                                             |
| `FiniteRenderTextureInfo *info` | Pointer to a texture info structure that will be filled with image metadata and raw pixels. |
| `bool forceAlpha`               | If true, the loaded image will be forced to have 4 channels (RGBA).                         |

## Code Example

## Notes



## Standard Usage



## Related Docs