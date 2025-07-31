# FiniteKeyboard

<div class="alert alert-info part text-info">
❔ FiniteKeyboard was last modified in <b>0.4.9</b>
</div>

```c
typedef struct {
    FiniteInput *input;

    struct wl_keyboard *keyboard;
    struct xkb_context *xkb_ctx;
    struct xkb_keymap *xkb_keymap;
    struct xkb_state  *xkb_state;

    FiniteKeyState keys[256];
    bool keys_down[256];
    bool keys_up[256];
} FiniteKeyboard;
```

The `FiniteKeyboard` struct refers to a single keyboard attached to a shell via the internal `FiniteInput` type.

## Properties

| Type                            | Decription                                                    |
| ------------------------------- | ------------------------------------------------------------- |
| `struct wl_keyboard *keyboard`  | The Wayland Keyboard that is connected to this FiniteKeyboard |
| `struct xkb_context *xkb_ctx`   | The xkb context for the input device.                         |
| `struct xkb_keymap *xkb_keymap` | The xkb keymapping for the input device.                      |
| `struct xkb_state  *xkb_state`  | The xkb state of the input device.                            |
| `FiniteKeyState keys[256]`      | The [`FiniteKeyState`](../FiniteKeyState)array.                                   |
| `bool keys_down[256]`           | The [`FiniteKey`](../../enums/FiniteKey) isDown array.                                 |
| `bool keys_up[256]`             | The [`FiniteKey`](../../enums/FiniteKey) isUp array.                                     |

## Standard Usage

This struct should be created with [`finite_input_keyboard_init`](../../functions/input/finite_input_keyboard_init) and destroyed with [`finite_keyboard_destroy`](../../functions/input/finite_keyboard_destroy)

## Related Docs

[`finite_input_keyboard_init`](../../functions/input/finite_input_keyboard_init)<br>
[`finite_keyboard_destroy`](../../functions/input/finite_keyboard_destroy)
