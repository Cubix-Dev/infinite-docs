# finite_input_keyboard_init

<div class="alert alert-info part text-info">
❔ finite_input_keyboard_init was last modified in <b>v0.6.0</b>.
</div>

```c
FiniteKeyboard *finite_input_keyboard_init(struct wl_display *device)
```

The `finite_input_keyboard_init` attempts to create a new [`FiniteKeyboard`](../../../types/FiniteKeyboard).

| Type                        | Decription                                       |
| --------------------------- | ------------------------------------------------ |
| `struct wl_display *device` | The Wayland Display to get keyboard events from. |

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

This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

The display parameter should be derived from the [`FiniteShell`](../../../types/FiniteShell) that is currently displaying data.

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_key_valid`](../finite_key_valid)
