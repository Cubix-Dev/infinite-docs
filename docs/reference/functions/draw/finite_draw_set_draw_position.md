# finite_draw_set_draw_position

<div class="alert alert-info part text-info">
❔ finite_draw_set_draw_position was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_set_draw_position(FiniteShell *shell, double x, double y)
```

The `finite_draw_set_draw_position` function attempts to set the draw position relative to screen.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |
| `double x`           | The x position to set the draw position to.                          |
| `double y`           | The y position to set the draw position to.                          |

## Code Example

```c
    #include <finite/draw.h>

    finite_draw_set_font(myShell, "KunbhSans", false, false, 24);

    FiniteColorGroup white = {
        .r = 0,
        .g = 0,
        .b = 0
    };

    finite_draw_set_draw_position(myShell, 30, 20);
    finite_draw_set_text(myShell, "Hello there!", &white);
```

## Standard Usage

The x and y values of this function should take into account any offset made with [`finite_draw_set_offset`](../finite_draw_set_offset).

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`finite_draw_text_group`](../finite_draw_text_group)<br>
[`FiniteColorGroup`](../../../types/Finit1eColorGroup)
