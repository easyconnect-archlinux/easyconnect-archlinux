pkgname=easyconnect
pkgver=7.6.7.3.76b7ebc57725ae1e999151cdc215f8e7cef8a31b
pkgrel=1
pkgdesc="Support access to ssl vpn. With easyconect，you can secure and speed up connection to cooperate network at ease!"
arch=('x86_64')
url="http://www.sangfor.com.cn"
license=('custom')
install=${pkgname}.install
source=("http://download.sangfor.com.cn/download/product/sslvpn/pkg/linux_767/EasyConnect_x64_7_6_7_3.deb")
md5sums=('3b690ab4a7752b120d8200d817721187')

package(){
        depends=(lib32-gtk2)
        
        tar xzf data.tar.gz -C "${pkgdir}"
        mkdir -p ${pkgdir}"/usr/share/sangfor/EasyConnect/oldlib/pango"
        tar xf ${srcdir}/../pango-1_1.42.4-1-x86_64.pkg.tar.xz -C ${pkgdir}"/usr/share/sangfor/EasyConnect/oldlib/pango"
        cd ${pkgdir}
        sed -i 's/Exec=/Exec=env LD_LIBRARY_PATH=\/usr\/share\/sangfor\/EasyConnect\/oldlib\/pango\/usr\/lib /g' "${pkgdir}/usr/share/applications/EasyConnect.desktop"
        install -D -m644 "${pkgdir}/usr/share/sangfor/EasyConnect/LICENSES.chromium.html" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}