# Maintainer: Alexander Sowitzki <dev@eqrx.net>
pkgname=wgpeer
pkgdesc='Dynamic endpoint manager for WireGuard'
pkgver=0.0.2
pkgrel=2
arch=('x86_64' 'aarch64')
url="https://dev.eqrx.net/$pkgname"
license=('AGPL3')
makedepends=('go')
source=("$pkgname-$pkgver.tar.gz::https://github.com/eqrx/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha512sums=('ed8f30f7e7fb48e80a80a1af14a3c14861e9eccb27e0b7419267b77f508df33db5a4a218b40bf39fe19190e61535c801161c2036a205be2d719d613343f040df')

build() {
  cd "$pkgname-$pkgver"
  ./build.sh
}

package() {
  cd "$pkgname-$pkgver"
  install -Dm644 init/$pkgname.service "$pkgdir"/usr/lib/systemd/system/$pkgname.service
  install -Dm755 bin/$pkgname "$pkgdir"/usr/bin/$pkgname
}
