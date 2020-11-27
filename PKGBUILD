# Maintainer: Benjamin Vialle <archlinux@vialle.io>
# PGP ID: 72DF86FBBBBD5EDAE8FF1834826884A347F9FD9A

pkgname=man-pages-fr
pkgver=4.2.0
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
sha512sums=('9f9d3153b512c7fb0dbc3916d3b049e8b30fc00a9d6f5bef9e2e2f645f8af8c2344f0e215a80f5da67e6cba9f80193b7c425f39925112579bde8c9e69756645c')

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
