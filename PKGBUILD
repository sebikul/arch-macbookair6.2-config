# Contributor: Sebastian Kulesz <sebikul@gmail.com>

pkgname=arch-macbookair6.2-config
_gitname=$pkgname
pkgver=1
pkgrel=1
pkgdesc="Configuration files for an optimal use of a MacbookAir6,2 (2013 13\")"
url="https://github.com/sebikul/${_gitname}"
arch=('any')
license=('GPL2')
depends=('dkms' 'linux-lts-headers')
install=$pkgname.install
source=("git+https://github.com/sebikul/${_gitname}.git")
md5sums=('SKIP')


pkgver() {
  cd "$srcdir/${_gitname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
  cd "${srcdir}/"
  install -Dm 644 mba6x_bl-dkms.conf "${pkgdir}/etc/modules-load.d/mba6x_bl-dkms.conf"

  cd "${srcdir}/${_gitname}"
  for FILE in Makefile dkms.conf mba6x_bl.c; do
    install -Dm 644 $FILE "${pkgdir}/usr/src/mba6x_bl-$pkgver/$FILE"
  done
}