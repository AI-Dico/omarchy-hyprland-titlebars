# Maintainer: Ryan Hughes <ryan@heyoodle.com>

pkgname=omarchy-hyprland-titlebars
pkgver=0.2.0
pkgrel=1
pkgdesc="Titlebars for Omarchy's floating workspaces"
arch=('x86_64' 'aarch64')
url='https://github.com/omacom/omarchy'
license=('BSD-3-Clause' 'MIT')
# A Hyprland plugin only loads into the exact Hyprland build it was compiled
# against. rebuild_on in .omarchy/package.json rebuilds it with every Hyprland.
depends=('hyprland=0.56.2' 'glibc' 'libgcc' 'libstdc++' 'hyprlang' 'hyprutils')
makedepends=('cmake' 'pkgconf')
options=('!lto' '!debug')
source=('CMakeLists.txt'
        'main.cpp'
        'barDeco.cpp'
        'barDeco.hpp'
        'BarPassElement.cpp'
        'BarPassElement.hpp'
        'appName.cpp'
        'appName.hpp'
        'globals.hpp'
        'LICENSE'
        'LICENSE.MIT')
sha256sums=('018fd3165d0869b9b9d583fbbd5e639f828c7a3247bae398237f389893cdbb03'
            '0879135faa5e7def2c53e80f85fb327a9f8fd9ef436471164ae9750bf68629d4'
            '308be2169693ae38e8419a8703607dd1083d7de7a913acdf2deb27e955a0b427'
            'dbdd56902558b36f7e7d01f7b9884530a93f7dda411a2b360acf69255a42c8f2'
            'e0074f71d8bbb3ae0a24a91a4647c4d0da6ab8c5effa0dce2b5a1bb8c85d085c'
            'dffbf8ddc768fd111b2a41697fe6547e954c46edc16750913c789d8daa8690cc'
            '4f936c3c60628d9d8a027d94d42ba2ca96d5ff233851e851712ad31563da4bf9'
            '1a089aa318942472f944d127ca39612f058cc57fb9265c2d137daacd69a738a9'
            '33999c894de2648bae9f618a0bc3b30cfc0eb627ec38cdc19005d3f688e1bc15'
            '3a1d080d85ce1d722b3bd84d87b74dd2332ba7b68a40a28a7126a86cfca6502a'
            '717ba1949502290f8e47688ae2e323acd06c8ca47aec9f7596b15f678c1af4a2')

build() {
  cmake -S "$srcdir" -B build \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 LICENSE.MIT "$pkgdir/usr/share/licenses/$pkgname/LICENSE.MIT"
}
