pkgname='koi'
_pkgname='Koi'
pkgver=0.2.4
pkgrel=2
pkgdesc="Scheduled LIGHT/DARK Theme Switching for the KDE Plasma Desktop"
arch=('x86_64')
url="https://github.com/baduhai/Koi"
license=('LGPL3')
depends=('plasma-desktop' 'plasma-integration' 'plasma-framework' 'kcoreaddons'
         'kwidgetsaddons' 'kconfig' 'kconfigwidgets' 'kpackage' 'hicolor-icon-theme')
makedepends=('glibc' 'qt5-base' 'qt5-svg' 'qt5-svg' 'cmake' 'extra-cmake-modules')
optdepends=('desktop-file-utils: Command line utilities for working with desktop entries'
            'xsettingsd: Apply settings to GTK applications on the fly')
source=(${_pkgname}-${version}.tar.gz::"https://github.com/baduhai/Koi/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('SKIP')

build() {
    mkdir -p "${srcdir}/${_pkgname}-${pkgver}/src/build/"

    cmake -S "${srcdir}/${_pkgname}-${pkgver}/src/" \
          -B "${srcdir}/${_pkgname}-${pkgver}/src/build/" \
          -DCMAKE_INSTALL_PREFIX=/usr/

    cd "${srcdir}/${_pkgname}-${pkgver}/src/build/"

    make all
}

package() {
    cd "${srcdir}/${_pkgname}-${pkgver}/src/build/"

    make DESTDIR="${pkgdir}" install all

    install -Dm644 "${srcdir}/${_pkgname}-${pkgver}/src/koi.desktop" -t "${pkgdir}/usr/share/applications/"
