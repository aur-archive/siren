# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=siren
pkgver=0.3.1
pkgrel=1
pkgdesc="A text-based audio player"
arch=(i686 x86_64)
url="http://www.kariliq.nl/siren/"
license=('custom:ISC')
depends=('ncurses')
makedepends=('libao' 'libpulse' 'libid3tag' 'libmad' 'wavpack')
optdepends=('libao: audio output support'
            'libpulse: pulseaudio support'
            'libid3tag: id3 tags support'
            'libmad: mpeg decoder support'
            'wavpack: wav decoder support')
source=(${url}dist/${pkgname}-${pkgver}.tar.gz)
md5sums=('b033eb6b7a1f7f7970ff571cac194361')

build() {
  cd $pkgname-$pkgver
  ./configure prefix=/usr \
              mandir=/usr/share/man
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir/" install

  # license
  install -d "$pkgdir/usr/share/licenses/$pkgname"
  head -n15 $pkgname.h > \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
