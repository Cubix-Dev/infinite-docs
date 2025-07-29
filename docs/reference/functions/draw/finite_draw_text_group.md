# finite_draw_text_group
<div class="alert alert-info part text-info">
❔ finite_draw_text_group was last modified in <b>v0.6.0</b>
</div>
```c
void finite_draw_text_group(FiniteShell *shell, FiniteTextGroup *groups, double x, double y, size_t n)
```

The `finite_draw_text_group` function attempts to draw a set of FiniteTextGroups to the screen.

## Parameters

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteShell *shell`|The [`FiniteShell`](../../../types/FiniteShell) where the window  is.|
|`FiniteTextGroup *groups`|An array of `FiniteTextGroups`.|
|`double x`|The x position to set the draw position to.|
|`double y`|The y position to set the draw position to.|
|`size_t n`|The number of [`FiniteTextGroups`](../../../types/FiniteTextGroup) in groups|

## Code Example
```c 
	#include <finite/draw.h>

    finite_draw_set_font(shell, "Kumbh Sans", false, true, 52);
        
    cairo_text_extents_t ext;

    FiniteTextGroup parts[3] = {
        {1,1,1,1,"Welcome to the "},
        {0.964, 0.674, 0.192,1,"Infinite "},
        {1,1,1,1,"Level"}
    }; 

    cairo_font_extents_t fext = finite_draw_get_font_extents(shell);
    printf("Font height: %f\n", fext.height);

    finite_draw_text_group(shell, parts, (shell->details->width * 0.03), (shell->details->height * 0.1), 3);
``` 

## Standard Usage
This function should have an array of atleast two `FiniteTextGroups`. Having less than 2 is both pointless and unnessary.

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs
[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`FiniteTextGroup`](../../../types/FiniteTextGroup)<br>
[`FiniteColorGroup`](../../../types/Finit1eColorGroup)