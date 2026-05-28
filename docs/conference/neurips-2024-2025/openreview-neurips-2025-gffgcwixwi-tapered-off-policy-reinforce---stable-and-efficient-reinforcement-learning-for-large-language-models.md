---
title: Tapered Off-Policy REINFORCE - Stable and efficient reinforcement learning for large language models
title_zh: 锥形离策略REINFORCE：稳定高效的大语言模型强化学习
authors: "Nicolas Le Roux, Marc G Bellemare, Jonathan Lebensold, Arnaud Bergeron, Joshua Greaves, Alexandre Fréchette, Carolyne Pelletier, Eric Thibodeau-Laufer, Sándor Tóth, Sam Work"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gFFgCWiXWI"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 提出新的RL算法用于LLM微调
tldr: 本文提出锥形离策略REINFORCE（TOPR）算法，用于大语言模型的强化学习微调。该方法采用非对称锥形重要性采样，无需KL正则化即可实现稳定高效的学习，支持完全离线训练，统一处理正负样本。在GSM8K和MATH推理基准上，TOPR在生成和奖励建模任务中均取得了性能提升。该算法简单实用，可广泛用于LLM的RL微调。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1297, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 691, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 622, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1420, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1015, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gffgcwixwi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1451, \"height\": 857, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gffgcwixwi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1498, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gffgcwixwi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 972, \"height\": 213, \"label\": \"Table\"}]"
motivation: 现有LLM离线RL算法存在稳定性或效率问题。
method: 提出TOPR，使用锥形重要性采样改进离策略REINFORCE。
result: 在数学推理任务上提升性能，且无需KL正则化。
conclusion: TOPR是一种稳定高效的LLM强化学习微调算法。
---

## Abstract
We propose a new algorithm for fine-tuning large language models using reinforcement learning. Tapered Off-Policy REINFORCE (TOPR) uses an asymmetric, tapered variant of importance sampling to speed up learning while maintaining stable learning dynamics, even without the use of KL regularization. TOPR can be applied in a fully offline fashion, allows the handling of positive and negative examples in a unified framework, and benefits from the implementational simplicity that is typical of Monte Carlo algorithms. We demonstrate the effectiveness of our approach with a series of experiments on the GSM8K and MATH reasoning benchmarks, finding performance gains for training both a model for solution generation and as a generative verifier. We show that properly leveraging positive and negative examples alike in the off-policy regime simultaneously increases test-time accuracy and training data efficiency, all the while avoiding the ``wasted inference'' that comes with discarding negative examples. We find that this advantage persists over multiple iterations of training and can be amplified by dataset curation techniques, enabling us to match 70B-parameter model performance with 8B language models. As a corollary to this work, we find that REINFORCE's baseline parameter plays an important and unexpected role in defining dataset composition in the presence of negative examples, and is consequently critical in driving off-policy performance.

---

## 论文详细总结（自动生成）

# 论文总结：TAPERED OFF-POLICY REINFORCE

## 1. 论文的核心问题与整体含义

- **研究动机**：现有的离策略 (off-policy) 强化学习算法用于大语言模型 (LLM) 微调时存在稳定性与效率的矛盾。Naive REINFORCE 在离策略下因负奖励项导致梯度无界，模型崩溃；PPO 等算法依赖 KL 正则化或限制更新步数，限制了离线数据复用；仅用正样本的 SFT 方法丢弃负样本，浪费推理资源且限制性能提升。
- **整体含义**：论文旨在提出一种既能稳定处理负样本、又能充分利用正样本加速学习的简单 RL 算法，使 LLM 在完全离线的单轮或多轮微调中持续提升推理能力，从而降低计算开销并达到更高基准性能。

## 2. 论文提出的方法论

### 2.1 核心思想

- 采用“锥形 (tapered)”重要性采样：对正样本保留完全梯度（等价于 SFT），对负样本使用截断的重要性比，当模型概率远低于采样分布时，负样本的梯度贡献逐渐消失，从而避免模型退化。
- 无需显式 KL 正则化，算法自然有界，实现简单。

### 2.2 关键技术细节

- 定义两个截断区间：正样本使用 `a⁺ = b⁺ = 1`，即重要性比恒为 1（不衰减），负样本使用 `a⁻ = 0, b⁻ = 1`，即重要性比上限截断在 1，下限无界。
- 基线 (baseline) 参数通过改变正负样本的有效权重来调节训练集组成，论文发现最优有效正样本比例约为 10%~20%，基线并非简单等于平均回报。
- 提出“安娜·卡列尼娜采样 (Anna Karenina sampling)”：对每个问题保留第一个正解及所有负解，以平衡数据集难度。

### 2.3 公式与算法流程

- 锥形梯度公式：
  \[
  \nabla J_{\text{TOPR}}(\pi) = \sum_{\tau:R(\tau)>0} \mu(\tau) R(\tau) \nabla \log \pi(\tau) + \sum_{\tau:R(\tau)<0} \mu(\tau) \left[ \frac{\pi(\tau)}{\mu(\tau)} \right]_{0}^{1} R(\tau) \nabla \log \pi(\tau)
  \]
- 算法 1（单轮）：
  1. 从参考策略 μ 采样响应。
  2. 对每个 (x, y)，计算重要性比 π(y|x)/μ(y|x)。
  3. 对正样本设置 α = 1，对负样本设置 α = (π/μ) 截断至 [0,1]。
  4. 计算损失 ℓ = stop_gradient(α) * R(x,y) * log π(y|x)，更新梯度。

## 3. 实验设计

### 3.1 数据集与场景

- **数学推理**：GSM8K（小学数学）和 MATH（高中竞赛），使用 Llama 3 8B/70B 及 DeepSeek-R1 8B。
- **学习搜索**：clinicaltrials.gov 查询扩展任务，使用 Llama3-70B 生成训练数据，8B 模型微调。

### 3.2 对比方法

- Naive REINFORCE（无截断）、PPO（ϵ=0.2）、DPO（偏好对）、SFT（仅正样本）、Truncated Importance Sampling (TIS) 等。
- 评估指标：Pass@1, Maj@K, 以及生成有效性（无效格式比例）。
- 消融实验：不同有效正样本比例、不同实际正样本比例（10% vs 50%）、梯度裁剪影响、多轮迭代、安娜·卡列尼娜采样 vs 均匀采样等。

## 4. 资源与算力

- **硬件**：使用单个 H100 节点进行数据并行，每 GPU batch size 为 1。
- **优化器**：Adafactor（低内存），恒定学习率 5e-7，无权重衰减与 KL 正则化。
- **训练时长**：论文未给出精确的 GPU 小时数，但提到“实验在数月间运行”，并使用了“不同供应商的混合计算资源”。因此具体算力开销未明确公开。

## 5. 实验数量与充分性

- **实验数量**：论文报告了约 6 组主要实验（图 1,3,4,5,7,10），并包含大量消融、基线调节、多轮迭代、学习搜索等附录实验（图 8-12, 表 2）。
- **充分性**：
  - 在多个难度不同的数据集上验证，覆盖生成和验证任务。
  - 使用了多种对比算法（REINFORCE, PPO, DPO, SFT, TIS）和多种设置（单轮、多轮、不同正比例）。
  - 提供了置信区间（bootstrap 法，64 或 16 次采样），实验设计较客观。
  - 消融实验充分（如重要性截断 vs 标准 IS、安娜·卡列尼娜采样 vs 均匀、基线影响）。
- **潜在不足**：实验仅在数学推理和搜索领域，未涉及更广泛的 RL 应用（如游戏、机器人）或在线 RLHF 场景，结论的通用性仍需更多验证。

## 6. 论文的主要结论与发现

- TOPR 在离线推理微调中表现显著优于 Naive REINFORCE、PPO、DPO，且无需 KL 正则化，训练稳定。
- 负样本的合理利用可同时提升准确率和数据效率，减少无效生成。
- 基线参数实际上起到调节正负样本有效比例的作用，最优有效正样本比例约为 10%~20%，而非平均回报。
- 多轮迭代下 TOPR 持续改进，结合安娜·卡列尼娜采样可使 8B 模型超越 70B 模型。
- 重要性截断（而不是全重要性采样）对稳定性至关重要，尤其在负样本比例较高时。

## 7. 优点

- **算法简洁**：只需在标准 REINFORCE 上增加一步重要性比截断，易于实现和集成。
- **理论保证**：对于负样本，截断后的目标函数有界，避免模型退化（Proposition 3.2）。
- **端到端高效**：无需额外 KL 项，离线单轮训练即可达到高精度，节省推理与训练计算。
- **实验全面**：覆盖多种主流对比方法，消融分析清晰，结论可靠。

## 8. 不足与局限

- **领域局限**：仅在数学推理和少量搜索任务上验证，未测试在对话、摘要等更通用 LLM 任务或传统 RL 环境（如 Atari, MuJoCo）的表现。
- **数据生成假定**：离线设置中参考策略 μ 固定为初始模型，未考虑 μ 与 π 差距极大（如使用不同模型生成）的情况，论文提及可能面临数值挑战。
- **与在线方法比较缺失**：未与在线 PPO/GRPO/Online DPO 等真实在线 RL 方法对比，离线优势在线下可能损失。
- **计算资源未量化**：未报告总 GPU 小时数或训练成本，不利于其他研究者复现或估算。
- **超参数敏感性**：虽然 TOPR 对基线较鲁棒，但最优有效正样本比例本身需通过实验确定，可能随任务变化。
- **负样本截断上限为 1**：该选择虽经验有效，但论文未系统性探讨不同 b⁻ 值的影响。

（完）
