# Maintainer: Philip Müller <philm[at]manjaro[dot]org>
# Maintainer: Bernhard Landauer <bernhard[at]manjaro[dot]org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=manjaro-keyring
pkgver=20230719
pkgrel=3
pkgdesc="Manjaro PGP keyring"
arch=('any')
url="https://gitlab.manjaro.org/packages/core/manjaro-keyring"
license=('GPL-3.0-or-later')
depends=('pacman')
install="${pkgname}.install"
source=('Makefile'
        'manjaro.gpg'
        'manjaro-revoked'
        'manjaro-trusted')
sha256sums=('b00e0304982253e15dc9ee076bd1c795585f1a1028112658a5d2c9f773c4d187'
            'c910ef777b26bd49a91b74e0b85eac9b795ca77de9b8776e7f1f460db1b01ac5'
            '3e909acd91874ea0b0dc7655f8ab549a2ea4cbae5ab6a19b08f71a654a728932'
            'ff6f35edd535703cd8e62adfb4b03e79005a04230da76d7ea8c394bb74bce4c6')

pkgver() {
  date +%Y%m%d
}

package() {
  make DESTDIR="${pkgdir}" install
}
