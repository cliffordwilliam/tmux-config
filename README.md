# tmux-config

My [tmux](https://github.com/tmux/tmux) config. Pairs with
[foot-config](https://github.com/cliffordwilliam/foot-config): foot launches
`tmux new-session` as its shell, so one foot window hosts multiple **named
windows ("tabs")** — foot stays a dead-simple single-window emulator and tmux
provides the tabs.

## Design

- **Ephemeral, no persistence.** `destroy-unattached on` — closing the foot
  window destroys the session and the server exits. Nothing lingers to reattach.
- **One thing at a time.** No split panes; move between windows or pick from a list.
- **Clean status bar.** No session name, no clock (GNOME's top bar already has those).
- **Truecolor** under foot via `terminal-overrides ",foot*:Tc"`.

## Keybinds

Prefix is **`Ctrl-j`**. Press it, release, then:

| Action | Key |
|--------|-----|
| **n**ew window (prompts for a name) | `n` |
| **r**ename window | `r` |
| **f**ind — vertical picker of all windows | `f` |
| move left / right (nvim-style) | `h` / `l` (or arrows) |
| jump to window N | `1`…`9` |
| reload this config | `R` |

## Install on a new machine

```sh
sudo apt install tmux
ln -s ~/repositories/tmux-config/tmux.conf ~/.tmux.conf
```

Then point foot at tmux (in `foot-config/foot.ini`):

```ini
shell=tmux new-session
```
