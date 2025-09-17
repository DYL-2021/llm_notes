---
tags:
  - sglang
  - WSL
  - 部署
time:
---
# 1 docker方法
1. [[wsl 启动docker]]
2. [需要做一些代理配置，使用windows的梯子才能拉镜像 - Kimi](https://www.kimi.com/chat/d336b298bjvmdfehi5k0)；确保 **Windows 代理开 LAN 模式**；
3. 更换国内镜像源[Docker 镜像断点续传及WSL2 DNS配置 - Kimi](https://www.kimi.com/chat/d3391818bjvmdff7jpq0)
4. `docker pull lmsysorg/sglang:latest`
5. WSL安装GPU驱动[我在WSL容器中启动容易说没有cuda，我的主机上已经安装了 - Kimi](https://www.kimi.com/chat/d33ag2jacc48jctgdoeg)
6. 
```
docker run -it --net=host --uts=host --ipc=host --device=/dev/dri --device=/dev/mxcd --privileged=true --group-add video --security-opt seccomp=unconfined --security-opt apparmor=unconfined --shm-size 16gb --ulimit memlock=-1 --gpus all --name dyl_sgl  -v /mnt/e/work/MetaX/AI/:/mnt/e/work/MetaX/AI/  fce5585fa8da  /bin/bash
```
7. 模型获取，量化模型获取：[deepseekr1的裁剪模型在哪里找 - Kimi](https://www.kimi.com/chat/d33auujof8jsdte4nuh0)

8. `python3 -m sglang.launch_server --model-path /mnt/e/work/MetaX/AI/sglang/models/DeepSeek-V2-Lite-w8a8-2layers/ --trust-remote-code`
# 2 直接安装方法
1. [查看sglang关键依赖库版本 | DeepWiki](https://deepwiki.com/search/sglangpytorch_488589d4-410e-44fd-87ed-75766e1c5da5)
2. 查看pytorch版本对应的cuda版本[Previous PyTorch Versions](https://pytorch.org/get-started/previous-versions/)
3. 根据硬件信息选择合适的cuda版本进行安装[win11+RTX4070Ti 安装 CUDA + cuDNN（图文教程）_window 4070安装cuda和cudnn-CSDN博客](https://blog.csdn.net/ZChen1996/article/details/134772066)
4. [(4 条消息) 超详细 CUDA 安装与卸载教程（图文教程） - 知乎](https://zhuanlan.zhihu.com/p/23071389812)
5. 