# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.1
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
sha256sums=('1a3cfbc08923d3e2e85c6eebb3415f279e2863011df3e45a80293c80c84f87e7'
            '395f07a950decb20ba00e161d3a07173bde1b31df0a4f8ee44de735b66e6a0c4'
            '49fffaf52c41d49bc204b6a240452a12f78ed3ee46a816c9a54f8376bd1c3d7f'
            '9692f4a08210258144ce783ab60048ee6d5a6e0f146ab4276d449026cc2bde4f')
backup=('etc/sing-box/config.json')

package() {
    install -Dm755 "$pkgname-${_pkgver}-linux-amd64v3/${pkgname}" -t "${pkgdir}/usr/bin"
    install -Dm644 "$pkgname-${_pkgver}-linux-amd64v3/LICENSE"    -t "${pkgdir}/usr/share/licenses/${pkgname}"
    install -Dm644 "config.json"                                  -t "${pkgdir}/etc/${pkgname}"
    install -Dm644 "sing-box.service"                             -t "${pkgdir}/usr/lib/systemd/system"
    install -Dm644 "sing-box@.service"                            -t "${pkgdir}/usr/lib/systemd/system"
}
