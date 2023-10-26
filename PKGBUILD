# Maintainer:   fft
# Contributor: redtide <redtid3 at gmail com>
# Contributor: dllud <dllud riseup net>
# Contributor: David McInnis <dave@dave3.xyz>
# Contributor: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Angel 'angvp' Velasquez <angvp[at]archlinux.com.ve>
# Contributor: djgera
# Contributor: Patrick Melo <patrick@patrickmelo.eti.br>

pkgname=geany-plugin-markdown
_downloadname=geany-plugins
pkgver=2.0
pkgrel=1
pkgdesc='Markdown plugin for Geany'
arch=('x86_64')
url='https://plugins.geany.org/'
license=('GPL')
depends=("geany>=$pkgver" 'webkit2gtk')
makedepends=('intltool')
#makedepends=('intltool' 'vala' 'gdb' 'cppcheck')
source=("https://plugins.geany.org/$_downloadname/$_downloadname-$pkgver.tar.bz2")
sha256sums=('9fc2ec5c99a74678fb9e8cdfbd245d3e2061a448d70fd110a6aefb62dd514705')
conflicts=('geany-plugins')

build() {
  cd "$_downloadname-$pkgver"

  ./configure --prefix=/usr --libexecdir=/usr/lib \
              --disable-all-plugins --enable-markdown
  make -C markdown
}

package() {
  make -C "$_downloadname-$pkgver/markdown" DESTDIR="$pkgdir" install
}

