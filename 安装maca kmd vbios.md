---
tags:
  - metax
  - maca
  - kmd
  - vbios
time: 2025-09-09T14:29:00
---

# 下载deb

wget maca-xxxx-xxx-deb.tar.xz

# 解压

XZ_OPT='-T0' tar xvJf maca-xxx-xxx-deb.tar.xz

# 卸载原有版本

sudo /opt/maca/bin/mxmaca-sdk-install.sh -U

# 安装新版本

sudo ./mxmaca-sdk-install.sh -f

先装driver

cd /mnt/dataset/yapan/

bash metax-driver-mxc500-20250326-366-deb-x86_64.run -- -f

再装vbios

cd /lib/firmware/metax/mxc500

sudo mx-smi -u mxvbios-1.25.0.0-766-C550.bin

sudo mx-smi -r -i all