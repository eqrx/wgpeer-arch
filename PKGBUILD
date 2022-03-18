# Maintainer: Alexander Sowitzki <dev@eqrx.net>
pkgname=wgpeer
pkgdesc='Dynamic endpoint manager for WireGuard'
pkgver=0.0.4
pkgrel=1
arch=('x86_64' 'aarch64')
url="https://eqrx.net/$pkgname"
license=('AGPL3')
makedepends=('go')
source=("$pkgname-$pkgver.tar.gz::https://github.com/eqrx/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha512sums=('45e7df15dc1dffed086c0ead7b9db79fc2e364c708ba352b9510e1685e74e1554540a7f94b56e0c53e5844135c05bd9097ba5e725513b9d2e31f5e798e452370')

build() {
  cd "$pkgname-$pkgver"
  ./build.sh
}

package() {
  cd "$pkgname-$pkgver"
  install -Dm644 init/$pkgname.service "$pkgdir"/usr/lib/systemd/system/$pkgname.service
  install -Dm755 bin/$pkgname "$pkgdir"/usr/bin/$pkgname
}
