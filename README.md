# TMUX Configuration (Remote Branch)

> [!NOTE]
> This is the **remote server** branch with status bar at the bottom.
> For local machines, use the `master` branch.

My self-contained tmux configuration made to work with my [neovim](https://github.com/iyioon/nvim) configuration.

## Requirements

- [Tmux](https://github.com/tmux/tmux/wiki/Installing)
- A [patched nerd font](https://www.nerdfonts.com/) for powerline and glyphs support.

## Installation

Make sure you have tmux installed:

```bash
# macOS
brew install tmux

# Debian/Ubuntu
sudo apt install tmux

# Fedora
sudo dnf install tmux
```

### 1. Clone this repository

```bash
git clone -b remote https://github.com/iyioon/tmux.git "${XDG_CONFIG_HOME:-$HOME/.config}"/tmux
```

### 2. Install TPM (Tmux Plugin Manager)

This configuration uses [TPM](https://github.com/tmux-plugins/tpm) to manage plugins. You must install it:

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### 3. Install plugins

Start tmux and press `Ctrl+a` followed by `Shift+I` (capital I) to install the plugins.

Alternatively, you can install plugins from the command line:

```bash
~/.tmux/plugins/tpm/bin/install_plugins
```

### 4. Reload tmux

```bash
tmux source ~/.config/tmux/tmux.conf
```

## Features

- Prefix key: `Ctrl + a`
- Status bar at **bottom**
- Window/pane index starts from 1
- Panes open from current directory
- Auto renumber windows when one is closed
- [Better mouse mode](https://github.com/NHDaly/tmux-better-mouse-mode)
- Status bar with hostname, CPU and RAM usage
- Vi-style copy mode:
  - Enter copy mode: `Ctrl+a` + `[`
  - Start selection: `v`
  - Move: `h`/`j`/`k`/`l`
  - Copy & exit: `y`

## Differences from master branch

| Setting | Master (local) | Remote (this branch) |
|---------|----------------|----------------------|
| Status bar | Top | Bottom |

## Adding plugins

Refer to [awesome-tmux](https://github.com/rothgar/awesome-tmux) for more plugins.
