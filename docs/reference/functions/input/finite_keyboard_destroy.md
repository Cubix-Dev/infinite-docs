# finite_keyboard_destroy

<div class="alert alert-info part text-info">
❔ finite_keyboard_destroy was last modified in <b>v0.6.0</b>.
</div>

```c
FiniteKeyboard *finite_keyboard_destroy(struct wl_display *device)
```

The `finite_keyboard_destroy` attempts to destroy a [`FiniteKeyboard`](../../../types/FiniteKeyboard).

| Type                    | Decription                      |
| ----------------------- | ------------------------------- |
| `FiniteKeyboard *board` | The FiniteKeyboard to destrooy. |

## Code Example

```c
#include <finite/input.h>
#include <finite/log.h>

FiniteKeyboard *kbd = finite_input_keyboard_init(myShell->display);

FiniteKey xKey = finite_key_from_string("X");
if (!finite_key_valid(xKey)) {
    FINITE_LOG_FATAL("Unable to poll NULL key");
}

// create wayland frame loop
while (wl_display_dispatch_pending(myShell->display) != -1) {
    // poll for input
    finite_input_poll_keys(kbd, myShell);

    // handle input
    if (finite_key_pressed(xKey, kbd)) {
        FINITE_LOG("X Pressed\n");
    }
}

finite_keyboard_destroy(kbd);
```

## Standard Usage

This function must have a valid [`FiniteKeyboard`](../../../types/FiniteKeyboard).

The function should be called as soon as the [`FiniteKeyboard`](../../../types/FiniteKeyboard). is no longer needed. [`FiniteKeyboards`](../../../types/FiniteKeyboard) are not automatically cleaned up.

## Related Docs

[`FiniteKeyboard`](../../../types/FiniteKeyboard)<br>
[`finite_key_valid`](../finite_key_valid)
