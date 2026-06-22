# Arch Linux Bootc built with mkosi
This repository makes use of systemd's [mkosi](https://github.com/systemd/mkosi) to build a bootable Arch Linux OCI image for [bootc](https://github.com/bootc-dev/bootc).

This image is extremely minimalist and designed to be used as a template for making your own. It comes with a kernel, bootc, an editor, setup in place for registering an admin user account using systemd-homed and functional run0 for privilege escalation.

If you do not wish to use homed and instead would like to register user accounts via an alternative method, simply remove the 100-systemd-homed.preset which enables it.
