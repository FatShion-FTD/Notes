# RG 相关文章
这些文章都是使用 R 和 G 作为 baseline, 基本方法没有什么大的区别

## Who Wrote this Code? Watermarking for Code Generation

这是垂直领域(写代码) + logits操作的例子

核心办法: 在 logits 中, 对于 low entropy 的 token, 略过; 只选取 high entropy 的 token 进行替换操作

## Advancing Beyond Identification: Multi-bit Watermark for Large Language Models

多位水印

核心办法: 操作对象依然是 tokens，依然依靠 logits 调整分布，2分变2^N分，将信息比如：1-15，编码对应到个4区间，然后在生成token时候，把 token 分为4类，依然采取软水印的形式进行选择, 选择时候从高到低进行排序, 并按照需要的编码需求选择. 

物理理解: 一个text, 里面每个 token 都是 4种颜色之一, 统计各种颜色出现的次数, 绘制频谱, 得出编码信息

## Towards Codable Text Watermarking for Large Language Models

多位水印

核心办法: 有一个来自 模型的 logit, 和一个水印的 logits, 求二者交集, 特别是其中对二者效果都好的 logits

## Watermarking Conditional Text Generation for AI Detection: Unveiling Challenges and a Semantic-Aware Watermark Remedy

单位水印

核心办法: 在 生成 R 和 G list 前, 根据 s(t-1) 时刻的文本, 构建一个语义相似矩阵, 把语义相似的 token 放到一起再生成 R 和 G

## Provable Robust Watermarking for AI-Generated Text

单位水印

核心办法: 对抗思想, 使用另一个 LM 去做 logits 对抗, 然后训练个新模型