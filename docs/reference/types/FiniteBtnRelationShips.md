# FiniteBtnRelationShips

<div class="alert alert-info part text-info">
❔ FiniteBtnRelationShips was last modified in **v0.4.0**
</div>

```c
typedef struct {
    int left;
    int right;
    int down;
    int up;
    // optional diagonals
    int leftUp;
    int rightUp;
    int leftDown;
    int rightDown;
} FiniteBtnRelationShips;
```

The `FiniteBtnRelationShips` struct describes the relationship between a given button and it's neighbors.

## Properties

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`int left,right,down....`|Each parameter refers to the id of the button in that direction.|

## Standard Usage

When creating a `FiniteBtn` this struct refers to relationship between it an other buttons. When there is more than one button you **must** include a valid `FiniteBtnRelationShips` by calling `finite_button_create_relation`.

## Related Docs

[`finite_button_create_relation`]()