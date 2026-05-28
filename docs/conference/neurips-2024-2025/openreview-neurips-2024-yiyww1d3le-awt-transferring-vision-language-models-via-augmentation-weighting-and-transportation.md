---
title: "AWT: Transferring Vision-Language Models via Augmentation, Weighting, and Transportation"
title_zh: "AWT: 通过增强、加权和传输迁移视觉语言模型"
authors: "Yuhan Zhu, Yuyang Ji, Zhiyu Zhao, Gangshan Wu, Limin Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=YiYww1d3lE"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型论文
tldr: 针对预训练视觉语言模型适应新概念时信息有限的问题，AWT框架通过图像变换和大语言模型增强输入，基于预测熵动态加权，并利用最优传输挖掘跨模态语义关联，实现了高效的迁移学习。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1356, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1373, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1081, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1404, \"height\": 1104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1085, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1373, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1366, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yiyww1d3le/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 701, \"height\": 600, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 730, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 703, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1138, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 643, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1382, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 1350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1170, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1412, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1455, \"height\": 1165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yiyww1d3le/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1440, \"height\": 2201, \"label\": \"Table\"}]"
motivation: 预训练视觉语言模型在适应新类别时，因新类信息有限而性能不足。
method: 增强输入多样性，基于熵加权，并用最优传输对齐视觉-语言空间。
result: 在各种视觉分类任务中显著提升了迁移性能。
conclusion: 该框架可无缝集成到多种视觉语言模型中，提升零样本和少样本适应能力。
---

## Abstract
Pre-trained vision-language models (VLMs) have shown impressive results in various visual classification tasks.
However, we often fail to fully unleash their potential when adapting them for new concept understanding due to limited information on new classes.
To address this limitation, we introduce a novel adaptation framework, AWT (Augment, Weight, then Transport). AWT comprises three key components: augmenting inputs with diverse visual perspectives and enriched class descriptions through image transformations and language models; dynamically weighting inputs based on the prediction entropy; and employing optimal transport to mine semantic correlations in the vision-language space.
AWT can be seamlessly integrated into various VLMs, enhancing their zero-shot capabilities without additional training and facilitating few-shot learning through an integrated multimodal adapter module.
We verify AWT in multiple challenging scenarios, including zero-shot and few-shot image classification, zero-shot video action recognition, and out-of-distribution generalization. AWT consistently outperforms the state-of-the-art methods in each setting. In addition, our extensive studies further demonstrate AWT's effectiveness and adaptability across different VLMs, architectures, and scales.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机

**问题背景**：预训练视觉语言模型（如 CLIP）在大规模图文对数据上训练后，在视觉分类任务上表现优异。然而，当直接应用于下游新类别时，由于新类别信息有限（仅提供类别名称），模型难以聚焦任务相关细节，导致性能不佳。

**研究动机**：现有方法主要依赖后训练提示（prompt tuning）来提供上下文，但这需要额外训练资源或标注数据。本文旨在**无需额外训练**的情况下，通过输入增强来充分挖掘 VLMs 的零样本迁移潜力，并进一步提升少样本性能。

## 2. 方法论：AWT 框架

**核心思想**：对原始输入进行增强（Augment），动态加权各增强视图（Weight），并利用最优传输（Transport）度量跨模态语义距离。整体流程无需训练，可无缝集成到任意双编码器 VLM 中。

### 关键技术细节
- **增强（Augment）**：
  - **视觉增强**：对原始图像进行随机裁剪、翻转，生成 N 个不同尺度和视角的图像。
  - **文本增强**：利用大语言模型（如 GPT-3.5）生成 M 个类别描述。采用**两步数据集感知提示**：第一步让 LLM 生成与数据集相关的问题，第二步结合具体类别生成丰富且相关的描述。
- **加权（Weight）**：
  - 基于**预测熵**评估每个视图的重要性。熵越低（置信度越高）则权重越大。
  - 图像视图权重：\( a_n = \frac{\exp(-H_n(t)/\gamma_v)}{\sum_j \exp(-H_j(t)/\gamma_v)} \)（\( H_n \) 为分类熵）
  - 文本视图权重：类似公式 \( b_{im} \)，基于固定图像和候选类别计算。
- **传输（Transport）**：
  - 将图像视图集和某类文本视图集建模为离散测度，质量即为权重。
  - 使用**最优传输**（Sinkhorn 算法）最小化运输代价（代价为余弦距离），求解传输计划 \( \tilde{P} \)。
  - 最终分类概率：\( p_{OT}(t_i|X) = \frac{\exp(s_i/\tau)}{\sum_j \exp(s_j/\tau)} \)，其中 \( s = \sum_{i,j} \tilde{P}_{ij}(1 - C)_{ij} \)。

### 算法流程（文字说明）
1. 输入图像、候选类别名。
2. 图像增强（N+1个视图），文本增强（M+1个描述/类）。
3. 对每个视图，用 CLIP 计算嵌入，分别计算图像熵权重 \( a_n \) 和文本熵权重 \( b_{im} \)。
4. 对每个类别 i，构建图像测度和文本测度，运行最优传输得到距离。
5. 用 OT 距离计算分类概率，输出预测。

> 少样本学习时，额外集成多模态 Adapter 模块（插入每个 Transformer 层），进行参数高效微调。

## 3. 实验设计

### 数据集与场景
- **零样本图像分类**：14 个数据集（ImageNet, Flowers, DTD, Pets, Cars, UCF, Caltech101, Food, SUN, Aircraft, SAT, Birdsnap, Caltech256, CUB）。
- **分布外泛化（OOD）**：4 个 ImageNet 变体（ImageNet-A, ImageNetV2, ImageNet-R, ImageNet-Sketch）。
- **零样本视频动作识别**：UCF101, HMDB51, Kinetics-600。
- **少样本图像分类**：11 个数据集，shots 为 1, 2, 4, 8, 16。
- **对比方法**：
  - 提示学习方法：CoOp, CoCoOp, MaPLe, PLOT++, POMP, ProVP-Ref。
  - 测试时提示调优：TPT, DiffTPT, PromptAlign, Self-TPT。
  - 增强方法：CuPL, VisDesc, WaffleCLIP, SuS-X-SD。
  - 视频方法：ActionCLIP, X-CLIP, FROSTER 等。
- **消融实验**：成分分析、视图数量、LLM 提示策略、加权温度、不同 LLM、不同 VLM 与 backbone。

### 评价指标
- 主要使用 Top-1 准确率（%），少样本取三次平均。

## 4. 资源与算力

- **GPU**：所有实验在**单张 NVIDIA A100-SXM4-80GB GPU** 上完成。
- **训练**：零样本任务无需训练；少样本任务使用 1 张 GPU，20–25 个 epoch。
- **提示**：未明确说明总 GPU 小时数，但根据实验规模（21 个数据集、多个消融、不同 backbone）合理推断算力需求适中。

## 5. 实验数量与充分性

- **总实验量**：涵盖 4 个主要场景，超过 20 个数据集，大量对比方法。
- **消融实验**：包括主成分、视图数量（2~100）、LLM 提示方式、加权温度、不同 backbone、不同 VLM（ALIGN, SigLIP, EVA-CLIP）等，较为全面。
- **公平性**：零样本对比中所有方法均在同一 backbone（CLIP-B/16）下评估；少样本采用相同数据划分和三次重复；消融设计合理。但部分对比方法（如 CoOp）需要训练，而 AWT 零样本无需训练，对比略有不对称。

## 6. 主要结论与发现

- AWT 在**零样本图像分类**上，平均 14 个数据集提升 2.05%（69.59% vs 前最好 67.54%）。
- **OOD 泛化**平均提升 3.62%（64.43% vs 前最好 60.81%）。
- **零样本视频动作识别**刷新三个数据集纪录，HMDB51 提升 2.4%，Kinetics-600 提升 1.3%。
- **少样本分类**：在 1~16 shot 下均超越现有方法，平均提升 1.57%~2.76%。
- 方法通用性强：在 ResNet 与 ViT 各种规模的 backbone 上均有效，适用 ALIGN、SigLIP、EVA-CLIP 等其他 VLM。

## 7. 优点

1. **零训练**：零样本情况下无需任何训练，仅通过测试时增强+加权+OT 即可大幅提升性能。
2. **通用集成**：可无缝接入任意双编码器 VLM，无需修改模型结构。
3. **双模态增强**：同时增强了图像和文本，并结合 LLM 的领域知识生成上下文描述。
4. **动态加权机制**：基于熵自适应调整视图重要性，比简单平均或固定权重更鲁棒。
5. **有效性跨任务验证**：在图像、视频、OOD 等多个场景均取得 SOTA，具有很强的泛化能力。
6. **详细消融分析**：视图数量、温度、提示策略等参数都被系统探索，便于实际部署。

## 8. 不足与局限

1. **计算代价**：使用大量增强视图（默认 N=50, M=50）推理较慢，FPS 大幅下降（从 CLIP 的约 180 降至 AWT 的约 10–36）。作者虽提供了性能-效率权衡分析，但未有效解决计算瓶颈。
2. **低分辨率图像失败**：在 CIFAR-10/100 等 32×32 图像上，随机裁剪导致模糊，性能下降。虽用 DALL·E 2 替代后提升，但引入额外生成成本，且未系统评估该解决方案泛化性。
3. **LLM 依赖**：文本增强依赖外部 LLM（GPT-3.5），存在生成质量不稳定或 API 成本问题；不同 LLM 结果略有波动。
4. **少样本设置中未比较零样本方法**：少样本时使用了可训练的 Adapter，与纯提示学习方法的对比不完全公平（Adapter 增加了参数量）。
5. **视频任务未做专门优化**：仅用时间采样帧作为视觉增强，未建模时序动态，性能虽好但可能仍有很大提升空间。
6. **未讨论偏差与公平性**：未分析模型在不同类别或敏感属性上的潜在偏差。

---

（完）
