# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.7.0
_pkgver=${pkgver//_/-}
pkgrel=1
pkgdesc='The universal proxy platform.'
arch=('x86_64')
url='https://sing-box.sagernet.org/'
license=('GPL3')
source=("https://github.com/SagerNet/sing-box/releases/download/v${_pkgver}/sing-box-${_pkgver}-linux-amd64v3.tar.gz"
        "https://github.com/SagerNet/sing-box/raw/v${_pkgver}/release/config/config.json"
        "https://github.com/SagerNet/sing-box/raw/v${_pkgver}/release/config/sing-box.service"
        "https://github.com/SagerNet/sing-box/raw/v${_pkgver}/release/config/sing-box@.service")
sha256sums=('5894a8460aec2051a9f62fe71c726ece5f59c1accf7726adcd73690851cb0d1f'
            '59aac6f3459d3a48c496ab3055d9a9c261179dd8ad73b54a4dccb9ebf3ae9a5b'
            '56cb2758d34e9d317537e29e424f883e1ed90022d2d764cca6ea457edd3f1042'
            '3987de625e0c70099ffd227d7e14c2eccb7245d7f0a8546f075f7ca686560223')
backup=('etc/sing-box/config.json')

build() {
    cd "$pkgname-${_pkgver}-linux-amd64v3/"
    mkdir -p ../completions
    ./sing-box completion bash > ../completions/bash
    ./sing-box completion fish > ../completions/fish
    ./sing-box completion zsh  > ../completions/zsh
}

package() {
    install -Dm755 "$pkgname-${_pkgver}-linux-amd64v3/${pkgname}" -t "${pkgdir}/usr/bin"
    install -Dm644 "$pkgname-${_pkgver}-linux-amd64v3/LICENSE"    -t "${pkgdir}/usr/share/licenses/${pkgname}"
    install -Dm644 "config.json"                                  -t "${pkgdir}/etc/${pkgname}"
    install -Dm644 "sing-box.service"                             -t "${pkgdir}/usr/lib/systemd/system"
    install -Dm644 "sing-box@.service"                            -t "${pkgdir}/usr/lib/systemd/system"

    install -Dm644 completions/bash "${pkgdir}/usr/share/bash-completion/completions/${pkgname}.bash"
    install -Dm644 completions/fish "${pkgdir}/usr/share/fish/vendor_completions.d/${pkgname}.fish"
    install -Dm644 completions/zsh  "${pkgdir}/usr/share/zsh/site-functions/_${pkgname}"
}
