# Maintainer: leothelion <ponte-vecchio>

pkgname=positron-ide-devel-bin
_pkgname=positron-ide
pkgver=2025.03.0.116
pkgver_url=2025.03.0-116
pkgrel=1
pkgdesc="A next-generation data science IDE. Positron is an extensible, polyglot tool for writing code and exploring data in Python, R, and other languages."
arch=('x86_64' 'aarch64')
options=('!debug')
url="https://github.com/posit-dev/positron"
posit_url="https://cdn.posit.co/positron/dailies/deb"
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
    'bash-completion: Bash completion support'
    'zsh-completions: Zsh completion support'
)
provides=("positron")
conflicts=("positron-bin")
source_x86_64=("${posit_url}/x86_64/Positron-${pkgver_url}-x64.deb")
source_aarch64=("${posit_url}/arm64/Positron-${pkgver_url}-arm64.deb")
sha256sums_x86_64=('6b2e1ca0085350286defb151dba250e1b006b199836cc1de8f2dc10e4acf8524')
sha256sums_aarch64=('a07aaa6e3043601328655319701e21c81c4e7193a8b0f93f8da1e36278a3b7d8')

package(){
    shopt -s extglob

    msg "Converting .deb package"
    if [ "${CARCH}" = "x86_64" ]; then
        ar x Positron-${pkgver_url}-x64.deb
    elif [ "${CARCH}" = "aarch64" ]; then
        ar x Positron-${pkgver_url}-arm64.deb
    fi

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