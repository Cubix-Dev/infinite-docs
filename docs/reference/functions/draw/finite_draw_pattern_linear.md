# finite_draw_text_group

<div class="alert alert-info part text-info">
❔ finite_draw_text_group was last modified in <b>v0.6.0</b>
</div>

```c
cairo_pattern_t *finite_draw_pattern_linear(double startX, double startY, double endX, double endY, FiniteGradientPoint *points, size_t n)
```

The `finite_draw_text_group` function attempts to create a cairo pattern as a linear gradient.

## Parameters

| Type                          | Decription                               |
| ----------------------------- | ---------------------------------------- |
| `double startX`               | The starting X position of the gradient  |
| `double starty`               | The starting Y position of the gradient  |
| `double endX`                 | The ending X position of the gradient    |
| `double endY`                 | The ending y position of the gradient    |
| `FiniteGradientPoint *points` | An array of FiniteGradientPoints         |
| `size_t n`                    | The number of items in the points array. |

## Code Example

```c
    #include <finite/draw.h>

    double xW = 338, yH = 68;
    double nW = (double)(width - 400), nY = (double)(height - 100);

    finite_draw_rounded_rect(shell, nW, nY, xW, yH, 20, &color, NULL, true);

    FiniteGradientPoint new_points[2] = {
        {0, 1, 0.325, 0.325},
        {1, 1, 0.474, 0.098}
    };

    cairo_pattern_t *pat = finite_draw_pattern_linear(nW, nY, (double)(width), (double)(height), new_points, 2);
    finite_draw_stroke(shell, NULL, pat, 14);
    cairo_pattern_destroy(pat);
```

## Standard Usage

This function creates a cairo_pattern_t that at some point must be destroyed with [`cairo_pattern_destroy`](https://cairographics.org/manual/cairo-cairo-pattern-t.html#cairo-pattern-destroy)

## Related Docs

[`finite_draw_set_text`](../finite_draw_set_text)<br>
[`finite_draw_set_font`](../finite_draw_set_font)<br>
[`FiniteTextGroup`](../../../types/FiniteTextGroup)<br>
[`FiniteColorGroup`](../../../types/Finit1eColorGroup)
