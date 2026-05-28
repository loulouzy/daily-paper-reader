---
title: Visual Anchors Are Strong Information Aggregators For Multimodal Large Language Model
title_zh: 视觉锚点：多模态大语言模型的强力信息聚合器
authors: "Haogeng Liu, Quanzeng You, Xiaotian Han, Yongfei Liu, Huaibo Huang, Ran He, Hongxia Yang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=2YPdpWzEsF"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 新的视觉语言连接器用于MLLM
tldr: 本文提出Anchor Former（AcFormer），一种针对多模态大语言模型的新型视觉语言连接器。首先揭示了Vision Transformer中存在视觉锚点，并设计低成本搜索算法逐步提取它们。AcFormer利用这些视觉锚点实现了高准确率和低计算成本。该方法显著提升了MLLM在多模态理解任务上的效率与性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1358, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 812, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 1342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-2ypdpwzesf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1396, \"height\": 876, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1245, \"height\": 736, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1229, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1460, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-2ypdpwzesf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1468, \"height\": 456, \"label\": \"Table\"}]"
motivation: 现有视觉语言连接器探索不足，难以同时实现高精度和低计算。
method: 发现视觉锚点并设计搜索算法提取，构建AcFormer连接器。
result: 在多项任务上达到更高精度且计算成本更低。
conclusion: 视觉锚点可作为有效的视觉信息聚合手段。
---

## Abstract
In the realm of Multimodal Large Language Models (MLLMs), vision-language connector plays a crucial role to link the pre-trained vision encoders with Large Language Models (LLMs). Despite its importance, the vision-language connector has been relatively less explored. In this study, we aim to propose a strong vision-language connector that enables MLLM to simultaneously achieve high accuracy and low computation cost. We first reveal the existence of the visual anchors in Vision Transformer and propose a cost-effective search algorithm to progressively extract them. Building on these findings, we introduce the Anchor Former (AcFormer), a novel vision-language connector designed to leverage the rich prior knowledge obtained from these visual anchors during pretraining, guiding the aggregation of information. 
Through extensive experimentation, we demonstrate that the proposed method significantly reduces computational costs by nearly two-thirds, while simultaneously outperforming baseline methods. This highlights the effectiveness and efficiency of AcFormer.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
多模态大语言模型（MLLMs）通过视觉语言连接器将预训练的视觉编码器与大语言模型（LLMs）连接起来。现有连接器设计探索不足：简单线性投影（如LLaVA）使用大量视觉标记（577个）导致计算成本高；而基于可学习查询的聚合器（如Q-Former、Perceiver Resampler）虽然减少了视觉标记数量，但需要海量数据训练且容易丢失信息，准确率下降。本文旨在设计一种既能保持高准确性又能显著降低计算成本的强视觉语言连接器。核心发现是Vision Transformer中存在“视觉锚点”——在特征图和注意力图中表现为少数高激活的标记，它们充当信息聚合的中心。基于此提出Anchor Former（AcFormer），利用这些视觉锚点的先验知识来高效聚合视觉信息。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：预训练的Vision Transformer在特征变换过程中，信息逐渐聚焦到少量视觉锚点上（[CLS] token和其他高注意力标记），这些锚点天然具有信息聚合能力。AcFormer利用这些锚点作为信息聚合器，代替随机初始化的可学习查询。
- **关键技术**：
  - **锚点选择器（Anchor Selector）**：利用最后层[CLS] token的注意力图，通过递进搜索算法按注意力头依次选取高注意力标记。算法首先将[CLS] token（索引0）作为必选锚点，然后对每个注意力头，按注意力分数排序后从高到低选择`(T-1)/H`个标记（H为头数），若重复则顺延下一个。
  - **信息聚合模块**：将选中的视觉锚点作为查询，原始视觉标记作为键和值，通过交叉注意力（双向Transformer编码器）进行信息聚合，再经过前馈网络。该模块以6层、隐藏维度512、8注意力头配置运行。
  - **最终输入**：聚合后的隐藏状态通过线性投影与文本嵌入拼接，送入LLM。
- **公式流程**：输入图像I → Vision Transformer提取特征`R_v` → 锚点选择器从注意力图中选出`TN+1`个锚点作为信息聚合器`IA` → 交叉注意力：`Aout = IA + Attn(query=LN(IA), key=LN(R_v), value=LN(R_v))` → `H = Aout + FF(LN(Aout))` → 线性投影`Proj(Hv)`后与文本嵌入拼接。

## 3. 实验设计
- **数据集/场景**：预训练使用LLaVA-1.5的558k样本，指令微调使用665k样本。评估使用9个基准：TextVQA、VizWiz、GQA、VQAv2、POPE、SciQA(Img)、MME、MMBench、MM-Vet，覆盖视觉感知、理解、推理、幻觉评估等场景。
- **对比方法**：LLaVA-1.5（线性投影）、Perceiver Resampler (PR)、C-Abstractor、Pooling、Pooling-PR、Random-PR等。对比不同视觉标记数量（65、145、257、577）下的性能。
- **实验结果**：AcFormer在使用145个视觉标记时，在MME（1846.1）、MMB（68.4）、TextVQA（58.0）等指标上超过或持平LLaVA-1.5（577标记），同时训练速度快2.23倍（7B模型）。在13B模型上同样表现优异。

## 4. 资源与算力
- **主实验**：使用8块NVIDIA A100(80G) GPU。预训练约1小时20分钟（145标记），指令微调约10小时12分钟。不同视觉标记数和13B模型的时间见表（附录E）。
- **数据规模实验**：使用16块A100(80G)，预训练约28小时，指令微调约5小时。

## 5. 实验数量与充分性
- 实验组数较多：主实验包括7B和13B两种LLM规模，分别测试9个基准；消融实验覆盖不同连接器变体（PR、C-Abstractor、Pooling、Random-PR等）和不同视觉标记数量（65/145/257）；额外进行数据规模实验（60M预训练+1.8M指令微调）、锚点直接输入比较、随机选择比较等。
- 充分性评估：实验覆盖了多种任务类型，消融设计合理，对比公平（保持相同训练数据和基础模型）。但未报告误差棒或统计显著性检验。

## 6. 主要结论与发现
- 视觉锚点现象存在于多种CLIP模型中，并且生成的文本注意力也聚焦于相似区域。
- AcFormer在显著减少视觉标记（145个）的同时，平均准确率超过或持平于使用577个标记的LLaVA-1.5，且计算成本降低近三分之二（训练速度提升2.2倍）。
- 可学习查询（PR）在小数据场景下性能最差，而AcFormer因其利用锚点先验知识，在有限数据和大量数据下均优于PR。

## 7. 优点
- **新颖发现**：首次揭示Vision Transformer中视觉锚点的存在及其信息聚合作用，并设计低成本提取方法。
- **高效率**：以极少视觉标记达到甚至超越高标记基线的性能，大幅降低LLM的计算开销。
- **通用性**：在7B和13B模型、不同数据集规模下均表现稳定，优于多种现有连接器。
- **开源**：代码已公开在GitHub。

## 8. 不足与局限
- **理论分析不足**：未给出视觉锚点为何出现的理论证明，仅凭观察和实验验证。
- **实验覆盖**：未测试更大规模模型（如70B）或更大训练数据集（如100M+）下的表现；未报告误差棒，可能存在随机波动。
- **潜在偏差**：基于LLaMA/Vicuna/CLIP搭建，继承了这些模型中的偏见和幻觉风险。
- **计算开销**：虽然总体计算成本降低，但锚点选择过程需要额外注意力图计算（不过作者声称开销很小）。

（完）
