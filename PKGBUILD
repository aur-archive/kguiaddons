# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kguiaddons
pkgver=4.99.0
pkgrel=2
pkgdesc='KGuiAddons'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kguiaddons'
license=('LGPL')
depends=('qt5-x11extras')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('203900cb056e428305ccd9bac635174d')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
