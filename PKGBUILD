# Maintainer: Gen2ly <toddrpartridge@gmail.com>

pkgname=gnome-shell-extension-bolt-git
pkgver=20120830
pkgrel=1
pkgdesc="Launcher that fuses the Ubuntu dash and the GNOME shell overview"
arch=('any')
url="https://github.com/zacbarton/gnome-shell-extension-bolt"
license=('GPL')
depends=('gnome-shell' 'xorg-xprop' 'zeitgeist')
install=

_gitroot="git://github.com/zacbarton/gnome-shell-extension-bolt"
_gitname="gnome-shell-extension-bolt"

build() {

  cd "$srcdir/"

  msg "Connecting to GIT server..."
  if [ -d $_gitname ]; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone --depth=1 $_gitroot $_gitname
  fi
  msg "GIT checkout done or server timeout"

}

package() {
  cd      "$srcdir/$_gitname"
  ext_dir="bolt@zacbarton.com"
  mkdir -p "$pkgdir/usr/share/gnome-shell/extensions/"
  cp -a   "$ext_dir" "$pkgdir/usr/share/gnome-shell/extensions/"
  # Give regular user permissions to parent directory and files as settings get 
  # stored here?
  chmod -R 0666 "$pkgdir/usr/share/gnome-shell/extensions/"$ext_dir""
  chmod    0777 "$pkgdir/usr/share/gnome-shell/extensions/"$ext_dir""
}

# vim:set ts=2 sw=2 et: