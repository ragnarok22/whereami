# Maintainer: Reinier Hernández <me@reinierhernandez.com>
pkgname=whatismyip
pkgver=0.1
pkgrel=1
epoch=1
pkgdesc="A simple utility to determine the location of a system using WiFi signals"
arch=('any')
url=https://github.com/ragnarok22/whereami
license=('GPL-3.0-or-later')
groups=()
depends=('curl' 'jq')
optdepends=('xclip: Copy location to clipboard')
source=("whereami")
sha256sums=('f1befd87b8b07f5d32a9800c2541521352c1ce49f2cd8b66672e186ebd4ecc76')

prepare() {
  echo "Checking dependencies..."
  if ! command -v curl &> /dev/null; then
    echo "Error: 'curl' is not installed. Please install it before proceeding."
    exit 1
  fi
}

check() {
  echo "checking..."
	# make -k check
}

package() {
	make DESTDIR="$pkgdir/" install
  install -Dm755 whereami "$pkgdir/usr/bin/whatismyip"
}
