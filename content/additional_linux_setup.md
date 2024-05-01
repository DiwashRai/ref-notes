---
title: "Additional Linux Setup"
tags:
-   linux
--

## install nerd fonts
Download JetBrains at least
- download nerd fonts from [here](https://www.nerdfonts.com/font-downloads)
- mkdir `~/.local/share/fonts`
- `unzip JetBrainsMono.zip -d ~/.local/share/fonts`

## zsh
- `sudo dnf install zsh`
  - `sudo dnf install util-linux-user`
  - `chsh -s $(which zsh)`
  - setup zsh settings upon first login
    - history
      - HISTSIZE=10000
      - SAVEHIST=10000
          - HISTFILE=~/.zsh_history
    - completion system
      - default
    - key bindings (vi or emacs)
      - vi
    - other shell options
      - unset beep
- install powerline10k

## other packages
- `sudo dnf install tmux`
- `sudo dnf install dmenu`
- `sudo dnf install neovim python3-neovim`
- `sudo dnf install vlc`
- lazygit

## install brave browser
- `sudo dnf install dnf-plugins-core`
- `sudo dnf config-manager --add-repo https://brave-browser-rpm-release.s3.brave.com/x86_64/`
- `sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc`
- `sudo dnf install brave-browser brave-keyring`

## monitor output stuff
- xrandr
- arandr
- autorandr
Use arandr to apply the layout. Use autorandr to save the profile.

## networking
- Fedora uses NetworkManager by default so these commands are probably not necessary
  - `sudo dnf install NetworkManager-tui`
  - `sudo systemctl enable NetworkManager`
  - `sudo systemctl start NetworkManager`
- If you decide to use NetworkManager you can also use the applet
  - `sudo dnf install NetworkManager-applet`
  - `nm-applet &` in qtile config. Requires a notification daemon to be running

## notifications
- `sudo dnf install dunst`

## touchpad settings
- ensure following packages are installed
  - `sudo dnf install libinput libinput-utils`
- create `/etc/X11/xorg.conf.d/30-touchpad.conf` with the following contents:

```conf
Section "InputClass"
    Identifier "libinput touchpad catchall"
    MatchIsTouchpad "on"
    MatchDevicePath "/dev/input/event*"
    Driver "libinput"
    Option "Tapping" "on"
    Option "NaturalScrolling" "true"
    Option "ScrollPixelDistance" "25"
    Option "ClickMethod" "clickfinger"
    Option "TappingButtonMap" "lrm"
    Option "AccelProfile" "adaptive"
    Option "AccelSpeed" "0.2"
    Option "DisableWhileTyping" "true"
EndSection
```

## keyboard settings
- remap caps to ctrl
  - `cd /etc/X11/xorg.conf.d`
  - `sudo vim 00-keyboard.conf`
  - add the following to the file

```conf
Section "InputClass"
        Identifier "system-keyboard"
        MatchIsKeyboard "on"
        Option "XkbOptions" "ctrl:nocaps"
EndSection
```
- For switching keyboard layouts
  - sudo dnf install setxkbmap
  - and use rofi script to switch layouts in scripts dir from .dotfiles

## rofi
- `sudo dnf install rofi`
- `rofi-theme-selector` to select a theme
- setup scripts
  - powermenu script
  - quick_access script
  - confedit script


## dev related setup
- vs code
  - [vs code setup](https://code.visualstudio.com/docs/setup/linux)
- cmake
- vcpkg
  - [vcpkg setup](https://vcpkg.io/en/getting-started.html)
  - general steps:
    - git clone
    - bootstrap script
    - vcpkg install catch2:x64-linux
    - vcpkg install benchmark:x64-linux


