pkgname=acl
pkgver=2.3.2
pkgrel=1
pkgdesc="Access control list utilities, libraries and headers"
arch=('x86_64')
url="https://savannah.nongnu.org/projects/acl"
license=('LGPL-2.1-only')
depends=('glibc' 'attr')
options=('!lto')
source=(https://download.savannah.gnu.org/releases/${pkgname}/${pkgname}-${pkgver}.tar.xz)
sha256sums=(97203a72cae99ab89a067fe2210c1cbf052bc492b479eca7d226d9830883b0bd)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        --disable-static
        --docdir=/usr/share/doc/${pkgname}-${pkgver}
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
