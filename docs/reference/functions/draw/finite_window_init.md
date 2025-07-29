# finite_window_init

<div class="alert alert-info part text-info">
❔ finite_window_init was last modified in <b>v0.6.0</b>
</div>

```c
void finite_window_init(FiniteShell *shell)
```

The `finite_window_init` function creates a new window with a given [`FiniteShell`](../../FiniteShell).


## Parameters

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
|`FiniteShell *shell`|The FiniteShell to create a window for.|

## Code Example

```c 
finite_window_init(myShell);

if (!myShell) {
    FINITE_LOG_FATAL("Unable to make shell");
}
```

## Standard Usage
When creating a new application (NOT A POPUP), you **must** call this function. Although libfinite support custom implementations of some function, all libfinite functions that interact with the window expect a [`FiniteShell`](../../FiniteShell).

## Related Docs
[`FiniteShell`](../../../types/FiniteShell)<br>
[`FiniteWindowInfo`](../../../types/FiniteWindowInfo)