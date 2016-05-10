pkgname=arduino
pkgver=1.6.9
pkgrel=1
pkgdesc="Arduino prototyping platform SDK"
arch=( 'x86_64')
category=Development
screenshot=http://i.imgur.com/twuGrHj.jpg
url="http://arduino.cc/"
license=('LGPL')
depends=('java-environment' 'gtk2' 'desktop-file-utils' 'giflib' 'avrdude-svn' 'libusb-compat' )
install="arduino.install"
source=('arduino.desktop'
        "http://downloads.arduino.cc/arduino-${pkgver}-linux64.tar.xz")
 md5sums=('df1f245d0455bd8f7bb3ffba6a375332'
                 'cf31421f10e2726afc2d2b320c2b5127')
options=(!strip)
package() {
  rm -f $srcdir/arduino-${pkgver}/hardware/tools/avr/bin/{avrdude,avrdude_bin}
  install -d -m 755 $pkgdir/usr/share/icons/hicolor
  mv $srcdir/arduino-${pkgver}/lib/icons/ $pkgdir/usr/share/icons/hicolor/
  install -d -m 755 $pkgdir/opt/$pkgname
   cp -Lr $srcdir/arduino-${pkgver}/* $pkgdir/opt/$pkgname/
  install -dm755 $pkgdir/usr/bin
  ln -s /opt/$pkgname/$pkgname $pkgdir/usr/bin/$pkgname
  install -dm755 $pkgdir/usr/share/applications/
        install -Dm644 $srcdir/arduino.desktop $pkgdir/usr/share/applications/arduino.desktop
   ln -s /usr/bin/avrdude ${pkgdir}/opt/arduino/hardware/tools/avr/bin/avrdude
}
