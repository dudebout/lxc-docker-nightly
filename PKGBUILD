# Maintainer: Nicolas Dudebout <nicolas.dudebout@gatech.edu>
pkgname=lxc-docker-nightly
pkgver=0.7.0rc4
pkgrel=1
pkgdesc='Docker: the Linux container engine'
arch=('x86_64')
url='http://www.docker.io'
license=('Apache')
# https://github.com/dotcloud/docker/blob/master/hack/PACKAGERS.md#runtime-dependencies
depends=('tar>=1.26'
         'iproute2>=3.5'
         'iptables>=1.4'
         'lxc>=0.8'
         'git>=1.7'
         'xz>=4.9')
provides=('lxc-docker-nightly')
conflicts=('lxc-docker' 'lxc-docker-git')
# See https://test.docker.io/ubuntu/dists/docker/main/binary-amd64/Packages for a list of available binaries
source=("docker::http://test.docker.io/builds/Linux/$arch/docker-0.7.0-rc4"
        'docker.service')
sha512sums=('SKIP'
            'f6e1f6cc2ed66cd3eb674383326d52dc1fad0599677103b1539ae7002d06e6458c2bc5dc9a04b2024058b5b2aa3cf9211a200acebbd93ab1016d48ed849d2499')

package() {
  install -D -m 755 "$srcdir/docker" "$pkgdir/usr/bin/docker"
  install -D -m 644 "$srcdir/docker.service" "$pkgdir/usr/lib/systemd/system/docker.service"
}
