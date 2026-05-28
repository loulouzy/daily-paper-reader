---
title: "LMFusion: Adapting Pretrained Language Models for Multimodal Generation"
title_zh: LMFusion：适配预训练语言模型用于多模态生成
authors: "Weijia Shi, Xiaochuang Han, Chunting Zhou, Weixin Liang, Xi Victoria Lin, Luke Zettlemoyer, LILI YU"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Kc1WTxZbrP"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 将纯文本LLM适配为多模态生成模型
tldr: 现有LLM主要是文本单一模态。本文提出LMFusion框架，在预训练文本LLM基础上添加并行的扩散模块处理图像，通过共享自注意力实现跨模态交互，同时冻结文本模块避免遗忘。训练后模型能理解和生成任意顺序的文本和图像，在多个多模态任务上达到优异性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1221, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 298, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kc1wtxzbrp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1463, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kc1wtxzbrp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 452, \"label\": \"Table\"}]"
motivation: 预训练文本LLM缺乏多模态生成能力，从头训练代价高昂。
method: 在LLM中引入并行的扩散模块，通过共享自注意力和模态专用前馈层实现多模态交互，冻结文本模块以保留语言能力。
result: LMFusion在多模态理解和生成基准上取得领先，且参数高效。
conclusion: 该方法为将文本LLM低成本扩展为多模态生成模型提供了有效途径。
---

## Abstract
We present LMFusion, a framework for empowering pretrained text-only large language models (LLMs) with multimodal generative capabilities, enabling them to understand and generate both text and images in arbitrary sequences. LMFusion leverages existing Llama-3's weights for processing texts autoregressively while introducing additional and parallel transformer modules for processing images with diffusion. During training, the data from each modality is routed to its dedicated modules: modality-specific feedforward layers, query-key-value projections, and normalization layers process each modality independently, while the shared self-attention layers allow interactions across text and image features. By freezing the text-specific modules and only training the image-specific modules, LMFusion preserves the language capabilities of text-only LLMs while developing strong visual understanding and generation abilities. Compared to methods that pretrain multimodal generative models from scratch, our experiments demonstrate that, LMFusion improves image understanding by 20% and image generation by 3.6% using only 50% of the FLOPs while maintaining Llama-3's language capabilities. We also demonstrate that this framework can adapt existing vision-language models with multimodal generation ability. Overall, this framework not only leverages existing computational investments in text-only LLMs but also enables the parallel development of language and vision capabilities, presenting a promising direction for efficient multimodal model development.

---

## 论文详细总结（自动生成）

# LMFusion: Adapting Pretrained Language Models for Multimodal Generation — 详细中文总结

## 1. 论文的核心问题与整体含义

- **研究背景**：现有的大语言模型（LLM）如 Llama-3 在纯文本任务上表现优异，但缺乏多模态理解与生成能力（如同时处理和生成文本与图像）。从头训练多模态模型（如 Transfusion、Chameleon）需要极大的计算资源（例如 Llama-3 已训练超过 15 万亿 token），且难以保留纯文本 LLM 的已有能力。
- **核心问题**：如何在不破坏预训练文本 LLM 语言能力的前提下，为其高效添加视觉理解与图像生成能力？
- **整体含义**：提出 LMFusion 框架，通过“模块分离+冻结文本模块”的方式复用预训练 LLM 的权重，避免从头训练，从而大幅降低计算成本，同时保持文本性能并显著提升多模态能力。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
- 基于 Transfusion 的架构（统一文本自回归生成 + 图像扩散），但引入模态特定的 Transformer 模块，使文本和图像数据路由到各自的专用前馈网络（FFN）、QKV 投影和层归一化，而共享的自注意力层允许跨模态交互。
- **关键创新**：冻结所有文本模块（来自 Llama-3），仅训练新增的图像模块，从而保留语言能力。

### 2.2 关键技术细节
- **架构设计**（图1）：
  - 文本 token 通过线性投影到隐藏状态 h_text_in。
  - 图像噪声表示通过 U-Net 下采样器得到 h_img_in。
  - **模态专用自注意力**：文本和图像各自有独立的 Q、K、V 矩阵，但注意力计算时拼接所有 Q/K/V，允许跨模态注意力。使用混合注意力掩码（文本因果掩码 + 图像双向掩码）。
  - **模态专用 FFN**：文本和图像分别通过不同的 FFN。
  - 输出：文本分支通过 LM-Head 得到 logits，图像分支通过 U-Net 上采样器得到预测噪声。
- **训练目标**：沿用 Transfusion 的联合损失：
  - 文本：交叉熵损失 (LLM)
  - 图像：DDPM 扩散损失 (L_DDPM)
  - 总损失：L = LLM + λ·L_DDPM
- **训练策略**：将参数分为两组，文本组（冻结，η_text=0），图像组（学习率 η_image=1e-4）。仅训练图像模块（包括 U-Net 下采样/上采样、图像专用 QKV/FFN 等）。

## 3. 实验设计

### 3.1 数据集
- **训练数据**：380M 张 Shutterstock 图像-标题对，图像中心裁剪并缩放到 256×256。80% 数据标题在前（条件图像生成），20% 图像在前（图像理解）。
- **评测基准**：
  - 语言能力：HellaSwag、SIQA、WinoGrande
  - 图像理解：MS-COCO 测试集上的 CIDEr 分数
  - 图像生成：MS-COCO 30K 随机提示，FID、CLIP 分数（有无 CFG）

### 3.2 对比方法 / Benchmark
- **主要对比**：Transfusion 7B 模型（原文从零训练）、以及从 Llama-3 初始化的 Transfusion 稠密模型。
- **其他对比**：在 LLaVAFusion 扩展实验中，对比 EMU-3、Show-O、Janus、Chameleon、MetaMorph、Transfusion 等统一多模态模型。
- **图像理解评测**：MMMU、ChartQA、RealWorldQA、MME-P
- **图像生成评测**：FID

## 4. 资源与算力

- **主实验**：使用 128 块 H100 GPU，训练 4 天（约 12,288 GPU·小时）。
- **模型规模**：基于 Llama-3 8B 初始化，新增图像 Transformer 模块（参数约 0.27B，来自 U-Net 下采样/上采样）。
- **训练数据量**：0.25T 图像-标题 token（与 Transfusion 的图像数据量一致），未额外使用纯文本数据。
- **消融实验**：使用小规模变体（0.03T 文本 + 0.03T 图像数据），训练 250K 步。

## 5. 实验数量与充分性

- **主实验**：对比了 LMFusion 的两个变体（0.5x FLOPs 和 1.0x FLOPs）与 Transfusion 在文本、图像理解、图像生成上的性能。
- **消融实验**（§5.1）：
  - 比较三种架构：无分离（稠密）、浅分离（仅 FFN 分离）、深分离（FFN+注意力分离）。
  - 在不同学习率比率（η_text/η_image ∈ {0, 0.1, 1}）下测试。
  - 每个配置训练 250K 步，记录过程中 CIDEr、CLIP、FID、HellaSwag 变化。
- **扩展实验**：LLaVAFusion 将 LMFusion 应用于 LLaVA-Next，对比多个基线模型（表2）。
- **充分性评估**：
  - 实验覆盖了语言、理解、生成三大维度，消融充分验证了模态分离和冻结策略的有效性。
  - 结果数据完整，训练过程曲线（图3-5）展示了动态变化，公平性较好（保持相同数据、超参、计算量对比）。

## 6. 论文的主要结论与发现

1. **模态分离+冻结文本模块**可有效保留预训练 LLM 的语言能力，同时获得强视觉能力。
2. LMFusion 相比 Transfusion 在图像理解（CIDEr 提升 20%）和图像生成（FID、CLIP 提升）上更优，且语言基准（HellaSwag 等）保持 Llama-3 水平。
3. **深分离（注意力+FFN）优于浅分离（仅 FFN）**，两者均优于无分离（稠密模型）。
4. 直接微调稠密 LLM 会导致语言能力严重下降，即使降低学习率也无法完全恢复。
5. 该框架可扩展至现有多模态模型（如 LLaVA-Next），进一步提升其图像生成能力。

## 7. 优点

- **参数高效**：复用预训练 LLM 权重，仅新增少量图像模块（0.27B），且训练过程中冻结文本模块，无需额外文本数据。
- **架构设计巧妙**：模态专用模块 + 共享自注意力，既保持独立处理又允许跨模态交互，避免了灾难性遗忘。
- **实验严谨**：消融实验对比了不同分离深度和学习率策略，全过程跟踪指标，结论可靠。
- **通用性**：不仅适用于纯文本 LLM，还可用于既有视觉语言模型，展示了框架的鲁棒性和迁移性。

## 8. 不足与局限

1. **仅处理静态图像**：当前框架只支持图像模态，未涉及视频、音频等其他模态。
2. **图像生成依赖扩散**：与一些使用离散 token 的模型（如 Chameleon）相比，推理流程较复杂。
3. **训练资源仍不小**：128×H100 四天对于许多研究者而言门槛较高；消融实验规模较小（0.03T token）可能不足以全面反映大模型行为。
4. **缺乏对生成质量的深度评估**：除 FID/CLIP 外，未进行人工评估或更细粒度的图像质量分析。
5. **未探讨不同初始 LLM 的泛化性**：仅使用 Llama-3，未测试其他 LLM（如 Mistral、Gemma）。
6. **忽略公平性与偏见分析**：论文未涉及模型生成内容可能存在的社会偏见或安全风险。

（完）
