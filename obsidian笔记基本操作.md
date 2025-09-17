---
tags:
  - obsidian
  - 基本格式
  - 语法
  - markdown
time: 2025-08-24T17:37:00
---
[基本格式语法 - Obsidian 中文帮助 - Obsidian Publish](https://publish.obsidian.md/help-zh/%E7%BC%96%E8%BE%91%E4%B8%8E%E6%A0%BC%E5%BC%8F%E5%8C%96/%E5%9F%BA%E6%9C%AC%E6%A0%BC%E5%BC%8F%E8%AF%AD%E6%B3%95)

[[添加单词Obsidian词典中]]

[Obsidian快速上手，25分钟学会它 你的知识不再遗忘_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1AatPe1Efo/?spm_id_from=333.337.search-card.all.click&vd_source=cfd43301fa3749e57347725fe185aa03)

模板：[讲解一下markdown常用语法，我想对我的笔记进行简单排版 - Kimi](https://www.kimi.com/chat/d334uubof8jsdtckdq3g)

# 课程/书名/会议名
日期：2025-09-14  标签：#数学 #机器学习

## 1 今日目标
- [ ] 搞懂梯度下降推导
- [ ] 跑通 demo 代码
- [ ] 写 300 字总结

## 2 要点记录
### 2.1 定义
损失函数：$$J(\theta)=\frac{1}{2m}\sum_{i=1}^m(h_\theta(x^{(i)})-y^{(i)})^2$$

### 2.2 推导
&gt; 链式法则 + 矩阵求导，详见 [[讲义 p12]](local_path.pdf)

### 2.3 代码
```python
def gd(X, y, lr=0.01):
    m, n = X.shape
    theta = np.zeros(n)
    for _ in range(1000):
        grad = 1/m * X.T @ (X @ theta - y)
        theta -= lr * grad
    return theta