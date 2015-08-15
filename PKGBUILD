# Archtrack maintainer: Evan Teitelman <teitelmanevan at gmail dot com>
# Contributor: Francesco Piccinno <stack.box@gmail.com>

pkgname=enumiax
pkgver=1.0
pkgrel=1
pkgdesc="IAX enumerator"
url="http://sourceforge.net/projects/enumiax/"
license=('GPL')
depends=('glibc')
arch=(i686 x86_64)
source=(http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('3e3826559574b637c9ca8830f956154b')

groups=(archtrack archtrack-info-gathering)

build() {
  cd "$srcdir/$pkgname-$pkgver"
  sed -i "s|ienumiaxtall|/bin/install|g" Makefile || return 1
  sed -i "s|\${DEBUG}|$CFLAGS|g" base.mk || return 1
  make || return 1

  install -d $pkgdir/usr/bin
  make BINDIR=$pkgdir/usr/bin install || return 1
}

