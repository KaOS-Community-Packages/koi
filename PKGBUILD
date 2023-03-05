pkgname=koi
_pkgname=Koi
pkgver=0.3
pkgrel=1
pkgdesc='Switch between light and dark themes on KDE Plasma'
arch=('x86_64')
url='https://github.com/baduhai/Koi'
license=('LGPL3')
depends=('plasma-desktop' 'kcoreaddons' 'kwidgetsaddons' 'kconfig' 'kconfigwidgets' 'kpackage' 'xsettingsd' 'hicolor-icon-theme')
makedepends=('qt5-base' 'cmake' 'extra-cmake-modules')
source=("https://github.com/MartinVonReichenberg/Koi/archive/refs/heads/master.tar.gz")
sha256sums=('SKIP')

build() {
    cd "$_pkgname-master/src"
    mkdir -p build && cd build

    cmake \
      -DCMAKE_INSTALL_PREFIX=/usr \
      ..

    make
}

package() {
    cd "$_pkgname-master/src/build"
    make DESTDIR="$pkgdir" install
}
