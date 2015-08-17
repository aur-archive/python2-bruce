# Contributor: masutu <masutu dot arch at gmail dot com>
# Contributor: MTsoul <forums+archlinux at oliverzheng dot com>
pkgname=python2-bruce
pkgver=3.2.1
pkgrel=1
pkgdesc="Bruce, the Presentation Tool, puts reStructuredText in your projector."
arch=('any')
url="http://pypi.python.org/pypi/bruce"
license=('BSD')
depends=('python2' 'python2-cocos2d' 'python2-docutils')
makedepends=('python2-setuptools')
source=(http://bruce-tpt.googlecode.com/files/bruce-$pkgver.tar.gz)
md5sums=('358fe59a477fa507f5ad2918abd9e3db')

prepare() {
  cd "$srcdir/bruce-$pkgver"
		
  # python2 fix
  for file in $(find . -name '*.py' -print); do
    sed -i 's_#!.*/usr/bin/env.*python_#!/usr/bin/env python2_' $file
  done
}

build() {
  cd "$srcdir/bruce-$pkgver"
  python2 setup.py build    
}

package () {
  cd "$srcdir/bruce-$pkgver"
  python2 setup.py install --root="$pkgdir"
  install -D -m644 LICENSE.txt $pkgdir/usr/share/licenses/$pkgname/LICENSE.txt
}
