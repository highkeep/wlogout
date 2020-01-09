# Maintainer: Haden Collins <collinshaden@gmail.com>
pkgname='wlogout'
pkgver=1.0.2
pkgrel=1
pkgdesc="Logout menu for wayland"
arch=('x86_64')
license=("MIT")
url="https://github.com/ArtsyMacaw/wlogout"
source=("$pkgname-$pkgver.tar.gz::https://github.com/ArtsyMacaw/$pkgname/releases/download/$pkgver/$pkgname.tar.gz" "$pkgname-$pkgver.tar.gz.sig::https://github.com/ArtsyMacaw/$pkgname/releases/download/$pkgver/$pkgname.tar.gz.sig")
validpgpkeys=("F4FDB18A9937358364B276E9E25D679AF73C6D2F")
makedepends=("meson" "git" "scdoc")
depends=("gtk3" "gtk-layer-shell")
optdepends=("swaylock: default buttons" 
            "systemd: default buttons"
)
md5sums=('086353a91236f196e3bd9f21b5910779'
         'SKIP')

build() {
    cd $srcdir
    meson build --prefix /usr 
    ninja -C build
}

package() {
    DESTDIR="$pkgdir" ninja -C build install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
