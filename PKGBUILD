# Maintainer: Charles Bos <charlesbos1 AT gmail>
# Contributor: Xiao-Long Chen <chenxiaolong@cxl.epac.to>

pkgname=unity-scope-home
_actual_ver=6.8.2
_extra_ver=+14.04.20131029.1
_source_date=20131029
pkgver=${_actual_ver}.${_source_date}
pkgrel=2
pkgdesc="Home scope that aggregates results from multiple scopes"
arch=('i686' 'x86_64')
url="https://launchpad.net/unity-scope-home"
license=('GPL')
groups=('unity')
depends=('dee' 'glib2' 'json-glib' 'libgee06' 'libsoup' 'libunity' 'lsb-release')
makedepends=('gnome-common' 'intltool' 'vala')
source=("https://launchpad.net/ubuntu/+archive/primary/+files/unity-scope-home_${_actual_ver}${_extra_ver}.orig.tar.gz")
sha512sums=('8f94915f4a3f4c70ac244e7974d000626805b2a4217abeed28b2137cce4e7c6c5ed2836b723a6b2e9b7f6fe3cf95cdd151e9c5bac577c3989e10d1367a5aa772')

build() {
  cd "${srcdir}/${pkgname}-${_actual_ver}${_extra_ver}"
  autoreconf -vfi
  intltoolize -f
  ./configure --prefix=/usr --libexecdir=/usr/lib/unity-scope-home
  make
}

package() {
  cd "${srcdir}/${pkgname}-${_actual_ver}${_extra_ver}"
  make DESTDIR="${pkgdir}/" install
}
