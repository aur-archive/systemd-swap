# Maintainer: Timofey Titovets <Nefelim4ag@gmail.com>
pkgname=systemd-swap
pkgver=2.19
pkgrel=1
pkgdesc="This is script for creating hybrid swap space from zram swaps, swap files and swap partitions. Swap file - auto create dinamic growing swap file and mount it via loop. For enable: sudo systemctl enable systemd-swap. Config in /etc/systemd-swap.cfg"
arch=('any')
url="https://github.com/TimofeyTitovets/systemd-swap"
license=('GPL3')
conflicts=(systemd-loop-swapfile zramswap zram)
replaces=(systemd-loop-swapfile zramswap zram)
depends=('systemd' 'bash')
makedepends=('git')
backup=(etc/systemd-swap.conf)
source=("$pkgname"::'git://github.com/TimofeyTitovets/systemd-swap.git#branch=master')
md5sums=( 'SKIP' )

package() {
    install -Dm644 $srcdir/$pkgname/systemd-swap.service $pkgdir/etc/systemd/system/systemd-swap.service
    install -Dm755 $srcdir/$pkgname/systemd-swap.sh      $pkgdir/usr/lib/systemd/scripts/systemd-swap.sh
    install -Dm644 $srcdir/$pkgname/systemd-swap.conf    $pkgdir/etc/systemd-swap.conf
}