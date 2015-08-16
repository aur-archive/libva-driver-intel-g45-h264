# Maintainer : Pedro Martinez-Julia <pedromj@um.es>
# Contributor : Alois Nešpor info@aloisnespor.info
# Contributor : Anugrah Redja Kusuma <anugrah.redja@gmail.com>
# Contributor : Vincent B. <vbmithr@gmail.com>

pkgname=libva-driver-intel-g45-h264
pkgver=20140512
pkgrel=1
pkgdesc="VA-API implementation for Intel G45 chipsets with H264 support."
arch=('i686' 'x86_64')
url="http://freedesktop.org/wiki/Software/vaapi"
license=('MIT')
makedepends=('automake' 'libtool' 'python2')
depends=('libva')
options=('!libtool')
conflicts=('libva-intel-driver')
provides=('libva-intel-driver')
replaces=('libva-intel-driver')
source=(https://downloads.sourceforge.net/project/g45h264/intel-driver-g45-h264-$pkgver.tar.gz)
sha256sums=('389845265ea6bc8935f2087e53d8104a679c8f0a9811f615745ccb3e37cc45ff')

build () {
    cd "$srcdir"/intel-driver-g45-h264
    ./autogen.sh --prefix=/usr
    sed -i 's|/usr/bin/env python|/usr/bin/env python2|' src/shaders/gpp.py
    make
}

package () {
    cd ${srcdir}/intel-driver-g45-h264
    make DESTDIR="${pkgdir}" install
    install -m644 -D COPYING ${pkgdir}/usr/share/licenses/${pkgname}/COPYING
}
