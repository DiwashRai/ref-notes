---
title: "Tmux"
tags:
-   tools
---

### install
- `sudo dnf install tmux`
- Install tmux plugin manager
  - `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
- ensure tmux conf exists at '~/.config/tmux/tmux.conf'
  - cd .dotfiles
  - stow tmux
- Install plugins
  - `tmux source ~/.tmux.conf`
  - `prefix + I` (capital i, as in Install) to fetch the plugin

### Cheat sheet
**New session**
- `tmux`

**Start new session with name mysession**
- `tmux new -s mysession`

**List all sessions**
- `tmux ls`
- Ctrl + b, s

