# Maintainer: Pavlos Kafritsas <pkafritsas@proton.me>

pkgname=aws-rat-picker
pkgver=1.0.0
pkgrel=1
pkgdesc="AWS Remote Access Tool (picker)"
arch=('x86_64')
url="https://github.com/pavloskafritsas/aws-rat-picker"
license=('MIT')
depends=(
    'aws-cli'
    'iniparser'
)
makedepends=('git' 'gcc' 'make')
source=(
    "git+https://github.com/pavloskafritsas/aws-rat-picker.git"
    "aws-rat-picker.desktop"
)
sha256sums=(
    'SKIP'
    'c5808ef554020b63bde8a4318b5e379d03c6af1becacf5388fafa21b28177767'
)

build() {
    cd "$srcdir/$pkgname"
    make
}

package() {
    cd "$srcdir/$pkgname"

    # Install binary
    install -Dm755 "bin/aws-rat-picker" "$pkgdir/usr/bin/aws-rat-picker"

    # Install license + documentation
    install -Dm644 LICENSE "$pkgdir/usr/share/doc/$pkgname/LICENSE"

    # Install documentation
    install -Dm644 README.md "$pkgdir/usr/share/doc/$pkgname/README.md"

    # Install .desktop entry
    install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
}
