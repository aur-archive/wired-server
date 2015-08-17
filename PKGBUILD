pkgname=wired-server
pkgver=2010.06.09
pkgrel=2
pkgdesc="Server for the Wired P2P protocol"
arch=(i686 x86_64)
url="http://zankasoftware.com/wired"
license=("custom")
depends=(openssl)
source=("http://zankasoftware.com/nightly/wired-${pkgver//./-}.tar.gz")
md5sums=('17062ad4db9a6e7a0feee5aeb479d5b1')

build() {
  cd "${srcdir}/wired-1.3.4"
  ./configure \
    --prefix=$pkgdir/srv # hooray, a crappy Makefile
  make
}

package()
{
  cd "${srcdir}/wired-1.3.4"
  make datarootdir=$pkgdir/usr install
  mkdir -p "$pkgdir/usr/bin"
  ln -s "/srv/wired/wiredctl" "$pkgdir/usr/bin/wiredctl"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
} 
