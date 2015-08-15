arch=(i686 x86_64)
pkgname=dilmaj-git
pkgver=20120403
pkgrel=1
pkgdesc="Small and fast English-to-Persian dictionary for GNU/Linux console."
url="http://farid.zanjanlug.org"
license="GPL"
depends=('php' 'php-gd')
options=('!strip')

source=()
md5sums=()

_gitroot="git://github.com/pesarkhobeee/Dilmaj.git"
_gitname="master"


build() {
  cd ${srcdir}

  msg "Connecting to GIT server...."
    if [[ -d $_gitname ]]; then
      cd "$_gitname" &&\
      git checkout "$_gitname" &&\
      git pull origin "$_gitname" &&\
  msg "The local files are updated."
    else
      git clone --depth 1 "$_gitroot" "$_gitname" &&\
      cd "$_gitname" &&\
      git checkout "$_gitname"
  fi
  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  chmod +x INSTALL.sh
  ./INSTALL.sh
}
