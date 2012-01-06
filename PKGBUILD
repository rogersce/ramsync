# Maintainer: graysky <graysky AT archlinux DOT us>

pkgname='ramsync'
pkgver=1.0
pkgrel=1
pkgdesc='Symlinks and syncs dirs to RAM thus reducing HDD/SDD calls and speeding up apps.'
arch=('any')
#url='https://wiki.archlinux.org/index.php/Ramsync'
license=('GPL')
depends=('rsync')
optdepends=('cron: allow hourly (default) or periodic syncs of tmpfs <--> HDD/SDD storage')
conflicts=('firefox-sync' 'firefox-tmpfs-daemon' 'chromium-tmpfs' 'tmpfs-store')
#replaces=('sync-browsers-daemon')
source="https://github.com/rogersce/ramsync-daemon/raw/master/$pkgname-source.tar.xz"
backup=("etc/$pkgname.conf")
install=readme.install
sha256sums=('6530662ab35b96f9f715a211d76efe92eeb9e9f926c905965a574cd561dcd6ce')

package() {
	cd "$srcdir/src"
	install -Dm644 $pkgname.conf "$pkgdir/etc/$pkgname.conf"
	install -Dm755 rc.$pkgname "$pkgdir/etc/rc.d/$pkgname"
	install -Dm755 $pkgname.cron.hourly "$pkgdir/etc/cron.hourly/$pkgname-update"
}
