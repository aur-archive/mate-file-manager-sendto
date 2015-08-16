# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-file-manager-sendto
pkgver=1.6.0
pkgrel=4
pkgdesc="A Caja extension for sending files."
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('dbus' 'gupnp' 'gtk2' 'mate-file-manager')
makedepends=('mate-common' 'perl-xml-parser')
optdepends=('pidgin: Support for sending to instant messaging networks.'
            'gajim: Support for sending to Jabber.'
            'mate-bluetooth: Support for sending to bluetooth.')
options=('!emptydirs')
groups=('mate-extra')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('cf81a12d6d5d90f431d96fd67eed893f472b36f0')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./autogen.sh \
        --prefix=/usr \
        --with-plugins=gajim,pidgin,removable-devices,upnp,emailclient
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
