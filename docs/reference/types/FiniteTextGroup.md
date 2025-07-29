# FiniteTextGroup

<div class="alert alert-info part text-info">
❔ FiniteTextGroup was last modified in <b>0.4.0</b>
</div>

```c
typedef struct {
    double r;
    double g;
    double b;
    double a;
    const char *text;
} FiniteTextGroup;
```

The `FiniteTextGroup` struct stores general information about a window.

## Properties

| Type               | Decription                                                                       |
| ------------------ | -------------------------------------------------------------------------------- |
| `double r,g,b,a`   | The [RGBA](https://www.w3schools.com/Css/css_colors_rgb.asp) value of the text.. |
| `const char *text` | The text.                                                                        |

## Notes

1. The RGB values must be double (float) values between 0 and 1. The way to convert the RGB colors to valid doubles is to divide the value by 255. Below is one way to get the correct RGB values.

```c
    size_t members = 2;

    FiniteTextGroup myGroup[2] = {
        {
            .r = 216.0/255.0,  // 0.847
            .g = 90.0/255.0,  // 0.352
            .b = 71.0/255.0, // 0.278
            .a = 1.0,
            .text = "Test "
        },
        {
            .r = 6.0/255.0, // 0.023
            .g = 190.0/255.0, //0.745
            .b = 31.0/255.0, // 0.121
            .a = 1.0,
            .text = "Subject."
        },
    }
```

## Standard Usage

When using a `FiniteTextGroup`, you should keep track of the number of items in the array. Additionally, `FiniteTextGroups` are meant to be stored in an array, as having a single item in a finite text group is both pointless and causes errors.

## Related Docs

[`finite_draw_set_text`](../../functions/draw/finite_draw_set_text)<br>
[`finite_draw_text_group`](../../functions/draw/finite_draw_text_group)
