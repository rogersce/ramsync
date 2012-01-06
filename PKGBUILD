# Maintainer: rogersce <carl DOT rogers AT gmail DOT com>

pkgname='ramsync'
pkgver=1.0
pkgrel=1
pkgdesc='Links and syncs dirs to RAM'
arch=('any')
#url='https://wiki.archlinux.org/index.php/Ramsync'
license=('GPL')
depends=('rsync')
optdepends=('cron: allow hourly (default) or periodic syncs of tmpfs <--> HDD/SDD storage')
conflicts=('firefox-sync' 'firefox-tmpfs-daemon' 'chromium-tmpfs' 'tmpfs-store')
source="https://github.com/rogersce/ramsync/tarball/v$pkgver"
backup=("etc/$pkgname.conf")
sha256sums=('d3032c42903844580d101ee3dae056ca58b50d6a7bf1170cfb52bda66d55d9b5')
package() {
	mv $srcdir/rogersce* $srcdir/$pkgname
        cd $srcdir/$pkgname/src
	install -Dm644 $pkgname.conf "$pkgdir/etc/$pkgname.conf"
	install -Dm755 rc.$pkgname "$pkgdir/etc/rc.d/$pkgname"
	install -Dm755 $pkgname.cron.hourly "$pkgdir/etc/cron.hourly/$pkgname-update"
}
