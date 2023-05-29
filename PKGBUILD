# Maintainer: Yuvraj Mishra <yuvrajmishrawork@gmail.com>

pkgname=python2-bin
_pkgname=python2
pkgver=2.7.18_1
_pybasever=2.7
pkgrel=1
pkgdesc="Python2 binaries for x86_64"
arch=('x86_64' 'armv7h' 'aarch64')
url="https://python.org"
license=('PSF')
groups=()
depends=('bzip2' 'expat' 'gdbm' 'libffi' 'libnsl' 'libxcrypt' 'openssl' 'sqlite' 'zlib')
makedepends=()
checkdepends=()
optdepends=()
provides=('python2')
conflicts=('python2')
replaces=()
backup=()
options=()
install=
changelog=
noextract=()
validpgpkeys=()
source_x86_64=("https://github.com/atomlong/python2-bin/releases/download/$pkgver/python2-build-amd64.tar.gz")
source_armv7h=("https://github.com/atomlong/python2-bin/releases/download/$pkgver/python2-build-armv7.tar.gz")
source_aarch64=("https://github.com/atomlong/python2-bin/releases/download/$pkgver/python2-build-arm64.tar.gz")
md5sums_x86_64=('d1a5929835018fa5ca18853c49c972ad')
md5sums_armv7h=('7f4470869d8240b68af9619f9e12ebe4')
md5sums_aarch64=('997b80dc5218c96f1b2f82a14079ab11')

package() {

	rm python2-build/bin/2to3
	rm python2-build/bin/idle
	rm python2-build/bin/pydoc
	rm python2-build/bin/python
	rm python2-build/bin/python-config
	rm python2-build/lib/pkgconfig/python.pc
	rm python2-build/share/man/man1/python.1

	sed -i "s|/mnt/storage/temp/python2-build|/usr|" python2-build/bin/python${_pybasever}-config
	sed -i "s|/mnt/storage/temp/python2-build|/usr|" python2-build/lib/pkgconfig/python-${_pybasever}.pc

	# copy recursively without overwriting
	mkdir -p $pkgdir/usr
	cp -rn python2-build/* "${pkgdir}/usr/" || true
}
