# FiniteDirectionType

<div class="alert alert-info part text-info">
❔ FiniteDirectionType was last modified in **v0.4.0**
</div>

```c
typedef enum {
    FINITE_DIRECTION_UP,
    FINITE_DIRECTION_DOWN,
    FINITE_DIRECTION_LEFT,
    FINITE_DIRECTION_RIGHT,
    FINITE_DIRECTION_LEFT_UP,
    FINITE_DIRECTION_LEFT_DOWN,
    FINITE_DIRECTION_RIGHT_UP,
    FINITE_DIRECTION_RIGHT_DOWN
} FiniteDirectionType;
```

The `FiniteDirectionType` enum describes FiniteBtn directions

## Standard Usage

When creating a FiniteBtn  this enum is expected as a parameter for `finite_button_create_relation()`

## Related Docs

[`finite_button_create_relation`]()