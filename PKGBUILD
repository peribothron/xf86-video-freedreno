#Maintainer: tbd

pkgname=xf86-video-freedreno
pkgver=1.3.0
pkgrel=1
pkgdesc="X.org driver for Adreno mobile GPUs"
arch=('armv7h')
url="http://cgit.freedesktop.org/xorg/driver/${pkgname}"
license=('custom')
depends=('glibc')
makedepends=('xorg-server-devel' 'X-ABI-VIDEODRV_VERSION=19')
conflicts=('xorg-server<1.16' 'X-ABI-VIDEODRV_VERSION<19' 'X-ABI-VIDEODRV_VERSION>=20')
groups=('xorg-drivers' 'xorg')
source=(http://ftp.x.org/pub/individual/driver/${pkgname}-${pkgver}.tar.bz2{,.sig})
sha256sums=('1c9d872d1e7389c7771c33e0070f6eb730c406511afcda63867b096aa3d9301d'
            '444e80427e1e326a85bc5eb1355a2f0aac607934cd0eef2ea31b2569e5eb6fa3')

build() {
  cd ${pkgname}-${pkgver}
  ##./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
  #install -d -m755 "${pkgdir}/usr/share/licenses/${pkgname}"
  #install -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/"
  
}
