# Maintainer: TDY <tdy@archlinux.info>

pkgname=ceylon
pkgver=1.1.0
pkgrel=1
pkgdesc="A powerful statically typed language for writing large programs in groups"
arch=('any')
url="http://ceylon-lang.org/"
license=('APACHE' 'GPL' 'LGPL')
depends=('java-environment>=7')
optdepends=('nodejs: for JavaScript interoperability')
install=$pkgname.install
source=($pkgname-$pkgver.zip::http://downloads.ceylon-lang.org/cli/$pkgname-$pkgver.zip)
sha256sums=('c08a900b13f42c38a38b403d620afd436cd18f2fe9a0942b626254bf4ad821c1')

package() {
  cd "$srcdir/$pkgname-$pkgver"
  install -Dm644 contrib/scripts/$pkgname-completion.bash \
    "$pkgdir/usr/share/java/$pkgname/$pkgname-completion.bash"
  install -Dm644 README.md "$pkgdir/usr/share/doc/$pkgname/README.md"

  # libs
  cp -a doc lib repo samples templates "$pkgdir/usr/share/java/$pkgname/"
  find "$pkgdir/usr/share/java/$pkgname/" -type f -exec chmod 644 '{}' \;
  find "$pkgdir/usr/share/java/$pkgname/" -type d -exec chmod 755 '{}' \;

  # bins
  install -Dm755 bin/$pkgname "$pkgdir/usr/share/java/$pkgname/bin/$pkgname"
  install -dm755 "$pkgdir/usr/bin/"
  ln -s /usr/share/java/$pkgname/bin/$pkgname "$pkgdir/usr/bin/$pkgname"
}

# vim:set ts=2 sw=2 et:
