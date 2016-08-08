# This package should install (as dependencies) and configure all of the software that makes up Alan's DE.

# Maintainer: Alan Reed
pkgname=ChromebookConfig-git # '-bzr', '-git', '-hg' or '-svn'
pkgver=0.1
pkgrel=1
pkgdesc="Alan's Chromebook Config"
arch=('x86_64')
license=('unknown')

depends=('xf86-input-synaptics')

makedepends=('git') 

provides=("${pkgname%-git}")
install=

source=('git+https://github.com/alanpreed/ChromebookConfig.git')
md5sums=('SKIP')


pkgver() {
	cd "$srcdir/${pkgname%-git}"

	# Git, no tags available (from example PKGBUILD)
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
	cd "$srcdir/${pkgname%-git}"



md5sums=('SKIP')

package() {
	#Configure touchpad
	install -d $pkgdir/etc/X11/xorg.conf.d/
	cp -r configs/xf86-input-synaptics/. $pkgdir/etc/X11/xorg.conf.d/

	# Disable suspend on lid close
	install -d $pkgdir/etc/systemd/logind.conf.d/
	cp -r configs/logind/. $pkgdir/etc/systemd/logind.conf.d/
}
