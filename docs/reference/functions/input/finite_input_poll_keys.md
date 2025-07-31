# finite_input_poll_keys

<div class="alert alert-info part text-info">
❔ finite_input_poll_keys was last modified in <b>v0.6.0</b>.
</div>

```c
bool finite_input_poll_keys(FiniteKey key, FiniteShell *shell)
```

The `finite_input_poll_keys` checks for any and all key events.

| Type                    | Decription                                                 |
| ----------------------- | ---------------------------------------------------------- |
| `FiniteKeyboard *board` | The FiniteKeyboard to check for key events from.           |
| `FiniteShell` \*shell`  | The FiniteShell that has the window to poll for key events |

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
    if (finite_key_up(xKey, kbd)) {
        FINITE_LOG("X not Pressed\n");
    }
}
```

## Standard Usage

This function checks for all key events. It should be called prior to checking for key events to ensure the data is up to date. For best results, place this function in a wl_display_dispatch call.

## Related Docs

[`finite_key_up`](../finite_key_pressed)<br>
[`finite_key_up`](../finite_key_up)<br>
[`FiniteKeyboard`](../../../types/FiniteKeyboard)
