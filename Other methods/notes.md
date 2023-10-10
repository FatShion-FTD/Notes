# 相关文章和其他办法

## Who Wrote this Code? Watermarking for Code Generation

这是垂直领域(写代码) + logits操作的例子

baseline 还是 RG 水印的那个

创新点: 第一个研究 code 领域; 方法足够简单, code 领域有 outperform 基线; code outperform 别的基线 

核心办法: 在 logits 中, 对于 low entropy 的 token, 略过; 只选取 high entropy 的 token 进行替换操作

## 