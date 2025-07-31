# finite_key_string_from_key

<div class="alert alert-info part text-info">
❔ finite_key_string_from_key was last modified in <b>v0.6.0</b>.
</div>

```c
const char *finite_key_string_from_key(FiniteKey key)
```

The `finite_key_string_from_key` takes a [`FiniteKey`](../../../types/FiniteKey) and returns an equalivlant string

| Type            | Decription                                                       |
| --------------- | ---------------------------------------------------------------- |
| `FiniteKey key` | The [`FiniteKey`](../../../types/FiniteKey) to get a string for. |

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
        const char *key = finite_key_string_from_key(xKey);
        FINITE_LOG("%s Pressed\n", key);
    }
}
```

## Standard Usage

When call this function you should **ALWAYS** call [`finite_key_valid`](../finite_key_valid) prior to avoid unexpected errors, undefined behavior or missed key events.

## Related Docs

[`finite_key_valid`](../finite_key_valid)<br>
[`finite_input_keyboard_init`](../finite_input_keyboard_init)<br>
[`FiniteKeyboard`](../../../types/FiniteKeyboard)
