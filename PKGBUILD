# Maintainer: olav-st <olav.s.th@gmail.com>

pkgname=nomachine
pkgver=4.2.25
pkgrel=1
pkgdesc="Remote desktop application"
url="http://www.nomachine.com"
license=('custom:"Copyright 2002-2014 NoMachine S.à r.l."')
arch=('x86_64' 'i686')
options=('!strip')
conflicts=('nxmanager nxwebplayer nxserver nxnode nxclient')
install=nomachine.install

if [ "${CARCH}" = "x86_64" ]; then
  md5sums=('ca83243d5d423d1ca0d561f0e3188adf')
  _carch=_x86_64
elif [ "${CARCH}" = "i686" ]; then
  md5sums=('2027ffed6d41e8dd735ebd062ffe9d12')
  _carch=_i686
fi
source=("http://download.nomachine.com/download/4.2/Linux/${pkgname}_${pkgver}_${pkgrel}${_carch}.tar.gz")

package()
{
  cd "${srcdir}"

  install -d "${pkgdir}/usr/"
  cp -a NX "${pkgdir}/usr/NX"
}
