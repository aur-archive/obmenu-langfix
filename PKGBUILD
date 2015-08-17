# Maintainer: Roman Kapl <arch@roman.lamer.la>
# Maintainer-old: Lukas Fleischer <archlinux at cryptocrack dot de>
# Contributor: Hugo Doria <hugodoria@gmail.com>
# Contributor: priyank <priyankmg@gmail.com>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>


pkgname=obmenu-langfix
_pkgname_base=obmenu
pkgver=1.0
pkgrel=9
pkgdesc='Openbox menu editor with fix for obm-xdg.'
arch=('any')
url='http://obmenu.sourceforge.net/'
license=('GPL')
conflicts=('obmenu')
depends=('python2' 'pygtk' 'openbox')
source=("http://downloads.sourceforge.net/${_pkgname_base}/${_pkgname_base}-${pkgver}.tar.gz" "locales_xdgmenu.patch")
md5sums=('710036a5edc9886d6d563ce46c747432' '79f368d9f806ee25ea10ea65a90b6785')

package() {
  cd "${srcdir}/${_pkgname_base}-${pkgver}"
  pwd
  patch -p2 -i "$srcdir/locales_xdgmenu.patch"
  sed -i -e 's#usr/bin/python#usr/bin/python2#g' *.py
  python2 setup.py install --root="${pkgdir}" --optimize=1
}

