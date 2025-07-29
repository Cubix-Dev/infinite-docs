# finite_draw_rounded_rect

<div class="alert alert-info part text-info">
❔ finite_draw_rounded_rect was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_rounded_rect(FiniteShell *shell, double x, double y, double width, double height, double radius, FiniteColorGroup *color, cairo_pattern_t *pat, bool withPreserve)
```

The `finite_draw_rounded_rect` function attempts to draw a rounded rectangle onto a window with Cairo.

## Parameters

| Type                      | Decription                                                        |
| ------------------------- | ----------------------------------------------------------------- |
| `FiniteShell *shell`      | The FiniteShell to resize.                                        |
| `double x`                | The x position to draw the rectangle at.                          |
| `double y`                | The y position to draw the rectangle at.                          |
| `double width`            | The width of the rectangle.                                       |
| `double height`           | The height of the rectangle                                       |
| `double radius`           | The Radoius of the rounded edges of the rectangle.                |
| `FiniteColorGroup *color` | A single [`FiniteColorGroup`](../../FiniteColorGroup)             |
| `cairo_pattern_t *pat`    | A single Cairo Pattern.                                           |
| `bool withPreserve`       | Determines whether to 'preserve' the data for things like stroke. |

## Code Example

```c
    #include <finite/draw.h>

    FiniteColorGroup myColor = {
        .r = 211.0/255.0,
        .g = 63.0/255.0,
        .b = 73.0/255.0
    };

    finite_draw_rounded_rect(myShell, 0,0, 100, 100, 15, &myColor, NULL, false);
```

## Notes

finite_draw_rounded_rect supports both solid colors with `FiniteColorGroup` and gradients with `cairo_pattern_t` but you CANNOT have both values set. One of the last two params MUST be NULL. Having two color values set will throw an error.

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

## Standard Usage

This function must have a valid [`FiniteShell`](../../FiniteShell).

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../FiniteShell) implementation beforehand.

## Related Docs

[`finite_draw_rect`](../finite_draw_rect)<br>
[`FiniteColorGroup`](../../../types/FiniteColorGroup)
