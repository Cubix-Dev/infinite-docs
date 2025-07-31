# FiniteKeyState

<div class="alert alert-info part text-info">
❔ FiniteKeyState was last modified in <b>0.4.9</b>
</div>

```c
typedef struct {
    uint16_t id;
    bool isHeld;
    bool isDown;
    bool isUp;
} FiniteKeyState;
```

The `FiniteKeyState` struct refers to the state single [`FiniteKey`](../../enums/FiniteKey)

## Properties

| Type          | Decription                      |
| ------------- | ------------------------------- |
| `uint32_t`    | The id of this FiniteKeyState.  |
| `bool isHeld` | Whether the key is being held.  |
| `bool isDown` | Whether the key is down.        |
| `bool isUp`   | Whether the key is not pressed. |

## Standard Usage

This struct is automatically created for all available keys with a [`FiniteKeyboard`](../FiniteKeyboard)

## Related Docs

[`finite_input_keyboard_init`](../../functions/input/finite_input_keyboard_init)<br>
[`FiniteKeyboard`](../FiniteKeyboard) <br>
[`finite_keyboard_destroy`](../../functions/input/finite_keyboard_destroy)
