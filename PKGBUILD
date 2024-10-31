# Maintainer: Jackson Massey <jackmassey2000@gmail.com>

pkgname=cudnn
pkgver=9.5.1.17
_cudaver=12
pkgrel=1
pkgdesc="NVIDIA CUDA Deep Neural Network library"
url="https://developer.nvidia.com/cuDNN"
arch=('x86_64')
license=('custom')
depends=('cuda>='"${_cudaver}")
options=(!strip staticlibs)

source=("https://developer.download.nvidia.com/compute/cudnn/redist/cudnn/linux-x86_64/cudnn-linux-x86_64-${pkgver}_cuda${_cudaver}-archive.tar.xz"
        "NVIDIA_SLA+cuDNN_Supp_Feb2017_release.pdf")
b2sums=('a0e7b64b37b47d115983da40f8236deb66e7b3244f9eecf7eb52b8b1b413d759d01b6bbab9ddd649fd65d557e2ff512c5ac4c0af3c443af98dede707355c5c52'
        '222e3d3640808a130dfc339fa8e48ea396f784af77d09d90fae1e5550de8272e643d9a765d832b3d950234a3f7a8706a12191d49717f732cff190e5fd920ed52')

package() {
  cd cudnn-linux-x86_64-${pkgver}_cuda${_cudaver}-archive

  mkdir "$pkgdir"/usr
  cp -r lib include "$pkgdir"/usr

  install -Dm644 LICENSE "${pkgdir}"/usr/share/licenses/${pkgname}/LICENSE
  install -Dm644 \
      "${srcdir}"/NVIDIA_SLA+cuDNN_Supp_Feb2017_release.pdf \
      "${pkgdir}"/usr/share/licenses/"${pkgname}"/NVIDIA_SLA+cuDNN_Supp_Feb2017_release.pdf
}

