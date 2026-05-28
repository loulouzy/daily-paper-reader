---
title: "Learning to Think: Information-Theoretic Reinforcement Fine-Tuning for LLMs"
title_zh: 学会思考：面向LLM的信息论强化微调
authors: "Jingyao Wang, Wenwen Qiang, Zeen Song, Changwen Zheng, Hui Xiong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=22CqLfjiVl"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 基于信息论的强化微调框架提升LLM推理效率
tldr: 现有LLM推理方法忽视效率与效果平衡，导致冗长推理链。本文提出L2T框架，采用信息论强化微调，通过层次化会话和基于信息增益的过程奖励，在减少令牌的同时保持推理质量。实验证明该方法能有效压缩推理链，提升令牌效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 535, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 896, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 741, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22cqlfjivl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 2161, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 672, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22cqlfjivl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 229, \"label\": \"Table\"}]"
motivation: 现有LLM推理方法忽略推理效率，导致不必要的长链和令牌浪费。
method: 提出基于信息论的过程奖励，在每个回合量化参数信息增益，实现层次化强化微调。
result: 在推理任务上以更少令牌达到甚至超越原有性能。
conclusion: 信息论过程奖励能有效平衡推理效果与效率，提升LLM实用性。
---

## Abstract
Large language models (LLMs) excel at complex tasks thanks to advances in their reasoning abilities. However, existing methods overlook the trade-off between reasoning effectiveness and efficiency, often encouraging unnecessarily long reasoning chains and wasting tokens. To address this, we propose Learning to Think (L2T), an information-theoretic reinforcement fine-tuning framework for LLMs to make the models achieve optimal reasoning with fewer tokens. Specifically, L2T treats each query-response interaction as a hierarchical session of multiple episodes and proposes a universal dense process reward, i.e., quantifies the episode-wise information gain in parameters, requiring no extra annotations or task-specific evaluators. We propose a method to quickly estimate this reward based on PAC-Bayes bounds and the Fisher information matrix. Theoretical analyses show that it significantly reduces computational complexity with high estimation accuracy. By immediately rewarding each episode's contribution and penalizing excessive updates, L2T optimizes the model via reinforcement learning to maximize the use of each episode and achieve effective updates. Empirical results on various reasoning benchmarks and base models demonstrate the advantage of L2T across different tasks, boosting both reasoning effectiveness and efficiency.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有 LLM 推理方法（如基于 outcome-reward 的 RL）侧重于通过延长链式思维（CoT）来提高准确率，但忽略了推理效率。这导致模型倾向于生成不必要的长链，浪费大量 token，甚至在简单任务上因冗余而降低性能。
- **背景**：研究表明推理长度与准确性并非严格正相关，过长的推理链会消耗过多计算资源且可能损害效果。现有方法缺乏对中间步骤的密集反馈，无法平衡推理效果与效率。
- **目标**：提出 Learning to Think (L2T) 框架，通过信息论密集过程奖励，在有限 token 预算下实现高效且有效的推理。

## 2. 方法论

### 核心思想
- 将每个问答交互视为一个由多个 **回合 (episode)** 组成的层次化会话，每个回合对应一段推理步骤。
- 设计一个**通用的信息论密集过程奖励**，用于量化每个回合的贡献，包含两部分：
  - **拟合信息增益**：衡量回合更新后模型对正确答案预测概率的提升（近似于互信息增量）。
  - **参数压缩惩罚**：惩罚吸收冗余信息，鼓励高效更新（基于参数与环境上下文的互信息增量）。
- 通过强化学习（基于 GRPO）优化策略，最大化累积奖励，使模型在关键步骤产生高贡献的 token，避免无意义延伸。

### 关键技术细节
- **问题重述**：将长对话分解为 K 个回合，每个回合后计算过程奖励。
- **奖励定义**（公式 3）：  
  `r_prg_k = (正确概率提升) - β * (互信息增量)`  
  其中正确概率提升通过两次前向传播估计，互信息增量通过 PAC-Bayes 和 Fisher 信息矩阵近似。
- **高效近似**（定理 4.2）：利用低秩参数代理（SVD）和高斯假设，将压缩惩罚近似为二次型，避免在完整参数空间计算 Fisher 矩阵，大幅降低复杂度。
- **优化机制**：结合稀疏结果奖励和密集过程奖励，通过 GRPO 实现稳定训练；每个回合的奖励按 token 的 log-概率惊奇度分配到各 token，形成优势函数。

## 3. 实验设计

### 数据集与场景
- **数学推理**：AIME 2024/2025、AMC 2023、MATH500、MinervaMATH、Omni-MATH（含 4 个难度层级）。
- **代码生成**：HumanEval（0-shot 和 5-shot 设置）。
- **评价指标**：Pass@1（主要）、Maj@4、token 消耗量（效率）。

### 对比方法
- **基线**：原始 base model（DeepScaleR-1.5B-Preview、DeepSeek-R1-Distill-Qwen-1.5B/7B）。
- **outcome-reward RL**：GRPO（仅最终答案奖励）。
- **长度惩罚**：对长链施加负奖励。
- **过程奖励方法**：ReST-MCTS、MRT（以及代码复现版）。
- **额外对比**：结合 MCTS 搜索、推理时重排序（log-likelihood、PRM、L2T 重排序）。

### 公平性保证
- 固定最大 token 预算（16,384），使用 20 次输出/问题减少方差，greedy decoding (temperature=0) 为主。

## 4. 资源与算力

- 文中提到所有实验在 **A100 GPU 集群** 上进行，使用 vLLM 加速，混合精度训练（BF16），batch size 256，最大 prompt 长度 4,096，最大 completion 长度 16,384。
- **未明确说明** GPU 具体数量、总训练时长或总能耗。虽提供部分超参数，但算力细节不够完整。

## 5. 实验数量与充分性

- **主要实验**：在 5 个数学基准和 2 个代码基准上，结合 3 种 base model 进行有效性-效率评估（结果见表 1、表 2、图 2、图 3、图 7、图 8）。
- **消融实验**：
  - 组件贡献（替换信息增益、移除压缩惩罚、随机采样层）。
  - 超参数敏感性（α 和 β 网格搜索，图 5）。
- **扩展实验**：
  - 与 MCTS 结合（表 3）。
  - 推理时重排序（表 4）。
  - 不同 token 预算下的性能曲线（图 3）。
- **总体评价**：实验覆盖多任务、多模型、多难度，消融设计合理，对比方法全面，数据量充分。但未进行大规模模型（如 72B）验证，且仅测试了 DeepSeek 系列（及 Qwen2-7B），缺少对其他架构（如 LLaMA）的评估。

## 6. 主要结论与发现

- L2T 在保持或提升推理准确率的同时，显著降低 token 消耗（约 50% 相较于 outcome-reward RL，约 20% 相较于过程奖励方法）。
- 信息论过程奖励能有效平衡效果与效率：通过信号增益鼓励关键步骤，通过压缩惩罚抑制冗余。
- 在多难度混合任务中，L2T 自适应分配推理深度，避免了“一刀切”的长链。
- 理论证明（定理 D.2、D.3）表明近似方法复杂度低且误差可控。
- L2T 可作为推理时重排序信号，优于 log-likelihood 和 PRM。

## 7. 优点

- **通用性强**：奖励仅基于模型内部信号（预测概率变化、参数信息增益），无需任务特定标注或外部评估器。
- **理论坚实**：基于 PAC-Bayes 和 Fisher 信息矩阵，提供了复杂度与误差的数学保证。
- **效率提升显著**：在多个基准上 token 消耗减少一半，准确率仍有提升。
- **适应性好**：在简单和困难问题上均能自动调整推理深度，避免过短或过长。
- **实验全面**：涵盖数学和代码推理，多模型、多难度层次，并与多种 SOTA 方法公平对比。

## 8. 不足与局限

- **模型覆盖有限**：仅测试了 DeepSeek 系列（1.5B/7B）和 Qwen2-7B，未验证更大模型（如 70B+）或其他主流架构。
- **基准有限**：代码推理仅用 HumanEval，未使用更复杂的 SWE-Bench 等；数学推理未包括最新 benchmark（如 GPQA）。
- **训练细节缺失**：GPU 数量、训练时长、总成本未报告，可重复性受限。
- **回合分割依赖 prompt**：使用标签 `<episode>` 分割，可能影响长链自然性；未分析不同分割粒度的影响。
- **超参数依赖**：α 和 β 需网格搜索，虽给出最优值，但泛化性未在其他任务上验证。
- **未讨论失败案例**：缺少定性分析或错误模式分析，无法理解在哪些情况下 L2T 可能不如基线。

（完）
