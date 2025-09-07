---
tags:
  - linux命令
  - 磁盘
time: 2025-08-24T17:57:00
---
1. 查看磁盘空间命令：**df** 是看“整个分区”还剩多少空间；**du** 是看“某个目录”实际用了多少空间。使用df命令可以查看所有目录挂载的磁盘，列出来的相当于该目录使用改磁盘的空间，否则使用根目录的空间。磁盘空间不够时候先查看这个目录是挂载在哪里，然后查看下级可删除目录文件
	```
	df -h
	#输出示例
	Filesystem                         Size  Used Avail Use% Mounted on
	tmpfs                              101G  4.5M  101G   1% /run
	/dev/mapper/ubuntu--vg-ubuntu--lv  437G  137G  278G  34% /
	tmpfs                              504G  5.1M  504G   1% /dev/shm
	tmpfs                              5.0M     0  5.0M   0% /run/lock
	/dev/sda2                          2.0G  566M  1.3G  31% /boot
	/dev/sda1                          1.1G  6.1M  1.1G   1% /boot/efi
	/dev/mapper/vg0-lv_data            6.9T  2.3T  4.3T  34% /data
	/dev/mapper/vg0-lv_home            6.9T  4.5T  2.1T  69% /home
	fs1.OSCHINA                        2.4P   12T  2.3P   1% /oschina1
	fs0.OSCHINA                        504T   25T  479T   5% /oschina0
	tmpfs                              101G  4.0K  101G   1% /run/user/1002

	```
	```
	du -sh /home/kyzg/models
	#输出示例
	221G    /home/kyzg/models/Qwen3-235B-A22B-int8
	
	#查看目录大小并排序
	du -h --max-depth=1 /home/kyzg | sort -hr | head -n 2
	4.5T    /home/kyzg
	3.1T    /home/kyzg/models
	
	```
2. find命令

- 按名字模糊查找
	```bash
	find /var/log -name "*.log"          # 区分大小写
	find /var/log -iname "*.log"         # 忽略大小写
	```
- 按类型查找
	```bash
	find /etc -type f                    # 普通文件
	find /etc -type d                    # 目录
	find /etc -type l                    # 符号链接
	```
3. 查看文件内容命令

- tail
	```bash
	# tail：显示文件末尾内容。
	# -f（follow）：实时追踪文件新增的内容。
	tail -f /var/log/syslog
	```
4. scp命令
	```bash
	# -P 指定端口（远程 SSH 不是 22 时）
	# 拷贝目录（记得加 -r）
	scp -P 2222 -r ~/project/ user@192.168.1.100:/opt/
	```


