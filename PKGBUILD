pkgname=photoqt
pkgver=2.2
pkgrel=1
pkgdesc="Fast and highly configurable image viewer with a simple and nice interface."
arch=('x86_64')
url="http://photoqt.org/"
license=('GPL2')
depends=('exiv2' 'graphicsmagick' 'qt5-imageformats' 'qt5-multimedia' 'qt5-svg' 'qt5-quickcontrols' 'libraw' 'qt5-graphicaleffects' 'hicolor-icon-theme' 'libarchive' 'kimageformats' 'poppler' 'pugixml')
makedepends=('cmake' 'qt5-tools' 'extra-cmake-modules')
source=(http://photoqt.org/pkgs/$pkgname-$pkgver.tar.gz)
md5sums=('8668813df93b458de6e7fa635d11e2ce')

build() {
    cd ${srcdir}/${pkgname}-${pkgver}
    cmake . -DCMAKE_INSTALL_PREFIX=/usr -DFREEIMAGE=OFF -DDEVIL=OFF
}

package() {
    cd ${srcdir}/${pkgname}-${pkgver}
    make DESTDIR=$pkgdir install
}
