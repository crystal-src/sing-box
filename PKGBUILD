# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.2.3
_pkgver=${pkgver//_/-}
pkgrel=1
pkgdesc='The universal proxy platform.'
arch=('x86_64')
url='https://sing-box.sagernet.org/'
license=('GPL3')
source=("https://github.com/SagerNet/sing-box/releases/download/v${_pkgver}/sing-box-${_pkgver}-linux-amd64v3.tar.gz"
        "https://github.com/SagerNet/sing-box/raw/v${_pkgver}/release/config/config.json"
        "sing-box.service"
        "sing-box@.service")
sha256sums=('b10548e2c22286f5177b1aae64eed8aa759f2c4779f58e0020cea5e0038606c4'
            '59aac6f3459d3a48c496ab3055d9a9c261179dd8ad73b54a4dccb9ebf3ae9a5b'
            '242e499ffb783111ff49e290a8ccbd34ff20786a0c90915625458b74e35a79c5'
            '72265c3a80f52c3fe3247da2fe73bffb5b117d7b50ab801f63874dc6eb86161b')
backup=('etc/sing-box/config.json')

package() {
    install -Dm755 "$pkgname-${_pkgver}-linux-amd64v3/${pkgname}" -t "${pkgdir}/usr/bin"
    install -Dm644 "$pkgname-${_pkgver}-linux-amd64v3/LICENSE"    -t "${pkgdir}/usr/share/licenses/${pkgname}"
    install -Dm644 "config.json"                                  -t "${pkgdir}/etc/${pkgname}"
    install -Dm644 "sing-box.service"                             -t "${pkgdir}/usr/lib/systemd/system"
    install -Dm644 "sing-box@.service"                            -t "${pkgdir}/usr/lib/systemd/system"
}
