# Maintainer: Philipp Schmitt <philipp@schmitt.co>
# Contributor: olav-st <olav.s.th@gmail.com>

pkgname=nomachine
pkgver=4.4.1
_pkgver="${pkgver}_1"
pkgrel=2
pkgdesc='Remote desktop application'
url='http://www.nomachine.com'
license=('custom:"Copyright 2002-2014 NoMachine S.à r.l."')
arch=('x86_64' 'i686')
options=('!strip')
conflicts=('nxmanager nxwebplayer nxserver nxnode nxclient')
install=nomachine.install
sha256sums=(
    '3eca94237f350db1890d2feef097e0a8399109d5a431db09bbefd3483073d83e'
    'c3987ad7d12d2155e873028fe254b678c073e116fcaeff1565cefc1338915b00'
    '3b82587a58d77ae9560a8f2cbe942bd522b2dded8caf3aac2194946168eeb7e5'
)

if [ "${CARCH}" = 'x86_64' ]; then
    sha256sums+=('15da8203ceaf6634a8d783783c5986202987236e3cce95f57532052e7ce8b06f')
elif [ "${CARCH}" = 'i686' ]; then
    sha256sums+=('5b8ef07dae1899b165777719b4d7a99f575a6e917864e1eb2d13bad1eea6041a')
fi

source=(
    'https://raw.github.com/pschmitt/aur-nomachine/master/nomachine.LICENSE'
    'https://raw.github.com/pschmitt/aur-nomachine/master/nxsensor.service'
    'https://raw.github.com/pschmitt/aur-nomachine/master/nxserver.service'
    "http://download.nomachine.com/download/4.4/Linux/${pkgname}_${_pkgver}_${CARCH}.tar.gz"
)

package() {
    cd "${srcdir}"
    # Install nomachine files
    install -d "${pkgdir}/usr/"
    # TODO: Install to a more standard path (/opt maybe?)
    cp -a NX "${pkgdir}/usr/NX"
    # Install license
    install -D nomachine.LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    # Install service files
    install -D nxsensor.service "${pkgdir}/usr/lib/systemd/system/nxsensor.service"
    install -D nxserver.service "${pkgdir}/usr/lib/systemd/system/nxserver.service"
}
