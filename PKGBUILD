pkgname=koi
_pkgname=Koi
pkgver=0.3
pkgrel=1
pkgdesc='Switch between light and dark themes on KDE Plasma'
arch=('x86_64')
url='https://github.com/baduhai/Koi'
license=('LGPL3')
depends=('plasma-desktop' 'kcoreaddons6' 'kwidgetsaddons6' 'kconfig6' 'kconfigwidgets6' 'kpackage6' 'xsettingsd' 'hicolor-icon-theme')
makedepends=('qt6-base' 'cmake' 'extra-cmake-modules')
source=("https://github.com/baduhai/${_pkgname}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('de3929c128920fb45050907485d17e3a90250ac97c11fabda0f3d8c8ca0f5ad9')

build() {
    cd "${_pkgname}-${pkgver}/src"
    mkdir -p build && cd build

    cmake \
      -DCMAKE_INSTALL_PREFIX=/usr \
      ..

    make
}

package() {
    cd "${_pkgname}-${pkgver}/src/build"
    make DESTDIR="$pkgdir" install
}
