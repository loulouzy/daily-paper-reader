---
title: Imitating Language via Scalable Inverse Reinforcement Learning
title_zh: 通过可扩展逆强化学习模仿语言
authors: "Markus Wulfmeier, Michael Bloesch, Nino Vieillard, Arun Ahuja, Jorg Bornschein, Sandy Huang, Artem Sokolov, Matt Barnes, Guillaume Desjardins, Alex Bewley, Sarah Maria Elisabeth Bechtle, Jost Tobias Springenberg, Nikola Momchev, Olivier Bachem, Matthieu Geist, Martin Riedmiller"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=5d2eScRiRC"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 逆强化学习用于语言模型微调
tldr: 当前语言模型训练主要基于最大似然估计，忽略序列结构。本文从逆强化学习角度重新审视模仿学习，通过提取奖励并直接优化序列代替令牌似然，为LLM微调提供新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 975, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1300, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1298, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1414, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1299, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1292, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 718, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 983, \"height\": 975, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1329, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 812, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5d2escrirc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1278, \"height\": 1055, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-5d2escrirc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1083, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5d2escrirc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 655, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5d2escrirc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 658, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5d2escrirc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 916, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5d2escrirc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 969, \"label\": \"Table\"}]"
motivation: 最大似然估计忽略序列结构，无法有效利用生成顺序。
method: 采用逆强化学习从演示中提取奖励，直接优化序列级目标。
result: 在细调LLM上展示优于传统方法的性能。
conclusion: 逆强化学习为语言模型微调提供更有效的序列级优化路径。
---

## Abstract
The majority of language model training builds on imitation learning. It covers pretraining, supervised fine-tuning, and affects the starting conditions for reinforcement learning from human feedback (RLHF). The simplicity and scalability of maximum likelihood estimation (MLE) for next token prediction led to its role as predominant paradigm. However, the broader field of imitation learning can more effectively utilize the sequential structure underlying autoregressive generation. We focus on investigating the inverse reinforcement learning (IRL) perspective to imitation, extracting rewards and directly optimizing sequences instead of individual token likelihoods and evaluate its benefits for fine-tuning large language models.  We provide a new angle, reformulating inverse soft-Q-learning as a temporal difference regularized extension of MLE. This creates a principled connection between MLE and IRL and allows trading off added complexity with increased performance and diversity of generations in the supervised fine-tuning (SFT) setting. We find clear advantages for IRL-based imitation, in particular for retaining diversity while maximizing task performance, rendering IRL a strong alternative on fixed SFT datasets even without online data generation. Our analysis of IRL-extracted reward functions further indicates benefits for more robust reward functions via tighter integration of supervised and preference-based LLM post-training.

---

## 论文详细总结（自动生成）

# 论文总结：Imitating Language via Scalable Inverse Reinforcement Learning

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大语言模型（LLM）的训练主要依赖于最大似然估计（MLE）进行下一个词预测，这本质上是模仿学习中的行为克隆（Behavioral Cloning, BC）。然而，MLE 忽略了自回归生成过程中动作（token）对未来序列的影响，容易导致暴露偏差和累积误差，且无法有效利用序列结构。
- **研究动机**：逆强化学习（Inverse Reinforcement Learning, IRL）能够直接基于整个序列进行优化，提取奖励函数并优化策略，从而更好地处理序列决策问题。论文希望探索 IRL 方法在 LLM 微调中的有效性，特别是在性能、生成多样性和计算效率方面的优势。
- **整体含义**：论文通过理论推导和实验，揭示了 IRL 可以作为 MLE 的一种强有效替代，在保持或提升任务性能的同时显著增加生成多样性，并且可以通过离线训练（无需在线采样）实现计算可扩展性。此外，IRL 提取的奖励函数可与后续的 RLHF 阶段更紧密地结合，提升奖励的鲁棒性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将语言生成建模为序贯决策问题，通过分布匹配（distribution matching）的 IRL 框架，最小化专家策略与所学策略的 γ-折扣状态-动作分布之间的 f-散度，并引入因果熵正则化。
- **关键技术细节**：
    - **非对抗性 IRL（IQLearn）**：基于逆软 Q 学习（Inverse Soft Q-Learning），利用 χ² 散度推导出新的目标函数（公式 14），显式地将 IRL 表示为 MLE 加上一个时间差分（TD）正则化项：
        \[
        \mathcal{J}_{\text{IQLearn}}(v_{r\lambda}, \pi_r) = \mathbb{E}_{\mu_E} \left[ \lambda \underbrace{(v_{r\lambda} + \log \pi_r - \mathbb{E}_{s'}[\gamma v'_{r\lambda}])^2}_{\text{TD regularization}} - \underbrace{\log(\pi_r)}_{\text{MLE}} \right]
        \]
        当 λ=0 时退化为标准 MLE；λ 越大，正则化越强。
    - **对抗性 IRL（GAIL）**：使用生成对抗网络，训练一个判别器区分专家数据与模型生成数据，策略通过梯度上升优化奖励信号。论文对 GAIL 进行了稳定性改进（如从 MLE 预训练检查点启动、添加 MLE 损失项）。
    - **在线与离线 IRL**：IQLearn 可以完全离线执行（仅使用固定专家数据集），也可通过混合在线数据（公式 16）扩展为在线版本，进一步利用模型自生成样本。
- **算法流程**（以离线 IQLearn 为例）：
    1. 从预训练 LLM 初始化策略 π 和价值函数（通过 logits 重新参数化为 Q 值）。
    2. 使用专家数据集 D，交替优化价值函数（TD 正则项）和策略（MLE 项）。
    3. 训练完成后，可直接用学到的策略进行推理。

## 3. 实验设计

- **数据集**：
    - XSUM（极端摘要）
    - GSM8k（数学推理）
    - TLDR（摘要）
    - WMT22（英德翻译，285M 样本）
- **基准（Benchmark）**：任务性能指标：用于数学的 Accuracy（带/不带计算器）、用于摘要的 ROUGE-1/2/LSUM、用于翻译的 BLEU/ChrF。多样性指标：Self-BLEU、每 token 熵。
- **对比方法**：
    - **MLE**（标准行为克隆，包括带熵正则化的 MLE）
    - **GAIL**（对抗性 IRL）
    - **IQLearn**（非对抗性 IRL，离线与在线版本）
- **模型规模**：T5（Base/Large/XL，250M-3B 参数）、PaLM2 Gecko（decoder-only 约 2B 参数）。
- **消融实验**：
    - 数据集大小对性能的影响（GSM8k、XSUM 的子集）。
    - 在线 vs 离线 IQLearn 的性能与多样性对比。
    - IRL 提取奖励与任务指标的斯皮尔曼秩相关系数分析。
    - GAIL 的稳定性分析（MLE 权重、熵正则化影响）。
    - 采样温度对性能的影响（PaLM2）。
- **统计显著性**：每个实验使用 3 个不同随机种子重复，报告均值标准误。

## 4. 资源与算力

- **计算资源**：
    - T5 模型实验使用 TPU v3 基础设施，每个实验运行约 3 天至 2 周。
    - PaLM2 模型实验使用 TPU v4 基础设施，每个实验运行不超过 1 周。
- **具体算力消耗**：未明确给出 GPU 型号、数量或精确的 FLOPS，但提供了不同模型更新和采样的时间对比（表 1），例如 T5-base 的 MLE 更新约 189ms、IQLearn 更新约 196ms、在线采样约 443ms。这些时间依赖于硬件和实现。

## 5. 实验数量与充分性

- **实验数量**：涵盖了 3 种数据集（XSUM、GSM8k、TLDR、WMT22），两种模型家族（T5 和 PaLM2），多个模型规模（Base/Large/XL/Gecko），以及多种算法变体（MLE、GAIL、IQLearn 离线/在线）。消融实验包括：数据集大小、熵正则化强度、采样温度、在线混合比例、奖励相关性等。整体实验数量较多。
- **充分性评价**：
    - **优点**：对比全面，涵盖了不同任务类型（摘要、推理、翻译）、不同模型架构（编码器-解码器 vs 解码器）、不同 IRL 范式（对抗 vs 非对抗，在线 vs 离线）。消融实验系统，分析了关键超参数的影响。统计显著性（3 个种子）合理。
    - **不足**：缺乏对更大模型（>10B 参数）的验证；奖励分析仅针对在线 IQLearn，且 GSM8k 的相关系数较低（0.17），表明对某些任务奖励信号提取效果有限。GAIL 训练不稳定，仅在 T5 上成功，PaLM2 上难以稳定，实验覆盖不完整。多样性仅用 Self-BLEU 和熵衡量，未使用更高级的多样性指标（如 MAUVE、BertScore 文中提及但未实际使用）。

## 6. 论文的主要结论与发现

1. **离线 IRL 优于 MLE**：在不需在线采样的条件下，IQLearn 在多个任务上取得与 MLE 相当或更好的任务性能，并显著提升生成多样性，特别是在数学推理（GSM8k）和摘要（XSUM）上。
2. **多样性-性能 Pareto 前沿更优**：IQLearn 能够更好地平衡任务性能与生成多样性，而 MLE 在增加熵正则化时往往导致性能严重下降。
3. **在线 IRL 进一步改善多样性**：引入少量在线数据（混合比例 0.1）可进一步提升多样性，但对任务性能提升有限。
4. **IRL 提取的奖励函数更有信息量**：IQLearn 积累的奖励与任务指标（如 ROUGE、BLEU）的斯皮尔曼相关系数显著高于 MLE 的对应值（如 TLDR 上 ROUGE-1 的 0.64 vs -0.05）。
5. **计算效率**：离线 IQLearn 的更新计算开销与 MLE 相近（约 196ms vs 189ms for T5-base），而 GAIL 和在线 IRL 则需额外采样成本。
6. **小数据集和长序列场景尤其受益**：在数据量少、目标序列长的任务中，IRL 对抗过拟合和累积误差的能力更强。

## 7. 优点

- **理论创新**：首次将 inverse soft-Q-learning 重新表述为 MLE 的 TD 正则化扩展，建立了 IRL 与 MLE 之间的显式联系，并允许灵活调节正则化强度。
- **实践可行性**：离线 IQLearn 无需在线采样，计算开销与 MLE 相当，易于集成到现有训练流程。
- **实验设计全面**：对比了多种 IRL 方法（对抗、非对抗）、多种模型规模、多种任务，并进行了多样化的消融实验。
- **奖励分析**：不仅关注生成性能，还分析 IRL 提取奖励的质量，为后续 RLHF 中的奖励学习提供了新思路。
- **稳定性改进**：通过起始于 MLE 预训练检查点、加入 MLE 损失项，稳定了 GAIL 训练。

## 8. 不足与局限

- **实验覆盖的局限**：
    - 仅在 3B 参数以下的模型上验证，未在更大模型（如 7B、13B 或 70B）上测试，可能限制了结论的普适性。
    - 多样性指标仅使用 Self-BLEU 和每 token 熵，未使用更精细的多样性或感知质量指标。
    - GAIL 在 PaLM2 上训练不稳定，未得到有效结果，对比不够完整。
- **奖励分析的局限**：
    - 仅在在线 IQLearn 上计算了奖励相关性，且对于 GSM8k 相关系数较低（0.17），说明奖励信号对最终答案正确性的区分能力有限。
    - 未在真实 RLHF 流水线中验证 IRL 提取的奖励对模型对齐性能的提升。
- **理论假设**：推导假设了确定性动力学（自回归生成），但论文中的 toy 实验指出，在无有效“纠正”动作的生成设定下，在线 IRL 的优势有限，这一点与实际 LLM 的单步单向生成相符，但未系统探讨“后退 token”等扩展机制（如 SequenceMatch 中的 backward token）。
- **计算资源表述模糊**：未明确报告训练时长、GPU 型号和数量，使得复现成本估计困难。
- **代码与数据未开源**：论文声明未提供代码和数据集，降低了可复现性。

（完）
