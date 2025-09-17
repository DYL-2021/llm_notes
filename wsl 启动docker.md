---
tags:
  - WSL
  - docker
---

1. 手动启动docker
```bash
sudo nohup dockerd \
  --host=unix:///var/run/docker.sock \
  --host=tcp://0.0.0.0:2375 \
  > /var/log/dockerd.log 2>&1 &
```
```bash
dockerd \
  --host=unix:///var/run/docker.sock \
  --host=tcp://0.0.0.0:2375 \
  > /var/log/dockerd.log 2>&1 &
```

2. [Windows 11：Docker Desktop 安装和配置指南 - 系统极客](https://www.sysgeek.cn/install-docker-desktop-windows-11/)