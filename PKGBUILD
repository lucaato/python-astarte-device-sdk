pkgname=python-astarte-device-sdk
pkgver=0.12.0
pkgrel=1
pkgdesc='A library to easily connect to an astarte cluster from a python application'
arch=('any')
url='https://github.com/astarte-platform/astarte-device-sdk-python'
license=('Apache-2.0' 'CCO-1.0')
depends=('python'
	'python-paho-mqtt'
	'python-cryptography'
	'python-requests>=2.22.0'
	'python-bson'
	'python-pyjwt>=1.7.0'
	'python-pytest')
makedepends=('python-setuptools')
source=("https://files.pythonhosted.org/packages/ca/fe/65e407c5997af3fc94965a89e56a6a8c649125848a1cc2bb1a4b9e47efe5/astarte-device-sdk-$pkgver.tar.gz")
sha256sums=('8ac2fe40f1c3bde6241b97028836eeb55ee39497544a40305deb7685954ac401')

build() {
  cd astarte-device-sdk-$pkgver
  python setup.py build
}

check() {
  cd astarte-device-sdk-$pkgver
  python -m pytest
}

package() {
  cd astarte-device-sdk-$pkgver
  python setup.py install --prefix=/usr --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

