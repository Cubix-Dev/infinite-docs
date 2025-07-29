# FiniteBtn

<div class="alert alert-info part text-info">
❔ FiniteBtn was last modified in **v0.4.0**
</div>

```c

typedef struct FiniteBtn FiniteBtn;
struct FiniteBtn {
    FiniteBtn *self;
    bool isActive;
    int id;
    FiniteBtnRelationShips *relations;
    void *data;
    FiniteShell *link;
    void (*on_select_callback)(FiniteBtn *self, int id, void *data);
    void (*on_focus_callback)(FiniteBtn *self, int id, void *data);
    void (*on_unfocus_callback)(FiniteBtn *self, int id, void *data);
};
```

The `FiniteBtn` struct refers to metadata for a button drawn with Cairo. In Cairo, everything is stateless, meaning there is no way to refer to specific parts of UI. FiniteBtn provides an easy way to refer to button elements and keep track of when they are selected.

## Properties

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteBtn *self`|Refers to this button.|
|`bool isActive`|Refers to whether this button is currently selected.|
|`int id`|The ID of the button. Button IDs start at 0 and refer to the position of the button in the array.|
|`FiniteBtnRelationShips *relations`|The [`FiniteBtnRelationShips`](../FiniteBtnRelationShips) for this button.|
|`FiniteShell *link`|The [`FiniteShell`](../FiniteShell/) assocciated with this button|
|void *data|Custom data|

## Functions
|Function|Description|
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`void *on_select_callback`|The on_selected callback. Fires when the button is active has recieved a Selected event.|
|`void *on_focus_callback`|The on_focused callback. Fires when the button becomes active.|
|` void *on_unfocus_callback`|The on_unfocused callback. Fires when the button becomes unactive after previously being active.|

## Notes

<div class="alert alert-warning part text-warning">
<h3> ⚠ Button ids can change!! </h3>
Button ids refer to the position of the data in the buttons array inside of [`FiniteShell`]((../FiniteShell/)). This means that if a button is deleted, all [`FiniteBtnRelationShips`](../FiniteBtnRelationShips) and other references to buttons that come after that button are **invalid**. If you have a lot of buttons that rely on each other, be extreme careful when deleting buttons.

Additionall, when creating temporary buttons, ensure all base buttons have been made first to avoid unexpected behavior
</div>

It's important to note that FiniteBtn **does not store location data**. It's up to you as the developer to figure out where buttons are. There are several different ways to do this, such as storing the button's location in a custom struct store in `FiniteBtn.data` or simply hardcoding the location.

## Standard Usage
When creating more than one `FiniteBtn`, a valid FiniteBtnRelatioShip is required to make both buttons selectable.

The link value should refer to a valid [`FiniteShell`]((../FiniteShell/)) that contains the drawn data of the button.

## Related Docs
[`finite_button_create_relation`]()<br>
[`FiniteShell`](../FiniteShell/)