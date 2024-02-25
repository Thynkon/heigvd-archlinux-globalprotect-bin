# Maintainer: Darkfish Tech <arch at darkfish dot com dot au>

pkgname=globalprotect-bin
pkgver=6.1.3.0
pkgrel=703
pkgdesc="GlobalProtect VPN Client Agent for HEIG-VD"
arch=('x86_64')
url="https://vpn.heig-vd.ch"
license=('custom')
groups=()
depends=('qt5-webkit' 'wmctrl')
options=()
install=globalprotect.install
source=(
	"GlobalProtect_UI_focal_deb-${pkgver}-${pkgrel}.deb"
	"heigvd-pangps.xml"
)
sha256sums=(
	'851b070171e4ec7f16f0820e7b9d7e6fa4afbe06b46980fbd854c593d7f2421b'
	'22da22cd4e3a0a9c23eff4a2997a44cd673acf6b6c72f336d405d659a63a3583'
)
package() {
	tar -xf data.tar.xz -C "$pkgdir/"

	# Adapted for Arch Linux from debian package postinst
	GPDIR="$pkgdir/opt/paloaltonetworks/globalprotect"

	# Install system and user services
	install -Dm644 $GPDIR/gpd.service "${pkgdir}/usr/lib/systemd/system/gpd.service"
	install -Dm644 $GPDIR/gpa.service "${pkgdir}/usr/lib/systemd/user/gpa.service"

	# Install desktop and autostart files
	install -Dm644 $GPDIR/gp.desktop "${pkgdir}/usr/share/applications/gp.desktop"
	install -Dm644 $GPDIR/PanGPUI.desktop "${pkgdir}/etc/xdg/autostart/PanGPUI.desktop"

	# Install executables
	install -Dm755 $GPDIR/globalprotect "${pkgdir}/usr/bin/globalprotect"
	install -Dm755 $GPDIR/PanGPUI "${pkgdir}/usr/bin/PanGPUI"

	# Install custom configuration for HEIG-VD
	install -Dm644 "$srcdir"/heigvd-pangps.xml $GPDIR/pangps.xml

}
