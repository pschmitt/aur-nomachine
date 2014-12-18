# Contributor: olav-st <olav.s.th@gmail.com>
# Maintainer: Philipp Schmitt <philipp@schmitt.co>

pkgname=nomachine
pkgver=4.4.1
_pkgver="${pkgver}_1"
pkgrel=1
pkgdesc="Remote desktop application"
url="http://www.nomachine.com"
license=('custom:"Copyright 2002-2014 NoMachine S.à r.l."')
arch=('x86_64' 'i686')
options=('!strip')
conflicts=('nxmanager nxwebplayer nxserver nxnode nxclient')
install=nomachine.install

if [ "${CARCH}" = "x86_64" ]; then
    md5sums=('f8059079c371753a70ad3012564552ad')
    _carch=_x86_64
elif [ "${CARCH}" = "i686" ]; then
    md5sums=('cbf13999144a166bf8b630ccbb1326b5')
    _carch=_i686
fi

source=("http://download.nomachine.com/download/4.4/Linux/${pkgname}_${_pkgver}${_carch}.tar.gz")

package() {
    cd "${srcdir}"
    install -d "${pkgdir}/usr/"
    cp -a NX "${pkgdir}/usr/NX"
}
