# Maintainer: Librewish <librewish@gmail.com>
# Contributor: Mark Wagie <mark dot wagie at tutanota dot com>
# Contributor: Paul Kasemir <paul.kasemir@gmail.com>
pkgname=find-the-command
pkgver=2.0.3
pkgrel=1
pkgdesc="Advanced command-not-found hook for bash, fish, and zsh using the power of pacman"
arch=('any')
url="https://github.com/Froggo8311/find-the-command"
license=('custom:WTFPL')
depends=('pacman')
optdepends=('fzf: highly recommended for package selection and previews'
            'pacman-contrib: for weekly pacman-filesdb-refresh.timer'
            'pkgfile: provides faster searches than pacman'
            'sudo: helpful for privilege elevation')
makedepends=('git')
provides=("${pkgname%}")
conflicts=("${pkgname%}")
install="${pkgname%}.install"
options=('docs')
source=('git+https://github.com/Froggo8311/find-the-command.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/${pkgname%-git}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "$srcdir/${pkgname%-git}"
  install -Dm644 README.md usr/share/doc/"${pkgname%}"/ftc.* -t \
    "$pkgdir/usr/share/doc/${pkgname%}"
  install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/${pkgname%}"
}
