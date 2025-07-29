# finite_draw_get_text_extents

<div class="alert alert-info part text-info">
❔ finite_draw_get_text_extents was last modified in <b>v0.6.0</b>
</div>

```c
cairo_text_extents_t finite_draw_get_text_extents(FiniteShell *shell, char *str)
```

The `finite_draw_get_text_extents` function attempts to draw a set of FiniteTextGroups to the screen.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |
| `char *str`          | The text to get the extents from.                                    |

## Code Example

```c
    #include <finite/draw.h>

    FiniteWindowInfo *det = shell->details;
    int32_t width = det->width;
    int32_t height = det->height;

    finite_draw_set_font(shell, "KumbhSans", false, false, 24);

    double xW = 338, yH = 68;
    double nW = (double)(width - 400), nY = (double)(height - 100);

    ext = finite_draw_get_text_extents(shell, "Let's go!");
    double text_x = nW + (xW - ext.width) / 2  - ext.x_bearing;
    double text_y = nY + (yH - ext.height) / 2 - ext.y_bearing;

    finite_draw_set_draw_position(shell, text_x, text_y);
    finite_draw_set_text(shell, "Let's go!", &white);
```

## Standard Usage

This function should only be called after `finite_draw_set_font` has been called. Text extents must have a valid reference font.

This function must have a valid `cairo_t` inside the [`FiniteShell`](../../../types/FiniteShell) (`shell.cr`).

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`FiniteTextGroup`](../../../types/FiniteTextGroup)<br>
[`FiniteColorGroup`](../../../types/Finit1eColorGroup)
