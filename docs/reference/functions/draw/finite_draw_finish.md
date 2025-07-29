# finite_draw_finish

<div class="alert alert-info part text-info">
❔ finite_draw_finish was last modified in <b>v0.6.0</b>.
</div>

```c

bool finite_draw_finish(FiniteShell *shell, int width, int height, int stride, bool withAlpha)
```

The `finite_draw_finish` function attempts to clean up the cairo objects and commit the data to the window.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |
| `int width`          | The width of the area to redraw.                                     |
| `int height`         | The height of the area to redraw.                                    |
| `stride`             | The stride of the window.                                            |
| `bool withAlpha`     | Whether or not the window supports Alpha Channels.                   |

## Code Example

```c
    #include <finite/draw.h>

    FiniteGradientPoint points[2] = {
        {0, 0.325, 0.325, 0.325, alpha},
        {0.5, 0.207, 0.207, 0.207, alpha}
    };

    cairo_pattern_t *pat = finite_draw_pattern_linear(0,0, (double)shell->details->width, (double)shell->details->height, points, 2);

    finite_draw_rect(shell, 0,0, shell->details->width, shell->details->height, NULL, pat);
    cairo_pattern_destroy(pat);

    finite_draw_finish(shell, shell->details->width, shell->details->height, shell->stride, true);
```

## Standard Usage

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

This function destroys the cairo draw object within a given [`FiniteShell`](../../../types/FiniteShell). The cairo_surface_t however is **not** destroyed.

At some point (likely after the render loop) you should call [`finite_draw_cleanup`](../finite_draw_cleanup)

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_draw_cleanup`](../finite_draw_cleanup)
