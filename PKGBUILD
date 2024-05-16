# Maintainer: Nick Syntychakis <nsyntych@punkops.dev>

pkgname=aws-cli-v2-bin
# https://github.com/aws/aws-cli/raw/v2/CHANGELOG.rst
pkgver=2.15.51
pkgrel=1
epoch=1
pkgdesc='Unified command line interface for Amazon Web Services (version 2) (binary release)'
arch=(x86_64 aarch64)
url='https://aws.amazon.com/cli/'
license=('Apache')
depends=()
optdepends=()
provides=(aws-cli)
conflicts=(aws-cli aws-cli-v2)
install=aws-cli-v2-bin.install

source=("aws_bash_completer"
        "aws_zsh_completer.sh")

sha256sums=('451a681062516a0473c8764a6593b0a65b6e558bf6128899b1d5e19b258f679e'
            '426e99f1e8cd00cce9263693d29ceac5b4834f6cf1766cd57b985a440eea2e87')

source_x86_64=(${pkgname}-${pkgver}-x86_64.zip::https://awscli.amazonaws.com/awscli-exe-linux-x86_64-${pkgver}.zip)
source_aarch64=(${pkgname}-${pkgver}-aarch64.zip::https://awscli.amazonaws.com/awscli-exe-linux-aarch64-${pkgver}.zip)

sha256sums_x86_64=('0dbb53f5cf49c9699d0a7b7fb7cd70f2b2b50e664928cdd645377557f2df7a1c')
sha256sums_aarch64=('ab9ac09ea7a02c775859235b055af48c24c9f007fcbe1c8b7ef632eef47b68b8')
validpgpkeys=(
  'FB5DB77FD5C118B80511ADA8A6310ACC4672475C'  # the key mentioned on https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
)

package() {
	mkdir -p $pkgdir/usr/local/aws-cli
  	mv aws/dist $pkgdir/usr/local/aws-cli/v2
	install -Dm644 aws_bash_completer $pkgdir/usr/share/bash-completion/completions/aws
	install -Dm644 aws_zsh_completer.sh $pkgdir/usr/bin/aws_zsh_completer.sh
	ln -sf /usr/local/aws-cli/v2/aws $pkgdir/usr/bin/aws
	ln -sf /usr/local/aws-cli/v2/aws_completer $pkgdir/usr/bin/aws_completer
}
