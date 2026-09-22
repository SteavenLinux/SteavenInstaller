# Maintainer: omarhanykasban <omarhanykasban706@gmail.com>

pkgname=SteavenLinuxInstaller
pkgver=1.0.0
pkgrel=1
pkgdesc="SteavenGamerYT's SteavenLinux's Installer"
arch=('any')
url="https://github.com/SteavenLinux/SteavenInstaller"
license=('MIT')
makedepends=('git')
source=(
  "SteavenInstaller::git+https://github.com/SteavenLinux/SteavenInstaller.git"
)
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/SteavenInstaller"
  git rev-parse --short HEAD
}

package() {
  cd "$srcdir/SteavenInstaller"
  install -Dm755 steavenlinuxinstall "$pkgdir/usr/bin/steavenlinuxinstall"
  install -Dm755 configure-system "$pkgdir/usr/share/steaveninstaller/configure-system"
  install -Dm644 pacman-cachyos.conf "$pkgdir/usr/share/steaveninstaller/pacman-cachyos.conf"
  install -Dm644 pacman-arch.conf "$pkgdir/usr/share/steaveninstaller/pacman-arch.conf"
  install -Dm644 steavenrepo-mirrorlist "$pkgdir/usr/share/steaveninstaller/steavenrepo-mirrorlist"

install -Dm644 \
    pkgs/cachyos-keyring-20240331-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/cachyos-keyring-20240331-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/cachyos-mirrorlist-27-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/cachyos-mirrorlist-27-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/cachyos-v3-mirrorlist-27-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/cachyos-v3-mirrorlist-27-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/cachyos-v4-mirrorlist-27-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/cachyos-v4-mirrorlist-27-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/chaotic-keyring-20251028-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/chaotic-keyring-20251028-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/chaotic-mirrorlist-20260428-1-any.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/chaotic-mirrorlist-20260428-1-any.pkg.tar.zst"

install -Dm644 \
    pkgs/pacman-7.1.0.r9.g54d9411-4-x86_64.pkg.tar.zst \
    "$pkgdir/usr/share/steaveninstaller/pkgs/pacman-7.1.0.r9.g54d9411-4-x86_64.pkg.tar.zst"

}