# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.1_beta13
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
sha256sums=('d348d779d27d97115c4ab77f904c016ea44811f31f3762b679dfad9a2f503181'
            '395f07a950decb20ba00e161d3a07173bde1b31df0a4f8ee44de735b66e6a0c4'
            '1d261002eeb521e0c09a254d4ad1ee65df261e7cff04160d5f7dc0d03a345f0b'
            '5b18a3d78ce4392bcc34cc76a15cb39b60a1f50f3130a29977d62605b22f227a')
backup=('etc/sing-box/config.json')

package() {
    install -Dm755 "$pkgname-${_pkgver}-linux-amd64v3/${pkgname}" -t "${pkgdir}/usr/bin"
    install -Dm644 "$pkgname-${_pkgver}-linux-amd64v3/LICENSE"    -t "${pkgdir}/usr/share/licenses/${pkgname}"
    install -Dm644 "config.json"                                  -t "${pkgdir}/etc/${pkgname}"
    install -Dm644 "sing-box.service"                             -t "${pkgdir}/usr/lib/systemd/system"
    install -Dm644 "sing-box@.service"                            -t "${pkgdir}/usr/lib/systemd/system"
}
