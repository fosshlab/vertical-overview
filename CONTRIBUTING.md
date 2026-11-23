# Contributing to Vertical Overview

Thanks for your interest! This is the maintained fork of
[RensAlthuis/vertical-overview](https://github.com/RensAlthuis/vertical-overview),
kept by the [FOSSH Lab](https://github.com/fosshlab). Contributions in English or
Spanish are welcome (*también se aceptan aportes en español*).

## Ways to help

- **Report bugs** using the [bug report template](https://github.com/fosshlab/vertical-overview/issues/new/choose).
  Please include your GNOME Shell version, X11 or Wayland, and any errors from the journal.
- **Ask questions or propose ideas** in [Discussions](https://github.com/fosshlab/vertical-overview/discussions).
- **Send pull requests** with fixes or improvements (see below).
- **Help porting to GNOME 45+**, which requires converting the extension to ES modules.

## Development setup

```sh
git clone https://github.com/fosshlab/vertical-overview.git
cd vertical-overview
glib-compile-schemas schemas
# replace the installed copy with a link to your clone
rm -rf ~/.local/share/gnome-shell/extensions/vertical-overview@RensAlthuis.github.com
ln -s "$PWD" ~/.local/share/gnome-shell/extensions/vertical-overview@RensAlthuis.github.com
gnome-extensions enable vertical-overview@RensAlthuis.github.com
```

GNOME Shell only loads new code after a restart: on X11 press `Alt+F2`, type `r`
and press Enter; on Wayland log out and back in.

To watch for errors while testing:

```sh
journalctl -f -o cat /usr/bin/gnome-shell | grep -iE 'vertical|JS ERROR'
```

### Testing without touching your session

You can run a nested GNOME Shell in a window, with its own temporary settings:

```sh
export XDG_CONFIG_HOME=$(mktemp -d) XDG_CACHE_HOME=$(mktemp -d)
dbus-run-session -- gnome-shell --nested --wayland
```

Note that `--nested` needs `--wayland` (it does not work with `--x11`).

## Pull request guidelines

- Keep each pull request focused on one change, and explain the problem it fixes.
- Make sure `disable()` undoes everything `enable()` does: every signal you
  connect must be disconnected, and every override must be restored.
  Note that `connectObject()` returns nothing; to disconnect later either keep the
  id returned by `connect()`, or pass a tracking object as the last argument of
  `connectObject()` and call `disconnectObject(thatObject)`.
- Test at least enabling and disabling the extension a few times, and, if your
  change touches multiple monitors, plugging and unplugging one.
- Don't leave debug logging enabled (`__DEBUG__` must stay `false`).
- Say which GNOME Shell version(s) and session type you tested on.

## License

By contributing you agree that your contributions are licensed under the
[GPL-3.0](LICENSE), the same license as the project.
