# finite_key_down

<div class="alert alert-info part text-info">
❔ finite_key_down was last modified in <b>v0.6.0</b>.
</div>

```c
bool finite_key_down(FiniteKey key, FiniteKeyboard *board)
```

The `finite_key_down` checks if a given [`FiniteKey`](../../../types/FiniteKey) is currently held down.

| Type                    | Decription                                           |
| ----------------------- | ---------------------------------------------------- |
| `FiniteKey key`         | The [`FiniteKey`](../../../types/FiniteKey) to check |
| `FiniteKeyboard *board` | The FiniteKeyboard to check for key events from.     |

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
    if (finite_key_down(xKey, kbd)) {
        FINITE_LOG("X Pressed\n");
    }
}
```

## Standard Usage

This function should be used for key held events. For Key pressed events use a function like [`finite_key_pressed`](../finite_key_pressed).

## Related Docs

[`finite_key_up`](../finite_key_up)<br>
[`finite_key_pressed`](../finite_key_pressed)<br>
[`FiniteKeyboard`](../../../types/FiniteKeyboard)
