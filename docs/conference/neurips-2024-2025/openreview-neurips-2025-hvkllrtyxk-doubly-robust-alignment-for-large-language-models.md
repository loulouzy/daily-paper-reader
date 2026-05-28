---
title: Doubly Robust Alignment for Large Language Models
title_zh: 大语言模型的双重鲁棒对齐
authors: "Erhan Xu, Kai Ye, Hongyi Zhou, Luhan Zhu, Francesco Quinzan, Chengchun Shi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HvklLrtyxK"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 使用强化学习从人类反馈对齐大语言模型，提出鲁棒偏好优化
tldr: 本文针对强化学习从人类反馈（RLHF）中偏好模型或参考策略指定错误导致微调不稳定的问题，提出了一种双重鲁棒偏好优化算法。该算法在偏好模型或参考策略之一正确时仍保持一致性，无需两者同时正确。理论分析和实验表明，该方法在多种对齐场景下均比现有算法更稳健且性能更优，为LLM安全对齐提供了可靠工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 640, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 653, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 632, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 630, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 632, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hvkllrtyxk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 632, \"height\": 477, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1347, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 537, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 678, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1144, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 1611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 1479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 1560, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 901, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 975, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 1229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 1010, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hvkllrtyxk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1454, \"height\": 714, \"label\": \"Table\"}]"
motivation: 现有RLHF算法对偏好模型和参考策略的误指定高度敏感，导致对齐效果不稳定。
method: 提出双重鲁棒偏好优化算法，当偏好模型或参考策略之一正确时保证一致性。
result: 在多个对齐基准上，该方法比现有算法更稳健，获得了更高的奖励和安全性指标。
conclusion: 双重鲁棒设计有效提升了RLHF的鲁棒性，是LLM对齐的重要进步。
---

## Abstract
This paper studies reinforcement learning from human feedback (RLHF) for aligning large language models with human preferences. While RLHF has demonstrated promising results, many algorithms are highly sensitive to misspecifications in the underlying preference model (e.g., the Bradley-Terry model), the reference policy, or the reward function, resulting in undesirable fine-tuning. To address model misspecification, we propose a doubly robust preference optimization algorithm that remains consistent when either the preference model or the reference policy is correctly specified (without requiring both). Our proposal demonstrates superior and more robust performance than state-of-the-art algorithms, both in theory and in practice. The code is available at https://github.com/DRPO4LLM/DRPO4LLM

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 强化学习从人类反馈（RLHF）是后训练阶段使大语言模型（LLM）与人类偏好对齐的主流范式，但其现有算法（如基于 PPO 或 DPO）对偏好模型（如 Bradley-Terry 模型）、参考策略或奖励函数的**误指定**高度敏感，导致微调不稳定甚至对齐失败。
- 本文旨在解决这一鲁棒性问题，提出一种**双重鲁棒偏好优化（DRPO）**算法，在偏好模型**或**参考策略之一正确指定时仍能保持一致性，从而显著提升 RLHF 的稳健性。

### 2. 论文提出的方法论
- **核心思想**：借鉴因果推断中的双重鲁棒估计方法，构造一个联合直接法（DM）和重要性采样（IS）的**估计函数** \(\psi\)（公式 8），用于评估目标策略相对于参考策略的总偏好概率 \(p^*(\pi)\)。
- **关键技术细节**：
  - 估计函数包含两项：第一项是 DM 项（依赖偏好模型 \(\hat{g}\)），第二项是 IS 项（依赖参考策略 \(\hat{\pi}_{\text{ref}}\) 和残差 \(Z-\hat{g}\)），以校正 DM 的偏差。
  - 通过最大化 \( \hat{p}_{\text{DR}}(\pi) - \beta \, \text{KL}(\pi \| \hat{\pi}_{\text{ref}}) \)（公式 10）进行优化，利用 KL 正则化防止过拟合。
  - 实际训练中采用**比率裁剪**（避免极端重要性权重）、**停止梯度**、**蒙特卡洛采样**（从当前策略采样新响应）和**分组相对策略优化（GRPO）风格的 KL 散度**以稳定训练。
- **理论性质**：
  - 偏好评估的 MSE 上界（定理 2）表明：当偏好模型或参考策略之一正确时，MSE 趋于零（双重鲁棒性，推论 3）；两者均正确时达到半参数效率（推论 4）。
  - 偏好优化策略的性能差距上界（定理 5）再次证明双重鲁棒性（推论 6）；在 Bradley-Terry 模型成立时，DRPO 的次优性上界优于 PPO 和 DPO（定理 7）。

### 3. 实验设计
- **数据集与场景**：
  - **IMDb**（合成数据集）：使用情感分类器作为真实偏好生成器，验证**偏好估计**的双重鲁棒性。
  - **TL;DR**（Reddit 摘要）：参考模型因训练数据过滤存在**参考策略误指定**，测试优化鲁棒性。
  - **Anthropic HH**（对话助手）：因存在噪声标注常用作**偏好模型误指定**场景，测试泛化能力。
- **基准方法**：PPO、DPO 及七种 DPO 变体（Dr. DPO、rDPO、cDPO、CPO、ORPO、IPO、RSO）；DRPO 使用两种偏好模型（BT 模型 DRPO-BT 和通用偏好模型 DRPO-GPM）。
- **评估指标**：GPT-4o-mini 的**胜率**（in-distribution）和 AlpacaEval 2.0 的**长度控制胜率**（out-of-distribution）。

### 4. 资源与算力
- 论文在附录 C 中提及实验硬件：
  - **偏好评估实验**：1× NVIDIA RTX 6000 Ada GPU + AMD Ryzen Threadripper PRO 7945WX 12-core CPU。
  - **偏好优化实验**：1× H20 NVLink GPU + 20 vCPU Intel Xeon Platinum 8457C 处理器。
- **未明确给出**各实验的具体训练时长、总 GPU 时数或模型参数量（模型规模为 125M、1B、1.5B 等中小型）。

### 5. 实验数量与充分性
- **实验组数**：
  - **偏好评估**：1 个数据集（IMDb），4 种模型规格组合（偏好模型/参考策略正确/误指定），500 次重复，不同样本量下报告 MSE 和 95% 置信区间。
  - **偏好优化**：2 个数据集（TL;DR、HH），每个数据集包含与 9 种基线方法的对比，并展示不同温度（0.25、0.75、1.0）下的胜率矩阵；额外进行 AlpacaEval 2.0 的分布外评估（仅在 HH）。
- **充分性评价**：实验设计较全面，覆盖了论文声称的两种误指定场景，且通过重复实验提供统计可靠性。但仅在**中小规模模型**（最大 1.5B）上验证，未扩展至 7B/13B 等更大模型；未见详细的消融实验（如裁剪阈值、KL 系数影响分析）。

### 6. 论文的主要结论与发现
- DRPO 在偏好评估中展现出明确的**双重鲁棒性**：当偏好模型或参考策略之一正确时 MSE 大幅下降，两者均正确时达到最优。
- 在偏好优化中，DRPO（尤其 DRPO-GPM）在 **TL;DR** 上显著优于所有基线（包括 PPO、DPO 及其鲁棒变体），在 **HH** 上与最先进的鲁棒 DPO 变体持平或略优，且优于 PPO。
- 理论分析表明 DRPO 的次优性上界更依赖**估计误差的乘积**，因此对单一模型误指定更具容错性。

### 7. 优点
- **理论扎实**：严格证明了双重鲁棒性、半参数效率及更优的次优性上界，填补了现有 RLHF 理论分析中缺少 DPO 次优性一般界（不依赖线性假设）的空白。
- **实现稳健**：采用重要性比率裁剪、停止梯度、GRPO 风格 KL 散度等实用技巧，兼顾稳定性和效率。
- **实验设计针对性强**：特意选择 TL;DR（参考策略误指定）、HH（偏好模型误指定）来验证鲁棒性，并用合成数据 IMDB 做定量评估。

### 8. 不足与局限
- **重要性采样的方差风险**：当目标策略与参考策略差异过大时，即使经过裁剪，方差仍可能较大，影响训练稳定性。
- **模型规模限制**：所有实验仅在 1B/1.5B 级模型上进行，未在更大模型（如 7B/13B）上验证，无法保证可推广性。
- **计算资源有限**：仅使用单 GPU 实验，缺少多 GPU 分布式训练下的性能和效率评估。
- **未考虑多样化的偏好**：本文主要关注二元偏好（胜率），未讨论模型输出多样性、公平性等更广泛的对齐指标。
- **消融不充分**：未系统分析各组件（裁剪阈值、KL 系数、蒙特卡洛采样数）的敏感性，可能限制实际部署时的超参数选择。

（完）
