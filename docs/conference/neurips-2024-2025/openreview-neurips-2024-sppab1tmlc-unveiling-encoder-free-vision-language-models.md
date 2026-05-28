---
title: Unveiling Encoder-Free Vision-Language Models
title_zh: 揭示无编码器的视觉语言模型
authors: "Haiwen Diao, Yufeng Cui, Xiaotong Li, Yueze Wang, Huchuan Lu, Xinlong Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=SpPAB1tmlC"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 无视觉编码器的视觉语言模型
tldr: 现有视觉语言模型（VLM）依赖视觉编码器提取特征，但编码器引入了归纳偏置。无编码器的纯VLM训练困难且性能低下。本文提出了一个简单有效的训练方案，弥合了有编码器和无编码器模型之间的差距，实现了无编码器VLMs的高效训练。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1402, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1404, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1419, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1421, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 306, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-sppab1tmlc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 762, \"height\": 308, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 638, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 805, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 677, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 681, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 818, \"height\": 938, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 609, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-sppab1tmlc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 442, \"label\": \"Table\"}]"
motivation: 视觉编码器带来的归纳偏置限制了VLM的灵活性和效率，无编码器模型训练困难。
method: 提出了包含特定训练策略的配方，使无编码器VLM达到与有编码器模型相当的性能。
result: 实验证明该方法训练的无编码器VLM在多项任务上接近或达到有编码器模型的水平。
conclusion: 无编码器VLM是可行的，为更灵活的多模态模型开辟了道路。
---

## Abstract
Existing vision-language models (VLMs) mostly rely on vision encoders to extract visual features followed by large language models (LLMs) for visual-language tasks. However, the vision encoders set a strong inductive bias in abstracting visual representation, e.g., resolution, aspect ratio, and semantic priors, which could impede the flexibility and efficiency of the VLMs. Training pure VLMs that accept the seamless vision and language inputs, i.e., without vision encoders, remains challenging and rarely explored. Empirical observations reveal that direct training without encoders results in slow convergence and large performance gaps. In this work, we bridge the gap between encoder-based and encoder-free models, and present a simple yet effective training recipe towards pure VLMs. Specifically, we unveil the key aspects of training encoder-free VLMs efficiently via thorough experiments: (1) Bridging vision-language representation inside one unified decoder; (2) Enhancing visual recognition capability via extra supervision. With these strategies, we launch EVE, an encoder-free vision-language model that can be trained and forwarded efficiently. Notably, solely utilizing 35M publicly accessible data, EVE can impressively rival the encoder-based VLMs of similar capacities across multiple vision-language benchmarks. It significantly outperforms the counterpart Fuyu-8B with mysterious training procedures and undisclosed training data. We believe that EVE provides a transparent and efficient route for developing pure decoder-only architecture across modalities.

---

## 论文详细总结（自动生成）

# 论文总结：Unveiling Encoder-Free Vision-Language Models (EVE)

## 1. 论文的核心问题与整体含义（研究动机和背景）

现有视觉-语言模型（VLM）普遍依赖视觉编码器（如CLIP、EVA）提取视觉特征，再接上大型语言模型（LLM）处理多模态任务。但视觉编码器带来了强归纳偏置——固定分辨率、固定宽高比、语义先验等，限制了模型的灵活性和效率（如高分辨率图像需要切片、部署时编码器成为瓶颈、编码器与LLM容量匹配困难）。为此，论文提出：能否去除视觉编码器，将感知与推理能力统一到单一的纯解码器架构中？直接训练无编码器VLM面临缓慢收敛和性能差距大的难题，本文旨在弥合有编码器与无编码器模型之间的鸿沟，给出有效的训练方案。

## 2. 论文提出的方法论：核心思想、关键技术细节

论文提出EVE（Encoder-free Vision-language model），核心思想包括两点：
- **视角1：LLM中心的预对齐**。在扩大预训练数据之前，先从一个冻结的LLM出发，仅训练轻量的补丁嵌入层（Patch Embedding Layer, PEL）和补丁对齐层（Patch Aligning Layer, PAL），建立视觉与语言模态的初步连接，防止后续训练崩溃。
- **视角2：增强视觉识别能力**。通过从预训练视觉编码器（如CLIP）中引入细粒度的补丁特征对齐（MSE损失），以及从语言概念对齐（下一个词预测的CE损失），来提升视觉感知。

**关键技术细节**：
- **Patch Embedding Layer (PEL)**：用卷积层、平均池化、交叉注意力（CA1、CA2）将图像转换为补丁特征，并添加`<CLS>`和`<SPL>`（换行）标记，支持任意宽高比输入。
- **Patch Aligning Layer (PAL)**：从EVE中间层选取特征，去除无关标记，经过自适应池化和逐层交叉注意力（CA3），与视觉编码器输出的对应位置特征计算MSE损失。
- **三阶段训练流程**：
  1. **LLM-guided Pre‑aligning**：冻结LLM，仅训练PEL和PAL，使用16M高质量图像-文本描述数据（由Emu2和LLaVA-1.5重新生成），同时优化CE和MSE损失。
  2. **Generative Pre‑training**：解冻全部LLM参数，使用33M图像-文本数据，继续CE+MSE损失。
  3. **Supervised Fine‑tuning**：使用LLaVA-mix-665K等指令数据，同样更新所有参数（PAL在推理时移除）。支持高分辨率版本（EVE-7B HD）额外使用1.2M SFT数据。

## 3. 实验设计：数据集、Benchmark与对比方法

- **预训练数据集**：SA-1B（11M）、OpenImages（7M）、LAION（15M），共33M公开数据，全部用Emu2或LLaVA-1.5重新生成高质量描述（EVE-cap）。Stage 1仅用其中16M。
- **监督微调数据集**：LLaVA-mix-665K（含纯文本对话）；高分辨率版本额外使用AI2D、DocVQA、ChartQA等1.2M数据。
- **Benchmark**：VQA-v2、GQA、VizWiz、TextVQA、ScienceQA-IMG、POPE、MME、MMBench、SEED-Bench、MM-Vet。
- **对比方法**：
  - 有编码器VLM：InstructBLIP、IDEFICS-9B、QwenVL(-Chat)、LLaVA-1.5/1.6、InternVL-Chat、mPLUG-Owl2、LVIS-4V、ShareGPT4V、Monkey等。
  - 无编码器VLM：Fuyu-8B。

## 4. 资源与算力

- 硬件：2个8×A100 (40G) 节点，即16张A100 40GB。
- 训练时长：约9天。
- 优化器：AdamW，学习率Stage 1: 4e-4，Stage 2: 4e-5，Stage 3: 2e-5；批大小分别为512、512、128。
- 数据量：Stage 1 16M，Stage 2 33M，Stage 3 665K（HD版1.8M）。

## 5. 实验数量与充分性

- 主要对比实验（Table 3）：在10个benchmark上与11个有编码器VLM和1个无编码器VLM（Fuyu-8B）对比，包含标准EVE-7B和EVE-7B (HD)。
- 消融实验（Table 4、5、6，Figure 5、6、7、8）：
  - 针对PEL各组件（CA1、CA2）和PAL有无的消融。
  - 针对Stage 1（有无LLM引导预对齐）在不同数据量下的表现。
  - 针对PAL中不同间隔因子的消融。
  - 与有编码器基线LLaVA-1.5在不同训练策略下的缩放性能对比。
  - 有/无视觉监督（PAL）在不同数据量下的性能对比。
  - 推理FLOPs和延迟对比（Table 6）。
- 充分性：实验设计较全面，覆盖了模型架构各个模块、训练阶段、数据规模、分辨率、与多种基线对比。但未报告多次运行的标准差/置信区间，可能随机性未充分考量。

## 6. 论文的主要结论与发现

1. **Stage 1（LLM引导的预对齐）至关重要**：缺少该阶段会导致训练崩溃，性能随数据量增加反而下降；有了该阶段则收敛稳定、性能持续提升。
2. **视觉监督（PAL）在数据量较小时显著加速收敛**；但数据量足够大（如24M以上）时，其作用减弱（差距0.3-0.8%），说明高质量描述可部分替代细粒度对齐。
3. **EVE-7B仅使用35M公开数据**即可与LLaVA-1.5等有编码器模型性能相当，远超Fuyu-8B；高分辨率版本进一步缩小差距。
4. **无编码器架构天然支持任意宽高比**，且部署时因去除视觉编码器，图像编码FLOPs和延迟降低一个数量级（如LLaVA-1.6图像部分FLOPs 1860G vs EVE HD 170G）。
5. **纯视觉-语言训练会导致语言能力遗忘**（ScienceQA下降），需引入语言数据混合或MoE策略。

## 7. 优点

- **架构简洁**：纯解码器，无需复杂视觉编码器，输入灵活。
- **效率高**：部署延迟和算力需求显著低于有编码器基线。
- **可复现性好**：完全使用公开数据，训练策略透明。
- **消融充分**：清晰揭示了预对齐阶段、视觉监督、多层级特征聚合等设计的作用。
- **结果具有启发性**：证明无编码器VLM在适当训练下可匹敌有编码器模型，为未来多模态统一架构提供了可行方向。

## 8. 不足与局限

- **性能仍有差距**：与最先进的编码器模型（如InternVL-Chat、ShareGPT4V）相比，EVE在多项基准上偏低，尤其在MME、MMBench、ScienceQA等需要强语言常识的任务上表现较弱。
- **语言能力退化**：仅用视觉-语言数据训练导致LLM原有语言能力下降（ScienceQA从65.3%降至63.0%），论文仅建议但未实验验证语言数据混合的效果。
- **PAL依赖固定分辨率的视觉编码器**：虽然训练后编码器可去除，但训练中仍需CLIP等编码器提供监督，且须将其输出对齐到EVE的灵活分辨率，存在间接限制。
- **缺乏统计显著性分析**：未报告实验结果的标准差或多次运行差异，难以评估结果稳定性。
- **高分辨率版本仅在SFT阶段引入**，预训练阶段仍使用较低分辨率，可能限制了高分辨率性能的进一步提升。
- **未探索更大规模模型和更多模态的扩展**（如音频、视频），仅作为展望提及。

（完）
