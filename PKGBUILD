# Downstream: manjaro-contrib
#
# Adds the manjaro-contrib build server key to the keyring and the trusted
# list, so a client that installs this package accepts packages we sign
# without importing a key by hand.
#
#   E8AAE31963A022B8480CC007A13A52A61B5D8836
#   manjaro-contrib build server <feedback@manjaro.download>
#
# `make update` re-fetches every trusted key from a keyserver and would
# drop ours, which is not published to one. Re-run it only together with
# re-appending gpg-public-key.asc from manjaro-contrib/packages.
#
# pkgver() upstream returns `date +%Y%m%d`, so each rebuild produced a
# differently-versioned package regardless of content. Pinned instead, and
# pkgrel carries our change.

# Maintainer: Philip Müller <philm[at]manjaro[dot]org>
# Contributor: Bernhard Landauer <bernhard[at]manjaro[dot]org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=manjaro-keyring
pkgver=20251003
pkgrel=2
pkgdesc="Manjaro PGP keyring, plus the manjaro-contrib build server key"
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
            'b4d5448c761ed6bbc755bb7a194293be05cadbb4e487b090ecbe855e6153000d'
            'af2081cc55ba21ec22226660fc8079f190ea7442008fe45d5de682860721972b'
            '8e76411b761a99b55c5ff0d15d7ca9375c2237848c85bf83d71fc89858558b83')

package() {
  make DESTDIR="${pkgdir}" install
}
