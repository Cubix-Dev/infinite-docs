# finite_shell_init

<div class="alert alert-info part text-info">
❔ finite_shell_init was last modified in  <b>v0.6.0</b>
</div>

```c
FiniteShell *finite_shell_init(char *device)
```

The `finite_shell_init` function creates a new [`FiniteShell`](../../FiniteShell).

## Parameters

| Type           | Decription                                                 |
| -------------- | ---------------------------------------------------------- |
| `char *device` | The Wayland device to conenct to. Defaults to "wayland-0". |

## Code Example

```c
    #include <finite/draw.h>

    FiniteShell *myShell = finite_shell_init("wayland-0");

    if (!myShell) {
        FINITE_LOG_FATAL("Unable to init shell");
    }
```

## Standard Usage

When creating a new application, you **must** call this function. Although libfinite support custom implementations of some function, all libfinite functions that interact with the window expect a [`FiniteShell`](../../FiniteShell).

In production, you should use "wayland-0" as the Wayland Device.

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_window_init`](../finite_window_init)
