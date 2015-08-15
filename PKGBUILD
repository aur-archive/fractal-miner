# Maintainer: Rikard Falkeborn <rikard.falkeborn@gmail.com>
# Constributor: moostik <mooostik_at_gmail.com>

pkgname=fractal-miner
pkgver=0.3.4
pkgrel=4
pkgdesc="An interactive multithreaded fractal renderer written in C++ using QT4 and OpenGL"
url='http://xwmw.org/fractal-miner/'
license=('GPL3')
arch=('i686' 'x86_64')
depends=('qt4' 'boost' 'libxml2' 'freeglut')
makedepends=('cmake')
source=("http://downloads.sourceforge.net/sourceforge/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.gz"
	"${pkgname}.desktop")
md5sums=('4f43c8db790764b3e1ed7b1fe81cb124'
         'e052ecbe314b26c020b2408afb612427')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  cmake .. -DCMAKE_CXX_LINK_FLAGS="-lglut -lGL -lboost_system -pthread" -DCMAKE_INSTALL_PREFIX="$pkgdir/usr"
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  make install
  install -D -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
