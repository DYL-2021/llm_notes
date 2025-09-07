---
tags:
  - sglang
  - client
  - generate_request
time: 2025-09-05T15:40:00
---
![[Pasted image 20250905154020.png]]
- 每个node都运行launch_server进程
- launch_server进程会启动子进程，每个GPU对应一个scheduler子进程
![[Pasted image 20250905154456.png]]

- 主节点会启动tokenizer or detokenizer，其它节点的launch_server进程等待在这里，直至scheduler进程退出
- 主节点launch_server进程从这里返回会进入下面启动fastapi,接收客户端请求进行推理
	- ![[Pasted image 20250906160432.png]]
	- ![[Pasted image 20250906160546.png]]
- [Search generate_request用户交互接口| DeepWiki](https://deepwiki.com/search/client-payload-text-if-isinsta_7c5915a8-8f83-49c3-a890-d7676902cb43)
- generate_request会自动转化client端的json结构的请求为GenerateReqInput，然后调用推理引擎，并返回推理结果