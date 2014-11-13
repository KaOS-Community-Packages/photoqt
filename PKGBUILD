pkgname=photoqt
pkgver=1.1.0.1
pkgrel=1
pkgdesc="Fast and highly configurable image viewer with a simple and nice interface."
arch=('x86_64')
url="http://photoqt.org/"
license=('GPL2')
depends=('exiv2' 'graphicsmagick' 'qt5-imageformats' 'qt5-multimedia')
makedepends=('cmake' 'qt5-tools')
install=$pkgname.install
source=(http://photoqt.org/pkgs/$pkgname-$pkgver.tar.gz)
md5sums=('f7e2f2898eb7b898a7302344df456276')

build() {
  cd $srcdir/$pkgname-$pkgver

  # Fix Build Type(Debug -> release)
  sed -i 's|Debug|release|' CMakeLists.txt

  # If you want to build PhotoQt with less features(without exiv2 and graphicsmagick), add (-DEXIV2=OFF -DGM=OFF) to next line.
  cmake . -DCMAKE_INSTALL_PREFIX=/usr       
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}
