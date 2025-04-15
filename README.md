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

## Tips (MacOS)

If you want to auto-start tmux (re-attach or create a new session), enter the following inside your `~/.zshrc` file:

```
if command -v tmux >/dev/null 2>&1; then
  if [ -z "$TMUX" ]; then
    tmux attach || tmux new -s iyioon
  fi
fi
```

This will automatically start tmux when you open a terminal. If `iyioon` session already exists, it will reattach. Else, it will create a new session named `iyioon`.

If you also want to start tmux with a clock, you can use this instead:

```
function start_tmux_safely {
  if [ -z "$TMUX" ]; then
    if tmux has-session -t iyioon 2>/dev/null; then
      # Session exists — attach and trigger clock
      tmux send-keys -t iyioon 'tmux clock-mode' C-m
      tmux attach -t iyioon
    else
      # Create session and show clock
      tmux new-session -s iyioon \; send-keys 'tmux clock-mode' C-m
    fi
  fi
}

autoload -Uz add-zsh-hook
add-zsh-hook precmd start_tmux_safely
```
