# finite_draw_png

<div class="alert alert-warning part text-warning">
❔ finite_draw_png was last modified in <b>v0.6.0</b>. 
</div>

```c
void finite_draw_png(FiniteShell *shell, const char *path, double x, double y);
```

The `finite_draw_png` function attempts to clean up and destroy the window.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |
| `const char *path`   | The path to the png image.                                           |
| `double x`           | The X position of the png.                                           |
| `double y`           | The Y position of the png.                                           |

## Code Example

```c
    #include <finite/draw.h>

    finite_draw_png(shell, "/home/cubix/Documents/Islands/setup/src/wifi-bad.png",0,0)
```

# Notes

This function **only** supports pngs. Additionally scaling png images requires some extra work not yet supported by libfinite natively.

## Standard Usage

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_draw_finish`](../finite_draw_finish)
