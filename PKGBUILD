# Maintainer: Sean Sullivan <sean@seansullivan.ai>
pkgname=st
pkgver=0.8.4
pkgrel=1
epoch=1
pkgdesc="Sean's simple terminal with sensible defaults, etc."
arch=('i686' 'x86_64' 'armv7h')
url="https://github.com/sullivan-sean/st"
license=('MIT')
depends=(libxft)
source=('git://github.com/sullivan-sean/st'
				'config.h')
sha1sums=('SKIP' 'SKIP')

build() {
  cd "$srcdir/${pkgname}"
  cp "$srcdir/config.h" config.h
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  local installopts='--mode 0644 -D'
  cd "$srcdir/${pkgname}"
  make PREFIX=/usr DESTDIR="$pkgdir/" install
  install $installopts LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install $installopts README "${pkgdir}/usr/share/doc/${pkgname}/README"
}

