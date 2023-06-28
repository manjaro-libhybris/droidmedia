# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=droidmedia
pkgver=0.20220929.0+1
pkgrel=1
_commit=f81cfcde18ea4f883c989dbc308ad7258e06c072
pkgdesc="Android media wrapper library"
url="https://github.com/droidian/droidmedia"
license=("Apache-2.0")
arch=('i686' 'x86_64' 'armv6h' 'armv7h' 'aarch64')
makedepends=('meson' 'git')
source=("git+https://github.com/droidian/droidmedia#commit=${_commit}")
sha256sums=('SKIP')

pkgver() {
  cd droidmedia
  basename $(git describe --tags | sed 's/^v//;s/-/+/g')
}

build() {
    rm -rf build
    arch-meson droidmedia build
    ninja -C build
}

package() {
    DESTDIR="${pkgdir}" ninja -C build install
}
