pkgname=superlu
pkgver=5.2.0
pkgrel=1
pkgdesc="General purpose library for the direct solution of large, sparse, nonsymmetric systems of linear equations."
arch=('x86_64')
url="http://crd.lbl.gov/~xiaoye/SuperLU/"
license=('custom')
depends=('lapack')
makedepends=('cmake' 'tcsh')
source=("http://crd.lbl.gov/~xiaoye/SuperLU/${pkgname}_${pkgver}.tar.gz")
md5sums=('ba3cfc93a93a8caed90bcf6f9b804ac7')
 
build() {
  mkdir -p build
  cd build
 
  cmake ../SuperLU_${pkgver} \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DBUILD_SHARED_LIBS=ON
  make
}
 
package() {
  cd build
  make DESTDIR=${pkgdir} install
 
  install -Dm644 ../SuperLU_${pkgver}/License.txt $pkgdir/usr/share/licenses/$pkgname
}
