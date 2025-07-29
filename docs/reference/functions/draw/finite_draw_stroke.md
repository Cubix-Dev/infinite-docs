# finite_draw_stroke

<div class="alert alert-info part text-info">
❔ finite_draw_stroke was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_stroke(FiniteShell *shell, FiniteColorGroup *color, cairo_pattern_t *pat, int width)
```

The `finite_draw_stroke` function attempts to draw a stroke around the latest rectangle.

## Parameters

| Type                      | Decription                                            |
| ------------------------- | ----------------------------------------------------- |
| `FiniteShell *shell`      | The FiniteShell where the window  is.       |
| `FiniteColorGroup *color` | A single [`FiniteColorGroup`](../../FiniteColorGroup) |
| `cairo_pattern_t *pat`    | A single Cairo Pattern.                               |
| `int width`               | The thickness of the stroke.                          |

## Code Example

```c
    #include <finite/draw.h>

    FiniteColorGroup myColor = {
        .r = 211.0/255.0,
        .g = 63.0/255.0,
        .b = 73.0/255.0
    };

    FiniteColorGroup myStroke = {
        .r = 254.0/255.0,
        .g = 96.0/255.0
        .b = 6.0/255.0
    };

    finite_draw_rect(myShell, 0,0, width, height, &myColor, NULL);

    finite_draw_stroke(myShell, myStroke, NULL, 5);
```

## Notes

This function doesn't use information from [`finite_draw_set_draw_position`](../finite_draw_set_draw_position) as of **v0.6.0**

If `shell.cr` is undefined, this function will **NOT** create a new Cairo draw tool as it expects a rectangle (and as a result a cairo draw tool) to exist prior to drawing.

## Standard Usage

This function, you must have a valid `cairo_t` inside the [`FiniteShell`](../../../types/FiniteShell) (`shell.cr`). Strokes may only be applied onto a surface that has already been initialized.

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_rect`](../finite_draw_rect)<br>
[`FiniteColorGroup`](../../../types/FiniteColorGroup)
