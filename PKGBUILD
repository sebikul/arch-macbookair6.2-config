# Contributor: Sebastian Kulesz <sebikul@gmail.com>

pkgname=arch-macbookair6.2-config
_gitname=$pkgname
pkgver=1.c23446c
pkgrel=1
pkgdesc="Configuration files for an optimal use of a MacbookAir6,2 (2013 13\")"
url="https://github.com/sebikul/${_gitname}"
arch=('any')
license=('GPL2')
depends=('dkms' 'linux-lts-headers')
makedepends=('git')
source=("git+https://github.com/sebikul/${_gitname}.git")
md5sums=('SKIP')


pkgver() {
  cd "$srcdir/${_gitname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
  cd "${srcdir}/${_gitname}"
  pwd
  install -Dm 644 udev/90-dev_power_save.rules "${pkgdir}/etc/udev/rules.d/90-dev_power_save.rules"
  install -Dm 644 udev/90-xhc_sleep.rules "${pkgdir}/etc/udev/rules.d/90-xhc_sleep.rules"

}