pkgname=photoqt
pkgver=1.7
pkgrel=1
pkgdesc="Fast and highly configurable image viewer with a simple and nice interface."
arch=('x86_64')
url="http://photoqt.org/"
license=('GPL2')
depends=('exiv2' 'graphicsmagick' 'qt5-imageformats' 'qt5-multimedia' 'qt5-svg' 'qt5-quickcontrols' 'libraw' 'qt5-graphicaleffects' 'hicolor-icon-theme' 'poppler-qt5' 'libarchive' 'kimageformats')
makedepends=('cmake' 'qt5-tools' 'extra-cmake-modules')
optdepends=('libqpsd-git: PSB/PSD support'
            'xcftools: for gimp xcf files support')
source=(http://photoqt.org/pkgs/$pkgname-$pkgver.tar.gz)
sha512sums=('abce55f103f97c80fb5fcf76a63d20aab034964218ae84dd9890fbda132a3d0f9b8e82d5919498625e724c08916ba38b5f8a9ebc0b4a16f52f6fffc186b3e156')

prepare() {
  cd $srcdir/$pkgname-$pkgver

  # If you want to build PhotoQt with less features(without exiv2 and graphicsmagick), add (-DEXIV2=OFF -DGM=OFF) to next line.
  cmake . -DCMAKE_INSTALL_PREFIX=/usr -DFREEIMAGE=OFF -DDEVIL=OFF    
}

build() {
  cd $srcdir/$pkgname-$pkgver
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}
