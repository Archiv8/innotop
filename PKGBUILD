#!/bin/bash

# Based on the original PKGBUILD by Jonathan Steel <jsteel at archlinux.org>, Massimiliano Torromeo <massimiliano.torromeo@gmail.com> and Nassim Kacha <nassim.kacha@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/innotop/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/innotop/discussions>

pkgname=innotop
pkgver=1.13.0
pkgrel=5
pkgdesc="A powerful 'top' clone for MySQL (MariaDB)"
arch=(
  "any"
)
url="https://github.com/innotop/innotop"
license=(
  "GPL2"
)
depends=(
  "perl-dbd-mysql"
  "perl-term-readkey"
)
options=(
  "!emptydirs"
)
source=(
  "https://github.com/innotop/innotop/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz"
)
sha512sums=(
  "827a6ec36355af023d24b85afdaabac44ef0c33c853c133d39f0725b2da3585cf1bc7b21e501d436a28ac6b798d9d502b4a81c2c9c28373abf91543519b4f45a"
)

build() {

  cd ${pkgname}-${pkgver}

  perl Makefile.PL
}

package() {

  cd ${pkgname}-${pkgver}

  make INSTALLSITESCRIPT=/usr/bin DESTDIR="${pkgdir}"/ install
}
