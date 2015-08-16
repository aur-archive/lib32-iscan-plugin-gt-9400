# Maintainer: David Spicer <azleifel@gmail.com>

_pkgsourcename=iscan-plugin-gt-9400
pkgname=lib32-${_pkgsourcename}
pkgver=1.0.0
pkgrel=6
pkgdesc="iscan plugin for the Epson Perfection 3170 PHOTO (GT-9400) scanner."
arch=('x86_64')
url="http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX"
license=('custom')
depends=('lib32-gcc-libs')
makedepends=('rpmextract')
source=(http://a1227.g.akamai.net/f/1227/40484/1d/download.ebz.epson.net/dsc/f/01/00/01/58/52/2da130fced78dc89c430122dc6111d69d182542b/${_pkgsourcename}-${pkgver}-1.c2.i386.rpm)
md5sums=('f76725766f44debe3f3fec06d0e2023b')

package() {
  cd "$srcdir"
  rpmextract.sh "$_pkgsourcename-$pkgver-1.c2.i386.rpm"

  install -d -m755 "$pkgdir/usr/lib32/iscan"
  install -d -m755 "$pkgdir/usr/share/iscan"
  install -d -m755 "$pkgdir/usr/share/licenses/$pkgname"

  cp -dp usr/lib/iscan/libesint32* "$pkgdir/usr/lib32/iscan"
  cp -p usr/share/iscan/esfw32.bin "$pkgdir/usr/share/iscan"
  cp -p usr/share/doc/$_pkgsourcename-$pkgver/EAPL.*.txt "$pkgdir/usr/share/licenses/$pkgname"
}

