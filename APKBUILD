# Contributor: TODO
# Maintainer: TODO

pkgname=cc65
_gitrev=f9204e5
pkgver="2.18_git20200416"
pkgrel=0
pkgdesc="cc65 is a complete cross development package for 65(C)02 systems."
url="https://www.cc65.org/"
arch="all"
license="Zlib"
subpackages="$pkgname-doc"
source="cc65-$pkgver.tar.gz::https://github.com/cc65/cc65/tarball/$_gitrev"
builddir="$srcdir"/cc65-cc65-"$_gitrev"

build() {
	cd "$builddir"
	make -j1 PREFIX=/usr
}

check() {
	cd "$builddir"/test
	CC65_HOME="$builddir" make dotests
}

package() {
	cd "$builddir"

	# TODO: Move samples to docs
	
	mkdir -p "$pkgdir"/usr/share/licenses/"$pkgname"
	install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/"$pkgname"/LICENSE

	make PREFIX=/usr DESTDIR="$pkgdir" install
}

sha512sums="3e383f6a9b807b0c9aa79d6e059f90d61369b1c7bc720721db6abef27163df500edc089990545777f093ee4a29b6fc6ac7c2b5df8ef13d70039f2b76f79a1159  cc65-2.18_git20200416.tar.gz"
