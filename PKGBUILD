# Maintainer: bko <aur at bil dot co dot ua>

pkgname=pgadmin4-server
pkgver=8.11
pkgrel=1
pkgdesc='The core server package for pgAdmin. pgAdmin is the most popular and feature rich Open Source administration and development platform for PostgreSQL, the most advanced Open Source database in the world.'
arch=('x86_64')
license=('PostgreSQL')
url='https://www.pgadmin.org/'
depends=('postgresql-libs' 'krb5' 'python-dbus')
provides=('pgadmin4-server')
source=(${pkgname}-${pkgver}-x86_64.deb::"https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/noble/dists/pgadmin4/main/binary-amd64/${pkgname}_${pkgver}_amd64.deb")
sha256sums=('1318b0f0a277b7944e50f1c54461df3c46aff265f75c4cabba646fda376751d9')

package() {
  # Extract package data
  tar -x --zstd -f data.tar.zst -C "${pkgdir}"
  sed -i "s|ALLOW_SAVE_TUNNEL_PASSWORD = False|ALLOW_SAVE_TUNNEL_PASSWORD = True|" "${pkgdir}/usr/pgadmin4/web/config.py"
}
