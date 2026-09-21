# SteavenInstaller

![Profile Image](https://avatars.githubusercontent.com/u/128651597?s=400&u=cfe5c1038e6b898b6a21b662723c8ee208225f8f&v=4)

An interactive UEFI installer for SteavenLinux, designed to run from an Arch Linux live environment.

## Before You Begin

- Boot the live environment in **UEFI mode** and ensure you have an internet connection.
- Run the installer as `root`.
- Automatic mode will erase all partitions and files on the selected disk. You must confirm `ERASE /dev/...` exactly.
- Manual mode will not partition, format, mount, or unmount anything. You must mount the root filesystem at `/mnt` and the EFI System Partition at `/mnt/boot` before proceeding.
- The live environment must be able to install SteavenLinux packages and must contain `/etc/pacman.d/steavenrepo-mirrorlist`.
- Before installing, the script refreshes the official Arch Linux keyring and imports the documented Chaotic-AUR primary key. It does not accept arbitrary package-signing keys.

## Running from a Checkout

