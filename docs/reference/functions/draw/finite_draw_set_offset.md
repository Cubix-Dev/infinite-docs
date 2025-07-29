# finite_draw_set_offset

<div class="alert alert-info part text-info">
❔ finite_draw_set_offset was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_set_offset(FiniteShell *shell, double x, double y)
```

The `finite_draw_set_offset` function attempts to set an offset for future drawing.

## Parameters

| Type                 | Decription                                      |
| -------------------- | ----------------------------------------------- |
| `FiniteShell *shell` | The FiniteShell where the window to draw to is. |
| `double x`           | The X offset.                                   |
| `double y`           | The Y offset.                                   |

## Code Example

```c
    #include <finite/draw.h>

    // create a color for later
    FiniteColorGroup grayGlass = {
        .r = 0.152,
        .g = 0.152,
        .b = 0.152,
        .a = 1
    };

    double miniWindow[4] = {
        ((shell->details->width  * 40) / 100), // x
        ((shell->details->height * 20) / 100), // y
        ((shell->details->width  * 55) / 100), // width
        ((shell->details->height * 60) / 100)  // hieght
    };

    finite_draw_set_offset(shell, miniWindow[0], miniWindow[1]);

    finite_draw_rounded_rect(shell, miniWindow[0], miniWindow[1], miniWindow[2], miniWindow[3], 35, &grayGlass, NULL, true);
    FiniteColorGroup outline = {
        .r = 0.788,
        .g = 0.788,
        .b = 0.788,
        .a = 0.4
    };

    finite_draw_stroke(shell, &outline, NULL, 6);
```

## Notes

This function is used to offset the drawing position of **all** draw functions. Even though some functions may manually take in x and y positions, they are universally affected by this function.

## Standard Usage

Offsets apply to everything drawn after it's been set as long as it's using the same `shell.cr`.

You should at some point call the inverse of this function (`finite_draw_set_offset(-x, -y)`) to reset the offset back to 0,0.

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_rect`](../finite_draw_rect)<br>
[`FiniteColorGroup`](../../FiniteColorGroup)
