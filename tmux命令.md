---
tags:
  - tmux
time: 2025-09-08T15:40:00
---

```bash
# 窗口同步
setw -g synchronize-panes off
```
```bash
# 设置鼠标
vim ~/.tmux.conf
set -g mouse on
tmux source-file ~/.tmux.conf
```
```tmux
# 设置日志行数
vim ~/.tmux.conf
set-option -g history-limit 10000
tmux source-file ~/.tmux.conf

```
