# TMUX Configuration

> [Info]
> My self-contained tmux configuration made to work with my (neovim)[https://github.com/iyioon/nvim] configuration.

## Requirements

- [Tmux](https://github.com/tmux/tmux/wiki/Installing)
- A [patched nerd font](https://www.nerdfonts.com/) for powerline and glyphs support.

## Installation

Make sure you have tmux installed:

```bash
brew install tmux
```

For Linux and Mac:

```bash
git clone https://github.com/iyioon/tmux.git "${XDG_CONFIG_HOME:-$HOME/.config}"/tmux
```

## Features

- New Prefix key: `Ctrl + a`
- Split panes number starts from 1
- Panes open from current directory
- [Better mouse mode](https://www.google.com/search?q=better+mouse+mode+tmux&sourceid=chrome&ie=UTF-8)
- Status bar with:
  - Battery status
  - CPU usage

## Addition

If you want to add more plugins, you can refer to [this](https://github.com/rothgar/awesome-tmux?tab=readme-ov-file) list.
