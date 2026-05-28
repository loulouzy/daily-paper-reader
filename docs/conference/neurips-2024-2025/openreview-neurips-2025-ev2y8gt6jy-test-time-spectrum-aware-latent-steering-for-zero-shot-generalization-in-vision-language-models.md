---
title: Test-Time Spectrum-Aware Latent Steering for Zero-Shot Generalization in Vision-Language Models
title_zh: 测试时频谱感知隐式引导实现视觉语言模型零样本泛化
authors: "Konstantinos M. Dafnis, Dimitris N. Metaxas"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eV2Y8Gt6JY"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型测试时引导
tldr: 视觉语言模型在测试时面临领域偏移会导致性能下降。本文提出频谱感知测试时引导（STS）框架，通过从文本嵌入中提取谱子空间定义语义方向，并学习轻量化调整隐式表示，实现了无需反向传播大编码器权重的零样本泛化增强。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 699, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 569, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ev2y8gt6jy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1148, \"height\": 692, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1100, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1340, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1406, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 998, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ev2y8gt6jy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1148, \"height\": 692, \"label\": \"Table\"}]"
motivation: VLM在测试时领域偏移下零样本泛化能力下降。
method: 提出STS框架，从文本嵌入中提取谱子空间，轻量调整隐式表示以适应分布变化。
result: 在不修改核心模型组件的情况下有效提升VLM对域外样本的适应能力。
conclusion: 为VLM的高效测试时自适应提供了轻量实用的方案。
---

## Abstract
Vision–Language Models (VLMs) excel at zero-shot inference but often degrade under test-time domain shifts. For this reason, episodic test-time adaptation strategies have recently emerged as powerful techniques for adapting VLMs to a single unlabeled image. However, existing adaptation strategies, such as test-time prompt tuning, typically require backpropagating through large encoder weights or altering core model components. In this work, we introduce Spectrum-Aware Test-Time Steering (STS), a lightweight adaptation framework that extracts a spectral subspace from the textual embeddings to define principal semantic directions, and learns to steer latent representations in a spectrum-aware manner by adapting a small number of per-sample shift parameters to minimize entropy across augmented views. STS operates entirely at inference in the latent space, without backpropagation through or modification of the frozen encoders. Building on standard evaluation protocols, our comprehensive experiments demonstrate that STS largely surpasses or compares favorably against state-of-the-art test-time adaptation methods, while introducing only a handful of additional parameters and achieving inference speeds up to 8× faster with a 12× smaller memory footprint than conventional test-time prompt tuning. The code is available at https://github.com/kdafnis/STS.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：视觉语言模型（VLM）在零样本推理中表现优异，但在测试时遇到领域偏移（如自然对抗样本、风格变化）时性能显著下降。现有的测试时适应（TTA）方法，如测试时提示调优（TPT），需要反向传播大型编码器权重或修改模型核心组件，导致高计算开销和内存占用，且不适用于黑盒场景。
- **整体目标**：提出一种轻量级、非侵入式的测试时适应框架，在不反向传播编码器、不修改模型架构的前提下，有效提升VLM对域外样本的零样本泛化能力。

### 2. 论文提出的方法论

- **核心思想**：利用文本嵌入的奇异值分解（SVD）提取低维谱子空间，定义主要的语义方向。在测试时，学习一个共享的、低维的系数向量，在该子空间内产生一条偏移向量，并将其施加到所有类文本原型上，使其更好地对齐当前视觉输入，从而提升分类性能。
- **关键技术细节**：
  1. **谱子空间识别**：对初始文本原型矩阵 \( Z_T^{init} \in \mathbb{R}^{C \times D} \) 进行SVD，保留前 \( k_t \) 个右奇异向量作为基矩阵 \( B_T \in \mathbb{R}^{D \times k_t} \)。\( k_t \) 通过 Gavish-Donoho 最优硬阈值方法自动选择，确保保留主要语义变化方向且过滤噪声。
  2. **潜在空间引导**：为每个测试样本优化一组可学习系数 \( \gamma \in \mathbb{R}^{k_t} \)，生成偏移向量 \( \Delta z_T = B_T \gamma \)，然后更新文本原型：\( (z_T^{adapted})_c = \text{normalize}((z_T^{init})_c + \Delta z_T) \)。
  3. **优化目标**：利用测试样本的多个增强视图，先进行置信度过滤（保留熵最低的前10%视图），然后最小化这些视图的平均预测分布的边际熵：\( \mathcal{L}_{\text{ent}} = H(\bar{P}_{\text{adapted}}) \)，并加入L2正则项 \( \mathcal{L}_{\text{reg}} = \lambda_R \|\Delta z_T\|^2 \)。
  4. **推理**：单步优化后，使用最终调整后的文本原型对所有增强视图进行平均预测得到最终类别。
- **关键公式**：仅需优化 \( k_t \) 个系数（通常远小于D），整个流程不涉及编码器反向传播，完全在潜空间操作。

### 3. 实验设计

- **数据集**：
  - **自然分布偏移**：ImageNet, ImageNet-A, ImageNet-V2, ImageNet-R, ImageNet-Sketch。
  - **细粒度分类 / 跨数据集泛化**：Flowers102, DTD, OxfordPets, UCF101, Caltech101, Aircraft, EuroSAT, StanfordCars, Food101, SUN397。
  - **额外鲁棒性测试**：CIFAR10-C（最高严重级别5）。
- **基准与对比方法**：零样本CLIP、Ensemble、CoOp、TPT、DiffTPT、C-TPT、TPS、TTL，以及基于MaPLe初始化的变体。所有方法均使用CLIP ViT-B/16作为骨干，部分实验扩展至ViT-L/14。
- **公平性**：所有TTA方法使用相同的增强策略（63个随机裁剪+水平翻转），单步优化，统一学习率5e-3，保证对比公平。

### 4. 资源与算力

- **硬件**：单张NVIDIA RTX8000 GPU（45GB显存）。
- **计算效率**：STS每样本测试时间0.09秒（使用7模板集成），而TPT为0.75秒；内存占用1.4 GB vs 17.6 GB，速度提升8倍，内存减少12倍。未提及总训练时长或多GPU设置。

### 5. 实验数量与充分性

- **主要实验**：2个大型对比表（表1：5个OOD数据集；表2：10个细粒度数据集）。
- **消融实验**：共7项以上，包括：
  - 计算效率与参数量分析（表3）。
  - 更新步数影响（表B3，1-5步，结果波动<0.1%）。
  - 共享系数 vs 每类系数（表B4, B5，性能几乎无差异）。
  - 奇异向量选择方法对比（表C1，Gavish-Donoho vs 能量阈值）。
  - CIFAR10-C鲁棒性（图3a，与TPT持平）。
  - 增强视图数量影响（图3b，64视图后饱和）。
  - 更大规模骨干ViT-L/14验证（表B6）。
- **充分性评价**：实验覆盖多种分布偏移类型，消融全面，对比基准完整，结果稳定（3随机种子+标准差报告）。实验设计客观、公平，结论可信。

### 6. 论文的主要结论与发现

- STS在OOD平均准确率上比零样本CLIP提升7.76%，比TPT提升4.23%；在细粒度分类上，STS Ensemble平均65.06%超越TPT的64.78%。
- 基于MaPLe初始化时，STS同样优于TPT，平均提升3.03%。
- 计算效率显著：速度8倍于TPT，内存占用仅为其1/12。
- 线性子空间引导足以应对大多数常见分布偏移，展示了潜空间适应范式的有效性。

### 7. 优点

- **高度轻量**：仅需优化 \( k_t \) 个系数（通常远小于D），完全不依赖于编码器反向传播。
- **黑盒兼容**：视编码器为冻结特征提取器，无需修改内部结构，适用于闭源或固定架构模型。
- **理论驱动**：利用SVD的低秩性质自动选择秩，避免手工调参，同时提供天然正则化，增强稳定性。
- **性能优异**：在多个基准上达到或超越SOTA，且计算开销显著降低。

### 8. 不足与局限

- **线性偏移局限**：子空间引导是线性的，对于高度非线性的复杂领域偏移可能表达能力不足，需要更复杂的非线性映射。
- **计算瓶颈**：对每个测试样本仍需多次前向传播图像编码器（线性于增强视图数），虽比TPT快但仍存在重复编码开销。
- **初始提示依赖**：性能受到初始文本原型（如手写模板）质量的影响，未充分探索视觉嵌入引导的潜力。
- **特定领域弱点**：在EuroSAT上表现不佳（与其他TTA方法类似），卫星图像需要特定增强策略。
- **骨干多样性有限**：主要实验基于ViT-B/16，更大模型仅测试了ViT-L/14一种，未覆盖更多架构（如ResNet、EVA等）。

（完）
