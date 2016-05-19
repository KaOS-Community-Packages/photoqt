pkgname=photoqt
pkgver=1.4
pkgrel=1
pkgdesc="Fast and highly configurable image viewer with a simple and nice interface."
arch=('x86_64')
url="http://photoqt.org/"
license=('GPL2')
depends=('exiv2' 'graphicsmagick' 'qt5-imageformats' 'qt5-multimedia')
makedepends=('cmake' 'qt5-tools')
optdepends=('xcftools: for gimp xcf files support')
install=$pkgname.install
source=(http://photoqt.org/pkgs/$pkgname-$pkgver.tar.gz)
sha512sums=('6f8e8caafa9edc4c7ec9892d763ad38251ecda964df6fef731ef2ba55c1f56b7b225ba74aebc09720dec2f9a5fa115978d301a5eb5153fa65895f9bd9685f79b')

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
