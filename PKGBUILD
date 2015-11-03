pkgname=photoqt
pkgver=1.3
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
sha512sums=('6fdc0c00449519304e0e0da09cabee6f096100ce8054213ca48f5093629328b5f2b6d45215edbbf5419e34189b456eac1389b561840077b3b8320461a1591762')

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
