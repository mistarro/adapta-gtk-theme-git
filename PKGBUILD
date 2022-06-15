# Maintainer : Michal Staromiejski <michal.staromiejski@gmail.com>
# Contributor: Yamada Hayao <hayao@fascode.net>
# Contributor: Maxime Gauduin <alucryd@archlinux.org> 
# Contributor: Phillip Schichtel <phillip.public@schich.tel>

pkgname='adapta-mint-gray-git'
pkgver=3.95.0.16.r1
pkgrel=1
pkgdesc='A flat gray theme with mint accents based on Adapta.'
arch=('any')
url='https://github.com/mistarro/adapta-mint-gray-git'
license=('GPL2')
depends=('gtk-engine-murrine' 'gtk3')
makedepends=('git' 'gnome-shell' 'inkscape' 'libxml2' 'parallel' 'sassc')
optdepends=('gnome-shell: The GNOME Shell'
            'gnome-flashback: The GNOME flashback shell'
            'budgie-desktop: The Budgie desktop'
            'cinnamon: The Cinnamon desktop'
            'xfdesktop: The Xfce desktop')
conflicts=('adapta-gtk-theme')
source=('git+https://github.com/mistarro/adapta-mint-gray.git')
sha256sums=('SKIP')

pkgver() {
  cd adapta-mint-gray
  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd adapta-mint-gray

  ./autogen.sh \
    --prefix='/usr' \
    --enable-parallel \
    --with-selection_color=#A3BE8C \
    --with-accent_color=#A3BE8C \
    --with-suggestion_color=#A3BE8C
  make
}

package() {
  cd adapta-mint-gray
  make DESTDIR="${pkgdir}" install
}

