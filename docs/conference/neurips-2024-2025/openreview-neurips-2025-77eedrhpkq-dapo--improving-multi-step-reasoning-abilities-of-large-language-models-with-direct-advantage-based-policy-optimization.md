---
title: "DAPO : Improving Multi-Step Reasoning Abilities of Large Language Models with Direct Advantage-Based Policy Optimization"
title_zh: DAPO：利用直接优势策略优化提升大语言模型的多步推理能力
authors: "Jiacai Liu, Chaojie Wang, Chris Yuhao Liu, Liang Zeng, Rui Yan, Yiwen Sun, Yang Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=77eEDRhPkQ"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 步级离线强化学习算法增强LLM推理
tldr: 强化学习提升LLM推理面临稀疏奖励和方差大的挑战。本文提出DAPO，一种步级离线RL算法，直接基于优势函数进行策略优化，无需价值函数估计，在数学推理等任务上显著提升推理能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-77eedrhpkq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1400, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-77eedrhpkq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1223, \"height\": 989, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-77eedrhpkq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1137, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-77eedrhpkq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1140, \"height\": 833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-77eedrhpkq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1357, \"height\": 564, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1395, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1385, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1271, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1129, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1390, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1368, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1485, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1693, \"height\": 805, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-77eedrhpkq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1697, \"height\": 570, \"label\": \"Table\"}]"
motivation: 现有RL方法受稀疏奖励影响，训练方差大且价值函数估计困难。
method: 提出步级离线RL算法，直接计算优势进行策略优化。
result: 在推理基准上超越现有响应级方法如DPO和GRPO。
conclusion: 步级优势估计能有效缓解稀疏奖励问题，提升LLM推理训练稳定性。
---

## Abstract
The role of reinforcement learning (RL) in enhancing the reasoning of large language models (LLMs) is becoming increasingly significant. Despite the success of RL in many scenarios, there are still many challenges in improving the reasoning of LLMs. One key challenge is the sparse reward, which introduces more training variance in policy optimization and makes it difficult to obtain a good estimation for value function in Actor-Critic (AC) methods.  To address these issues, we introduce Direct Advantage-Based Policy Optimization (DAPO), a novel step-level offline RL algorithm  with theoretical guarantees for enhancing the reasoning abilities of LLMs. Unlike response-level methods (such as DPO and GRPO) that the update directions of all reasoning steps are governed by the outcome reward uniformly, DAPO employs a critic function to provide step-level dense signals for policy optimization. Additionally, the actor and critic in DAPO are trained independently, ensuring that critic is a good estimation of true state value function and avoiding the co-training instability observed in standard AC methods. We train DAPO on mathematical and code problems and then evaluate its performance on multiple benchmarks. Our results show that DAPO can effectively enhance the mathematical and code capabilities on both SFT models and RL models, demonstrating the effectiveness of DAPO.

---

## 论文详细总结（自动生成）

# 基于论文《DAPO：利用直接优势策略优化提升大语言模型的多步推理能力》的中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在利用强化学习（RL）提升大语言模型（LLMs）的多步推理能力（如数学解题、代码生成）时，面临**奖励稀疏**（仅最终token获得奖励）导致的高训练方差问题；同时，标准的Actor-Critic（AC）方法（如PPO）中，价值函数估计困难且actor与critic联合训练容易不稳定或崩溃。
- **背景**：现有响应级方法（如DPO、GRPO）将所有推理步骤的更新方向统一由最终结果奖励决定，忽视了中间步骤的贡献差异，引入额外方差；而在线AC方法则因非平稳目标和交替更新导致不稳定。
- **整体含义**：本文提出**DAPO（Direct Advantage-Based Policy Optimization）**，一种**步级（step-level）离线RL算法**，通过独立训练的critic为每个推理步骤提供稠密的优势信号，实现细粒度策略优化，从而提升推理能力。

## 2. 论文提出的方法论

- **核心思想**：将LLM生成过程建模为马尔可夫决策过程（MDP），每个推理步骤为一个动作，利用预训练好的critic网络估计状态值函数，进而计算每一步的优势，直接基于优势进行策略优化。
- **关键技术细节**：
  - **双阶段训练**：
    1. **Critic训练阶段**：使用生成器（generator）产生多个完整轨迹，提取中间状态；对每个状态，用reference策略（completer）采样多个子轨迹，通过蒙特卡洛（MC）估计得到状态值，训练critic网络`Vϕ`，采用二元交叉熵损失。
    2. **策略优化阶段**：对每个状态`s`，从completer的输出中提取多个候选下一步动作`{a_i}`，利用已训练的critic计算每个动作的Q值估计，进而计算优势`A_i = Vϕ(s◦a_i) - mean(Vϕ(s◦a_j))`。然后最小化如下损失：
       \[
       \min_\theta \frac{1}{2} \mathbb{E}_{(s,a,\hat{A}) \sim \mathcal{D}} \left[ \left( \frac{1}{\beta} \hat{A}(s,a) - \log \frac{\pi_\theta(a|s)}{\pi_{\text{ref}}(a|s)} \right)^2 \right]
       \]
       其中`β`为KL正则化系数。
  - **理论保证**：定理3.2证明，只要reference策略非最优，DAPO必然产生单调改进的策略。
- **算法流程**（文字描述）：  
  输入训练问题集和初始actor/critic → 循环迭代：  
  - 使用当前actor生成多条完整响应 → 提取所有中间状态。  
  - 对每个状态，用reference策略采样多个子轨迹 → 计算MC值 → 训练critic拟合状态值。  
  - 对每个状态，用critic计算多个候选动作的优势 → 构造优势数据集。  
  - 在优势数据集上优化actor损失 → 得到新actor。

## 3. 实验设计

- **数据集**：
  - 数学任务：训练集使用**MATH**的7500道题（仅用问题和标准答案，不提供解题过程）；测试集包含MATH测试集（5K题）、GSM8K、Minerva Math、Olympiad Bench、College Math等**领域外基准**。
  - 代码任务：训练集从**TACO**中选取约4000道竞赛级编程题；测试集包括HumanEval、HumanEval+、MBPP、MBPP+、LiveCodeBench。
- **基准方法**：与**GRPO**（响应级）、**PPO**（标准AC方法）对比；同时对比初始模型（SFT模型或已有RL模型）。
- **基模型**：涵盖通用模型（Llama-3.1-8B-Instruct、OpenO1-Llama-8B-v0.1等）和数学专用模型（Skywork-Math-Llama、Qwen2-Math-7B-Instruct、Qwen2.5-Math-7B-Instruct等），包括已经过RL训练的模型。
- **评估方式**：零样本、贪婪解码（temperature=0），报告准确率。

## 4. 资源与算力

- 论文**未明确**给出使用的GPU型号、数量及总训练时长。
- 但提供了计算成本估算分析（Appendix E）：假设响应长度L≈2048，推理步骤T≈20，生成数n1=32，筛选后n=6，每个状态完成数m=16。分析了inference和training tokens的消耗。
- 提到DAPO的主要局限是高计算成本，尤其是critic预训练阶段；但实验表明，在相似计算预算下，DAPO仍优于GRPO（GRPO易过拟合，DAPO稳定提升）。

## 5. 实验数量与充分性

- **实验组数**：数学任务上测试了7个不同基模型（含SFT与RL模型），代码任务上测试了2个模型；包含迭代DAPO（2轮）实验、超参数消融（β取值、MC采样数n）；与GRPO、PPO的对比实验（4个模型）。
- **充分性**：实验覆盖了多种模型家族（Llama、Qwen、Skywork）、不同规模（8B、72B）、不同预训练方式（SFT、RL），并在多个领域外基准上评估泛化性；消融实验探讨了关键超参数影响。总体较为充分和客观。
- **公平性**：对比方法（PPO、GRPO）的训练细节在Appendix F中给出，设定了相近的batch size、学习率等；但未报告统计显著性检验或多次运行误差棒，因为采用贪婪解码，随机性低。

## 6. 论文的主要结论与发现

- **DAPO能显著提升模型在多步推理任务上的表现**：在MATH测试集上，对所有基模型均取得正向提升（绝对提升1.8% ~ 8.64%），并泛化到领域外基准。
- **优于响应级方法GRPO和标准AC方法PPO**：在Llama-3.1-8B-Instruct、OpenO1-Llama-8B、Qwen2-Math-7B等模型上，DAPO的改进幅度大于GRPO和PPO。
- **迭代DAPO可进一步增益**：两轮迭代在Skywork-Math-Llama上提升8.64%，在Qwen2-Math-7B上提升1.94%，表明仍有提升空间。
- **DAPO训练稳定**：训练过程中测试准确率稳步上升，未出现GRPO的过拟合下降现象。
- **超参数敏感性可控**：β=0.01、MC采样数n=16效果较好。

## 7. 优点

- **步级细粒度优化**：利用critic提供每一步的稠密优势信号，突破响应级算法的统一更新限制，降低方差。
- **独立训练critic**：避免actor-critic联合训练的不稳定性，保证价值函数估计质量。
- **理论保障**：证明了单调改进性质，且可迭代应用。
- **通用性强**：在多种基模型（通用/数学/代码）和多种基准上均有效，且能持续改进已有RL模型。
- **离线训练**：数据效率高，无需在线rollout，便于复现。

## 8. 不足与局限

- **高计算成本**：critic预训练需要为每个状态进行大量MC采样（m=16），推理步骤多时总token消耗大（尤其是状态数T²增长）。论文承认这是主要限制。
- **实验覆盖有限**：仅测试了数学和代码任务，未涵盖更多推理类型（如逻辑推理、常识问答）；也未在更大规模模型（如70B以上，除72B一个点）上验证。
- **无统计显著性报告**：因采用贪婪解码，但未报告多次运行的标准差或置信区间，可能削弱结果稳健性。
- **泛化风险**：在部分领域外基准上（如Minerva MATH），某些模型出现下降（如OpenO1-Llama-8B的Minerva MATH -2.94%），提示可能存在过拟合训练集分布的风险。
- **动作空间近似**：实践中仅使用有限个候选动作（来自completer采样）作为近似动作空间，可能遗漏更优动作。
- **优势估计依赖critic质量**：critic训练依赖MC值，若MC采样不足或基策略偏差，优势估计可能不准。

（完）
