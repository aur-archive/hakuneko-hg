# Maintainer: kozec <kozec2 at kozec dot com>
# Developer: Ronny Wegener <wegener.ronny@gmail.com>
# Based on hakuneko package by Jan Keith Darunday <jkcdarunday@uplb.edu.ph>

pkgname=hakuneko-hg
pkgver=r130.8cbdacc157d7
pkgrel=1
pkgdesc="A Manga Downloader for Linux"
arch=('i686' 'x86_64')
url="http://sourceforge.net/p/hakuneko"
license=('MIT')
depends=('wxgtk2.8')
makedepends=('tar' 'mercurial')
source=("hg+http://hg.code.sf.net/p/hakuneko/code")

build() {
	cd "$srcdir"/code
	sed -i 's/wx-config/wx-config-2.8/g' config_default.sh
	./configure
	make
}

package() {
	cd "$srcdir"/code
	make PREFIX=/usr DESTDIR="$pkgdir" install
}

pkgver() {
	cd "$srcdir"/code
	printf "r%s.%s" "$(hg identify -n)" "$(hg identify -i)"
}

md5sums=('SKIP')
