pkgname=openarena
pkgver=0.8.8
pkgrel=1
pkgdesc="A violent, sexy, multiplayer first person shooter based on the ioquake3 engine (binary package)"
arch=('x86_64')
url="http://openarena.ws/"
license=('GPL')
depends=('sdl' 'libvorbis' 'curl' 'openal')
source=("http://download.tuxfamily.org/openarena/rel/088/openarena-${pkgver}.zip"
        "openarena.png"
        "launch-openarena.sh"
        "openarena.desktop"
)
md5sums=("9f353d96d7889c377349d692c3905e5b"
         "c69f824dc500d436fc631b78b6a62dc8"
         "9abde879d5eaceec55d724fbdc0d35aa"
         "f05bba1688883a0b54f0024bdb2fda24"
)

build() {
  cd ${srcdir}/openarena-${pkgver}
  rm *.dll *.exe
  rm -rf __MACOSX *.app
  rm openarena.i386
}

package() {
    install -d ${pkgdir}/opt/openarena
    cp -r * ${pkgdir}/opt/openarena/
    chmod +x ${pkgdir}/opt/openarena/openarena-0.8.8/openarena.x86_64
    
    install -Dm755 ${srcdir}/launch-openarena.sh ${pkgdir}/usr/bin/launch-openarena.sh
    install -Dm644 $srcdir/openarena.desktop ${pkgdir}/usr/share/applications/openarena.desktop
    install -Dm644 ${srcdir}/openarena.png ${pkgdir}/usr/share/pixmaps/openarena.png
}
