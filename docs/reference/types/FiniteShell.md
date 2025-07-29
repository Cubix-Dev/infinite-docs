# FiniteShell

<div class="alert alert-info part text-info">
❔ FiniteShell was last modified in <b>0.4.0</b>
</div>

```c
typedef struct FiniteShell FiniteShell;
struct FiniteShell{
    int shm_fd;
    int pool_size;
    int stride;
    uint8_t *pool_data;
    struct wl_display *display;
    struct wl_registry *registry;
    struct wl_output *output;
    struct wl_shm *shm;
    struct wl_shm_pool *pool;
    struct wl_buffer *buffer;
    struct wl_compositor *isle;
    struct wl_surface *isle_surface;
    struct xdg_wm_base *base;
    struct xdg_surface *surface;
    struct xdg_toplevel *window;
    struct zwlr_layer_shell_v1 *shell;
    struct zwlr_layer_surface_v1 *layer_surface;
    FiniteWindowInfo *details;
    cairo_t *cr;
    cairo_surface_t *cairo_surface;
    unsigned char *snapshot;
    FiniteBtn **btns;
    int _btns;
    int activeButton;
    void *data;
};
```

The `FiniteShell` struct stores general information about a window.


## Properties

| Type                           | Decription                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------- |
| `int shm_fd`                   | An integer file descriptor for the shared memory(shm) buffer associated with the file. |
| `int pool_size`                | The size of the shm pool                                                               |
| `int stride`                   | The spacing between blocks of memory when drawing with Cairo.                          |
| `uint8_t pool_data`            | The mmapped data in the pool.                                                          |
| `struct wl_display *display`   | The Wayland display associated with the FiniteShell.                                   |
| `struct wl_registry *registry` | The Wayland registry associated with the display.                                      |
| `struct wl_output *output`     | The Wayland Output that is currently connected.                                    |
| `struct wl_shm *shm`           | The Wayland shm struct associated with the FiniteShell                                 |
| `struct wl_shm_pool *pool`     | The Wayland shm pool associated with the shm|
|`struct wl_buffer *buffer`| The Wayland shm buffer associated with the FiniteShell|
|`struct wl_compositor *isle`| The Compositor connected the display|
|`struct wl_surface *isle_surface`| The Wayland surface connected to display|
|`struct xdg_wm_base *base`| The [xdg_wm_base](https://wayland.app/protocols/xdg-shell#xdg_wm_base) associated with the FiniteShell|
|`struct xdg_surface *surface`| The xdg_surface associated with the base|
|`struct xdg_toplevel *window`| The xdg_toplevel where data will be rendered to.|
|`struct zwlr_layer_shell_v1 *shell`| The [layer shell](https://wayland.app/protocols/wlr-layer-shell-unstable-v1#zwlr_layer_shell_v1) associated with the FiniteShell|
|`struct zwlr_layer_surface_v1 *layer_surface`| The layer surface associated with the layer shell|
|`FiniteWindowInfo *details`| Data about the window|
|`cairo_t *cr`|The Cairo drawing object.|
|`cairo_surface_t *cairo_surface`|The cairo surface associated with the window.|
|`unsigned char *snapshot`|A single cairo snapshot|
|` FiniteBtn **btns`|An array of FiniteBtns|
|`int _btns`| The number of FiniteBtns currently visible.|
|`int activeButton`|The Array position of the currently selected |
|`void *data`|Custom data|

## Notes

1) wl_output is a pointer but not an array. The Islands compositor only allows one output at a time which is reflected in this value.<br>
2) Snapshots are able to be recovered to return the UI to a previous state. They currently do not apply array related changes to buttons.<br>

## Standard Usage
When creating an appplication in libfinite you must **always** use a FiniteShell object created with `finite_shell_init`. Unless you need a specific wayland client, "wayland-0" should be the parameter passed into `finite_shell_init`.

The Cubix Infinite uses Wayland as it's display server so in order to keep the FiniteShell session alive you'll need to use use the wayland function [`wl_display_dispatch`](https://wayland.freedesktop.org/docs/html/apb.html#Client-classwl__display_1a30a9c4f020f3e77581c7a81ecdb4913d) for cairo based applications or [`wl_display_dispatch_pending`](https://wayland.freedesktop.org/docs/html/apb.html#Client-classwl__display_1ac4b6b5ad31932bc3830ff362d2938560) for Vulkan based applications.

When creating an application in libfinite you'll need to call either `finite_window_init` or `finite_overlay_init` depending on what you're creating. For more information, see their corresponding pages.

## Related Docs
[`finite_shell_init`](../../functions/draw/finite_shell_init)<br>
[`finite_window_init`](../../functions/draw/finite_window_init)<br>
[`finite_overlay_init`](../../functions/draw/finite_overlay_init)<br>