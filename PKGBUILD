# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-lame
epoch=1
pkgver=2.0.2
_codename=Leia
pkgrel=1
pkgdesc="LAME Audio Encoder add-on for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/audioencoder.lame'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-audioencoder')
provides=('kodi-audioencoder-lame')
replaces=('kodi-audioencoder-lame')
depends=('kodi' 'lame')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/audioencoder.lame/archive/$pkgver-$_codename.tar.gz")
sha512sums=('e4a73dadba4fafc8e60c1730404f9390a191bec58823202c3193f7f0571e914151c74b6d18e7d48551ae2f493b9ef11a84ddb27976a5f766e1ba512f1a0e141b')

build() {
    cd "audioencoder.lame-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "audioencoder.lame-$pkgver-$_codename"
    make DESTDIR="$pkgdir/" install
}

