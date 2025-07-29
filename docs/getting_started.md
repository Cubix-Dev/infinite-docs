# Getting Started

## Prerequisites

To get started developing on Libfinite, you'll need these prerequisites

<div class="alert alert-info part text-info">
❓ The Infinite Library is intended to be used on a Linux based system.
</div>

🔸 [cglm](https://github.com/recp/cglm) - A C based Graphics Math library<br>
🔸 [Wayland](https://gitlab.freedesktop.org/wayland/wayland) - The window compositing protocol.<br>
🔸 [Wayland Protocols](https://gitlab.freedesktop.org/wayland/wayland-protocols) - Additional Non Standard features for Wayland. (v1.24 or higher)<br>
🔸 [Cairo](https://cairographics.org/) - Graphics Library for drawing data to buffers.<br>
🔸 [Vulkan](https://github.com/KhronosGroup/Vulkan-Loader/) - An explicit graphical libary that gives users the full control over the rendering process.<br>
🔸 [xkbcommon](https://github.com/xkbcommon/libxkbcommon) - Keymap library.<br>
🔸 [libevdev](https://www.freedesktop.org/wiki/Software/libevdev/) - evdev device library<br>
🔸 [sndfile](https://github.com/libsndfile/libsndfile) - C library for reading and writing audio data<br>
🔸 [ALSA](https://www.alsa-project.org/wiki/Main_Page) - The Advanced Linux Sound Architecture<br>
🔸 [Meson](https://github.com/mesonbuild/meson) - The Meson Build System

Also make sure you've built the library from source as `sudo`

```sh
meson setup build --prefix=/usr
sudo ninja -C build install
```

## Libfinite "Weirdness"

<div class="alert alert-warning part text-warning">
⚠ Libfinite is <b>still in development</b> and the information here is <b> subject to change.</b>
</div>

Before you start writing code, there are quite a few "quirks" about libfinite that you should be familiar with.

### 1) Functions are wrapped in Macros in C

All this really means is that functions act weird in VSCode. This site is your best friend for providing explainations on how functions work so check here often for information.

### 2) `draw` and `render` are NOT for mixing.

You may have notice there are `finite_draw*` and `finite_render*` and thought you could do something like call `finite_draw_rect()` and then draw your little cube on the same window. That will not work without extra effort and is not the intended behavior of those function groups. If you are using `finite_draw` (with Cairo) then you should NOT use `finite_render` (with Vulkan) on the same surface. If you do this anyways, you were warned.

### 3) Reinvent the wheel as a Power User

If you want extended functionality of any libfinite function, you can always write a local version yourself. libfinite functions don't call on each other (with a few exceptions, such as [`finite_render_begin_oneshot_command`](../reference/functions/finite_render_begin_oneshot_command)) so you're free to do what you want (within reason).

#### Other Weird things

- _vars are indexing variables. Don't mix these up
- finite_draw functions render from back to front
- finite_audio requires multithreading for audio control

## Required Files

In order to build a libfinite project you'll need these files which we've graciously provided.

- [xdg-shell.xml](../starter-files/xdg-shell.xml)
- [layer-shell.xml](../starter-files/layer-shell.xml)
- [meson.build](../starter-files/meson.build)

These files should be in the root of your project. They are required to make libfinite work correctly.

## A barebones project

Below is an example of a BAREBONES project that does nothing but set up a window and keep it alive. To start drawing to the screen check out the `finite_draw` or `finite_render` function families.

```c
#include <finite/draw.h>
#include <finite/log.h>

int main() {
    // create a new shell
    FiniteShell *myShell = finite_shell_init("wayland-0");

    if (!myShell) {
        FINITE_LOG_FATAL("Unable to init shell");
    }

    // to draw windows make a window
    finite_window_init(myShell);

    if (!myShell) {
        FINITE_LOG_FATAL("Unable to make shell");
    }

    // do rendering here

    // now just keep the window alive
    while (wl_display_dispatch(myShell->display) != -1) {
        // do per frame events here (such as finite_input_poll_keys())
    }
    // cleanup here
    wl_display_disconnect(myShell->display);
}
```
