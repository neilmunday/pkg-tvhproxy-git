# Based upon https://aur.archlinux.org/tvhproxy-git.git
pkgname=tvhproxy-git
pkgdesc='A small flask app to proxy requests between Plex Media Server and Tvheadend.'
pkgver=r43.d4ce022
pkgrel=1
arch=('any')
url=https://github.com/chkuendig/tvhProxy
license=('unknown')
provides=('tvhproxy')
makedepends=()
depends=('python-flask' 'python-requests' 'python-gevent')
source=("${pkgname}::git+https://github.com/chkuendig/tvhProxy"
        'tvhproxy.service'
        'tvhproxy.conf.d')
sha256sums=('SKIP'
            '15498cf09f8faa7c756a3cbd101355ac342540fd8cdcdf857d0f639eef893d8b'
            'c31c5c0abb243db6b0ae0c395dd1f56eab49a5c1ee7e29a12ccf05941afe3214')

pkgver() {
    cd "${srcdir}/${pkgname}"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "${srcdir}/${pkgname}"
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/tvhproxy/LICENSE"
    install -Dm755 tvhProxy.py "${pkgdir}/usr/lib/tvhproxy/tvhProxy.py"
    install -Dm644 ssdp.py "${pkgdir}/usr/lib/tvhproxy/ssdp.py"
    install -Dm644 "${srcdir}/tvhproxy.service" "${pkgdir}/usr/lib/systemd/system/tvhproxy.service"
    install -Dm644 "${srcdir}/tvhproxy.conf.d" "${pkgdir}/etc/conf.d/tvhproxy"
    msg "Don't forget to configure /etc/conf.d/tvhProxy."
}
