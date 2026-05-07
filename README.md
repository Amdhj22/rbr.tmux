<h1 align="center">
  🏁&nbsp;&nbsp;rbr.tmux
</h1>

<p align="center">
  <i>A Red Bull Racing theme for tmux — the tmux port of <a href="https://github.com/Amdhj22/rbr">rbr-theme</a>.</i>
</p>

<p align="center">
  <a href="https://github.com/Amdhj22/rbr.tmux/stargazers"><img src="https://img.shields.io/github/stars/Amdhj22/rbr.tmux?colorA=0a1128&colorB=e84a55&style=for-the-badge"/></a>
  <a href="./LICENSE"><img src="https://img.shields.io/github/license/Amdhj22/rbr.tmux?colorA=0a1128&colorB=b8d49e&style=for-the-badge"/></a>
  <a href="https://github.com/Amdhj22/rbr"><img src="https://img.shields.io/badge/palette-rbr--theme-e84a55?colorA=0a1128&style=for-the-badge"/></a>
</p>

&nbsp;

## About

`rbr.tmux` paints your tmux status bar, window tabs, pane borders, and prompts with the [RBR color scheme](https://github.com/Amdhj22/rbr) — **kerb red** for the focused pane and active window, **RB yellow** for session badges and messages. tmux has no syntax surface, so the third RBR brand accent (**chequer white**, used for functions in editor ports) does not apply here. See the upstream [`STYLE-GUIDE.md`](https://github.com/Amdhj22/rbr/blob/main/STYLE-GUIDE.md) for the full design rules.

> [!NOTE]
> This scheme is a fan tribute. Not affiliated with or endorsed by Red Bull Racing, Oracle Red Bull Racing, or Red Bull GmbH.

&nbsp;

## Requirements

- **tmux 3.0+** (for hex color support in style specs)
- A **truecolor** terminal. Add to your `~/.tmux.conf` if you haven't already:
  ```tmux
  set -g  default-terminal "tmux-256color"
  set -ag terminal-overrides ",*:RGB"
  ```

&nbsp;

## Install

### Via [tpm](https://github.com/tmux-plugins/tpm) (recommended)

```tmux
# ~/.tmux.conf
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'Amdhj22/rbr.tmux'
run '~/.tmux/plugins/tpm/tpm'
```

Reload tmux, then press `prefix + I` to install.

### Manual

```bash
# 1. Clone anywhere convenient
git clone https://github.com/Amdhj22/rbr.tmux.git ~/.config/tmux/rbr

# 2. Source it from ~/.tmux.conf
echo 'source-file ~/.config/tmux/rbr/rbr.tmux' >> ~/.tmux.conf

# 3. Reload
tmux source-file ~/.tmux.conf
```

&nbsp;

## What it paints

| Element                      | Color                          | Why                                               |
| ---------------------------- | ------------------------------ | ------------------------------------------------- |
| Active pane border           | Kerb Red `#e84a55`             | Exactly one focused pane per viewport             |
| Inactive pane border         | Overlay 0 `#3a4466`            | Recedes; present but unobtrusive                  |
| Current window tab           | Kerb Red bg                    | Mirrors the "one focused thing" rule              |
| Session badge (status-left)  | RB Yellow bg                   | Most-needed info: which session you're in         |
| Clock / date (status-right)  | RB Yellow bg                   | Always-visible attention without being loud       |
| `:` command prompt           | RB Yellow bg                   | Matches the editor cursor's "attention now" role  |
| Copy mode selection          | RB Yellow bg                   | Same as above — an active interaction             |
| Messages (`display-message`) | RB Yellow bg                   | Attention color                                   |
| Bell / activity              | Kerb Bright / RB Yellow        | Escalating warning colors                         |
| Clock mode (`prefix+t`)      | Kerb Red                       | Large focal element gets the brand color          |

&nbsp;

## Keeping the palette in sync

Color values live upstream in [`Amdhj22/rbr`](https://github.com/Amdhj22/rbr)'s `palette.json`. This repo vendors the hex values directly in `rbr.tmux`. When the upstream palette changes, update the hex codes in `rbr.tmux` to match.

&nbsp;

## Companion ports

For a consistent look across the rest of your stack:

| Tool | Repo |
|---|---|
| Neovim | [Amdhj22/rbr.nvim](https://github.com/Amdhj22/rbr.nvim) |
| VS Code | [Amdhj22/rbr.vscode](https://github.com/Amdhj22/rbr.vscode) |
| Obsidian | [Amdhj22/rbr.obsidian](https://github.com/Amdhj22/rbr.obsidian) |
| Ghostty / iTerm2 / Powerlevel10k / eza | [Amdhj22/rbr](https://github.com/Amdhj22/rbr) |

&nbsp;

## License

[MIT](./LICENSE) © Amdhj22
