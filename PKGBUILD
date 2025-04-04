# Maintainer: Knut Ahlers <knut at ahlers dot me>
# Contributor: Oscar Garcia Amor <ogarcia@connectical.com>

arch=('x86_64')
backup=('etc/vault.hcl')
conflicts=('vault' 'vault-git')
install='vault.install'
license=('MPL')
pkgname=vault-bin
pkgdesc='A tool for managing secrets'
pkgrel=1
pkgver=1.19.1
url='https://vaultproject.io/'
source=(
	'vault.tmpfiles'
	'vault.sysusers'
	'vault.service'
	'vault.hcl'
	"LICENSE_${pkgver}::https://raw.githubusercontent.com/hashicorp/vault/v${pkgver}/LICENSE"
	"https://releases.hashicorp.com/vault/${pkgver}/vault_${pkgver}_linux_amd64.zip"
)
sha512sums=('aa56041c53434195dbf544ce9bf18d7bfb530bf65c9b692163621185b0a46035273a4eeda6454ceb93201117f23662e44ac9c88eda3cf12153cdce40df0fde09'
            '92616ccf83fa5ca9f8b0d022cf8ceb1f3549e12b66bf21d9f77f3eb26bd75ec1dc36c155948ec987c642067b85fbfc30a9217d6c503d952a402aa5ef63e50928'
            'a97d10208fd99b29cf532c9b5882fe1bbb3faee1d1d706f95a9c379fef461c65a9f16c8530438920024e69871ebd8c7329e6b65025ad65092950bfb74ce393b3'
            '8f8769f2c285f77b10c1f96e43acb233c70509ca657a8113f9d1f13a73ba55de6acdc6984597a4e1da19d6a7748e05f3523461a3b4bce10b9541aa5340400dd6'
            'cc03a3d13acf4a091fe2edb9e59923abe77d9d04d7ccfe3d91c1732316365e5fc7971d5102e2a88aaa25071a86b7848a0fd6ff74c3cd7e77bb9d2a501efc750e'
            'f13690d4fbf1b58f825f0f1cf94d140b518501797fbe62c98696f8948bbd7070baffda664282d904ebebefb1ddaba0ef5614cf1f26460dc830b037494295458e')

package() {
	install -Dm755 vault "${pkgdir}/usr/bin/vault"
	install -Dm644 "LICENSE_${pkgver}" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 "${srcdir}/vault.hcl" "${pkgdir}/etc/vault.hcl"
	install -Dm644 "${srcdir}/vault.service" "${pkgdir}/usr/lib/systemd/system/vault.service"
	install -Dm644 "${srcdir}/vault.sysusers" "${pkgdir}/usr/lib/sysusers.d/vault.conf"
	install -Dm644 "${srcdir}/vault.tmpfiles" "${pkgdir}/usr/lib/tmpfiles.d/vault.conf"
}
