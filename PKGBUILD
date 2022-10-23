# Maintainer: everyx <lunt.luo#gmail.com>

pkgname=sing-box
pkgver=1.1_beta10
_pkgver=${pkgver//_/-}
pkgrel=2
pkgdesc='The universal proxy platform.'
arch=('x86_64')
url='https://sing-box.sagernet.org/'
license=('GPL3')
makedepends=('go')
source=("${pkgname}-${_pkgver}.tar.gz::https://github.com/SagerNet/sing-box/archive/v${_pkgver}.tar.gz")
sha256sums=('f6230c395e63a2e9919230df2f721290ba1380dfc0a9a2ae12c78f961bcd2916')
backup=('etc/sing-box/config.json')

_tags=with_quic,with_grpc,with_wireguard,with_shadowsocksr,with_ech,with_utls,with_clash_api,with_gvisor,with_lwip
build(){
    cd ${pkgname}-${_pkgver}

    export GOAMD64=v3 GOFLAGS="-buildmode=pie -trimpath -ldflags=-linkmode=external"
    export CGO_LDFLAGS="${LDFLAGS}"
    export CGO_CFLAGS="${CFLAGS}"
    export CGO_CPPFLAGS="${CPPFLAGS}"

    go build -tags "$_tags" ./cmd/sing-box
}

package() {
    cd ${pkgname}-${_pkgver}

    install -Dm755 "${pkgname}"                         -t "${pkgdir}/usr/bin"
    install -Dm644 "LICENSE"                            -t "${pkgdir}/usr/share/licenses/${pkgname}"
    install -Dm644 "release/config/config.json"         -t "${pkgdir}/etc/${pkgname}"
    install -Dm644 "release/config/sing-box.service"    -t "${pkgdir}/usr/lib/systemd/system"
    install -Dm644 "release/config/sing-box@.service"   -t "${pkgdir}/usr/lib/systemd/system"
}
