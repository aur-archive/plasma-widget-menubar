# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: György Balló <ballogy@freestart.hu>

pkgname=plasma-widget-menubar
pkgver=0.1.18
pkgrel=1
pkgdesc="A Plasma widget to display menubar of application windows"
arch=('i686' 'x86_64')
url='https://launchpad.net/plasma-widget-menubar'
license=('GPL')
depends=('kdelibs' 'qjson')
makedepends=('cmake' 'automoc4')
optdepends=('appmenu-gtk2: support for GTK+ 2 apps'
            'appmenu-gtk3: support for GTK+ 3 apps'
            'appmenu-qt: support for Qt apps'
            'libreoffice-extension-menubar: support for LibreOffice')
source=("https://launchpad.net/$pkgname/trunk/$pkgver/+download/$pkgname-$pkgver.tar.bz2"{,.asc})
md5sums=('37055ea768d561e8ba7acc1e2ce3502e'
         '877e54b39f140a5d05071c8e49b62fda')

build() {
  cd "${srcdir}"
  mkdir build
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "${srcdir}"/build
  make DESTDIR="${pkgdir}" install
}
