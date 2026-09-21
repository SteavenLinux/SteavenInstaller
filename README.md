# SteavenInstaller

An interactive UEFI installer for SteavenLinux, designed to run from an Arch Linux live environment.

## Before you start

- Boot the live environment in **UEFI mode** and connect it to the internet.
- Run the installer as `root`.
- Automatic mode destroys every partition and file on the selected disk. It requires the exact confirmation `ERASE /dev/...`.
- Manual mode never partitions, formats, mounts, or unmounts anything. Mount the root filesystem at `/mnt` and the EFI System Partition at `/mnt/boot` before continuing.
- The live environment must already be able to install SteavenLinux packages and must contain `/etc/pacman.d/steavenrepo-mirrorlist`.
- Before installing, the script refreshes the official Arch Linux keyring and imports the documented Chaotic-AUR primary key. It does not accept arbitrary package-signing keys.

## Running from a checkout

```bash
chmod +x steavenlinuxinstall configure-system
./steavenlinuxinstall
```

## What it configures

Automatic mode creates a GPT layout with a 2 GiB EFI System Partition and an ext4 root partition. The installer installs the base system, generates a fresh `fstab`, configures the locale, timezone, accounts, GRUB, network service, and a GNOME or KDE desktop. Selecting GNOME installs `SteavenLinux-gnome-meta`; selecting KDE installs `SteavenLinux-plasma-meta`. It adds Flathub system-wide and installs LibreWolf as a system Flatpak.

CachyOS repositories are optional and disabled by default. When enabled, repository packages are signature-checked; the installer does not install CachyOS's custom `pacman` package.

## Quality checks

Every push and pull request runs Bash syntax validation and ShellCheck through GitHub Actions. You can run the syntax check locally with:

```bash
bash -n steavenlinuxinstall configure-system PKGBUILD
```

## Recovery

If installation stops, mounted filesystems are deliberately left available for diagnosis. Check the reported failure and `/mnt`; only then, if safe, unmount the target before rebooting:

```bash
umount -R /mnt
```
