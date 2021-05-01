# Maintainer: Benjamin Vialle <archlinux@vialle.io>
# PGP ID: 72DF86FBBBBD5EDAE8FF1834826884A347F9FD9A

pkgname=man-pages-fr
pkgver=4.9.3
pkgrel=1
pkgdesc="French man pages"
arch=('any')
url="https://salsa.debian.org/manpages-l10n-team/manpages-l10n"
license=('GPL3')
conflicts=('man-pages-fr-git' 'man-pages-pacman-fr')
depends=('man-db')
makedepends=('po4a')
changelog=$pkgname.changelog
options=('!emptydirs')
source=(https://salsa.debian.org/manpages-l10n-team/manpages-l10n/-/archive/v$pkgver/manpages-fr-l10n-v${pkgver}.tar.bz2)
sha512sums=('e2744ffde55f50030296930d66c72727e7ea588a43ffc286749bd67a8d7f701d49a9282b0339d2ab4de767b2a5062073f85b6bc2a736c765969ce35a9dbaada0')

build() {
  cd "${srcdir}"/manpages-l10n-v4.1.0-39f19d6149a9393655cbdb35202410ae750e1e90
  ./configure --prefix=/usr --enable-distribution=archlinux
  
  cd po/fr
  make
}

package() {
  cd "${srcdir}"/manpages-l10n-v4.1.0-39f19d6149a9393655cbdb35202410ae750e1e90/po/fr

  make DESTDIR="${pkgdir}" install
}
