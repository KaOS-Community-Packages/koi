pkgname=koi
_pkgname=Koi
pkgver=0.2.3
pkgrel=2
pkgdesc='Switch between light and dark themes on KDE Plasma'
arch=('x86_64')
url='https://github.com/baduhai/Koi'
license=('LGPL3')
depends=('plasma-desktop' 'kconfig' 'kcoreaddons' 'kwidgetsaddons')
makedepends=('qt5-base')
source=("https://github.com/baduhai/Koi/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('811f6bdaa8146f0da6103742816cc48f571d344d2cd8cd9ac2448ca518825e32')

build() {
    cd "$_pkgname-$pkgver/src"
    mkdir -p build && cd build

    cmake \
      -DCMAKE_INSTALL_PREFIX=/usr \
      ..

    make
}

package() {
    cd "$_pkgname-$pkgver/src/build"
    make DESTDIR="${pkgdir}" install
}
