---
title: "LangHOPS: Language Grounded Hierarchical Open-Vocabulary Part Segmentation"
title_zh: LangHOPS：语言引导的分层开放词汇部件分割
authors: "Yang Miao, Jan-Nico Zaech, Xi Wang, Fabien Despinoy, Danda Pani Paudel, Luc Van Gool"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=v6Oo0zO2oA"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 利用多模态大语言模型实现开放词汇部件分割
tldr: 该论文提出首个基于多模态大语言模型（MLLM）的开放词汇部件实例分割框架LangHOPS。不同于依赖视觉分组的传统方法，LangHOPS将对象-部件层次在语言空间进行锚定，利用MLLM的丰富知识和推理能力联动多粒度概念。实验在域内和跨数据集场景下均取得优异分割效果，并支持零样本语义分割。这展示了MLLM在精细视觉理解任务中的潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-v6oo0zo2oa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1400, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v6oo0zo2oa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1352, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v6oo0zo2oa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1323, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v6oo0zo2oa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1425, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v6oo0zo2oa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1420, \"height\": 669, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1368, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 444, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1182, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1290, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 516, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 892, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1443, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1014, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 767, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1225, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1228, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v6oo0zo2oa/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1518, \"height\": 212, \"label\": \"Table\"}]"
motivation: 现有开放词汇分割方法依赖启发式视觉分组，缺乏语言层次指导。
method: 将多模态大语言模型集成到部件解析流程，在语言空间中锚定对象-部件层次。
result: 在开放词汇部件分割任务中优于现有方法，并展现零样本能力。
conclusion: MLLM可有效提升细微视觉概念的识别与分割能力。
---

## Abstract
We propose LangHOPS, the first Multimodal Large Language Model (MLLM)-based framework for open-vocabulary object–part instance segmentation. Given an image, LangHOPS can jointly detect and segment hierarchical object and part instances from open-vocabulary candidate categories. Unlike prior approaches that rely on heuristic or learnable visual grouping, our approach grounds object–part hierarchies in language space. It integrates the MLLM into the object-part parsing pipeline to leverage rich knowledge and reasoning capabilities, and link multi-granularity concepts within the hierarchies. We evaluate LangHOPS across multiple challenging scenarios, including in-domain and cross-dataset object-part instance segmentation, and zero-shot semantic segmentation. LangHOPS achieves state-of-the-art results, surpassing previous methods by 5.5% Average Precision(AP) (in-domain) and 4.8% (cross-dataset) on the PartImageNet dataset and by 2.5% mIOU on unseen object parts in ADE20K (zero-shot). Ablation studies further validate the effectiveness of the language-grounded hierarchy and MLLM-driven part query refinement strategy.

---

## 论文详细总结（自动生成）

# LangHOPS: 语言引导的分层开放词汇部件分割 — 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有开放词汇分割方法（如基于CLIP的方法）在处理对象–部件（object–part）层次关系时，主要依赖启发式视觉分组或隐式CLIP嵌入空间关联，缺乏显式的语言层次建模。这些方法在部件粒度变化、跨数据集泛化以及零样本场景下表现不佳。
- **核心问题**：如何实现**开放词汇的对象–部件实例分割**（Open-Vocabulary Object-Part Instance Segmentation, OVPIS），即同时检测并分割图像中对象的实例及其对应部件的实例，且能泛化到训练时未见过的对象或部件类别。
- **整体含义**：本文提出首个基于多模态大语言模型（MLLM）的OVPIS框架LangHOPS，将对象–部件层次结构显式锚定在语言空间中，利用MLLM的丰富知识和推理能力连接多粒度概念，从而提升部件分割的准确性和泛化能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将对象–部件层次关系**在语言空间中显式建模**，生成包含对象上下文的语言锚定部件查询（language-grounded part queries）。
- 利用**多模态大语言模型（MLLM）** 对这些查询进行精细化处理，连接视觉与语言信息，最终解码出部件掩码和类别。

### 关键技术细节（流程）
1. **对象分割**：使用基于MaskDINO/GLEE的对象解码器，结合CLIP文本编码器进行开放词汇分类，输出对象级掩码、边界框和类别。
2. **语言锚定层次（Language-grounded Hierarchies）**：
   - 从用户定义的候选类别C中提取对象–部件层次。
   - 对每个预测的对象类别，检索其可能部件类别的CLIP文本嵌入。
   - 将对象查询（视觉特征）与各部件文本嵌入拼接，形成初始部件查询 \( p_i^0 = (O_L \| f_{CO}(e_i^o)) \)。
   - 每个部件查询重复 \( N_p \) 次以适应同一对象多个相同部件实例。
3. **基于MLLM的解析（MLLM-based Parsing）**：
   - 使用PaliGemma 2作为MLLM，输入图像、拼接的对象–部件查询 \( P_0 \) 以及结构化文本提示。
   - MLLM输出精炼后的部件查询 \( P \)，融合视觉信息、对象上下文和部件语言先验。
   - 文中强调将Gemma 2作为前馈模型使用（而非自回归生成），以保证输出结构可控。
4. **部件分割**：使用与对象解码器结构相同的部件解码器，基于精炼查询预测部件类别、边界框和掩码。

### 损失函数与训练策略
- **两阶段训练**：
  - 第一阶段：仅优化对象实例分割损失（分类、边界框、掩码）。
  - 第二阶段：联合优化对象和部件分割损失。
- 损失函数包括focal loss（分类）、L1 loss（边界框）、focal loss + dice loss（掩码）。

## 3. 实验设计：数据集、场景、benchmark、对比方法

### 数据集
- **训练/测试**：Pascal-Part-116 (PPS-116), PartImageNet, ADE20K, 以及额外数据集 COCO, VisualGenome, LVIS (INS), SA1B, PACO (PART) 用于可扩展性实验。
- **评估场景**：
  - **跨数据集（Cross-dataset）**：PPS-116 → PartImageNet 和 PartImageNet → PPS-116。
  - **域内（In-domain）**：在同一数据集上训练和测试。
  - **零样本语义分割（Zero-shot）**：在OV-Part基准上评估未见部件类别的mIoU。

### 对比方法
- **主要基线**：VLPart, PartGLEE（直接OVPIS方法），PSALM†（经适配的LLM分割方法），PartCATSeg, PartCLIPSeg, CAT-Seg等（零样本语义分割方法）。

### Benchmark指标
- 对象–部件实例分割：**mAP mask**（对象、部件、总体AP）。
- 零样本分割：**hIoU**（seen和unseen类别的调和平均mIoU）。

## 4. 资源与算力
- **硬件**：4 × Nvidia H200 GPU。
- **批大小**：16。
- **模型大小**：约4B参数（含PaliGemma2-3B）。
- **训练时长**：
  - 训练GPU小时：72小时（对应PPS116+INS+PART → PartImageNet设置）。
  - 训练碳排放：约23.9 kg CO₂e。
- **推理时间**：396 ms（H200上）。
- 相比PSALM†（92小时/628ms）和PartGLEE（40小时/240ms），LangHOPS在性能和效率间取得平衡，但推理时间较长。

## 5. 实验数量与充分性
- **主要实验**：
  - 跨数据集实验：两种方向（PPS-116↔PartImageNet），每种含不同训练集组合（仅基础/ +INS / +INS+PART）。
  - 在域内实验：PartImageNet和PPS-116各自在域内性能。
  - 零样本实验：三个数据集（PPS-116, PartImageNet, ADE20K）。
  - 消融实验：对象–部件协同效应、MLLM模块有效性、层次模块有效性、查询重复数 \( N_p \)、两阶段vs一阶段训练、骨干网络微调、提示鲁棒性、噪声层次鲁棒性等。
- **充分性评估**：
  - 实验覆盖了多个主流基准和复杂场景，消融实验深入拆解各组件贡献。
  - 统计稳定性：给出了3次不同随机种子的均值±标准差（附录A.2），显示结果可靠。
  - 对比方法均为当前SOTA，设置公平（无额外数据增强不公）。
- **结论**：实验数量充分，设计合理，客观公平。

## 6. 论文的主要结论与发现
1. **性能领先**：LangHOPS在跨数据集和域内OVPIS任务上显著超越所有基线，例如在PartImageNet跨数据集上AP提升5.5%，域内提升4.8%。
2. **零样本能力强**：在零样本语义分割基准上，LangHOPS在PPS-116和PartImageNet上取得最高hIoU，在ADE20K上达第二，且seen类别mIoU最高。
3. **可扩展性好**：当增加更多部件级训练数据（INS+PART）时，LangHOPS性能提升更大（+10.0% AP），优于PartGLEE。
4. **对象–部件协同**：首次证明部件级监督能显著提升对象级分割（提升5.4% AP），这得益于MLLM模块的双向梯度传播。
5. **语言锚定层次的价值**：消融实验表明，使用语言空间层次建模比可学习查询或Q-Former方法更优。
6. **MLLM的重要性**：替换MLLM为Q-Former导致性能下降，证明MLLM在连接视觉-语言概念中的关键作用。

## 7. 优点
- **创新性**：首次将MLLM引入开放词汇部件实例分割，设计语言锚定层次结构显式建模对象–部件关系。
- **性能突出**：在多个基准上达到SOTA，尤其在跨数据集和零样本泛化上表现优异。
- **丰富的消融实验**：深入分析了各模块贡献、协同效应、训练策略、鲁棒性等，验证了设计合理性。
- **可扩展性**：随着更多训练数据增加，性能提升明显，展示了成为基础模型的潜力。
- **开放代码**：承诺开源，利于复现和后续研究。

## 8. 不足与局限
- **计算成本高**：由于集成了MLLM（PaliGemma2-3B），推理时间（396 ms）和模型大小（4B）均高于基线，不利于实时或嵌入式应用。
- **训练数据覆盖有限**：主要使用常见对象和部件类别，在专业领域（如机器人操作中的可动部件）可能仍需微调。
- **跨数据集泛化仍存问题**：如在零样本场景下，对某些未见部件（如动物眼睛）分割失败（附录A.1），且不同数据集注释粒度差异导致风格偏差。
- **层次依赖人工定义**：尽管实验验证了对自动挖掘层次有一定鲁棒性，但完全自动化的层次构建仍有挑战。
- **实验局限**：零样本任务本身是语义分割（非实例分割），虽结果优秀，但与专门设计的方法在公平性上需注意。

（完）
