---
title: "FOCUS: Unified Vision-Language Modeling for Interactive Editing Driven by Referential Segmentation"
title_zh: FOCUS：基于指代分割驱动的交互式编辑统一视觉语言建模
authors: "Fan Yang, Yousong Zhu, Xin Li, Yufei Zhan, Hongyin Zhao, Shurong Zheng, Yaowei Wang, Ming Tang, Jinqiao Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FACJ0478oQ"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 统一视觉语言模型用于交互式编辑
tldr: 当前视觉语言模型将“看什么”和“怎么编辑”分开处理。本文提出FOCUS，一个统一的大视觉语言模型，通过双分支视觉编码器同时支持分割感知与可控生成，实现端到端交互式编辑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1347, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 354, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 353, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 355, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 354, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 358, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 353, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 357, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 355, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 349, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 356, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 356, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 351, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-facj0478oq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1395, \"height\": 1653, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 662, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 719, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1456, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1188, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1377, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1412, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 952, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1434, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1370, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-facj0478oq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1363, \"height\": 524, \"label\": \"Table\"}]"
motivation: 现有方法把分割和生成分离，缺少统一框架。
method: 采用双分支视觉编码器同时建模分割感知和物体中心生成。
result: 在指代分割和条件生成任务上取得一致优势。
conclusion: 统一框架可更高效地支持交互式图像编辑应用。
---

## Abstract
Recent Large Vision Language Models (LVLMs) demonstrate promising capabilities in unifying visual understanding and generative modeling, enabling both accurate content understanding and flexible editing. However, current approaches treat \textbf{\textit{"what to see"}} and \textbf{\textit{"how to edit"}} separately: they either perform isolated object segmentation or utilize segmentation masks merely as conditional prompts for local edit generation tasks, often relying on multiple disjointed models. To bridge these gaps, we introduce FOCUS, a unified LVLM that integrates segmentation-aware perception and controllable object-centric generation within an end-to-end framework. FOCUS employs a dual-branch visual encoder to simultaneously capture global semantic context and fine-grained spatial details. In addition, we leverage a MoVQGAN-based visual tokenizer to produce discrete visual tokens that enhance generation quality. To enable accurate and controllable image editing, we propose a progressive multi-stage training pipeline, where segmentation masks are jointly optimized and used as spatial condition prompts to guide the diffusion decoder. This strategy aligns visual encoding, segmentation, and generation modules, effectively bridging segmentation-aware perception with fine-grained visual synthesis.
Extensive experiments across three core tasks, including multimodal understanding, referring segmentation accuracy, and controllable image generation, demonstrate that FOCUS achieves strong performance by jointly optimizing visual perception and generative capabilities.

---

## 论文详细总结（自动生成）

# FOCUS：基于指代分割驱动的交互式编辑统一视觉语言模型 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

当前的大视觉语言模型（LVLMs）虽然在统一视觉理解和生成建模方面展现了潜力，但现有方法将“看什么”（即内容理解与分割）和“怎么编辑”（即图像生成与编辑）分开处理：

- 一方面，它们要么执行孤立的物体分割，要么仅将分割掩码作为局部编辑生成的提示条件；
- 另一方面，这些方法通常依赖多个独立的模型模块（如分割器、编辑器、语言处理器等），缺乏统一的端到端联合建模和深层的特征级交互。

因此，论文的核心动机是：**构建一个统一的LVLM，能够将分割感知（segmentation-aware perception）与可控的以物体为中心的生成（controllable object-centric generation）整合在单个端到端框架中**，从而支持在自然语言引导下的细粒度图像/视频编辑、指代分割和条件生成。

---

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 整体架构
FOCUS 是一个端到端的统一LVLM，由以下核心组件构成：
- **双分支视觉编码器**：包含一个“普通编码器”（Vanilla Encoder，基于 QwenViT）用于提取全局语义特征，和一个“层次编码器”（Hierarchical Encoder，基于 ConvNeXt-L）用于提取高分辨率多尺度细粒度局部特征。两者通过交叉注意力融合，再经过门控交叉注意力适配器（Gated Cross-Attention Adapter）将多尺度视觉特征注入语言模型。
- **生成式视觉分词器**：采用 MoVQGAN 架构，包含两个分支：
  - 语义分支（下采样率 28×，码本大小 32,768）：捕捉高层语义概念；
  - 像素分支（下采样率 16×，码本大小 98,304）：保留细粒度纹理。
  为避免量化信息损失，将量化前的连续特征作为语言模型的视觉输入。
- **大语言模型**：采用 Qwen2.5-3B，接受多模态输入（融合视觉特征、结构化文本提示、像素级视觉特征、可学习查询特征），输出语义增强的掩码令牌和离散视觉令牌（语义令牌+像素令牌）。
- **分割预测模块（Segmentation Predictor）**：基于 LLM输出 + 多尺度视觉特征，预测二进制掩码、类别分数和实例级嵌入。
- **扩散解码器（Diffusion Decoder）**：基于 SDXL 的潜在扩散模型，以 LLM生成的离散令牌和分割掩码作为空间条件，通过交叉注意力注入 UNet 进行区域可控生成。

### 2.2 关键技术流程
- **输入方案**：使用结构化提示，包括任务指令提示（SI）和条件提示（SC），例如“请根据语言描述分割目标”+具体描述。
- **渐进式多阶段训练流水线**（共4阶段）：
  1. **Stage 1**：预训练双分支视觉分词器和扩散解码器（58M 图像-文本对，分辨率 256→512），纯图像建模，不涉及分割或可控生成。
  2. **Stage 2**：视觉-语言适配器预热（30M 数据，分辨率 256），训练投影头、可学习查询和门控交叉注意力，冻结主干编码器。
  3. **Stage 3**：多模态预训练 + 分割感知对齐（35M 图像-文本+3M分割+5M对话，分辨率 256→512），联合训练 LLM、视觉适配器和掩码解码器，监督包括令牌交叉熵、分割损失（Dice+BCE）和图像重建损失（L2）。
  4. **Stage 4**：指令微调用于区域可控编辑（7M 编辑+2M分割+0.5M交互，分辨率 512→1024），联合训练 LLM、掩码解码器和扩散模型交叉注意力层，冻结视觉编码器和分词器。

### 2.3 公式/算法流程（文字说明）
- 双分支编码：XL → QwenViT 得到 X'_L；XH → ConvNeXt-L 得到 X'_H；通过交叉注意力和 MLP 得到融合视觉特征 E_img。
- 门控交叉注意力：第 l 层查询 h^(l) 与多尺度特征 f_img^(j) 进行交叉注意力，加可学习缩放参数 tanh(γ) 和 tanh(β)，注入细粒度信息。
- 分割预测：F_p({E_k^P}, {E_j^Q}, f_img) → (m_j, z_j, e_j)。
- 扩散生成：使用语义令牌 z_sem 和像素令牌 z_pix 映射为连续嵌入，与噪声潜变量拼接；分割掩码下采样后通过线性投影得到空间引导序列 f_m，注入 UNet 交叉注意力层实现区域引导。

---

## 3. 实验设计

### 3.1 使用的数据集与场景
- **多模态理解基准**：POPE、MMBench、SEED、MME-P、MM-Vet、MMMU、AI2D（通用）；VQA-text、ChartQA、DocVQA、InfoVQA、OCRBench（文档导向）。
- **可控生成与编辑基准**：
  - 图像生成：MJHQ-30K（FID）、GenAI-bench（Basic/Adv）、GenEval（Single Obj, Two Obj, Counting, Colors, Position, Color Attri）；
  - 图像编辑：Emu Edit 基准（DINO、CLIP-I、CLIP-T、CLIP-DIR）。
- **指代分割基准**：RefCOCO、RefCOCO+、RefCOCOg、gRefCOCO（mIoU）。
- **其他分割任务（附录）**：ReasonSeg、ReVOS（推理分割）、COCO-Interactive（用户交互）、DAVIS17（视频分割）、Ref-YT、Ref-DAVIS、YouTube-VIS（视频实例分割）等。

### 3.2 对比方法
- **理解**：InstructBLIP、Qwen-VL-Chat、LLaVA-1.5、ShareGPT4V、LLaVA-NeXT、Emu3-Chat 等；统一理解与生成模型：Unified-IO、Chameleon、LWM、Show-o、VILA-U、Janus、Janus-Pro、ILLUME+。
- **生成**：SDv1.5、PixArt-α、SDXL、Emu3-Gen 等；统一模型同上。
- **编辑**：InstructPix2Pix、MagicBrush、OmniGen、Emu Edit、PUMA、ILLUME、ILLUME+。
- **分割**：CRIS、LAVT、PolyFormer-B、LISA-7B、PixelLM7B、PSALM、HyperSeg 等。

### 3.3 实验数量与充分性
- 论文进行了 **大量实验**：在3大类任务（多模态理解、指代分割、可控生成与编辑）上共覆盖约20+个标准基准。
- 在理解任务中，与10+种基线对比；在生成任务中与9种基线对比；在编辑任务中与7种基线对比；在分割任务中与9种基线对比。
- 消融实验进行了 **4组**：
  1. 多阶段训练中不同分辨率的影响（256/512/1024 vs 渐进式）；
  2. 门控交叉注意力中多尺度特征的作用（单尺度、双尺度、三尺度）；
  3. 连续视觉令牌输入的效果；
  4. 分割掩码引导的作用（无掩码、通用掩码、FOCUS自己掩码）。
- 附录中还补充了视频分割、交互分割、推理分割等场景的实验。
- **充分性评价**：实验覆盖全面，消融设计合理，对比方法均为各领域代表性方法，实验公平、客观。但未报告统计显著性误差棒（论文指出为确定性实验）。

---

## 4. 资源与算力

论文在实现细节部分明确给出了算力信息：
- **双分支视觉分词器训练**：约3天（在计算集群上）。
- **扩散解码器训练**：约3天。
- **3B参数多模态LLM的三阶段训练**：约13天。
- **GPU型号**：未明确说明具体型号（通常为A100或类似高端GPU），但提到了使用计算集群，并采用 AdamW 优化器。
- 训练数据总量：Stage1约45M图像-文本对（文本用？实际是58M？论文中Stage1提到58M，但附录表8给出45M，可能指不同子阶段）。
- 总体算力消耗较大，但作者未给出精确的GPU数量，仅给出天数。

---

## 5. 实验数量与充分性（已在第3点部分覆盖，此处补充）

- **总计实验组数**：主表4张+附录大量补充结果（约10+张表格），消融4组+可视化示例。
- **公平性**：所有对比均为标准设置，指标均为广泛接受指标（FID、mIoU、CLIP分数等）。FOCUS在两个主要理解基准上以3B参数超越许多7B模型，且与同参数量ILLUME+接近或更好。
- **局限性**：未进行跨模态或少样本测试；视频编辑仅展示定性结果，缺乏定量评估；对幻觉现象仅在消融中提到高分辨率会导致语言理解轻微下降，未深入分析。

---

## 6. 论文的主要结论与发现

1. FOCUS 成功实现了一个**统一的端到端框架**，将像素级分割感知与区域可控图像生成相结合，支持自然语言驱动的交互式编辑。
2. 渐进式多阶段训练策略（分辨率逐步提升、任务复杂度递增）有效缓解了高分辨率下语言理解下降的问题，实现了各任务间的平衡。
3. 双分支视觉编码器 + 门控交叉注意力适配器在分割和生成任务中均优于单分支或简单融合方案。
4. 连续视觉令牌输入比离散令牌输入显著提升了语言理解和生成质量（POPE从82.1→85.3，MMB从50.4→70.9，GenAI-bench Adv从0.65→0.72）。
5. 分割掩码用于空间引导是区域编辑效果的关键：FOCUS自己生成的、与指令对齐的掩码优于无掩码或通用分割掩码。
6. FOCUS 在指代分割上接近或超越专门的分割模型，在多模态理解上达到同参数量最优，在可控生成上达到领先水平。

---

## 7. 优点

1. **完全端到端统一**：首次将分割、理解、生成三个模块在一个LVLM内联合训练，无需外部分割器或工具路由。
2. **渐进式训练策略**：逐步增加分辨率和任务复杂度，避免了感知与生成之间的优化冲突。
3. **双分支视觉编码器+门控交叉注意力**：有效兼顾全局语义与局部细节，并高效注入LLM。
4. **生成质量高**：通过MoVQGAN双分支分词器+ SDXL扩散解码器，在GenAI-bench和GenEval上达到一流水平，尤其在复杂指令理解上（Adv类别）表现突出。
5. **实验覆盖广**：从静态图像分割到视频实例分割，从纯理解到编辑，从交互式编辑到推理分割，覆盖主流多模态任务。
6. **消融设计清晰**：每个关键组件（多尺度、连续令牌、掩码引导、渐进训练）均通过实验验证其必要性。

---

## 8. 不足与局限

1. **高分辨率下语言理解的幻觉问题**：论文在表5中指出，直接用1024分辨率训练会导致POPE/MMB/SEED下降，虽通过渐进式训练缓解，但未根本解决特征冲突。
2. **视频编辑缺少定量评价**：附录中进行了视频分割的定量实验（DAVIS、YouTube-VIS等），但视频编辑（如帧一致性编辑）仅给出图1示例，无标准基准验证。
3. **训练成本高**：3B参数模型需要约13天，且未提供详细GPU数量，对于资源有限团队复现门槛较高。
4. **未见跨域/开放域泛化测试**：实验主要集中在COCO系列和通用基准，未在极端风格、医学图像、卫星图像等场景测试。
5. **未报告统计误差**：论文指出实验为确定性，但多轮训练可能带来方差，缺少误差棒可能影响可重复性验证。
6. **安全与偏见问题未讨论**：论文在NeurIPS Checklist中声称无社会影响，但生成编辑模型存在潜在滥用风险（deepfake等），未提出应对措施。
7. **模型参数量固定**：仅采用3B LLM，未探索更大规模（如7B/13B）的效果，也未见对知识蒸馏或轻量化方法的讨论。

（完）
