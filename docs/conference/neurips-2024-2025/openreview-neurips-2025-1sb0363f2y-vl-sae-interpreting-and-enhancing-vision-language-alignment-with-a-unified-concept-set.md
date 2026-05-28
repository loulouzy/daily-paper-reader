---
title: "VL-SAE: Interpreting and Enhancing Vision-Language Alignment with a Unified Concept Set"
title_zh: "VL-SAE: 通过统一概念集解释和增强视觉语言对齐"
authors: "Shufan Shen, Junshu Sun, Qingming Huang, Shuhui Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1Sb0363f2y"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 视觉语言模型可解释性方法
tldr: 视觉语言模型（VLM）的跨模态对齐可解释性未得到充分研究，难点在于将多模态表征映射到统一概念集。本文提出VL-SAE，使用稀疏自编码器将视觉语言表征编码为隐藏激活，每个神经元对应一个概念（由语义相似的图像和文本表示），从而用统一概念集解释对齐。该方法增强了VLM的可解释性并有助于提升性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1365, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 621, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 326, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 436, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 436, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1433, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1sb0363f2y/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1450, \"height\": 645, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1465, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 976, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1371, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1122, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 931, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1036, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 660, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1214, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 766, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1192, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1201, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1176, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 818, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1sb0363f2y/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1236, \"height\": 138, \"label\": \"Table\"}]"
motivation: 现有VLM的对齐机制缺乏可解释性，难以理解跨模态表征的语义。
method: 提出VL-SAE稀疏自编码器，将视觉语言表征编码到隐藏层，每个神经元对应一个跨模态概念。
result: 实验表明该方法能有效解释对齐，并可用于提升下游任务性能。
conclusion: VL-SAE为VLM的可解释性和增强提供了新工具。
---

## Abstract
The alignment of vision-language representations endows current Vision-Language Models (VLMs) with strong multi-modal reasoning capabilities. However, the interpretability of the alignment component remains uninvestigated due to the difficulty in mapping the semantics of multi-modal representations into a unified concept set. To address this problem, we propose VL-SAE, a sparse autoencoder that encodes vision-language representations into its hidden activations. Each neuron in the hidden layer correlates to a concept represented by semantically similar images and texts, thereby interpreting these representations with a unified concept set. To establish the neuron-concept correlation, we encourage semantically similar representations to exhibit consistent neuron activations during self-supervised training. First, to measure the semantic similarity of multi-modal representations, we perform their alignment in an explicit form based on cosine similarity. Second, we construct the VL-SAE with a distance-based encoder and two modality-specific decoders to ensure the activation consistency of semantically similar representations. Experiments across multiple VLMs (e.g., CLIP, LLaVA) demonstrate the superior capability of VL-SAE in interpreting and enhancing the vision-language alignment. For interpretation, the alignment between vision and language representations can be understood by comparing their semantics with concepts. For enhancement, the alignment can be strengthened by aligning vision-language representations at the concept level, contributing to performance improvements in downstream tasks, including zero-shot image classification and hallucination elimination. Codes are provided in the supplementary and will be released to GitHub.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有视觉语言模型（VLM）的跨模态对齐机制缺乏可解释性。虽然VLM通过对比学习或问答任务实现了视觉与语言表征的有效对齐，但很难直观理解其内部语义对应关系。主要原因在于：将多模态表征的语义映射到一个统一的概念集非常困难。
- **背景**：已有解释方法往往只关注单一模态（仅视觉或仅语言）。若分别对两个模态做解释，会导致概念不匹配（概念集不同），无法进行跨模态语义比较。这限制了我们对模型行为（如幻觉）的理解和修正。
- **整体目标**：提出一种能够将视觉和语言表征语义同时映射到统一概念集的工具，从而既解释对齐机制，又能增强下游任务性能。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：使用稀疏自编码器（SAE）将视觉和语言表征编码为隐藏层激活，每个隐藏神经元对应一个“概念”（由语义相似的图像和文本共同定义）。通过自监督训练，促使语义相似的多模态表征激活相同神经元，从而获得统一的概念集。
- **关键技术细节**：
  - **显式对齐辅助**：对于LVLM（如LLaVA），由于其对齐是隐式的，先通过一个辅助自编码器将原始表征转换为中间表征，并用对比损失（InfoNCE）使其按余弦相似度显式对齐。对于CVLM（如CLIP），直接使用原始表征。
  - **距离编码器**：基于归一化欧氏距离的变体（与余弦相似度负相关）计算激活值，该距离满足三角不等式，确保语义相似的表征与同一权重向量距离相近，从而一致激活神经元。
  - **模态特定解码器**：使用两个独立的解码器分别重建视觉和语言表征，避免将模态特有的分布信息编码到隐藏激活中，保护激活的一致性。
  - **稀疏化**：采用Top-k操作（保留最大k个激活值）实现稀疏性，无需额外L1损失。
- **公式/算法流程（文字说明）**：
  1. 对于LVLM，先训练辅助自编码器（Encoder+Decoder）使中间表征按余弦相似度对齐。
  2. 将（对齐后的）视觉和语言表征输入VL-SAE的距离编码器，计算每个神经元的激活值，取Top-k得到稀疏隐藏激活。
  3. 两个模态特定解码器分别从隐藏激活重构原始表征。
  4. 训练损失：只使用重构损失（MSE）；对于LVLM，辅助自编码器使用对比损失+重构损失。

## 3. 实验设计：数据集/场景、基准方法
- **数据集**：
  - 训练VL-SAE：使用CC3M数据集（300万图像-文本对），按4:1划分训练集和测试集。
  - 下游任务评估：零样本图像分类（14个数据集，如Caltech101, Cifar10/100, Country211等）；幻觉消除（POPE benchmark，含Random、Popular、Adversarial三种设置）；开源生成（CHAIR基准）。
- **模型**：
  - CVLM：OpenCLIP（ViT-B/32, B/16, L/14, H/14）。
  - LVLM：LLaVA 1.5，Qwen-VL。
- **对比方法**：
  - 概念质量：SAE-D（双模态分别训练SAE）、SAE-S（单SAE共享两模态）。
  - 幻觉消除：Regular（标准解码）、VCD（视觉对比解码）。
- **评价指标**：
  - 概念质量：CLIP分数（Intra-Similarity同一概念内图像-文本相似度越高越好；Inter-Similarity不同概念间越低越好）。
  - 分类：平均准确率。
  - 幻觉：Accuracy、Precision、Recall、F1 Score（POPE）；CHAIR S、CHAIR I、Recall（CHAIR）。

## 4. 资源与算力
- **训练设备**：单张NVIDIA GeForce RTX 4090 GPU。
- **训练时间**：
  - CVLM（如ViT-B/16）：VL-SAE训练约132秒。
  - LVLM（LLaVA 1.5）：辅助自编码器50 epochs + VL-SAE 10 epochs（未提供具体耗时，但整体算力需求低）。
- **参数规模**：VL-SAE参数约两个线性层，显存开销很小（例如对LLaVA 1.5增加467M参数，FLOPs约0.875G）。

## 5. 实验数量与充分性
- **实验数量**：非常充分。
  - 概念质量：4种CVLM + 2种LVLM，多种k值，含定量（图3）和定性（图4、图7）评估。
  - 零样本分类：4种CVLM×14个数据集（共56组），并给出α超参表。
  - 幻觉消除：2种LVLM×3种设置（POPE）及CHAIR基准（共12组结果）。
  - 消融实验：编码器类型、解码器、辅助自编码器、稀疏化方法、数据比例（表3-5）、α超参（表A6、A15、A16）。
  - 额外分析：训练开销、推理速度、t-SNE可视化等。
- **充分性与公平性**：实验设计全面，涵盖了不同类型的VLM和多种下游任务，对比了主流基线（VCD），并做了详细的消融和超参分析。但未报告误差棒或置信区间（按惯例未提供）。整体充分、客观、公平。

## 6. 主要结论与发现
1. **概念质量**：VL-SAE学到的概念集比SAE-D和SAE-S具有更高的Intra-Similarity和更低的Inter-Similarity，即每个概念内语义更一致，概念间更分散。
2. **可解释性**：通过可视化激活概念，可以揭示模型预测中的单模态无关激活和跨模态对齐的语义对应关系，帮助理解幻觉产生的本质（视觉表征中对象信息未充分传递到语言表征）。
3. **性能提升**：
   - 在零样本分类上，用VL-SAE的概念激活进行辅助预测，在所有模型和数据集上稳定提升（平均提升约0.5%~1%）。
   - 在幻觉消除上，VL-SAE超越了专门方法VCD，在POPE和CHAIR上均取得更好结果。
4. **消融证实**：距离编码器、模态特定解码器、显式对齐辅助等组件均不可或缺。

## 7. 优点（亮点）
- **方法新颖**：首次将SAE用于跨模态统一概念集学习，解决了概念不匹配问题。
- **通用性**：适用于多种VLM（CVLM和LVLM），且训练成本极低。
- **双重能力**：既能解释模型内部机制，又能直接增强下游性能（零样本分类和幻觉消除），展示了可解释性对实用性的价值。
- **设计巧妙**：利用三角不等式保证激活一致性，模态特定解码器避免分布干扰，都是简单有效的设计。
- **实验丰富**：覆盖多种模型、任务和消融，验证充分。

## 8. 不足与局限
- **死神经元问题**：与标准SAE一样，VL-SAE也存在部分神经元从未被激活（dead neurons），影响概念利用率（附录图A8）。
- **高频概念干扰**：部分概念被几乎所有样本激活，削弱了特定语义，虽进行了重加权，但未根本解决。
- **关系建模有限**：当前方法将概念视为独立神经元，未建模概念间的语义关系。
- **CC3M依赖性**：训练VL-SAE依赖CC3M数据集，但CC3M是VLM预训练子集，不带来新知识，且α超参需要针对不同任务调整（虽然可泛化，但最优值不同）。
- **数值差距微小**：CLIP相似度数值差异可能不能完全反映概念质量改进（附录C.2承认这一点）。
- **未与更多可解释性方法比较**：仅对比了SAE变体，未与注意力归因等方法（如Grad-CAM）比较。

（完）
