# Maintainer: Benjamin Hodgetts <ben@xnode.org>

pkgname=vice-svn
pkgver=r37523
pkgrel=1
pkgdesc="The Versatile Commodore Emulator (Commodore 64/C64)."
arch=('i686' 'x86_64')
url="http://vice-emu.sourceforge.net"
license=('GPL')
depends=('giflib' 'lame' 'libjpeg' 'libpng' 'libxrandr' 'libnet' 'libpcap' 'xdialog')
makedepends=('xorg-font-utils' 'pkg-config')
optdepends=('pulseaudio' 'pulseaudio-alsa' 'alsa-lib')
provides=('vice')
replaces=('vice')
source=("${pkgname}::svn://svn.code.sf.net/p/vice-emu/code/trunk")
md5sums=('SKIP')

pkgver() {
	echo r$(svnversion "${SRCDEST}"/${pkgname}/)
}

build() {
	cd "${pkgname}/vice"
	./autogen.sh
	./configure --prefix=/usr --without-oss --without-alsa --enable-native-gtk3ui
	make
}

package() {
	cd "${pkgname}/vice"
	make install DESTDIR="${pkgdir}/"
}
