# finite_draw_cleanup

<div class="alert alert-info part text-info">
❔ finite_draw_cleanup was last modified in <b>v0.6.0</b>.
</div>

```c

bool finite_draw_cleanup(FiniteShell *shell)
```

The `finite_draw_cleanup` function attempts to clean up and destroy the window.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |

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

    while (wl_display_dispatch(shell->display) != -1) {
        FINITE_LOG("Window is open.");
    }

    finite_draw_cleanup(shell);
```

## Standard Usage

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

This function destroys and cleans up. It **must** be called at the end of an application that uses Cairo.

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_draw_finish`](../finite_draw_finish)
