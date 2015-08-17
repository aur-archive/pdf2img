# Maintainer: wifiextender <aaron_caffrey at hotmail dot com>

pkgname=pdf2img
pkgver=76.69d9e51
pkgrel=1
pkgdesc="Convert easily PDF to multiple images in various formats with a single mouse click. PyGTK+3 version of pdf2img"
arch=('any')
url="https://github.com/wifiextender/pdf2png"
license=('GPL3')
depends=('ghostscript' 'python2-gobject' 'webkitgtk' 'pywebkitgtk' 'python2')
makedepends=('git')
source=('git+https://github.com/wifiextender/pdf2png.git'
         pdf2img.sh
         pdf2img-pygtk3.desktop)
md5sums=('SKIP'
         '570337487bd341a2b83401e377baaf99'
         '1d94ee6c41c598ed940bd22a9fe3479f')

package() {
  cd $srcdir

  # Program
  install -d $pkgdir/usr/share/pdf2img-pygtk3
  cp -rf pdf2png/pygtk3/* $pkgdir/usr/share/pdf2img-pygtk3

  # Start file
  install -Dm755 pdf2img.sh $pkgdir/usr/bin/pdf2img-pygtk3

  # Desktop icon
  install -Dm644 pdf2img-pygtk3.desktop $pkgdir/usr/share/applications/pdf2img-pygtk3.desktop
  install -Dm644 pdf2png/pygtk3/img/pdf2img_icon.png $pkgdir/usr/share/pixmaps/pdf2img_pygtk3_icon.png  
}

pkgver() {
  cd $srcdir/pdf2png
  echo $(git rev-list --count master).$(git rev-parse --short master)
}