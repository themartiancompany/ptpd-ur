# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Contributor: Matthew McGinn <mamcgi@gmail.com>

_pkg=ptpd
pkgname="${_pkg}"
pkgver=2.3.1
pkgrel=2
_pkgdesc=(
  "The PTP daemon (PTPd) implements the Precision Time protocol (PTP)"
  "as defined by the relevant IEEE 1588 standard."
  "PTP Version 2 implements IEEE-1588-2008."
  "PTP was developed to provide very precise time coordination of LAN connected computers."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://github.com/${_pkg}/${_pkg}"
license=(
  'BSD'
)
depends=(
  'libpcap'
)
optdepends=(
  'net-snmp'
)
provides=(
)
_sf="http://sourceforge.net/projects/${_pkg}"
source=(
  "${_pkg}-${pkgver}.tar.gz::${_sf}/files/${_pkg}/${pkgver}/${_pkg}-${pkgver}.tar.gz/download"
)
md5sums=(
  '253bab7ab51d969616ea811be1f132f3'
)
sha256sums=(
  '0dbf54dd2c178bd9fe62481d2c37513ee36636d8bf137cfdad96891490cdbf93'
)

prepare() {
  cd \
    "${pkgname}-${pkgver}"
}

build() {
  local \
    _opts=()
  _opts=(
    --prefix=/usr
    --sbindir=/usr/bin
  )
  cd \
    "${pkgname}-${pkgver}"
  ./configure \
    "${_opts[@]}"
  make
}

check() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    -k \
    check
}

package() {
  cd \
    "${pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

