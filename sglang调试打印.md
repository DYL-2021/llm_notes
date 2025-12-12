---
tags:
  - sglang
  - debug
time: 2025-10-30T10:25:00
---
```python utils.py

def logger_debug(is_print,message):

    if is_print:

        logger.info(message)
```
```python
logger_debug(is_print,f'mb_id{mb_id} cur_batch {self.cur_batch}')
```
