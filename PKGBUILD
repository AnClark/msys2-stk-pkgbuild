# Maintainer: AnClark Liu <clarklaw4701@gmail.com>

pkgbase=stk
pkgname=mingw-w64-x86_64-${pkgbase}
pkgver=4.6.1
pkgext=
pkgrel=1
pkgdesc='Synthesis Toolkit - a set of open source audio signal processing and algorithmic synthesis classes'
arch=('x86_64')
url='https://ccrma.stanford.edu/software/stk/'
license=('LGPL3')
depends=()
makedepends=('mingw-w64-x86_64-gcc' 'bash' 'make' 'grep')
conflicts=()
groups=()
source=("http://ccrma.stanford.edu/software/stk/release/stk-${pkgver}.tar.gz")
sha512sums=('SKIP')

prepare() {
  cd "stk-${pkgver}"

  ./configure --build=x86_64-w64-mingw32 --host=x86_64-w64-mingw32
}

build() {
  cd "stk-${pkgver}"
  make -j$(grep -c processor /proc/cpuinfo)
}

package() {
  cd "stk-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
