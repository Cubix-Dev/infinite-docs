# finite_draw_create_snapshot

<div class="alert alert-warning part text-warning">
❕ finite_draw_create_snapshot was last modified in <b>v0.6.0</b>. 

It is incomplete and thus subject to change.
</div>
```c
void finite_draw_create_snapshot(FiniteShell *shell) 
```

The `finite_draw_create_snapshot` function attempts to create a restore point of a cairo surface. This function is still in testing.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |

## Code Example
```c 
	#include <finite/draw.h>
    finite_shm_alloc(shell, true);
    finite_draw_create_snapshot(myShell);
``` 

## Standard Usage
This function must have a valid [`FiniteShell`](../../../types/FiniteShell)

This function uses Cairo which requires a valid cairo_surface_t in [`FiniteShell`](../../../types/FiniteShell) implementation (shell.cairo_surface) beforehand.

This function copys all current data on screen and stores it in `shell.snapshot` in [`FiniteShell`](../../../types/FiniteShell)<br>

At some point [`finite_draw_finish`](../finite_draw_finish) should be called to apply the changes made by the snapshot visually.

## Related Docs
[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_draw_load_snapshot`](../finite_draw_load_snapshot)