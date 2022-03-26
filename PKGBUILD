# Maintainer: Alexander Sowitzki <dev@eqrx.net>
pkgname=wgpeer
pkgdesc='Dynamic endpoint manager for WireGuard'
pkgver=0.0.5
pkgrel=1
arch=('x86_64' 'aarch64')
url="https://eqrx.net/$pkgname"
license=('AGPL3')
makedepends=('go')
source=("$pkgname-$pkgver.tar.gz::https://github.com/eqrx/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha512sums=('8e0e6097e69b5ad1965ce08a62f7df0b5b1fee7d19644e502fc30e3b0a7b19a7edcbcb1e001a4bdda08b99f3da6be3116f7e81ece7b6ea9c662c937eb846d009')

build() {
  cd "$pkgname-$pkgver"
  ./build.sh
}

package() {
  cd "$pkgname-$pkgver"
  install -Dm644 init/$pkgname.service "$pkgdir"/usr/lib/systemd/system/$pkgname.service
  install -Dm755 bin/$pkgname "$pkgdir"/usr/bin/$pkgname
}
