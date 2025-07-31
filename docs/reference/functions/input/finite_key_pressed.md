# finite_key_pressed

<div class="alert alert-info part text-info">
❔ finite_key_pressed was last modified in <b>v0.6.0</b>.
</div>

```c
bool finite_key_pressed(FiniteKey key, FiniteKeyboard *board)
```

The `finite_key_pressed` checks if a given [`FiniteKey`](../../../types/FiniteKey) is currently being pressed.

| Type                    | Decription                                            |
| ----------------------- | ----------------------------------------------------- |
| `FiniteKey key`         | The [`FiniteKey`](../../../types/FiniteKey) to check. |
| `FiniteKeyboard *board` | The FiniteKeyboard to check for key events from.      |

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
```

## Standard Usage

This function returns true if the key was pressed and then released. For Key held events use a function like [`finite_key_down`](../finite_key_down).

## Related Docs

[`finite_key_down`](../finite_key_down)<br>
[`finite_key_up`](../finite_key_up)<br>
[`FiniteKeyboard`](../../../types/FiniteKeyboard)
