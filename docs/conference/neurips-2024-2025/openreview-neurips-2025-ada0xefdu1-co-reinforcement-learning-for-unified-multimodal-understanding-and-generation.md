---
title: Co-Reinforcement Learning for Unified Multimodal Understanding and Generation
title_zh: 面向统一多模态理解与生成的协同强化学习
authors: "Jingjing Jiang, Chongjie Si, Jun Luo, Hanwang Zhang, Chao Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=aDa0xEFDu1"
tags: ["query:llm-vlm"]
score: 10.0
evidence: 多模态上下文中大语言模型的强化学习
tldr: "针对统一多模态大语言模型中理解和生成能力难以协同提升的问题，CoRL提出两阶段强化学习框架：先联合优化两种能力，再针对特定任务精调，使模型ULM-R1在多项基准上平均提升7%，实现了双能力的协同进化。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ada0xefdu1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 741, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ada0xefdu1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ada0xefdu1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 1387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ada0xefdu1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ada0xefdu1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 517, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 975, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 835, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 632, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 335, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 423, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ada0xefdu1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 337, \"label\": \"Table\"}]"
motivation: 统一多模态大语言模型的理解与生成能力如何协同增强尚未被探索。
method: 提出CoRL框架，包括统一RL阶段联合优化和精调RL阶段任务增强。
result: "ULM-R1在多种多模态任务上平均提升7%。"
conclusion: 协同强化学习能有效同步提升多模态理解和生成能力。
---

## Abstract
This paper presents a pioneering exploration of reinforcement learning (RL) via group relative policy optimization for unified multimodal large language models (ULMs), aimed at simultaneously reinforcing generation and understanding capabilities. Through systematic pilot studies, we uncover the significant potential of ULMs to enable the synergistic co-evolution of dual capabilities within a shared policy optimization framework. Building on this insight, we introduce \textbf{CoRL}, a \textbf{Co}-\textbf{R}einforcement \textbf{L}earning framework comprising a unified RL stage for joint optimization and a refined RL stage for task-specific enhancement. With the proposed CoRL, our resulting model, \textbf{ULM-R1}, achieves average improvements of 7\% on three text-to-image generation datasets and 23\% on nine multimodal understanding benchmarks. These results demonstrate the effectiveness of CoRL and highlight the substantial benefits of reinforcement learning in facilitating cross-task synergy and optimization for ULMs. Code is available at \url{https://github.com/mm-vl/ULM-R1}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：大语言模型的后训练阶段中，强化学习（RL）已展现出优异的数据效率和对齐能力，特别是基于可验证奖励的组相对策略优化（GRPO）方法（如DeepSeek-R1）。然而，现有RL在多模态领域的应用主要集中在**理解任务**（推理、问答）或**生成任务**，缺乏对**统一多模态大语言模型（ULM）** 中**理解与生成双重能力协同增强**的探索。
- **核心问题**：ULM如何通过RL同时提升理解和生成能力？能否实现跨任务的正向协同进化？
- **整体含义**：论文首次验证了GRPO在ULM上联合优化双能力的可行性，并提出**CoRL框架**，使模型ULM-R1在多项基准上取得显著提升，为后训练阶段ULM的能力增强提供了新范式。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用“Foundation-then-Specialization”策略，即**两阶段强化学习**：
  1. **统一RL阶段（Unified RL）**：将理解和生成任务的数据及奖励纳入同一GRPO优化过程，实现双能力联合进化。
  2. **精调RL阶段（Refined RL）**：分别对理解和生成任务进行独立的、任务特定的RL精调，提升各自专有能力。
- **关键技术细节**：
  - **奖励设计**：
    - **生成任务**：提出**双向循环一致性奖励** `R_cycle`（LPIPS衡量视觉一致性 + SPICE衡量文本重述一致性）和**文本-图像匹配奖励** `R_TIM`（基于ULM自身的token级余弦相似度），替代简单的CLIP Score。
    - **理解任务**：使用**准确性奖励**（选择题/开放题正确性）和**格式奖励**（强制要求`<think>`、`<answer>`格式）。
  - **优化算法**：基于**GRPO**（Group Relative Policy Optimization），采用组内相对优势估计，避免额外价值模型。
  - **训练流程**：
    - 阶段一：统一目标函数 `L_S1`（公式6），**省略KL散度约束**以提高效率。
    - 阶段二：分别使用任务特定奖励，**重新引入KL散度约束**以保证稳定性。
  - **超参数**：`λ`（公式5中平衡理解和生成奖励的系数）设为0.8，可使双任务达到最佳平衡。

### 3. 实验设计：使用了哪些数据集/场景、基准、对比方法

- **生成基准**：GenEval（对象级对齐）、WISE（世界知识）、DPG-Bench（密集提示遵循）。
- **理解基准**：MMStar、MMMU（多选）；MMVet、POPE、LogicVista（开放题）；WeMath、MathVista、MathVerse、MathVision（数学推理，混合格式）。
- **基线模型**：
  - 专门生成模型：PixArt-α、SD系列、DALL·E 3、LlamaGen、SimpleAR等。
  - 统一理解与生成模型：TokenFlow、Emu3、LWM、Janus-Pro、Show-o、HermesFlow等。
  - 仅理解模型：SmolVLM、Qwen2.5-VL、InternVL3等。
- **消融实验**：
  - 四种RL范式对比（单独RL、权重合并、循环RL、统一RL）。
  - 奖励函数消融（`R_cycle`、`R_TIM`、`R_CLIP`组合）。
  - 视觉一致性度量对比（PSNR、MSE、SSIM、LPIPS）。
  - 超参数λ的影响。
  - 可扩展性验证（Janus-1.3B、Janus-Pro-7B）。

### 4. 资源与算力

- **硬件**：8块 **NVIDIA H20 (96GB)** GPU。
- **训练配置**：阶段一：batch size 16，学习率4e-6，8个采样；阶段二：学习率1e-6，16个采样（生成任务）或32个采样（理解任务）。
- **未明确说明**：具体训练时长（epoch数）、总GPU小时数未在原文中提供。

### 5. 实验数量与充分性

- **实验数量**：涵盖了3个生成基准、9个理解基准，共12个标准评测；进行了5项主要消融（表3-7）及定性对比。
- **充分性**：
  - 对比了当前主流专用模型和统一模型，包括同规模和更大规模模型。
  - 消融实验覆盖了RL策略、奖励函数、一致性度量、超参数、模型规模可扩展性。
  - 提供了定性样例展示成功与失败案例。
  - 实验设计较为全面、客观，使用统一评估工具（VLMEvalKit），结果可复现。

### 6. 论文的主要结论与发现

- **统一RL优于其他范式**：统一RL（联合优化）比单独RL、权重合并、循环RL在双任务上均取得更好成绩。
- **CoRL框架有效**：在Janus-Pro-1B基础上，生成平均提升7%（GenEval 73.0→77.3；DPG 82.6→83.9），理解平均提升23%（WeMath 5.9→21.1；LogicVista 23.9→34.5等）。
- **奖励设计贡献显著**：`R_cycle`＋`R_TIM`组合优于单独使用或使用CLIP Score；LPIPS作为视觉一致性度量效果最佳。
- **可扩展性**：CoRL在较大模型（Janus-Pro-7B）和较小模型（Janus-1.3B）上均带来一致提升，但推理能力提升幅度未随规模线性增长。

### 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 首次将GRPO应用于ULM的联合理解与生成优化，提出“统一+精调”两阶段范式。
  - 设计**双向循环一致性奖励**和**自文本-图像匹配奖励**，无需外部模型即可实现细粒度对齐。
- **实验严谨**：
  - 预实验系统比较四种RL策略，为方法选择提供实证依据。
  - 消融实验全面覆盖奖励、超参数、模型变体等关键因素。
  - 开源训练数据和代码，提升可复现性。
- **结果显著**：在多个困难推理基准（如WeMath）上取得大幅提升，验证了RL在能力跃迁中的潜力。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **能力差距**：虽然双能力均有提升，但生成与理解之间仍存在性能鸿沟，理解奖励设计较简单（仅正确性+格式）。
- **实验规模**：主要实验基于1.5B模型，7B模型仅用LoRA微调，更大规模（如70B）的效果未验证。
- **计算资源**：仅使用8块H20，训练细节（如总时长、收敛速度）未报告，复现成本可能偏高。
- **奖励局限性**：生成奖励依赖LPIPS和SPICE，对风格、艺术性等较难捕捉；理解奖励未考虑推理过程的质量，仅关注最终答案。
- **安全性/偏见**：未讨论模型输出可能存在的有害内容或偏见，应用时需注意。
- **任务范围**：目前仅限文本到图像生成和视觉问答，未扩展至视频、音频等多模态。

（完）
