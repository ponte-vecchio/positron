# Maintainer: leothelion <ponte-vecchio>

pkgname=positron-ide-devel-bin
_pkgname=positron-ide
pkgver=2024.11.0.69
pkgver_url=2024.11.0-69
pkgrel=1
pkgdesc="A next-generation data science IDE. Positron is an extensible, polyglot tool for writing code and exploring data in Python, R, and other languages."
arch=('x86_64')
options=('!debug')
url="https://github.com/posit-dev/positron"
licence=('Elastic-2.0')
license=('Elastic-2.0')
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
provides=("positron")
conflicts=("positron-bin")
sha256sums_x86_64=('aa118403941ab3e83d0ad1b5a53732578e8eae3e9524e5e06381a92588a99dda')
source_x86_64=("${url}/releases/download/${pkgver_url}/Positron-${pkgver_url}.deb")

package(){
    shopt -s extglob

    msg "Converting .deb package"
    ar x Positron-${pkgver_url}.deb

    cd "${srcdir}"
    tar --zstd -xf data.tar.xz -C "${pkgdir}"

    # copy licence from root directory
    # msg "Copying licence"
    # install -Dm644 "../LICENCE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

    msg "Installing"
    install -d "${pkgdir}/usr/share/appdata"
    install -d "${pkgdir}/usr/share/applications"
    install -d "${pkgdir}/usr/share/mime/packages"
    install -d "${pkgdir}/usr/share/positron"
}