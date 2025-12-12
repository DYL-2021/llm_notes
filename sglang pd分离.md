---
tags:
  - sglang
  - pd分离
time: 2025-10-24T14:27:00
---

[Search | DeepWiki](https://deepwiki.com/search/popbootstrapped_047a211f-e7ce-458c-bddf-5e0fad7f81a3?mode=fast)

![[Pasted image 20251024143421.png]]


![[Pasted image 20251024143522.png]]
Prefill 端: 
1. Bootstrap 完成 → wait_queue_entry_time 
2. Prefill forward → forward_entry_time 
3. Forward 完成 → 调用 send_kv_chunk() 
4. 进入 inflight 队列 → prefill_transfer_queue_entry_time 
5. 传输完成 → completion_time 

Decode 端: 
1. Bootstrap 完成 → decode_transfer_queue_entry_time 
2. 等待传输 → 轮询 KVPoll 状态 
3. 传输完成 → wait_queue_entry_time 
4. Decode forward → forward_entry_time