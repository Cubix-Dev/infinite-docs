# finite_draw_set_text

<div class="alert alert-info part text-info">
❔ finite_draw_set_text was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_set_text(FiniteShell *shell, char *text, FiniteColorGroup *color)
```

The `finite_draw_set_text` function attempts to draw text to the screen.

## Parameters

| Type                      | Decription                                                                      |
| ------------------------- | ------------------------------------------------------------------------------- |
| `FiniteShell *shell`      | The [`FiniteShell`](../../../types/FiniteShell) where the window  is. |
| `char *text`              | The text  the screen.                                                 |
| `FiniteColorGroup *color` | The color of the text to draw.                                                  |

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

This function is intended to be used to draw colored text to screen. However it does not take in a position. As such, you should call [`finite_draw_set_draw_position`](../finite_draw_set_draw_position) directly before each `finite_draw_set_text` call to ensure that things are rendered at the correctly.

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_set_draw_position`](../finite_draw_set_draw_position)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`finite_draw_text_group`](../finite_draw_text_group)<br>
[`FiniteColorGroup`](../../../types/FiniteColorGroup)
