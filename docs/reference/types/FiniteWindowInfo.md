# FiniteWindowInfo

<div class="alert alert-info part text-info">
❔ FiniteWindowInfo was last modified in **v0.1.8**
</div>

```c
struct wl_output *output;
    int xPos;
    int yPos;
    int width;
    int height;
} FiniteWindowInfo;
```

The `FiniteWindowInfo` struct refers to the active dimensions of the window. Windows are anchored to the top-left corner of the screen.

## Properties

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`int xPos`|The x position of the window. Defaults to 0.|
|`int yPos`|The y position of the window. Defaults to 0.|
|`int width`|The width of the window. Defaults to the width of the monitor in pixels.|
|`int height`|The height of the window. Defaults to the height of the monitor in pixels.|


## Standard Usage

When creating a [`FiniteShell`](../FiniteShell) with `finite_window_init` this struct is automatically created and assigned to the full size of the monitor. You can call `finite_window_set_size` to change the value of this.

It's recommended that you store the original FiniteWindowInfo somewhere.

In order to be Infinite compliant, games should be the full size of the screen.

## Related Docs

[`FiniteShell`](../FiniteShell)<br>
[`finite_window_size_set`](../functions/draw/finite_window_size_set)