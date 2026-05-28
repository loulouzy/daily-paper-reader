---
title: Reducing the Probability of Undesirable Outputs in Language Models Using Probabilistic Inference
title_zh: 使用概率推理降低语言模型中不良输出的概率
authors: "Stephen Zhao, Aidan Li, Rob Brekelmans, Roger Baker Grosse"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BneVLr7iis"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 大语言模型的强化学习
tldr: 针对标准RL优化平均奖励但忽视不良输出概率的问题，RePULSe引入额外损失，利用学习到的提案指导采样低奖励输出并降低其概率，从而在不牺牲平均性能的前提下减少不良输出，实现了更优的权衡。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 672, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 678, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 679, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 679, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 673, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 682, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 680, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 678, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bnevlr7iis/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 679, \"height\": 509, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1477, \"height\": 841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 901, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 2093, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 1526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 2062, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1456, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bnevlr7iis/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 1657, \"label\": \"Table\"}]"
motivation: 现有RL对齐方法优化平均奖励，但难以有效降低不良输出概率，且往往以平均性能为代价。
method: 在标准RL损失基础上增加额外损失，引导采样低奖励输出并降低其概率。
result: 实验表明，在保持平均奖励的同时显著降低了不良输出的概率。
conclusion: 该方法为语言模型安全对齐提供了新的权衡优化策略。
---

## Abstract
Reinforcement learning (RL) has become a predominant technique to align language models (LMs) with human preferences or promote outputs which are deemed to be desirable by a given reward function. Standard RL approaches optimize average reward, while methods explicitly focused on reducing the probability of undesired outputs typically come at a cost to average-case performance. To improve this tradeoff, we introduce RePULSe, a new training method that augments the standard RL loss with an additional loss that uses learned proposals to guide sampling low-reward outputs, and then reduces those outputs’ probability. We run experiments demonstrating that RePULSe produces a better tradeoff of expected reward versus the probability of undesired outputs and is more adversarially robust, compared to standard RL alignment approaches and alternatives.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在大语言模型（LLM）的强化学习（RL）对齐中，标准方法（如RLHF）优化平均奖励，但难以有效降低低概率但高风险的“不良输出”（undesirable outputs）的概率。即使百万分之一的失败率在规模化部署中也可能造成严重后果（如用户因聊天机器人而自杀的案例）。因此，需要一种能在保持平均性能的同时，更有效地减少不良输出概率的训练方法。
- **研究动机**：现有RL算法（如REINFORCE、PPO）在训练后期很少采样到低奖励输出，导致对其概率的直接梯度更新不足；而一些风险敏感的RL方法（如CVaR-RL）虽关注尾部风险，但样本效率低，难以直接应用于语言模型场景。因此，作者提出一种利用概率推断技术持续聚焦低奖励样本，并显式降低其概率的新方法。
- **整体含义**：该工作旨在改善“期望奖励”与“不良输出概率”之间的权衡，使LLM对齐更安全、更鲁棒。

## 2. 方法论

### 核心思想
- **RePULSe (Reducing the Probability of Undesirable Low-reward Sequences)**：在标准RL损失（如REINFORCE）基础上，增加一个额外的损失项，该损失使用**学习得到的提议分布（proposal）** 来引导采样低奖励输出，然后显式降低这些输出的概率。
- 关键创新：通过概率推断技术（如自归一化重要性采样，SNIS）构建一个**目标分布** $\sigma_\theta$，它放大当前LM策略下低奖励区域的概率质量，并学习一个提议分布$q_\xi$来近似从$\sigma_\theta$中采样。这确保了即使在RL训练后期，也能持续获得低奖励样本用于梯度更新。

### 关键技术细节
1. **整体梯度**（式3）：
   $$-\mathbb{E}_{s_0\sim D} \left[ \nabla_\theta \mathcal{L}_r + \alpha \, \mathbb{E}_{s_{1:T}\sim \sigma_\theta} [\nabla_\theta \mathcal{L}_u] \right]$$
   - $\mathcal{L}_r$：标准RL损失（如REINFORCE），维护期望奖励。
   - $\mathcal{L}_u$：降低低奖励样本概率的损失，本文直接使用**梯度上升**（负SFT梯度）：$-\nabla_\theta \log p_\theta(s_{1:T}|s_0)$。
   - $\alpha$：超参数，权衡两部分。

2. **低奖励目标分布** $\sigma_\theta$ 的选择：
   - 温度缩放（Negative Temperature Scaling）：$\sigma_\theta(s_{1:T}|s_0) \propto p_\theta(s_{1:T}|s_0) e^{-\beta r(s_{0:T})}$
   - 奖励阈值（Reward Thresholding）：$\sigma_\theta(s_{1:T}|s_0) \propto p_\theta(s_{1:T}|s_0) \mathbb{I}[r(s_{0:T}) < \eta]$
   - 本文主要使用温度缩放形式。

3. **提议分布学习**：
   - 使用自归一化重要性采样（SNIS）从$\sigma_\theta$近似采样，需要与目标匹配的提议分布$q_\xi$。
   - 学习$q_\xi$时，最小化质量覆盖的KL散度 $D_{KL}(\sigma_\theta \parallel q_\xi)$，以确保覆盖多种不良输出。
   - 采用本文改进的**对比扭曲学习（CTL）** 损失（基于Zhao et al., 2024），通过新颖的提议参数化（直接参数化$q_\xi$，并通过其与$p_\theta$的比值反推出扭曲函数$\psi$），减少了计算量并保持模型容量。
   - 算法流程（Alg.1）：每个训练步，先从$q_\xi$采样K_q个序列用于更新$q_\xi$（CTL），再用这些样本通过SNIS估算$\mathcal{L}_u$，同时从$p_\theta$采样K_p个序列用于$\mathcal{L}_r$，最后更新$p_\theta$。

4. **与基线方法的对比**：标准RL（PPO/RLOO）、带奖励变换的REINFORCE、不使用学习提议分布的$p_\theta$-proposal基线。

## 3. 实验设计

### 数据集/场景
- **玩具实验（Toy Experiment）**：使用DistilGPT2作为LM，toxicity classifier（Corrêa, 2023）作为奖励模型。训练于单个提示“This man is a”，最多输出2个token。定义不良输出为包含特定脏话token的序列。可解析计算总概率。
- **更真实的实验（Realistic Experiments）**：
  - **场景1**：SmolLM-135M-Instruct作为LM，Deberta-v3-large-v2作为RM，输出最多20个token。
  - **场景2**：Llama-3.2-1B-Instruct作为LM，Skywork-Reward-V2-Llama-3.2-1B作为RM，输出最多100个token。
  - 训练数据集：20,000个提示，混合了对抗性提示（来自ALERT）和非对抗性提示（来自OpenRLHF collection，主要来自UltraFeedback）。测试集为同类但未训练的提示。
  - 不良输出定义：根据阈值$\eta$（场景1：r<-5；场景2：r<-7）判定。
  - 奖励中加入了KL散度惩罚（系数$1/\beta$分别为0.2和2）以保持流畅性和防止奖励作弊。

### 对比方法
- PPO（无奖励变换）
- RLOO（REINFORCE-Leave-One-Out，无奖励变换）
- RLOO + 多种奖励变换（如$r'(s)=r(s)e^{\beta r(s)}$等）
- $p_\theta$-proposal基线（使用$p_\theta$本身作为提议分布，结合温度缩放目标）
- RePULSe（使用学习到的$q_\xi$提议分布）

### 评估指标
- **平均回报（Average Return）**：包括KL惩罚的奖励期望。
- **不良输出概率**：采样中$r(s_{0:T})<\eta$的比例。
- **对抗鲁棒性**：使用GCG（Greedy Coordinate Gradient）攻击，对10个对抗提示生成1000个样本，若有任何样本$r<\eta$则攻击成功。

## 4. 资源与算力

文中明确说明：
- 玩具实验（DistilGPT2）和场景1（SmolLM-135M-Instruct）在单GPU（A40或A6000，48G内存）上运行。每个种子玩具实验<30分钟；场景1约2小时训练 + 40分钟对抗评估。
- 场景2（Llama-3.2-1B-Instruct）分布在4块L40S GPU（每块48G内存）上，每个种子约4小时训练（≈16 GPU小时），对抗评估约40分钟。
- 算力消耗中等，对大模型实验做了适当控制。

## 5. 实验数量与充分性

- **实验数量**：
  - 玩具实验：多个种子（显示置信区间），做了两组（无KL惩罚和有KL惩罚）。
  - 真实场景实验：场景1每个方法/超参数组合进行10个种子平均；场景2进行5个种子平均。超参数搜索范围较广（学习率、$\alpha$、$\beta$等）。
  - 对抗鲁棒性测试：使用10个手动选择的对抗提示，每个方法测试多个种子。
  - 消融实验：包含同更新次数对比（附录E.2）、CVaR指标对比（附录E.2）、$p_\theta$-proposal基线对比等。
- **充分性与客观性**：
  - 实验中为公平比较，RePULSe因需额外采样$q_\xi$，仅做一半的$p_\theta$梯度更新（主文中），同时也提供了同更新次数的对比（附录），结论一致。
  - 错误线采用95%置信区间（玩具实验用t分布，真实实验用bootstrap），统计严谨。
  - 但实验规模有限（135M和1B模型），未在更大规模模型（如7B、70B）上验证；输出长度也较短（最多100 token）。因此外推至前沿模型需谨慎。

## 6. 主要结论与发现

- **更好的权衡**：RePULSe在主实验和玩具实验中均能在保持期望奖励的同时，显著降低不良输出概率，改进了Pareto前沿。
- **对抗鲁棒性**：在GCG攻击下，RePULSe的对抗成功率更低，显示出更好的鲁棒性。
- **提议学习的重要性**：使用学习到的$q_\xi$（而非$p_\theta$本身作为提议）是实现上述改进的关键。
- **效率**：尽管使用一半的$p_\theta$更新次数，RePULSe仍优于基线，说明将部分计算从训练$p_\theta$转移到训练$q_\xi$是值得的。

## 7. 优点

- **方法创新性强**：将概率推断（重要性采样、扭曲）与RL对齐结合，自适应地聚焦低奖励区域，解决了标准RL采样不足的问题。
- **实验设计公平**：考虑了计算公平性（补偿采样成本），提供了同更新次数对比和多种奖励变换基线。
- **统计严谨**：报告了置信区间，使用bootstrap处理非正态分布。
- **鲁棒性分析**：不仅关注平均回报和不良概率，还测试了对抗攻击下的表现，实用价值高。
- **实现细节透明**：开源代码和数据集，提供复现命令。

## 8. 不足与局限

- **依赖接近收敛**：实验中基线经过4个epoch训练后改进较小，表明接近收敛。若训练更短或可持续改进，RePULSe使用一半$p_\theta$更新的劣势可能更明显。作者已提到在较低KL惩罚下的实验中观察到这一现象。
- **探索与规模问题**：提议分布$q_\xi$需要持续探索以覆盖$\sigma_\theta$，在更大规模模型或初始模型已经很少产生不良输出时，学习$q_\xi$的梯度信号可能不足。
- **实验规模有限**：仅测试了135M和1B模型，输出长度短（20/100 token），数据集规模中等（20K提示），未验证在7B+模型、长文本生成或大规模部署下的表现。
- **超参数敏感**：$ \alpha$和$\beta$需要调节，且不同设置下最优值差异较大。
- **潜在安全风险**：$q_\xi$被训练为倾向于产生不良输出，如果模型泄露或被恶意使用，可能造成危害。作者已讨论，但未提供具体防护措施。
- **未与DPO等非RL方法对比**：虽然论文专注于RL方法，但未与DPO等流行对齐方法比较，且实验中KL惩罚较高，可能限制了对Pareto前沿的完整刻画。

（完）
