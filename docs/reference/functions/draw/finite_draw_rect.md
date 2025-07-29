# finite_draw_rect

<div class="alert alert-info part text-info">
❔ finite_draw_rect was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_rect(FiniteShell *shell, double x, double y, double width, double height, FiniteColorGroup *color, cairo_pattern_t *pat)
```

The `finite_draw_rect` function attempts to draw a regular rectangle onto a window with Cairo.

## Parameters

| Type                      | Decription                                                     |
| ------------------------- | -------------------------------------------------------------- |
| `FiniteShell *shell`      | The FiniteShell where the window  is.                |
| `double x`                | The x position to draw the rectangle at.                       |
| `double y`                | The y position to draw the rectangle at.                       |
| `double width`            | The width of the rectangle.                                    |
| `double height`           | The height of the rectangle                                    |
| `FiniteColorGroup *color` | A single [`FiniteColorGroup`](../../../types/FiniteColorGroup) |
| `cairo_pattern_t *pat`    | A single Cairo Pattern.                                        |

## Code Example

```c
    #include <finite/draw.h>

    FiniteColorGroup myColor = {
        .r = 211.0/255.0,
        .g = 63.0/255.0,
        .b = 73.0/255.0
    };

    finite_draw_rect(myShell, 0,0, 100, 100, &myColor, NULL);
```

## Notes

finite_draw_rect supports both solid colors with `FiniteColorGroup` and gradients with `cairo_pattern_t` but you CANNOT have both values set. One of the last two params MUST be NULL. Having two color values set will throw an error.

This function doesn't use information from [`finite_draw_set_draw_position`](../finite_draw_set_draw_position) as of **v0.6.0**

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

## Standard Usage

This function must have a valid [`FiniteShell`](../../../types/FiniteShell).

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation beforehand.

## Related Docs

[`finite_draw_rounded_rect`](../finite_draw_rounded_rect)<br>
[`FiniteColorGroup`](../../../types/FiniteColorGroup)
