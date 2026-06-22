# Arch Linux Bootc built with mkosi
This repository makes use of systemd's [mkosi](https://github.com/systemd/mkosi) to build a bootable Arch Linux OCI image for [bootc](https://github.com/bootc-dev/bootc).

This image is extremely minimalist and designed to be used as a template for making your own. It comes with a kernel, bootc, an editor, setup in place for registering an admin user account using systemd-homed and functional run0 for privilege escalation.

If you do not wish to use homed and instead would like to register user accounts via an alternative method, simply remove the 100-systemd-homed.preset which enables it.

## A Note on Pacman
With the setup on this image, pacman will not have the necessary database files downloaded and they must be downloaded manually instead. This means when installing packages on a bootc usroverlay you should always install with `pacman -Sy [package]` or to be safe `pacman -Syu [package]`.

This is not a suitable configuration for persistent overlays. If you wish to support those on your image, it is necessary to either get all your packages from the [Arch Linux archive](https://archive.archlinux.org/) or build your overlays at the same time as the image (e.g. using systemd-sysext).
