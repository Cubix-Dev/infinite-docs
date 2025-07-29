# finite_overlay_init

<div class="alert alert-info part text-info">
❔ finite_overlay_init was last modified in **v0.6.0**
</div>

```c
void finite_overlay_init(FiniteShell *shell, int layer, char *name)
```

The `finite_overlay_init` function creates a new layer shell window with a given [`FiniteShell`](../../FiniteShell).

## Parameters

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteShell *shell`|The FiniteShell to create a overlay for.|
|`int layer`|The [layer](https://wayland.app/protocols/wlr-layer-shell-unstable-v1#zwlr_layer_shell_v1:enum:layer) of the overlay|
|`char *name`|The name of the layer.|

```c
finite_overlay_init(myShell);

if (!myShell) {
    FINITE_LOG_FATAL("Unable to make shell");
}
```

## Standard Usage

When creating a new popup (NOT APPLICATION), you **must** call this function. Although libfinite support custom implementations of some function, all libfinite functions that interact with the window expect a [`FiniteShell`](../../FiniteShell).

## Related Docs

[`FiniteShell`](../../FiniteShell)<br>
[`finite_window_init`](../finite_window_init)