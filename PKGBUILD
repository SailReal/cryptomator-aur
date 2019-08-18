# Maintainer: Aaron Graves <linux@ajgraves.com>
# Contributor: Morten Linderud <morten@linderud.pw>
# Contributor: Sebastian Stenzel <sebastian.stenzel@gmail.com>

pkgname=cryptomator
pkgver=1.4.15
pkgrel=1
pkgdesc="Multiplatform transparent client-side encryption of your files in the cloud."
arch=('x86_64')
url="https://cryptomator.org/"
license=('GPL3')
depends=('fuse2')
source=("cryptomator-${pkgver}-x86_64.AppImage::https://dl.bintray.com/cryptomator/cryptomator/${pkgver}/cryptomator-${pkgver}-x86_64.AppImage"
        'cryptomator.desktop'
        'cryptomator.png'
        'cryptomator-vault.xml')
sha256sums=('9d52051abc07727e2b6868e70347910d41347147078213e3ea846d26d113c047'
            '5f82b1846e5db21fcca2fb914321eecbc9906c8580ef4318d6a12c011e1e3285'
            'fb1213c07d01c86757744507a151b37d4e917b69965a7db6d28bd99fcc735e6b'
            '78537ead26dcc1488d7fff02f47fce559f70f9bb2d7fa7fa1741ad3cd151bfad')
options=('!strip')

package() {
  install -Dm755 "${srcdir}/cryptomator-${pkgver}-x86_64.AppImage" "${pkgdir}/opt/cryptomator/cryptomator-${pkgver}-x86_64.AppImage"
  install -Dm644 "${srcdir}/cryptomator-vault.xml" "${pkgdir}/usr/share/mime/packages/cryptomator-vault.xml"
  install -Dm644 "${srcdir}/cryptomator.desktop" "${pkgdir}/usr/share/applications/cryptomator.desktop"
  install -Dm644 "${srcdir}/cryptomator.png" "${pkgdir}/opt/cryptomator/cryptomator.png"
  mkdir -p "${pkgdir}/usr/bin/"
  ln -s "/opt/cryptomator/cryptomator-${pkgver}-x86_64.AppImage" "${pkgdir}/usr/bin/cryptomator"
}
