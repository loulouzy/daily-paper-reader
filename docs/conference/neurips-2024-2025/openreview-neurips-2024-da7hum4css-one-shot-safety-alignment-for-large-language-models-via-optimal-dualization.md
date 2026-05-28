---
title: One-Shot Safety Alignment for Large Language Models via Optimal Dualization
title_zh: 基于最优对偶化的大语言模型单步安全对齐
authors: "Xinmeng Huang, Shuo Li, Edgar Dobriban, Osbert Bastani, Hamed Hassani, Dongsheng Ding"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=dA7hUm4css"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 基于RLHF和安全对齐的最优对偶化
tldr: 针对大语言模型的安全对齐需求，基于约束RLHF方法存在计算昂贵和不稳定的问题。本文提出最优对偶化视角，将对齐转化为等价的无约束优化，通过预优化光滑凸对偶函数实现单步安全对齐，显著降低了计算复杂度。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1244, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1405, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1308, \"height\": 1294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-da7hum4css/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 874, \"height\": 863, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1177, \"height\": 848, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1167, \"height\": 805, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 447, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 127, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1534, \"height\": 1594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1528, \"height\": 2177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1541, \"height\": 1090, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-da7hum4css/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1536, \"height\": 1130, \"label\": \"Table\"}]"
motivation: 约束RLHF的安全对齐方法计算昂贵且不稳定。
method: 提出对偶化观点，将约束对齐转化为等价的无约束问题，预优化光滑凸对偶函数。
result: 单步即完成安全对齐，避免繁琐的主-对偶策略迭代，计算效率大幅提升。
conclusion: 为LLM安全对齐提供了一种高效、稳定的新方法。
---

## Abstract
The growing safety concerns surrounding large language models raise an urgent need to align them with diverse human preferences to simultaneously enhance their helpfulness and safety. A promising approach is to enforce safety constraints through Reinforcement Learning from Human Feedback (RLHF). For such constrained RLHF, typical Lagrangian-based primal-dual policy optimization methods are computationally expensive and often unstable. This paper presents a perspective of dualization that  reduces constrained alignment to an equivalent unconstrained alignment problem. We do so by pre-optimizing a smooth and convex dual function that has a closed form. This shortcut eliminates the need for cumbersome primal-dual policy iterations, greatly reducing the computational burden and improving training stability. Our strategy leads to two practical algorithms in model-based and preference-based settings (MoCAN and PeCAN, respectively). A broad range of experiments demonstrate the effectiveness and merits of our algorithms.

---

## 论文详细总结（自动生成）

# 论文《One-Shot Safety Alignment for Large Language Models via Optimal Dualization》详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

大型语言模型（LLM）在自然语言生成中展现出强大能力，但其安全性问题日益突出，例如偏见、虚假信息、敏感信息泄露等。为了在使用中确保模型既有用（helpfulness）又安全（safety），通常采用基于人类反馈的强化学习（RLHF）进行安全对齐。然而，标准RLHF仅优化单一奖励函数，难以兼顾安全约束；而引入安全约束的约束RLHF方法（如拉格朗日原-对偶策略优化）存在计算成本高、训练不稳定、需要反复更新对偶变量并重新训练模型等缺陷。本文的核心问题是：**能否在安全约束下，以“单步”（one-shot）方式完成语言模型的对齐，而无需繁琐的迭代过程？**

## 2. 方法论

### 核心思想
论文提出**最优对偶化（optimal dualization）**视角，将约束对齐问题等价转化为无约束对齐问题。核心思路是预先优化一个光滑且凸的对偶函数（dual function），该函数具有闭式解形式，从而避免原-对偶策略迭代，大幅降低计算负担并提升训练稳定性。

### 关键技术细节
1. **问题建模**：将LLM对齐建模为带约束的RLHF问题：
   - 目标：最大化期望奖励与KL散度正则化的差。
   - 约束：对齐后的模型在m个安全属性上需超出参考模型指定边际 \( b_j \)。
2. **对偶函数闭式表达**：利用Donsker–Varadhan变分公式，推导出对偶函数 \( D(\lambda) = \beta \mathbb{E}_{x \sim \mathcal{D}} \left[ \ln \mathbb{E}_{y \sim \pi_{\text{ref}}(\cdot|x)} \exp\left( \frac{r(x,y) + \langle \lambda, h(x,y) \rangle}{\beta} \right) \right] \)，其中 \( h \) 为偏移后的安全函数。
3. **优化性质**：证明对偶函数是凸的、光滑的，且在最优对偶变量附近局部强凸。因此可使用投影梯度下降高效优化。
4. **两阶段策略 (CAN)**：
   - **阶段1**：最小化对偶函数 \( D(\lambda) \)，得到最优对偶变量 \( \lambda^\star \)。
   - **阶段2**：利用 \( \lambda^\star \) 构造修正奖励 \( r_{\lambda^\star} = r + \langle \lambda^\star, g \rangle \)，进行无约束对齐（通过RL或DPO）。
5. **具体算法**：
   - **MoCAN (Model-based CAN)**：基于离线收集的奖励/安全分数，先优化对偶函数，再用伪偏好数据通过DPO微调模型。
   - **PeCAN (Preference-based CAN)**：无需预训练奖励/安全模型，直接利用人类偏好数据先获得未约束预对齐模型（如DPO训练），再通过对数概率差分等价地优化对偶函数，最后进行伪偏好DPO微调。
6. **稳定性分析**：证明了当奖励和安全模型满足一定精度时，CAN得到的策略在目标函数和约束上均接近最优，误差可控。

## 3. 实验设计

### 数据集与场景
- **数据集**：PKU-SafeRLHF-30K，包含约27000条训练样本和3000条测试样本，每条样本包含一对回复以及人类标注的有用性/安全性偏好。
- **场景**：分为模型基（MoCAN）和偏好基（PeCAN）两种设置。实验中仅考虑单一安全约束（安全性）。

### 基准模型
- **参考模型**：SFT（Alpaca-7b-reproduced，通过监督微调得到）。
- **对比方法**：
  - DPO S,β（仅安全导向的DPO）
  - DPO H,β（仅有用性导向的DPO）
  - Safe-RLHF（beaver-7b-v1.0，基于原-对偶PPO训练的安全对齐模型）
  - MoCAN及PeCAN不同超参数版本

### 评估方式
- **模型基评估**：使用代理奖励和安全模型计算平均得分。
- **GPT基评估**：使用gpt-4-turbo进行成对比较（有用性和安全性胜率）。

## 4. 资源与算力

文中在附录J.2中说明：实验使用**单张48G NVIDIA A6000 GPU**，每次模型对齐耗时约**15小时**。对比而言，constrained RLHF（文献[26]）在更强的A100 GPU上需约20小时；safe-RLHF（文献[12]）因使用PPO且在更大数据集上，预计需40-60小时。本文方法在更廉价的GPU上实现了至少25%的时间节省。但论文坦承由于资源限制，未在更大规模模型上测试，但认为7B模型提供了公平的比较基础，且方法可扩展。

## 5. 实验数量与充分性

论文进行了多组实验（具体数量未逐一统计，但包括）：
- **MoCAN**：针对8种不同安全边际 \( b \) 值（从-1.4到5.4）分别训练模型，并评估安全提升与有用性-安全性的帕累托曲线。
- **PeCAN**：在两种KL正则化参数（β=0.025, 0.1）下训练，并与MoCAN及baseline对比。
- **消融/分析**：
  - 对偶优化收敛性演示（图1）。
  - 预测安全改善与实际训练结果的比较（图2左）。
  - 离线数据量（prompt数量、每prompt回复数量）对最优对偶变量的影响（图4）。
  - 可靠性图分析（附录M）说明模型分数与log-probability的校准性差异。
- **红队测试**：附表5-8展示不同模型对恶意prompt的回复示例。

**实验充分性评价**：实验覆盖了模型基和偏好基两种主流场景，对比了多种前沿方法（DPO、Safe-RLHF），并进行了多维度的定量和定性分析。但从规模看，仅在7B模型和单约束下验证，缺乏多约束或更大模型（如13B/70B）的实验，可能影响泛化性结论的强度。

## 6. 主要结论与发现

1. **对偶视角有效**：最优对偶化可将约束对齐转化为单步无约束优化，大幅简化流程。
2. **MoCAN和PeCAN均能实现有效安全对齐**：在多个安全边际下，对齐后的模型几乎满足预期约束，且预测的安全改善与实际训练高度吻合。
3. **帕累托最优**：MoCAN在有用性与安全性之间实现了明显优于DPO和Safe-RLHF的帕累托前沿；PeCAN略逊于MoCAN，主要归因于预对齐模型的对数概率校准不足。
4. **数据效率**：对偶优化所需离线数据量适中（约600个prompt、每prompt约128个回复即可稳定），但每prompt回复数量对估计精度影响更大。
5. **稳定性与鲁棒性**：理论分析表明，当代理模型满足一定精度时，CAN的输出在目标函数和约束上均有可靠保证。

## 7. 优点

- **方法创新**：首次将最优对偶化引入LLM安全对齐，将约束问题简化为无约束问题，提供了理论坚实的“单步”解决方案。
- **计算高效**：避免迭代原-对偶训练，单次训练即可完成，显著降低GPU算力和时间成本。
- **适用场景广**：同时覆盖模型基（有预训练奖励/安全模型）和偏好基（仅有偏好数据）两种常见场景，算法设计清晰。
- **稳定性好**：对偶函数光滑且局部强凸，优化过程稳定；理论证明了在代理模型有误差时的鲁棒性。
- **实验充分**：多维度评估（模型打分、GPT评判、红队测试），并与多个强基线对比，结果可靠。

## 8. 不足与局限

- **实验规模有限**：仅在7B模型上验证，未在更大模型（如13B、70B）上测试；仅考虑单约束，缺乏多安全属性的联合约束实验。
- **偏好基校准问题**：PeCAN效果略差于MoCAN，主要因为DPO预对齐模型的对数概率不能完美反映真实偏好，论文未提出有效缓解手段。
- **数据依赖性**：对偶函数估计依赖于离线收集的奖励/安全模型分数或对数概率，如果代理模型与真值偏差较大，对齐效果可能下降（虽然理论提供了误差界，但实际中误差界可能较宽松）。
- **泛化能力**：方法基于Bradley-Terry偏好模型和KL散度正则化，若偏好结构或正则形式改变，需要重新推导对偶函数。
- **资源报告不够详细**：虽提及单GPU及15小时，但未说明对比方法（Safe-RLHF等）的具体运行时间与资源需求，不利于严格对比。

（完）
