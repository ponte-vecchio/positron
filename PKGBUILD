# Maintainer: leothelion <ponte-vecchio>

pkgname=positron-ide-devel-bin
_pkgname=positron-ide
pkgver=2024.07.0.21
pkgver_url=2024.07.0-21
pkgrel=1
pkgdesc="A next-generation data science IDE. Positron is an extensible, polyglot tool for writing code and exploring data in Python, R, and other languages."
arch=('x86_64')
options=('!debug')
url="https://github.com/posit-dev/positron"
licence=('custom: Elastic License 2.0')
depends=(
    'ca-certificates'
    'alsa-lib'
    'at-spi2-core'
    'atkmm'
    # 'glibc' # mesa
    # 'cairo' # pango
    'libcups'
    'curl'
    # 'libdrm' # mesa
    # 'expat' # mesa
    'mesa'
    # 'glib2' # pango
    'krb5'
    'gtk4'
    # 'nspr' # nss
    'nss' 
    'pango'
    # 'gcc-libs' # mesa
    # 'libx11' # mesa, pango
    # 'libxcb' # mesa
    'libxcomposite'
    'libxdamage'
    # 'libxext' # mesa
    # 'libxfixes' # mesa
    # 'libxkbcommon' # at-spi2-core
    # 'libxkbfile' # mesa
    'libxrandr'
    'xdg-utils'
)
optdepends=(
    # libvullkan1
    'vulkan-intel: Intel Vulkan driver'
    'vulkan-radeon: Radeon Vulkan driver'
    'vulkan-icd-loader: Vulkan ICD loader'
)
provides=("positron-positron")
conflicts=("positron-positron")
sha256sums_x86_64=('a766ae3e743f1057c213bbdd8139317729589b8a4e959d198a19f5f5355a7e18')
source_x86_64=("${url}/releases/download/${pkgver_url}/Positron-${pkgver_url}.deb")

package(){
    shopt -s extglob

    msg "Converting .deb package"
    ar x Positron-${pkgver_url}.deb

    cd "${srcdir}"
    tar --zstd -xf data.tar.zst -C "${pkgdir}"

    msg "Installing"
    install -d "${pkgdir}/usr/share/appdata"
    install -d "${pkgdir}/usr/share/applications"
    install -d "${pkgdir}/usr/share/mime/packages"
    install -d "${pkgdir}/usr/share/positron"
}