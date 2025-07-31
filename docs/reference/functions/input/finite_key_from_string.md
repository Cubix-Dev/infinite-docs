# finite_key_from_string

<div class="alert alert-info part text-info">
❔ finite_key_from_string was last modified in <b>v0.6.0</b>.
</div>

```c
FiniteKey finite_key_from_string(const char *name)
```

The `finite_key_from_string` creates a [`FiniteKey`](../../../types/FiniteKey) from a given string

| Type               | Decription                                     |
| ------------------ | ---------------------------------------------- |
| `const char *name` | The name of the key to create a FiniteKey for. |

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

When calling this function you should **ALWAYS** call [`finite_key_valid`](../finite_key_valid) afterword to avoid unexpected errors, undefined behavior or missed key events.

## Related Docs

[`finite_key_valid`](../finite_key_valid)<br>
[`finite_input_keyboard_init`](../finite_input_keyboard_init)<br>
[`FiniteKeyboard`](../../../types/FiniteKeyboard)
