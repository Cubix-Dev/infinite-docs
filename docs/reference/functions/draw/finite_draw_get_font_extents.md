# finite_draw_get_font_extents
<div class="alert alert-info part text-info">
❔ finite_draw_get_font_extents was last modified in <b>v0.6.0</b>
</div>
```c
cairo_font_extents_t finite_draw_get_font_extents(FiniteShell *shell);
```

The `finite_draw_get_font_extents` function attempts to get the extents of the current font

## Parameters

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteShell *shell`|The [`FiniteShell`](../../../types/FiniteShell) where the window  is.|

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
A font must be set prior to calling this function with [`finite_draw_set_font`](../finite_draw_set_font). Failure to do so will throw an error.

This function must have a valid `cairo_t` inside the [`FiniteShell`](../../../types/FiniteShell) (`shell.cr`).

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs
[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`FiniteTextGroup`](../../../types)<br>
[`FiniteColorGroup`](../../../types/Finit1eColorGroup)