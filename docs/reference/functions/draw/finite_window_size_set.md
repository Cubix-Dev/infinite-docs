# finite_window_size_set

<div class="alert alert-info part text-info">
❔ finite_window_size_set was last modified in <b>v0.6.0</b>
</div>

```c
void finite_window_size_set(FiniteShell *shell, int xPos, int yPos, int width, int height)
```

The `finite_window_size_set` function attempts to resize a window with a given [`FiniteShell`](../../FiniteShell).


## Parameters

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteShell *shell`|The FiniteShell to resize.|
|`int xPos`|The new x position.|
|`int yPos`|The new y position.|
|`int width`|The new width.|
|`int height`|The new height|

## Code Example

```c 
FiniteWindowInfo *det = myShell->details;
    int32_t true_width = det->width;
    int32_t true_height = det->height;

finite_window_size_set(myShell, ((true_width * 20) / 100), ((true_height *25) / 100), ((true_width * 60) / 100), ((true_height *50) / 100));
```

## Standard Usage
In order to call this function you **must** call [`finite_window_init`](../finite_window_init) or [`finite_overlay_init`](../finite_overlay_init) beforehand in order to get a valid `wl_output`

This function is meant to be used to resize windows but in production, all Infinite applications must be the full size of the screen which they are by default.

## Related Docs
[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_window_init`](../finite_window_init)<br>
[`finite_overlay_init`](../finite_overlay_init)