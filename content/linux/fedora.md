---
title: "Linux Fedora"
tags:
-   linux
---

# Fedora workstation setup

## Create USB bootable drive
-   Download Fedora Workstation ISO from [here](https://getfedora.org/en/workstation/download/)
-   Download Rufus from [here](https://rufus.ie/)
-   Open Rufus and select the USB drive
-   Select the Fedora ISO
-   Click start

## Disable secure boot
-   Restart the computer
-   Press F2 to enter BIOS
-   Navigate to the security tab
-   Disable secure boot

## Install Fedora
-   Restart the computer
-   Press F12 to enter boot menu
-   Select the USB drive
-   Select install Fedora
-   Select the language
-   Select the keyboard layout
-   Select the installation destination
    -   Use custom partitioning
    -   Click "click here to create them automatically"
    -   Ensure ext4 is selected not btrfs
    -   Click done

## Setup gnome desktop environment
-   Follow initial setup instructions
-   connect to wifi

## Configure dnf and update
-   sudo vi /etc/dnf/dnf.conf
    -   add `max_parallel_downloads=10`
    -   add `keepcache=true`
-   sudo dnf update

## Enable RPM Fusion
-   reference: https://rpmfusion.org/Configuration
    -   run 'Fedora with dnf' command
    -   AppStream metadata command
    -   Multimedia on Fedora
    -   fullfmpeg
    -   install additional codecs
-   `flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`

## Install NVIDIA drivers
-   reference: https://rpmfusion.org/Howto/NVIDIA
    -   `sudo dnf update -y` - reboot if kernel updated
    -   `sudo dnf install akmod-nvidia`
    -   `sudo dnf install xorg-x11-drv-nvidia-cuda` - optional for cuda/nvdec/nvenc

## Gnome tweaks
-   `sudo dnf install gnome-tweaks`
    -   enable minimize/maximize buttons
    -   Mouse acceleration profile: Flat

## Install Qtile
-   `sudo dnf copr enable frostyx/qtile`
-   `sudo dnf install qtile`
-   `sudo dnf install qtile-extras`

