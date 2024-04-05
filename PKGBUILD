pkgname='koi'
_pkgname='Koi'
pkgver=0.2.4
pkgrel=3
pkgdesc="Scheduled LIGHT/DARK Theme Switching for the KDE Plasma Desktop"
arch=('x86_64')
url="https://github.com/baduhai/Koi"
license=('LGPL3')
depends=('plasma-desktop' 'plasma-integration' 'libplasma' 'kcoreaddons'
         'kwidgetsaddons' 'kconfig' 'kconfigwidgets' 'kpackage' 'hicolor-icon-theme')
makedepends=('glibc' 'qt5-base' 'qt5-svg' 'qt5-svg' 'cmake' 'extra-cmake-modules')
optdepends=('xsettingsd: Apply settings to GTK applications on the fly')
source=("${_pkgname}-${version}.tar.gz::https://github.com/baduhai/Koi/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('SKIP')

prepare() {
    mkdir -p "${srcdir}/${_pkgname}-${pkgver}/src/build/"
}

build() {
    cmake -S "${srcdir}/${_pkgname}-${pkgver}/src/" \
          -B "${srcdir}/${_pkgname}-${pkgver}/src/build/" \
          -DCMAKE_INSTALL_PREFIX=/usr/

    make -C "${srcdir}/${_pkgname}-${pkgver}/src/build/" all
}

package() {
    make -C "${srcdir}/${_pkgname}-${pkgver}/src/build/" DESTDIR="${pkgdir}" install

    install -Dm644 "${srcdir}/${_pkgname}-${pkgver}/src/koi.desktop" -t "${pkgdir}/usr/share/applications/"
}
