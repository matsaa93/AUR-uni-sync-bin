# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Matsaa93 <matsaa93@gmail.com>
pkgname=uni-synci-bin
_pkgname=uni-sync
pkgver=0.3.1
#pkgver() {
#  cd "${_sourceName}"
#  git describe --tags | sed 's/^v//'
#}
pkgrel=1
pkgdesc="Uni-Sync : A Synchronization Tool for Lian Li Fan Controllers"
arch=("any")
url="https://github.com/EightB1ts/uni-sync.git"
license=('MIT')
#groups=()
depends=("systemd-libs" "libudev0-shim" "hidapi" "libusb")
makedepends=("git"
             "rust")
checkdepends=()
#optdepends=('to enable uni-sync: systemctl enable uni-sync && sudo systemctl restart uni-sync')
provides=("${_pkgname}")
#conflicts=()
#replaces=()
#backup=()
#options=()
#install=
#changelog=
validpgpkeys=(A90CF879EC922C4751F26A61258971F7992C02F6)
source=("LICENSE" "uni-sync" "uni-sync.service" "uni-sync.json")
noextract=()
sha256sums=('c8fe62ed278d3c8b6e9ab88c9e5b5d8db131a65b2040eb0f6e38e25b8f0fc6c9'
            '57e8dbf2787383207cf4ca6601ea9c14912950e03c1beda9c9f16df80957227d' 
            'bb8e21acc5c1b38ca120ac355f4cf326a49e31a9f528eed88a302a9ae0a498ee' 
            '1e905f9eb8f3132833a438a6df1066ee348280d100b07cced8bbb0f594810269')
validpgpkeys=()

#pkgver() {
#  cd $srcdir/${_pkgname}
#  printf "0.3.1r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
#}

#prepare() {
#	cd "$srcdir"
#	patch -u ${_pkgname}/uni-sync.service -i "uni-sync.service.patch"
#}

#build() {
#	cd "$srcdir/${_pkgname}"
#    cargo build --release
#    mv target/release/uni-sync .
#    rm -rf ./target
#	#./configure --prefix=/usr
#	#make
#}

#check() {
#	cd "$pkgname-$pkgver"
#	make -k check
#}

package() {
	cd "$srcdir"
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm755 ${_pkgname}.service "${pkgdir}/etc/systemd/system/${_pkgname}.service"
    install -Dm755 ${_pkgname}.json "${pkgdir}/etc/uni-sync/${_pkgname}.json"
    install -Dm755 ${_pkgname} "${pkgdir}/usr/bin/${_pkgname}"
	#make DESTDIR="$pkgdir/" install
}
