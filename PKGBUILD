# Maintainer: Erik Beran <eberan AT_gmail_DOT com>
# Contributor: Sigitas Mazaliauskas <sigisnn AT gmail DOT com>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>
# Contributor: not_anonymous

pkgname=jgnash
pkgver=2.15.2
pkgrel=1
pkgdesc='A double-entry based personal finance manager, written in Java'
arch=('any')
url='http://jgnash.sourceforge.net/'
# Main program is GPL3, 3rd party libs, content and docs under other licenses
license=('GPL3' 'GPL2' 'LGPL' 'BSD' 'MIT' 'Apache' 'FDL1.3' 'CCPL:by-sa 2.5')
depends=('sh' 'java-environment')
makedepends=('imagemagick')
source=("http://downloads.sourceforge.net/project/${pkgname}/Active%20Stable%202.x/${pkgname}-${pkgver}-bin.zip"
        "https://jgnash.svn.sourceforge.net/svnroot/jgnash/jgnash2/trunk/gnome-money.ico"
        'jgnash.desktop'
        'jgnash.sh'
        'LICENSE')
sha256sums=('a956b1acdbcce0fa0bc7b790a487dbaa0b7f5b8ba72de01e5d2c39bff1354f44'
            'a948982e6711fd05df248ff989f9ad17fca713774bfe5d9cade0496569dfd926'
            '66342b681a404219d8e3dea14f87ab90c610b428bd83319ab89e32a954690538'
            'f002291ba454bda78d1204e9bada4e1b051923d44689464286ce384aec46d173'
            '7ed7b378a77cc6ec45876a078158f36cd645194837d632fcfc258eee7480e6fe')

build() {
  cd ${pkgname}-${pkgver}
  convert ${srcdir}/gnome-money.ico jgnash.png
}

package() {
  install -D -m644 jgnash.desktop ${pkgdir}/usr/share/applications/jgnash.desktop
  install -D -m755 jgnash.sh ${pkgdir}/usr/bin/jgnash
  install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/jgnash/LICENSE

  cd ${pkgname}-${pkgver}

  install -D -m644 ${pkgname}2.jar ${pkgdir}/usr/share/java/${pkgname}/${pkgname}2.jar
  cp -r lib ${pkgdir}/usr/share/java/${pkgname}

  install -D -m644 jgnash.png ${pkgdir}/usr/share/pixmaps/jgnash.png
}

