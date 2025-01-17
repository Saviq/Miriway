# Miriway

## Introducing Miriway
Miriway is a starting point for creating a Wayland based desktop environment using Mir.

At the core of Miriway is `miriway-shell`, a Mir based Wayland compositor that provides:
* A "floating windows" window managament policy;
* Support for Wayland (and via `Xwayland`) X11 applications; 
* Dynamic workspaces;
* Additional Wayland support for "shell components" such as panels and docs; and,
* Configurable shortcuts for launching standard apps such as launcher and terminal emulator.

In addition to `miriway-shell`, Miriway has:

* A "terminal emulator finder" script `miriway-terminal`, that works with most terminal emulators;
* A launch script `miriway` to simplify starting Miriway;
* A default configuration file `miriway-shell.config`; and,
* A greeter configuration `miriway.desktop` so Miriway can be selected at login

Miriway has been tested with shell components from several desktop environments 
and there are notes on enabling these in `miriway-shell.config`.

## In development

Miriway uses an updated version of the Mir API. This will be released in 
Mir 2.9, and, until then, is available from the mir-team "development" PPA:

```plain
sudo apt-add-repository ppa:mir-team/dev
```

## Dependencies

Build dependencies:
```plain
sudo apt install libmiral-dev
```

Additional runtime dependencies:
```plain
sudo apt install mir-graphics-drivers-desktop
```

The default install is minimal and provides a basic shell and a default 
`Ctrl-Alt-T` command that tries to find a terminal emulator (by using 
`miriway-terminal`). If you don't already have a terminal emulator 
installed, then `sudo apt install xfce4-terminal` is a simple option.

## Building and Installing

```plain
mkdir build
cd build
cmake ..
cmake --build .
```

Installing

```plain
sudo cmake --build . -- install
```

Now you can run with `miriway`, or select "Miriway" from the login screen.

## Keyboard shortcuts

Keys|Action
--|--
Ctrl-Alt-BkSp|Exit (long press to force if apps are open)
Meta-Left|Dock left
Meta-Right|Dock right
Meta-PkUp|Previous workspace
Meta-Shift-PkUp|Move window to previous workspace
Meta-PkDn|Next workspace
Meta-Shift-PkDn|Move window to next workspace
Meta-Home|First workspace
Meta-Home-PkUp|Move window to first workspace
Meta-End|Last workspace
Meta-End-PkDn|Move window to last workspace

### Keyboard shortcuts using `Meta` and `Ctrl-Alt` can be added or amended

These (and other) defaults are specified in `/etc/xdg/xdg-miriway/miriway-shell.config` but can be overridden 
in `~/.config/miriway-shell.config`. You should typically copy and edit the default config file. It provides
some examples using components from existing desktop environments. (And the corresponding `apt install` commands)

Keys|Action
--|--
Ctrl-Alt-T|Terminal emulator
