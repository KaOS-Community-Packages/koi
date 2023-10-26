pkgname='koi'
_pkgname='Koi'
pkgver=0.2.3
_pkgver=master
pkgrel=1
pkgdesc="Scheduled LIGHT/DARK Theme Switching for the KDE Plasma Desktop"
arch=('x86_64')
url="https://github.com/baduhai/Koi"
license=('LGPL3')
depends=('plasma-desktop' 'plasma-integration' 'plasma-framework' 'kcoreaddons'
         'kwidgetsaddons' 'kconfig' 'kconfigwidgets' 'kpackage' 'hicolor-icon-theme')
makedepends=('glibc' 'qt5-base' 'qt5-svg' 'qt5-svg' 'cmake' 'extra-cmake-modules')
optdepends=('desktop-file-utils: Command line utilities for working with desktop entries'
            'xsettingsd: Apply settings to GTK applications on the fly')
source=(${_pkgname}-${_version}.tar.gz::"https://github.com/baduhai/Koi/archive/refs/heads/master.tar.gz")
sha256sums=('SKIP')

build() {
	cd "${_pkgname}-${_pkgver}/src"
    mkdir -p build && cd build

    cmake \
    -DCMAKE_INSTALL_PREFIX=/usr \
    ..

    make all
}

package() {
    cd "${_pkgname}-${_pkgver}/src/build"
    make DESTDIR="${pkgdir}" install all
}
