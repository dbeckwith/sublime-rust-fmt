## Overview

RustFmt is a Sublime Text 3 plugin that auto-formats Rust code with [`rustfmt`](https://github.com/rust-lang-nursery/rustfmt) or another executable.

Unlike `BeautifyRust`, it's fast and works on buffers that have yet not been saved as files. Unlike `RustFormat`, it preserves the buffer scroll position. It also supports `rustfmt.toml`.

## Dependencies

Requires Sublime Text version 3124 or later.

Requires [`rustfmt`](https://github.com/rust-lang-nursery/rustfmt) to be on [PATH](https://en.wikipedia.org/wiki/PATH_(variable)). Install it with Cargo:

```sh
cargo install rustfmt
```

## Installation

### Package Control

1. Get [Package Control](https://packagecontrol.io)
2. Open command palette: `Shift+Super+P` or `Shift+Ctrl+P`
3. `Package Control: Install Package`
4. `RustFmt`

### Manual

1. Open Sublime Text menu → Preferences → Browse Packages. This should open
   the packages folder in your OS file manager.

2. Clone repo:

```sh
git clone https://github.com/Mitranim/sublime-rust-format.git RustFmt
```

## Usage

By default, RustFmt will autoformat files before save. You can trigger it manually with the `Ctrl+Super+k` hotkey or the `RustFmt: Format Buffer` command in the command palette.

If the plugin can't find the executable:

  * run `which rustfmt` to get the absolute executable path
  * set it as the `executable` setting, see [Settings](#settings) below

On my MacOS system, the path looks like this:

```sublime-settings
  "executable": "/Users/username/.cargo/bin/rustfmt"
```

`executable` also accepts a list of command line arguments:

```sublime-settings
  "executable": ["rustup", "run", "nightly", "rustfmt"]
```

## Settings

See [`RustFmt.sublime-settings`](RustFmt.sublime-settings) for all available settings. To override them, open:

```
Preferences → Package Settings → RustFmt → Settings
```

RustFmt looks for settings in the following places:

  * `"RustFmt"` dict in general Sublime settings, possibly project-specific
  * `RustFmt.sublime-settings`, default or user-created

The general Sublime settings take priority. To override them on a per-project basis, create a `"RustFmt"` entry:

```sublime-settings
  "RustFmt": {
    "format_on_save": false
  }
```

## Commands

Open the command palette with `Shift+Super+P` or `Shift+Ctrl+P`.

* `RustFmt: Format Buffer` (`Ctrl+Super+k`)

## License

https://en.wikipedia.org/wiki/WTFPL
