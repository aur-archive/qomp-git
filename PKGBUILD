# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=qomp-git
pkgver=475.2c4858c
pkgrel=1
pkgdesc="Quick(Qt) Online Music Player for different online music hostings."
arch=('i686' 'x86_64')
url="http://qomp.sourceforge.net"
license=('GPL2')
depends=('hicolor-icon-theme' 'taglib' 'qt5-multimedia')
makedepends=('cmake' 'git' 'qt5-tools')
conflicts=('qomp' 'qomp-qt5-git')
source=('git+https://github.com/qomp/qomp')
md5sums=('SKIP')

prepare() {
  cd $srcdir/qomp
  git submodule init
  git submodule update

  cmake -DCMAKE_INSTALL_PREFIX=/usr -DUSE_QT5=ON -DCMAKE_BUILD_TYPE=Release
}

build() {
  cd $srcdir/qomp
  make
}

package() {
  cd $srcdir/qomp
  make DESTDIR=$pkgdir install
}

pkgver() {
  cd $srcdir/qomp
  echo $(git rev-list --count master).$(git rev-parse --short master)
}