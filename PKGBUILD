# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.1.4
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
sha256sums=('f7dbef588b9ba6646eff4a1c556753563f6026361b3350eb422050ea266a6bf4'
            '395f07a950decb20ba00e161d3a07173bde1b31df0a4f8ee44de735b66e6a0c4'
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
