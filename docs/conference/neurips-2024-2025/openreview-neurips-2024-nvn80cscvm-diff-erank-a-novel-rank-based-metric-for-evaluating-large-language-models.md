---
title: "Diff-eRank: A Novel Rank-Based Metric for Evaluating Large Language Models"
title_zh: Diff-eRank：一种评估大型语言模型的新型基于排序的度量
authors: "Lai Wei, Zhiquan Tan, Chenghai Li, Jindong Wang, Weiran Huang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=nvn80cscVm"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 大语言模型评估指标：Diff-eRank
tldr: 大型语言模型（LLM）评估需要多样化指标。本文提出Diff-eRank，一种基于信息论和几何原理的排序度量，通过分析模型隐藏表示评估LLM去除冗余信息的能力。实验表明Diff-eRank随模型规模增大而增加，并与下游性能相关。该方法也适用于多模态设置。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvn80cscvm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvn80cscvm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 641, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvn80cscvm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvn80cscvm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 523, \"height\": 384, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 955, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 751, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 619, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 755, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 739, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1092, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 889, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvn80cscvm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 882, \"height\": 203, \"label\": \"Table\"}]"
motivation: 缺乏定量评估LLM隐藏表示效率的指标。
method: 基于信息论和几何原理，从隐层表示排序量化信息冗余消除程度。
result: Diff-eRank与模型规模及任务性能高度相关。
conclusion: Diff-eRank为LLM评估提供了新的有效度量。
---

## Abstract
Large Language Models (LLMs) have transformed natural language processing and extended their powerful capabilities to multi-modal domains. As LLMs continue to advance, it is crucial to develop diverse and appropriate metrics for their evaluation. In this paper, we introduce a novel rank-based metric, Diff-eRank, grounded in information theory and geometry principles. Diff-eRank assesses LLMs by analyzing their hidden representations, providing a quantitative measure of how efficiently they eliminate redundant information during training. We demonstrate the applicability of Diff-eRank in both single-modal (e.g., language) and multi-modal settings. For language models, our results show that Diff-eRank increases with model size and correlates well with conventional metrics such as loss and accuracy. In the multi-modal context, we propose an alignment evaluation method based on the eRank, and verify that contemporary multi-modal LLMs exhibit strong alignment performance based on our method. Our code is publicly available at https://github.com/waltonfuture/Diff-eRank.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）在自然语言处理和多模态领域取得了巨大成功，但现有评估指标（如准确率、困惑度、交叉熵损失）大多基于模型的外部预测（extrinsic），缺乏对模型内部表示质量（intrinsic）的度量。  
- **背景**：一种流行观点认为，LLM 的训练过程类似于“降噪”——模型通过消除冗余信息，学习到数据中共享的隐藏结构。因此，量化“噪声消除”程度有望成为新的评估视角。  
- **核心问题**：如何设计一个既反映数据表示几何特性（如有效维度），又根植于信息论的度量，来评估 LLM 的内部表示效率。

## 2. 方法论：核心思想、技术细节与公式

- **核心思想**：将模型训练视为“噪声消除”过程。训练前模型表示杂乱（高有效秩），训练后表示结构化（低有效秩）。通过计算未训练模型与训练模型在表示上的有效秩之差（Diff-eRank），量化噪声消除能力。  
- **关键概念**：  
  - **协方差矩阵**：对句子中每个 token 的隐藏表示进行中心化、归一化后，计算协方差矩阵 $\Sigma_S$。  
  - **有效秩（eRank）**：基于奇异值的连续化秩，定义为 $eRank(A) = \exp\left(-\sum_i \frac{\sigma_i}{\sum_j \sigma_j} \log \frac{\sigma_i}{\sum_j \sigma_j}\right)$，与矩阵熵（冯·诺依曼熵）等价。  
  - **Diff-eRank**：对单个句子 $x$，$\Delta eRank(x, M_0, M_1) = eRank(\Sigma_{M_0(x)}) - eRank(\Sigma_{M_1(x)})$。对整个数据集取平均（基于平均矩阵熵）。  
- **算法流程**（文字说明）：  
  1. 对输入句子，分别从未训练模型 $M_0$ 和训练模型 $M_1$ 的最后一层提取每个 token 的隐藏表示。  
  2. 对每个句子，计算表示向量的均值 $\bar{z}$，并对所有向量进行中心化和单位归一化。  
  3. 构建协方差矩阵 $\Sigma$。  
  4. 对 $\Sigma$ 进行奇异值分解，计算有效秩。  
  5. 计算两个模型有效秩的差值，得到该句子的 Diff-eRank。  
  6. 对整个数据集，对所有句子的矩阵熵取指数平均后相减。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **单模态（语言）实验**：  
  - **模型**：OPT 家族（125M~13B），以及 Cerebras-GPT、OpenELM 家族。  
  - **数据集**：预训练数据（Wikipedia、OpenWebText2）、指令数据（dolly-15k）、偏好数据（hh-rlhf）、基准数据集（OpenBookQA、PIQA、Winogrande）。  
  - **基准**：与传统指标对比——带*减少损失*（Reduced Loss = 未训练损失 - 训练损失）和下游任务准确率（Accuracy）。  
- **多模态（视觉-语言）实验**：  
  - **模型**：LLaVA-1.5、MiniGPT-v2。  
  - **数据集**：detail_23k、cc_sbu_align（图像-指令-响应三元组）。  
  - **指标**：  
    - *图像缩减比* = (eRank₁ - eRank₂) / eRank₁（衡量连接器对视觉信息的压缩效率）。  
    - *图像-文本对齐度* = avg(eRank₃, eRank₄, eRank₅) / max(eRank₃, eRank₄, eRank₅)（衡量多模态表示一致性）。  
  - **对比**：两个模型间比较，以及旋转图像后的影响分析。  
- **消融实验**：  
  - 不同模型家族（OPT、Cerebras-GPT、OpenELM）。  
  - 不同算法变体（基于平均熵 vs. 基于平均 eRank）。  
  - 不同层（首层、中间层、末层）。  
  - 不同采样大小（Wikipedia 子集 1000、5000、10000）。

## 4. 资源与算力

- **算力说明**：论文在附录 A.3 中明确提到，使用 **NVIDIA A800-80G GPU** 进行实验。计算一个 1.3B 参数 OPT 模型在 dolly-15k 数据集上的 Diff-eRank 大约需要 **1 小时**。  
- **未明确**：未给出全部实验的总 GPU 小时数、使用的 GPU 数量等详细算力统计。

## 5. 实验数量与充分性

- **实验数量**：  
  - 单模态：在 4 个不同数据集（dolly-15k、Wikipedia、OpenWebText2、hh-rlhf）上对 OPT 家族 5 种规模进行 Diff-eRank 和 Reduced Loss 对比（共 4×5=20 组主要结果）。  
  - 多模态：2 个模型 × 2 个数据集 = 4 组结果，另加旋转图像对比实验。  
  - 消融实验：  
    - 不同模型家族（3 家族，每家族多种规模，共约 15 组）。  
    - 不同算法设计（2 种算法，5 种模型规模）。  
    - 不同层（3 种层，5 种模型规模）。  
    - 不同采样大小（3 种采样，1 个模型）。  
    - 训练阶段观察（4 个阶段）。  
  - 合计约 **40+ 组实验**。  
- **充分性与公平性**：  
  - 覆盖了多个模型家族、多种数据集、不同规模，验证了 Diff-eRank 与模型规模的正相关性及其与传统指标的一致性。  
  - 消融实验检验了算法鲁棒性（不同计算方式、不同层、不同采样量），说明结论稳健。  
  - 但仅评估了 OPT、Cerebras-GPT、OpenELM 三个家族，未覆盖更大规模（如 70B+）或不同架构（如 decoder-only 变体）的模型。多模态部分仅两个模型，且无其他对齐指标对比（如 CLIP 分数）。数据随机采样可能引入偏差。

## 6. 主要结论与发现

1. **Diff-eRank 随模型规模增大而上升**，且这一趋势在多个数据集和模型家族中一致。  
2. **Diff-eRank 与 Reduced Loss 和下游准确率呈正相关**，表明其可作为有效的内在评估指标。  
3. **仅在最后一层观察到稳定的递增趋势**，早期层无此规律，说明模型整体信息处理能力体现在最终表示。  
4. **多模态 LLM 的模态对齐评估**：基于 eRank 的图像缩减比和图像-文本对齐度指标显示，LLaVA-1.5 和 MiniGPT-v2 均表现良好，且 LLaVA-1.5 对齐更优，与其公开榜单表现一致。  
5. **图像旋转实验**：旋转会降低对齐分数，证明模型能感知语义变化，且连接器能传递视觉信息变化到 LLM。  
6. **训练阶段观察**：Diff-eRank 在训练中先升后降（过拟合时微降），与 loss 和准确率趋势一致，可辅助监控训练。

## 7. 优点

- **方法新颖**：从模型内部表示出发，区别于传统基于预测的指标，提供了理解 LLM“降噪”能力的新视角。  
- **理论基础扎实**：结合信息论（矩阵熵/冯·诺依曼熵）和几何（有效秩），定义清晰且可解释。  
- **跨模态扩展**：将 eRank 应用于多模态对齐评估，指标设计直观（图像缩减比、对齐度）。  
- **实验充分**：涵盖多个模型家族、多种规模、多个数据集，并通过消融验证了算法鲁棒性。  
- **代码开源**：便于复现和后续研究。

## 8. 不足与局限

- **计算成本**：对每个句子需要计算协方差矩阵和 SVD，在大规模数据集或长序列上可能开销较高，论文未讨论扩展性。  
- **模型覆盖有限**：仅测试了 OPT、Cerebras-GPT、OpenELM 等中等规模模型（最大 13B），未验证更大模型（如 70B+）或不同架构（如 MoE）。  
- **多模态评估粗糙**：仅用两个模型和两个数据集，未与常见的多模态评测基准（如 MME、MMBench）进行系统性对比。旋转实验仅作为一种初步验证。  
- **指标数值无参考范围**：Diff-eRank 的绝对值含义不明确，论文仅用于相对比较。不同模型家族间数值不可直接比较（因为表示维度不同）。  
- **采样偏差风险**：对于大型预训练数据集（如 Wikipedia）采用随机 10000 条子集，尽管消融显示对采样量不敏感，但仍可能未完全代表原始分布。  
- **训练阶段分析有限**：仅对一个模型大小（OPT-1.3B）在单一数据集上观察了四个阶段，未对整个预训练过程进行细粒度跟踪。  
- **缺少理论保证**：Diff-eRank 与 loss 的相关性是实证观察，无理论证明。

（完）
