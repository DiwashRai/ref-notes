---
title: "Linux Mint"
tags:
-     linux
---

# Linux mint setup
Official guide can also be found here:  
https://linuxmint-installation-guide.readthedocs.io/en/latest/

## Create USB Bootable drive
-   Download it from the main linux mint website(google)
    -   Consider the cinnamon 'edge' version which will come with newer kernel
-   Use Balena etcher to flash the usb

## Installing Linux mint
-   When you boot from USB you need to start Linux Mint in live session where you can then access
the installer
-   Connect to the internet if possible. Required later for nvidia driver
-   Installation type: Erase disk and install Linux Mint
    -   CT1000P3PSSD8 - linux drive

## First steps
**Desktop Colours**
-   Dark theme

**System Snapshots**
-   Default everything
-   Create first snapshot

**Driver Manager**
-   Use most recent/recommended

**Update Manager**
-   Opt to use a local mirror
-   Install updates

## Settings
-   Check trackpad two finger right click works

## Initial packages
-   git stow kitty
-   dmenu dunst rofi
-   python3 python3-pip
-   cmake nodejs npm
-   arandr autorandr
-   brave-browser
    -   https://brave.com/linux/

## Install nerdfont
-   ~/.local/share/fonts/
-   JetBrainsMono nerdfont

## qtile setup
```
sudo apt install xserver-xorg xinit
sudo apt install libpangocairo-1.0-0
sudo apt install python3-pip python3-xcffib python3-cairocffi

cd ~/code/public-repos
cd qtile
pip install .
```

