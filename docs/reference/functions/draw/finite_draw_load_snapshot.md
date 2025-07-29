# finite_draw_load_snapshot

<div class="alert alert-warning part text-warning">
❕ finite_draw_load_snapshot was last modified in <b>v0.6.0</b>.

It is incomplete and thus subject to change.

</div>

```c
void finite_draw_load_snapshot(FiniteShell *shell)
```

The `finite_draw_load_snapshot` function attempts to restore a cairo surface from a restore point. This function is still in testing.

## Parameters

| Type                 | Decription                                                           |
| -------------------- | -------------------------------------------------------------------- |
| `FiniteShell *shell` | The [`FiniteShell`](../../../types/FiniteShell) where the window is. |

## Code Example

```c
	#include <finite/draw.h>

    finite_draw_load_snapshot(myShell);
    finite_draw_finish(myShell);
```

## Standard Usage
In order to load a snapshot, one must be created with [`finite_draw_create_snapshot`](../finite_draw_create_snapshot) at the point you'd like to restore to.

This function destroys all current data on screen and replaces it with the data in `shell.snapshot` in [`FiniteShell`](../../../types/FiniteShell)<br>

At some point [`finite_draw_finish`](../finite_draw_finish) should be called to apply the changes made by the snapshot visually.

## Related Docs

[`FiniteShell`](../../../types/FiniteShell)<br>
[`finite_draw_create_snapshot`](../finite_draw_create_snapshot)
