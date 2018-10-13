# Maintainer: Christian Hesse <mail@eworm.de>
# Maintainer: Angel Velasquez <angvp@archlinux.org>
# Contributor: Eric Belanger <eric@archlinux.org>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=htop-custom
pkgver=2.2.0
pkgrel=3
conflicts=('htop')
provides=('htop')
pkgdesc="Interactive process viewer"
arch=('x86_64')
url="http://hisham.hm/htop/"
license=('GPL')
depends=('ncurses')
makedepends=('python')
optdepends=('lsof: show files opened by a process'
            'strace: attach to a running process')
validpgpkeys=('8460980B2B79786DE0C7FCC83FD8F43C2BB3C478') # Hisham Muhammad <h@hisham.hm>

build() {
  ../configure \
      --prefix=/usr \
      --sysconfdir=/etc \
      --enable-unicode \
      --enable-openvz \
      --enable-vserver \
      --enable-cgroup

  make -j8
}

package() {
  make DESTDIR="$pkgdir" install
}
