# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# The following guidelines are specific to BZR, GIT, HG and SVN packages.
# Other VCS sources are not natively supported by makepkg yet.

# Maintainer: Pierre-Emmanuel Wulfman <pierre-emmanuel@wulfman.fr>
pkgname=ligo-next-git # '-bzr', '-git', '-hg' or '-svn'
pkgver=r11364.09b2c1a6c
pkgrel=1
pkgdesc="High Level Smart Contract Language for Tezos"
arch=(any)
url="https://gitlab.com/ligolang/ligo"
license=('MIT')
groups=('LigoLANG')
depends=(
	'opam'
	'rust'
	'libev'
	'libevdev'
	'perl'
	'pkg-config'
	'gmp'
	'hidapi'
	'm4'
	'libcap'
	'bubblewrap'
	'rsync'
	'python-jsonschema'
)
makedepends=('git')
provides=('ligo')
conflicts=("${pkgname%-git}" 'ligo')
replaces=()
backup=()
options=()
install=
source=("ligo-next::git+https://gitlab.com/ligolang/ligo")
noextract=()
md5sums=('SKIP')

# Please refer to the 'USING VCS SOURCES' section of the PKGBUILD man page for
# a description of each element in the source array.

pkgver() {
	cd "$srcdir/${pkgname%-git}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/${pkgname%-git}"
	make
}

package() {
	cd "$srcdir/${pkgname%-git}"
	make DESTDIR="$pkgdir/" install
}
