# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=baloo-frameworks
pkgver=5.1.0.1
pkgrel=1
pkgdesc="A framework for searching and managing metadata"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/kdelibs/baloo'
license=('LGPL')
depends=('xapian-core' 'kfilemetadata5' 'kidletime' 'kcmutils' 'kdelibs4support')
makedepends=('extra-cmake-modules' 'kdoctools' 'python')
conflicts=('baloo4')
provides=('baloo')
source=("http://download.kde.org/stable/plasma/5.1.0/baloo-$pkgver.tar.xz")
md5sums=('eaa814bfc28416ffd6ab87c20fa87e26')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../baloo-5.1.0 \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DSYSCONF_INSTALL_DIR=/etc \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
