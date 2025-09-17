---
tags:
  - sglang
  - parallel
  - communication
time: 2025-09-16T16:51:00
---

# 1、考虑PP和TP
   [并行方式通信组问题 | DeepWiki](https://deepwiki.com/search/16pp2-tp8pprank-tprank-gpuid_934cf83f-2f93-4b05-9cac-ca8dbfcc7a9d)
1. 两机16卡，pp2tp8情况，编号情况:
	**节点0（node_rank=0）的8张卡：**

	- GPU 0: pp_rank=0, tp_rank=0, gpu_id=0
	- GPU 1: pp_rank=0, tp_rank=1, gpu_id=1
	- GPU 2: pp_rank=0, tp_rank=2, gpu_id=2
	- GPU 3: pp_rank=0, tp_rank=3, gpu_id=3
	- GPU 4: pp_rank=0, tp_rank=4, gpu_id=4
	- GPU 5: pp_rank=0, tp_rank=5, gpu_id=5
	- GPU 6: pp_rank=0, tp_rank=6, gpu_id=6
	- GPU 7: pp_rank=0, tp_rank=7, gpu_id=7

	所以节点1上的GPU分配是：
	- GPU 0: pp_rank=1, tp_rank=0, gpu_id=0
	- GPU 1: pp_rank=1, tp_rank=1, gpu_id=1
	- GPU 2: pp_rank=1, tp_rank=2, gpu_id=2
	- GPU 3: pp_rank=1, tp_rank=3, gpu_id=3
	- GPU 4: pp_rank=1, tp_rank=4, gpu_id=4
	- GPU 5: pp_rank=1, tp_rank=5, gpu_id=5
	- GPU 6: pp_rank=1, tp_rank=6, gpu_id=6
	- GPU 7: pp_rank=1, tp_rank=7, gpu_id=7

2. 



