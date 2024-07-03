# Maintainer: malwareslayer <alternate-egoist@protonmail.com>

pkgname=mbuild
pkgver=2024.05.05
pkgrel=1
pkgdesc="Python-based build system used for building XED"
arch=('any')
url='https://intelxed.github.io/'
license=('Apache')
depends=('python')
makedepends=('python-build' 'python-installer' 'python-wheel')
source=("https://github.com/intelxed/mbuild/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('8cac881634e963cfe3eeee467e4d7fa91440d2e624d50673e10f20ff4654ced9')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    python -m build --wheel --no-isolation
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    python -m installer \
        --prefix=/usr \
        --destdir="$pkgdir" \
        --compile-bytecode=1 \
        dist/*.whl
}

# vim: set ts=4 sw=4 et :
