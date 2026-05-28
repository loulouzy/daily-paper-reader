---
title: "DISP-LLM: Dimension-Independent Structural Pruning for Large Language Models"
title_zh: DISP-LLM：大语言模型的维度无关结构化剪枝
authors: "Shangqian Gao, Chi-Heng Lin, Ting Hua, Zheng Tang, Yilin Shen, Hongxia Jin, Yen-Chang Hsu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=YxaY6tHgg0"
tags: ["query:llm-vlm"]
score: 6.0
evidence: 大语言模型结构化剪枝
tldr: 大语言模型参数量大，结构化剪枝是重要压缩手段。现有方法在灵活性和额外参数上存在折中。本文提出维度无关的结构化剪枝方法，放松维度约束，在保持模型性能的同时显著降低计算和存储开销。实验显示在多种规模LLM上有效。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 723, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1408, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1408, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1401, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1388, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1396, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 421, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 423, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-yxay6thgg0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1399, \"height\": 337, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 819, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 941, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 676, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 677, \"height\": 106, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1426, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 681, \"height\": 93, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 561, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 647, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 622, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1425, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 622, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-yxay6thgg0/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1431, \"height\": 1054, \"label\": \"Table\"}]"
motivation: 现有结构化剪枝方法灵活性受限或引入额外参数。
method: 提出维度无关的结构化剪枝，通过松弛结构依赖实现灵活剪枝。
result: 在多个LLM上实现了高压缩比且维持了较低的精度损失。
conclusion: 维度无关结构化剪枝是平衡LLM规模与性能的有效方案。
---

## Abstract
Large Language Models (LLMs) have achieved remarkable success in various natural language processing tasks, including language modeling, understanding, and generation. However, the increased memory and computational costs associated with these models pose significant challenges for deployment on resource-limited devices. Structural pruning has emerged as a promising solution to reduce the costs of LLMs without requiring post-processing steps. Prior structural pruning methods either follow the dependence of structures at the cost of limiting flexibility, or introduce non-trivial additional parameters by incorporating different projection matrices. In this work, we propose a novel approach that relaxes the constraint imposed by regular structural pruning methods and eliminates the structural dependence along the embedding dimension. Our dimension-independent structural pruning method offers several benefits. Firstly, our method enables different blocks to utilize different subsets of the feature maps. Secondly, by removing structural dependence, we facilitate each block to possess varying widths along its input and output dimensions, thereby significantly enhancing the flexibility of structural pruning. We evaluate our method on various LLMs, including OPT, LLaMA, LLaMA-2, Phi-1.5, and Phi-2. Experimental results demonstrate that our approach outperforms other state-of-the-art methods, showing for the first time that structural pruning can achieve an accuracy similar to semi-structural pruning.

---

## 论文详细总结（自动生成）

以下是基于论文《DISP-LLM: Dimension-Independent Structural Pruning for Large Language Models》的中文总结：

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

大语言模型（LLMs）在自然语言处理中表现出色，但其巨大的参数量导致高昂的内存和计算成本，难以部署到资源受限设备。结构化剪枝作为一种有前景的压缩方案，能减少模型规模而不需额外后处理。然而，现有结构化剪枝方法存在两类局限：一是依赖结构连通性（如LLM-Pruner），导致不同层必须使用相同的特征子集，灵活性低；二是引入额外参数（如SliceGPT需要在残差连接中插入投影矩阵，增加约5%~13%原始参数）。本文旨在**打破结构依赖**，在**不增加额外参数**的前提下提升剪枝灵活性，从而获得更优的剪枝性能。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：解除传统结构化剪枝中残差连接带来的结构依赖，允许不同层沿嵌入维度使用不同的特征子集，并允许各层输入/输出宽度不同，从而显著提升剪枝灵活性。

**关键技术细节**：

- **索引选择与索引加法**：在注意力层和MLP层中插入多个选择矩阵（S1–S5），用于从残差连接中选取对应子集，并在计算后通过“索引加法”将结果加回残差。这样就不需要修改残差连接本身。
- **维度无关设计**：对于每个Transformer块，注意力输入输出分别用S1、S2选择；MLP输入、中间、输出分别用S3、S4、S5选择。不同层可以使用完全不同的索引集合，且宽度可变。
- **超网络（HyperNetwork）学习宽度**：采用GRU+全连接层的超网络生成连续潜在参数，再通过Straight-Through Estimator（具体用ReinMax）二值化得到选择矩阵。超网络使用梯度优化学习各层的剪枝宽度。
- **优化目标**：最小化语言建模损失 + λ × 参数正则化损失（使实际参数量接近目标预算p×T_total）。
- **剪枝后推理**：将选择矩阵转换为索引操作，在推理时执行Index_Select和Index_Add，实现动态维度变换。

**公式/算法流程**（文字说明）：
- 注意力层：`Attention(X) = MultiHead(X S1^T W_q, ...) W_o S2`
- 门控MLP层（LLaMA风格）：`MLP(X) = (σ(X S3^T W1 S4) ⊙ (X S3^T W2 S4)) S4^T W3 S5`
- 推理算法（Algorithm 1）：对每个块依次做索引选择、层归一化、注意力计算、索引加法、MLP计算、索引加法。

### 3. 实验设计

- **数据集**：
  - 训练超网络：WikiText-2 和 Alpaca（使用语言建模损失，非指令微调）。
  - 评估：WikiText-2（困惑度）；零样本任务：PIQA、WinoGrande、HellaSwag、ARC-e、ARC-c（准确率）。
- **模型**：OPT（125M/1.3B/2.7B/6.7B）、LLaMA（7B/13B）、LLaMA-2（7B/13B）、Phi-1.5、Phi-2。
- **对比方法**：
  - 结构化剪枝：SliceGPT、K-OBD、LLM Surgeon、LLM-Pruner（含微调/不含微调）。
  - 半结构化/权重剪枝：SparseGPT、Wanda、Magnitude（2:4稀疏）。
- **剪枝比例**：10%–50%（主要报告20%–50%）。
- **评估方式**：使用llm-eval-harness进行零样本评估；困惑度在WikiText-2上计算。

### 4. 资源与算力

- **GPU型号**：NVIDIA A100（80GB）。
- **GPU数量**：小模型（OPT-125M/Phi-1.5等）1块；OPT-6.7B/LLaMA-7B/LLaMA-2-7B用2块；LLaMA-13B/LLaMA-2-13B用4块。
- **训练时长**：
  - LLaMA/LLaMA-2 7B：约2.41小时（2块A100）。
  - LLaMA/LLaMA-2 13B：约8.83小时（4块A100）。
- **迭代次数**：超网络训练10,000次迭代。
- **成本对比**：相比LLM Surgeon，本文方法在7B模型上快约27倍，在13B上快约15倍。

### 5. 实验数量与充分性

- **实验组数**：
  - 困惑度实验（表1）：覆盖5个OPT模型+2个LLaMA-2模型×4个剪枝比例×多种对比方法。
  - 与半结构化对比（表2）：4个模型×1个比例（50% vs 2:4）。
  - 零样本任务（表3/7/8/9）：多个模型、多个剪枝比例、多个基线。
  - 消融实验（图5）：超网络 vs 无超网络 vs 约束剪枝；不同λ；不同迭代次数。
  - 超网络架构消融（表4）：无超网络、无Bi-GRU、完整超网络对比。
  - 多运行统计（表10）：对Phi-1.5做5次运行报告均值±标准差。
- **充分性评价**：实验覆盖了多种主流LLM、多种剪枝比例、多种任务，对比了最先进的结构化和半结构化方法，消融系统全面。但**大部分结果仅报告单次运行**，除了一次5次运行（表10）。公平性方面，基线方法采用其默认设置，且作者说明未更新模型权重（除某些基线外），对比相对公平。

### 6. 论文的主要结论与发现

- DISP-LLM在所有实验模型和剪枝比例上**显著优于**现有结构化剪枝方法（如SliceGPT、K-OBD、LLM Surgeon），且**无需权重更新**。
- 在50%剪枝比例下，DISP-LLM在LLaMA-2 7B/13B上的困惑度比LLM Surgeon低5.54/2.22，比K-OBD低36.8/9.49。
- 首次证明**结构化剪枝能达到与半结构化剪枝（SparseGPT/Wanda）相当甚至更好的性能**，例如在LLaMA-13B和LLaMA-2 7B/13B上优于2:4稀疏剪枝。
- 零样本任务平均准确率上，DISP-LLM也全面超越LLM-Pruner、K-OBD等，且在50%剪枝下优于LLM Surgeon 5.37个百分点。
- 可视化显示，**每个嵌入维度都被不同层利用**（约80%保留率），并非集中于少数维度。
- 超网络（GRU+线性层）**加速了子网络学习**，相比无超网络的结构搜索效果更好。

### 7. 优点

- **创新性强**：从根源上打破结构化剪枝的维度依赖性，提出“索引操作”实现维度无关剪枝。
- **效率高**：不更新模型权重，训练开销仅与LoRA相当；推理时吞吐量提升（1.08×–1.5×）。
- **灵活性高**：允许不同层使用不同特征子集和可变宽度，且不引入额外参数。
- **结果强**：在多个模型上达到SOTA，且能与半结构化剪枝竞争。
- **消融完善**：对超网络架构、λ参数、迭代次数、有无超网络均做了系统分析。

### 8. 不足与局限

- **推理加速不稳定**：由于PyTorch原生索引操作效率有限，吞吐量提升在不同模型上不一致。作者指出可通过自定义矩阵乘法进一步优化，但未实现。
- **实验结果缺乏误差条**：除表10外，所有表均报告单次运行结果，统计显著性不足。
- **代码未公开**：因公司政策，代码需经内部审核后释放，当前无法完全复现。
- **超网络设计敏感性**：消融显示无超网络或无极GRU会导致性能下降（表4），说明超网络架构对结果有较大影响，尚未充分探索最优结构。
- **应用限制**：仅针对Transformer架构；索引操作在硬件部署时可能不易高效支持。
- **额外分析缺少公平性**：对比SliceGPT时，其“slicing ratio”与实际压缩率存在差异（图10），文中已指出但未在表格中统一实际参数量。

---

（完）
