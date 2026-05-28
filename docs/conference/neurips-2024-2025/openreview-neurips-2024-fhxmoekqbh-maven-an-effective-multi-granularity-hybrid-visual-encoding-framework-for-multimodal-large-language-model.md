---
title: "MaVEn: An Effective Multi-granularity Hybrid Visual Encoding Framework for Multimodal Large Language Model"
title_zh: MaVEn：面向多模态大语言模型的高效多粒度混合视觉编码框架
authors: "Chaoya Jiang, Jia Hongrui, Haiyang Xu, Wei Ye, Mengfan Dong, Ming Yan, Ji Zhang, Fei Huang, Shikun Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=fHxmoekQBh"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 面向多模态大语言模型的多粒度视觉编码框架
tldr: 现有MLLM专注于单图像理解，多图像推理能力弱。本文提出MaVEn框架，融合离散视觉符号序列（粗粒度语义）与连续表示序列（细粒度特征），增强多图像间信息整合能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fhxmoekqbh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 615, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-fhxmoekqbh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fhxmoekqbh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fhxmoekqbh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fhxmoekqbh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1312, \"height\": 193, \"label\": \"Table\"}]"
motivation: 现有MLLM在多图像推理中表现不佳，缺乏跨图像语义理解。
method: 结合离散视觉符号和连续表示的双编码方法。
result: 在多图像推理任务上显著提升性能。
conclusion: 多粒度视觉编码可有效补全MLLM在多图像场景下的不足。
---

## Abstract
This paper presents MaVEn, an innovative Multi-granularity Visual Encoding framework designed to enhance the capabilities of Multimodal Large Language Models (MLLMs) in multi-image reasoning. Current MLLMs primarily focus on single-image visual understanding, limiting their ability to interpret and integrate information across multiple images. MaVEn addresses this limitation by combining discrete visual symbol sequences, which abstract coarse-grained semantic concepts, with traditional continuous representation sequences that model fine-grained features. This dual approach bridges the semantic gap between visual and textual data, thereby improving the model's ability to process and interpret information from multiple images effectively. Additionally, we design a dynamic reduction mechanism by for long-sequence continuous features to enhance multi-image processing efficiency. Experimental results demonstrate that MaVEn significantly enhances MLLMs' understanding in complex multi-image scenarios, while also improving performance in single-image contexts.

---

## 论文详细总结（自动生成）

# MaVEn: 面向多模态大语言模型的高效多粒度混合视觉编码框架 —— 中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：当前多模态大语言模型（MLLMs）主要针对单图像场景设计，在跨多图像理解与推理任务（如基于知识的VQA、视觉关系推理、多图像推理等）中表现严重不足。主要原因是：① 视觉编码序列过长，多图像输入导致上下文长度爆炸、计算开销大；② 连续视觉编码（如ViT）与文本表示之间存在语义鸿沟，难以精确对齐；③ 离散视觉编码（如VQ-VAE、SEED）虽能提供粗粒度语义抽象，但会丢失细粒度细节。
- **整体含义**：本文提出MaVEn框架，通过融合离散符号序列（粗粒度语义）与连续表示序列（细粒度特征）的多粒度混合编码，并设计动态缩减机制与多阶段训练策略，旨在同时提升MLLM在多图像及单图像场景下的理解与推理能力。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：对每张输入图像同时采用离散视觉编码器（SEED）和连续视觉编码器（ViT），得到两套特征序列：
  - **离散视觉符号序列**：由SEED将图像token化为nd个离散索引（来自大小为Nv的视觉词汇表），再与LLM原有文本词汇表合并为统一多模态词汇表（大小Nu = N + Nv），嵌入层权重矩阵扩展为Nu×z。
  - **连续视觉序列**：ViT输出nc个连续向量（patch特征），经过文本语义感知的patch缩减模块后保留与文本相关的部分，再通过MLP投影器映射到LLM语义空间。
- **关键技术细节**：
  - **动态缩减机制（Continuous Visual Tokens Reduction Mechanism）**：
    1. 将离散视觉token序列输入LLM，取<EOS>位置的隐藏状态heos作为全局信息。
    2. 将每个patch的连续特征向量与heos拼接，输入Patch Selector（一个三层MLP + Sigmoid），预测该patch与离散语义的相关性得分ai。
    3. 根据得分保留Top-m个关键patch（m = nc × α，α为保留率，默认0.25），丢弃其余冗余patch。
  - **伪标签构建**：利用Grounding SAM对图像进行文本引导的语义分割，根据每张patch与分割掩码的重叠情况生成二值标签（重叠为1，否则为0），用于训练Patch Selector。
- **训练范式（四阶段）**：
  - **Stage 1**：冻结其他参数，用COCO + Visual Genome + RefCOCO生成的100万条patch级伪标签训练Patch Selector。
  - **Stage 2**：仅用离散视觉编码，在LLaVA 558K + MMC4-core交错图像-文本数据上训练LLM的扩展嵌入层（适应统一词汇表），进行跨模态自回归生成（文本->图像离散token，图像离散token->文本）。
  - **Stage 3**：仅用连续视觉编码（经过缩减），在LLaVA 558K单图像描述数据上训练视觉投影器，使连续特征对齐嵌入层语义空间。
  - **Stage 4**：全模型微调（冻结视觉编码器与Patch Selector），使用LLaVA 665K指令微调数据集，进行指令跟随训练。

## 3. 实验设计

- **数据集与场景**：
  - **多图像场景**：DEMONBench（7个子任务：多模态对话、视觉故事讲述、视觉关系推理、多模态完形填空、知识基础QA、文本丰富图像QA、多图像推理）；SEED-Bench（包含视频理解任务，如动作预测、动作识别、过程理解）。
  - **单图像场景**：VQA数据集（VQAv2, GQA, VizWizQA, TextVQA, SciQA）；多模态基准（MME, MMBench, MM-Vet）。
- **对比方法**：BLIP-2, mPLUG-Owl, InstructBLIP, LLaMA-Adapter-v2, LLaVA, MiniGPT-4, LLaVA-1.5, Otter, OpenFlamingo, VPG-C, Unified-IO XL, Shikra, Qwen-VL-Chat等。
- **评估方式**：零样本评估（zero-shot）为主，报告准确率或综合分数。

## 4. 资源与算力

- **明确信息**：使用8块NVIDIA A100 GPU（每块80GB显存）。训练设置中，指令微调阶段（Stage 4）学习率2e-5，batch size 256，训练1 epoch。
- **未明确信息**：各阶段具体训练时长、总GPU小时数、数据加载/预处理耗时未说明。

## 5. 实验数量与充分性

- **实验组数**：
  - **主结果**：在多图像（DEMONBench 7个任务、SEED-Bench）和单图像（5个VQA + 3个多模态基准）上共约15个评估点。
  - **消融实验**：① 多粒度混合编码消融（仅离散、仅连续、混合）；② 保留率α影响实验（从0.1到1.0共10档），观察长度、SEED-Bench、DEMONBench、通用VQA、MMBench性能。
  - **定性分析**：离散token语义分布可视化、patch选择与相关性分数可视化、注意力权重可视化（含/不含离散token对比）。
  - **附录**：提供了NeurIPS论文清单，但未额外展示更多实验。
- **充分性评价**：
  - **多图像场景**：覆盖多个典型任务，对比了多种基线（包括专门训练多图像数据的模型），结果展示充分。
  - **单图像场景**：在标准VQA和MLLM基准上与SOTA对比，性能优于LLaVA-1.5等。
  - **消融实验**：验证了混合编码的必要性，以及保留率选择（0.25）的合理性（在性能与效率间平衡）。
  - **公平性**：所有对比均采用零样本设置，部分基线使用更大视觉编码器或更多参数（如BLIP-2用ViT-g 1.3B），但MaVEn仅用ViT-L+SEED（1.3B）+Vicuna 7B，在参数规模上并不占优，结果仍有优势。
  - **局限性**：未提供统计显著性检验、多次运行标准差；未讨论跨领域泛化（如视频理解仅用SEED-Bench）；消融实验中未单独验证动态缩减机制对单图像性能的影响（仅在多图像上展示效率-性能权衡）。

## 6. 主要结论与发现

1. **多粒度混合编码显著提升多图像理解**：在DEMONBench的视觉关系推理、多模态完形填空、知识基础QA、文本丰富图像QA、多图像推理5个任务上取得最高分；在SEED-Bench视频理解上比LLaVA-1.5提升约5分（42.11 vs 37.3）。
2. **单图像场景性能未降反升**：在VQAv2 (79.1)、GQA (62.5)、TextVQA (59.8)、MME (1530.10)、MMBench (65.2) 上均优于LLaVA-1.5，表明多粒度编码具有泛化优势。
3. **动态缩减机制有效**：保留率0.25时，视觉token长度从567降至144（离散32+连续144=176），而性能下降很小；保留率越低性能越差，0.25是最佳折中点。
4. **离散token提供高层语义引导**：定性分析显示，离散token（如索引4568）对应“雪人”等概念；注意力可视化表明，多粒度混合编码使模型在解码时更关注视觉信息，而纯连续编码容易忽略视觉token。
5. **多阶段训练策略关键**：四阶段训练逐步适配不同模块，确保离散/连续编码的有效协同。

## 7. 优点

- **创新性强**：首次在MLLM中系统性地融合离散与连续视觉编码，利用两者互补性（粗粒度语义+细粒度细节），提出语义缩减机制与伪标签构建方法。
- **效率与性能平衡**：动态缩减将连续token减少约75%，显著降低多图像场景下的计算与内存开销，同时性能损失极小。
- **实验全面**：覆盖多图像、单图像、视频理解等多场景，对比多个基线，消融实验和可视化分析充分。
- **可复现性较好**：使用了公开数据集（COCO, VG, RefCOCO, LLaVA 558k/665k, MMC4-core）和开源模型（SEED, ViT, Vicuna），训练设置清晰（8×A100, batch size, lr等）。
- **结果具有竞争力**：在多个基准上超越或持平SOTA（如Qwen-VL-Chat、InstructBLIP），且参数量更小（7.2B）。

## 8. 不足与局限

- **实验覆盖不足**：未在视频理解数据集（如MSVD, MSRVTT）上评估，仅用SEED-Bench中的视频子集；未在更多多图像交互任务（如图表理解、多模态阅读）上测试。
- **缺失统计显著性检验**：未报告多次运行的标准差或置信区间，无法判断性能差异是否显著。
- **伪标签噪声风险**：基于Grounding SAM生成patch级伪标签，可能引入错误标签（特别是遮挡、小物体场景），影响Patch Selector训练质量。
- **离散编码依赖特定模型**：仅使用了SEED作为离散编码器，未验证替换为其他离散编码器（如VQ-GAN）的效果；SEED本身需要大量预训练数据，可能成为部署瓶颈。
- **动态缩减机制依赖文本语义**：训练时需预先获取描述性文本（caption）来生成引导，实际推理时若无文本（如纯视觉问答）可能需要特殊处理。
- **未讨论安全性、偏见等问题**：缺乏对模型在敏感内容、公平性等方面的分析；未提及伦理审查。
- **计算资源虽明确但未提供完整训练时间**：仅说明最终阶段1 epoch，但未给出总GPU小时数，难以复现全流程成本。

（完）
