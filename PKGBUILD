# Maintainer: Reinier Hernández <me@reinierhernandez.com>
pkgname=whereami
pkgver=0.1
pkgrel=1
pkgdesc="A simple utility to determine the location of a system using WiFi signals"
arch=('any')
url=https://github.com/ragnarok22/whereami
license=('GPL-3.0-or-later')
groups=()
depends=('curl' 'jq')
optdepends=('xclip: Copy location to clipboard')
install=
changelog=
source=("whereami")
noextract=()
sha256sums=()
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver"
  echo "Checking dependencies..."
  if ! command -v curl &> /dev/null; then
    echo "Error: 'curl' is not installed. Please install it before proceeding."
    exit 1
  fi
}

check() {
	cd "$pkgname-$pkgver"
	# make -k check
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
  install -Dm755 whereami "$pkgdir/usr/bin/whereami"
}
