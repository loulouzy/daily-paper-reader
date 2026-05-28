---
title: "FUDOKI: Discrete Flow-based Unified Understanding and Generation via Kinetic-Optimal Velocities"
title_zh: FUDOKI：基于离散流和动力学最优速度的统一理解与生成
authors: "Jin Wang, Yao Lai, Aoxue Li, Shifeng Zhang, Jiacheng Sun, Ning Kang, Chengyue Wu, Zhenguo Li, Ping Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RSVdHXZN6D"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 新的多模态LLM架构，使用离散流匹配
tldr: 本文提出FUDOKI模型，摒弃了当前多模态大语言模型中主流的自回归架构，采用离散流匹配作为统一框架。通过利用度量诱导的概率路径和动力学最优速度，模型同时实现了视觉理解和图像生成。实验表明该方法在多个任务上胜过自回归基线，并克服了光栅扫描顺序等限制。该工作为MLLM提供了新的架构范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 364, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 365, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 363, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 365, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 218, \"height\": 149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 238, \"height\": 151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 200, \"height\": 152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 219, \"height\": 146, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 129, \"height\": 153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 1160, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1433, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 473, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 467, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1433, \"height\": 1382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1426, \"height\": 1449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1435, \"height\": 1045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 226, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 266, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 222, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 227, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 278, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 263, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 268, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 270, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 270, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 271, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 268, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 271, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 269, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1163, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 264, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rsvdhxzn6d/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 317, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rsvdhxzn6d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1030, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rsvdhxzn6d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rsvdhxzn6d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 1055, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rsvdhxzn6d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1190, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rsvdhxzn6d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 680, \"height\": 132, \"label\": \"Table\"}]"
motivation: 自回归架构在图像生成和因果推理上存在固有限制。
method: 采用离散流匹配替代自回归，结合动力学最优速度进行统一建模。
result: 在理解和生成任务上均优于自回归基线。
conclusion: 离散流匹配可作为自回归的有效替代，推动MLLM发展。
---

## Abstract
The rapid progress of large language models (LLMs) has catalyzed the emergence of multimodal large language models (MLLMs) that unify visual understanding and image generation within a single framework. However, most existing MLLMs rely on autoregressive (AR) architectures, which impose inherent limitations on future development, such as the raster-scan order in image generation and restricted reasoning abilities in causal context modeling. In this work, we challenge the dominance of AR-based approaches by introducing FUDOKI, a unified multimodal model purely based on discrete flow matching, as an alternative to conventional AR paradigms. By leveraging metric-induced probability paths with kinetic optimal velocities, our framework goes beyond the previous masking-based corruption process, enabling iterative refinement with self-correction capability and richer bidirectional context integration during generation. To mitigate the high cost of training from scratch, we initialize FUDOKI from pre-trained AR-based MLLMs and adaptively transition to the discrete flow matching paradigm. Experimental results show that FUDOKI achieves performance comparable to state-of-the-art AR-based MLLMs across both visual understanding and image generation tasks, highlighting its potential as a foundation for next-generation unified multimodal models. Furthermore, we show that applying test-time scaling techniques to FUDOKI yields significant performance gains, further underscoring its promise for future enhancement through reinforcement learning.

---

## 论文详细总结（自动生成）

基于您提供的论文 PDF 提取文本，我将按照要求生成一份详细的中文总结。

---

# FUDOKI：基于离散流和动力学最优速度的统一理解与生成 —— 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：当前大多数统一多模态大语言模型（MLLMs）依赖自回归（AR）架构，但其存在固有限制，例如图像生成时必须遵循光栅扫描顺序、因果上下文建模限制了推理能力、难以进行自我纠正等。这些限制在需要复杂推理和深度上下文理解的场景（如具身AI、自主智能体）中尤为突出。因此，寻找 AR 之外的替代架构范式是推动下一代 MLLM 发展的关键问题。
- **整体含义**：本文提出 **FUDOKI**，第一个完全基于**离散流匹配（Discrete Flow Matching）** 的统一多模态模型，目标是挑战 AR 范式的主导地位，将离散流匹配作为统一的生成与理解框架，实现视觉理解和图像生成的无缝融合。

## 2. 方法论

### 核心思想
- 采用**离散流匹配**框架，定义从源分布到目标分布的概率路径，并通过**动力学最优速度**（kinetic-optimal velocities）驱动生成过程。该方法超越了先前仅依赖掩码噪声过程的掩码扩散模型。
- 关键创新：使用**度量诱导的概率路径**（metric-induced probability paths），通过 token 嵌入之间的语义距离定义软插值，使得语义相似的 token 也能被合理过渡，增强学习的语义意义。

### 关键技术细节
1. **概率路径定义**：
   - 给定距离函数 \(d(\cdot, \cdot)\)（采用归一化 token 嵌入的 L2 距离），条件概率定义为：
     \[
     p_t(x_i \mid x_i^1) = \text{softmax}\left(-\beta_t \cdot d(x_i, x_i^1)\right)
     \]
     其中 \(\beta_t\) 为单调调度，\(\beta_0=0,\ \beta_1=\infty\)。
2. **动力学最优速度**：
   - 通过最小化动能（flux 幅值）获得最优速度 \(u_t^i\)，使得概率质量从较远的状态流向较近的状态，实现单调收敛。
3. **模型架构**：
   - 基于 Janus-1.5B 架构改造：使用**全注意力掩码**（双向上下文）替代因果掩码；对输出 logits 进行**移位操作**以继承预训练 AR 模型的 next-token 预测能力；**移除显式时间嵌入层**，让模型从噪声输入中隐式推断时间步。
   - 文本使用 102,400 词汇 tokenizer；图像理解使用 SigLIP 语义编码器，图像生成使用 LlamaGen 像素编码器/解码器（词表大小 16,384）。两个输出头（文本头、图像头）根据任务选择。
4. **训练**：
   - 两阶段微调：第一阶段冻结编码器和适配器，仅微调 Transformer 主体（快速适应离散流范式）；第二阶段全参数微调。
   - 损失函数：期望交叉熵，预测目标序列 \(x_1\)。
5. **推理**：
   - 使用欧拉求解器模拟连续时间马尔可夫链：每一步预测 \(x_1\)，计算条件转移率 \(\lambda_i\)，依据随机阈值决定是否跳转到更接近预测的 token。**每个 token 在后续步骤中都可以被修改**，实现自我纠正，区别于掩码扩散中一旦揭掩码即固定的做法。

## 3. 实验设计

- **生成任务基准**：
  - **GenEval**：评估单对象、两对象、计数、颜色、位置、颜色属性等细粒度对齐，Overall 得分。
  - **DPG-Bench**：包含 1,065 个密集长提示，评估全局、实体、属性、关系等细粒度语义对齐。
- **理解任务基准**：
  - **POPE**（目标幻觉）、**MME-P**（综合感知）、**MMB**（多模态理解）、**SEED**（多模态理解）、**GQA**（场景推理）、**MMMU**（专家级多学科理解）、**MM-Vet**（综合能力）。
  - 额外：**MathVista**（数学推理）。
- **对比方法**：
  - AR 模型：LlamaGen, Emu3-Gen, Janus, Janus-Pro, LWM, Chameleon, ILLUME, TokenFlow-XL 等。
  - AR+扩散混合：Show-o, Transfusion。
  - 扩散模型：UniDisc, D-DiT。
  - 同时对比了生成专用模型（SD v1.5, SDXL, DALL-E 3, PixArt-α 等）。
- **消融实验**：
  - AR 初始化 vs 从头训练。
  - 时间嵌入层的有无。
  - 推理步数对质量-速度权衡的影响（不同 timestep）。
  - 自纠正能力量化（使用 MMVet 基准，让模型修正基线回答）。
- **推理缩放**：使用 VILA-Judge 对 32 个候选生成图像选优，或 LLM Judge 对 8 个候选理解答案选优。
- **额外定性实验**：迷宫导航任务（FUDOKI vs GPT-4o/Image-1）。

## 4. 资源与算力

- **训练算力**：整个训练过程约 **43,000 GPU 小时**。
- **GPU 型号与数量**：论文未明确说明具体的 GPU 型号（如 A100 或 H100）及数量，仅提到总时长。训练数据规模约 13M 样本。

## 5. 实验数量与充分性

- **实验数量**：包含 2 个图像生成基准（GenEval, DPG-Bench）、8 个理解基准（POPE, MME-P, MMB, SEED, GQA, MMMU, MM-Vet, MathVista），以及多项消融和分析实验（自纠正、推理缩放、训练策略、速度-质量权衡、迷宫导航）。总计 10 余组定量实验 + 多个定性对比。
- **充分性与公平性**：
  - 对比了多种主流方法（AR、AR+扩散、纯扩散），且基线均为公开报告结果。
  - 与同规模（1.5B 参数）模型直接对比（Janus-1.5B, Janus-Pro-1B, Show-o-1.3B），公平性较好。
  - 消融实验设计合理，覆盖了初始化策略、架构选择（时间嵌入）、推理效率等关键因素。
  - 但训练数据规模（13M）远小于一些基线（如 Chameleon 1.4B），可能影响公平比较。
  - 未报告多次运行的方差或置信区间，统计显著性未明确。

## 6. 主要结论与发现

- FUDOKI 在**视觉理解**和**图像生成**两个任务上均达到与最先进 AR 模型（如 Janus-Pro-1B）相当的性能，甚至在某些子项上更优（例如 GenEval 总体 0.77 vs Janus-Pro 0.73）。
- 离散流匹配框架带来的**双向上下文集成**和**迭代自纠正**能力，在复杂推理（如 MathVista 38.6 vs Janus-Pro 35.1）和自纠正实验中表现出明显优势。
- **推理缩放**（test-time scaling）可显著提升生成和理解性能（GenEval 从 0.77 升至 0.88；MM-Vet 从 38.0 升至 55.5），表明模型具有通过强化学习进一步优化的潜力。
- 离散流匹配在较少推理步数下即可实现与 AR 相当或更优的质量速度权衡，推理效率更高。

## 7. 优点

- **架构创新**：首个完全基于离散流匹配的统一多模态模型，为 MLLM 提供了不同于 AR 的新范式。
- **自纠正能力**：推理过程中每个 token 均可被修改，克服了 AR 和掩码扩散中错误累积/固定不可修改的缺陷，提高了输出一致性。
- **推理灵活性**：支持可变的采样步数和推理缩放，可对多个候选结果进行后选优，适应不同质量-速度要求。
- **高效初始化策略**：从预训练 AR 模型进行两阶段迁移，大幅降低从头训练的成本，同时保留部分预训练知识。
- **定性表现**：在迷宫导航等需多步决策的任务中表现出良好的空间一致性和状态跟踪能力，超越 GPT-4o/Image-1。

## 8. 不足与局限

- **固定序列长度**：当前实现要求采样前固定序列长度，不支持动态长度生成，限制了开放任务的应用。
- **复杂场景仍存在失败**：如文本生成（图像中嵌入特定文字）、专家级知识理解（如植物病理识别）等场景仍表现不佳。
- **数据规模较小**：训练仅使用 13M 数据，低于许多基线（如 Chameleon 的 1.4B），可能未充分挖掘模型潜力。与更大规模模型（如 Bagel 14B）存在显著差距。
- **模型规模有限**：仅实验了 1.5B 参数版本，未探索更大规模下的扩展性。
- **实验覆盖不足**：未涉及视频理解/生成、多轮对话中的隐含任务、跨语言场景；未报告多次运行统计误差。
- **潜在偏差与公平性**：论文未讨论数据集中的偏见、模型安全过滤机制或伦理影响评估。

（完）
