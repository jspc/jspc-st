# Contributor: Patrick Jackson <PatrickSJackson gmail com>
# Maintainer: Christoph Vigano <mail@cvigano.de>
# Variant Maintainer: James Condron <james@zero-internet.org.uk>

pkgname=st-jspc
pkgver=0.6
pkgrel=2
pkgdesc='JSPC Variant; A simple virtual terminal emulator for X.'
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxft')
makedepends=('ncurses')
url="http://st.suckless.org"
source=(http://dl.suckless.org/st/st-$pkgver.tar.gz
        config.h)

build() {
  cd $srcdir/st-$pkgver
  cp $srcdir/config.h config.h
        make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd $srcdir/st-$pkgver
  sed -i '/\@tic /d' Makefile
  make PREFIX=/usr DESTDIR="$pkgdir" TERMINFO="$pkgdir/usr/share/terminfo" install
        install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
        install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
}
md5sums=('1a926f450b4eacb7e2f5ac5b8ffea7c8'
         '6a2b4c9dd0e8339999daebeea0a16adb')
