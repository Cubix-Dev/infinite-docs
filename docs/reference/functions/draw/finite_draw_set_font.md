# finite_draw_set_font

<div class="alert alert-info part text-info">
❔ finite_draw_set_font was last modified in <b>v0.6.0</b>
</div>

```c
void finite_draw_set_font(FiniteShell *shell, char *font_name, bool isItalics, bool isBold, int size)
```

The `finite_draw_set_font` function attempts to set the font of future text.

## Parameters

| Type                 | Decription                                                                      |
| -------------------- | ------------------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window  is. |
| `char *font_name`    | The name of the font.                                                           |
| `bool isItalics`     | Toggles text italics.                                                           |
| `bool isBold`        | Toggles text boldness.                                                          |
| `int size`           | The size of the text.                                                           |

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

When using this function to setup text loading, you must use a valid libfinite function. Currently, the Cubix Infinite supports these fonts:

- [KumbhSans](https://fonts.google.com/specimen/Kumbh+Sans)
- [LiberationSans](https://github.com/liberationfonts/liberation-fonts)
- [OpenSans](https://fonts.google.com/specimen/Open+Sans)
- [Montserrat](https://fonts.google.com/specimen/Montserrat)
- [NotoSans](https://fonts.google.com/noto/specimen/Noto+Sans)

This function should be called whenever you're planning on changing the size or style of text. It will only impact text drawn after it's been called.

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

If `shell.cr` is undefined, this function will create a new Cairo draw tool and set it to `shell.cr`

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`finite_draw_set_draw_position`](../finite_draw_set_draw_position)<br>
[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_text_group`](../finite_draw_text_group)<br>
[`FiniteColorGroup`](../../../types/FiniteColorGroup)
