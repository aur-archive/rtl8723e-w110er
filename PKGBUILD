# Maintainer: # Maintainer: blackleg <hectorespertpardo@gmail.com>

pkgname=rtl8723e-w110er
#pkgname=rtl8723e
pkgver=3.6.8
pkgrel=4
pkgdesc="Realteck kernel module for the rtl8723e. (Linux-w110er kernel)"
#pkgdesc="Realteck kernel module for the rtl8723e."
arch=("x86_64")
#arch=("i686" "x86_64")
url=https://github.com/tianon/linux-rtlwifi-8188ce
license=(unknown)
groups=(modules)
depends=("linux-w110er=${pkgver}" "linux-firmware")
#depends=("linux=${pkgver}" "linux-firmware")
makedepends=(linux-w110er-headers=${pkgver})
#makedepends=(linux-headers=${pkgver})
source=("https://github.com/tianon/linux-rtlwifi-8188ce/archive/master.zip" "rtl8723e.install")

md5sums=('beb040e518a5f00a4ded4e2b52e8a7db'
         '65e80822383eded228812f985a95353d')

install=rtl8723e.install

build() {

	cd "${srcdir}/linux-rtlwifi-8188ce-master"
	make ${MAKEFLAGS}
}
package() {

	cd "${srcdir}/linux-rtlwifi-8188ce-master"

	#mkdir -p "$pkgdir/lib/firmware/rtlwifi"
	#install -p -m 644 ./firmware/rtlwifi/rtl8723*.bin  "$pkgdir/lib/firmware/rtlwifi"

	mkdir -p "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi"
	#mkdir -p "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192se"
	#mkdir -p "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192ce"
	#mkdir -p "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192de"
	mkdir -p "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8723e"

	install -p -m 644 rtlwifi.ko  "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/newrtlwifi.ko"
	#install -p -m 644 ./rtl8192se/rtl8192se.ko  "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192se"
	#install -p -m 644 ./rtl8192ce/rtl8192ce.ko  "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192ce"
	#install -p -m 644 ./rtl8192de/rtl8192de.ko  "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8192de"
	install -p -m 644 ./rtl8723e/rtl8723e.ko  "$pkgdir/lib/modules/`uname -r`/kernel/drivers/net/wireless/rtlwifi/rtl8723e"
	
	find "${pkgdir}" -name '*.ko' -exec gzip -9 {} \;
	
}
