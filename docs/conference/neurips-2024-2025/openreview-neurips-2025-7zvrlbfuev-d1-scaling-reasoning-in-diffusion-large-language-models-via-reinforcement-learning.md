---
title: "d1: Scaling Reasoning in Diffusion Large Language Models via Reinforcement Learning"
title_zh: d1：通过强化学习扩展扩散大语言模型的推理能力
authors: "Siyan Zhao, Devaansh Gupta, Qinqing Zheng, Aditya Grover"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7ZVRlBFuEv"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 通过强化学习扩展扩散大语言模型的推理能力
tldr: 扩散大语言模型在推理能力上尚未探索。本文提出d1框架，采用监督微调与强化学习结合，将预训练掩码扩散LLM转化为推理模型。实验证明RL能有效提升扩散LLM的推理性能，扩展了非自回归生成范式的推理能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1075, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1164, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1223, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 413, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7zvrlbfuev/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 66, \"height\": 72, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7zvrlbfuev/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7zvrlbfuev/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1329, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7zvrlbfuev/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 728, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7zvrlbfuev/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7zvrlbfuev/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 369, \"label\": \"Table\"}]"
motivation: 扩散LLM的推理能力尚未被研究，缺乏RL应用。
method: 提出结合SFT和RL的框架，将掩码扩散LLM适配为推理模型。
result: 在推理任务上展示出与自回归模型相当的性能。
conclusion: RL可成功应用于扩散LLM，为非自回归推理打开新方向。
---

## Abstract
Recent large language models (LLMs) have demonstrated strong reasoning capabilities that benefits from online reinforcement learning (RL).
These capabilities have primarily been demonstrated within the left-to-right autoregressive (AR) generation paradigm. 
In contrast, non-autoregressive paradigms based on diffusion generate text in a coarse-to-fine manner. Although recent diffusion-based large language models (dLLMs) have achieved competitive language modeling performance compared to their AR counterparts, it remains unclear if dLLMs can also leverage recent advances in LLM reasoning.
To this end, we propose, a framework to adapt pre-trained masked dLLMs into reasoning models via a combination of supervised finetuning (SFT) and RL.
Specifically, we develop and extend techniques to improve reasoning in pretrained dLLMs: (a) we utilize a masked SFT technique to distill knowledge and instill self-improvement behavior directly from existing datasets, and (b) we introduce a novel critic-free, policy-gradient based RL algorithm called diffu-GRPO, the first integration of policy gradient methods to masked dLLMs. Through empirical studies, we investigate the performance of different post-training recipes on multiple mathematical and planning benchmarks. We find that d1 yields the best performance and significantly improves performance of a state-of-the-art dLLM.

---

## 论文详细总结（自动生成）

# 论文总结：d1：通过强化学习扩展扩散大语言模型的推理能力

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：当前大型语言模型（LLM）的推理能力主要基于自回归（AR）生成范式（从左到右逐词生成）。最近在线强化学习（RL）方法（如DeepSeek-R1、Kimi K1.5）显著提升了AR模型的推理性能。然而，非自回归范式——基于扩散的LLM（dLLM）采用从粗到细的迭代去噪生成方式，其推理能力尚未得到充分探索。
- **核心问题**：扩散LLM能否也利用RL等后训练方法来提升推理能力？现有的RL算法（如PPO、GRPO）依赖对策略分布的log概率计算，而dLLM的生成过程不满足自回归分解，无法直接应用。
- **研究动机**：填补扩散LLM在RL后训练方面的空白，探索将监督微调（SFT）和强化学习结合，使预训练掩码扩散LLM具备推理能力。
- **整体含义**：这项工作首次将策略梯度RL成功应用于大规模掩码扩散LLM，为非自回归生成范式下推理能力的扩展开辟了新方向。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
提出 **d1** 框架，采用两阶段后训练：
1. **第一阶段**：监督微调（SFT）——在高质量推理轨迹数据集（s1K）上进行微调，使模型学习逐步推理、自我验证和回溯行为。
2. **第二阶段**：强化学习——提出 **diffu-GRPO**，一种针对掩码dLLM的无评论家策略梯度算法，基于GRPO但适配了扩散模型的log概率估计。

### 关键技术细节

- **高效log概率估计**：
  - **序列级log概率**采用平均场近似，分解为独立token log概率的乘积。
  - **逐token log概率**采用一步估计：对原始prompt随机掩码（概率 \( p_{\text{mask}} \)），得到新prompt \( q' \)，然后通过一次前向传播（一步去噪）计算 \( \log f_\theta(o_k | q' \oplus \text{mask...}) \) 作为 \( \log \pi_\theta(o_k | q) \) 的估计。该方法避免了多步去噪的昂贵计算。
- **随机掩码正则化**：在每次策略梯度更新时，对prompt施加不同的随机掩码模式（distinct masking patterns），相当于数据增强，允许每个batch进行更多梯度更新（高μ值），减少所需在线生成次数，显著降低计算时间。
- **diffu-GRPO算法流程**（算法1）：
  - 采样prompt \( q \)，从旧策略 \( \pi_{\theta_{\text{old}}} \) 生成G个完成 \( o_i \)。
  - 计算奖励 \( r_i \) 和优势 \( A_i = r_i - \text{mean}(\{r_j\}) \)（未归一化）。
  - 对每个内部更新迭代，随机掩码prompt得到 \( q' \)，估计每个完成相对于 \( q' \) 的log概率。
  - 优化目标：包含裁剪的比率项和反向KL散度惩罚项（公式4）。
- **SFT算法**（算法2）：使用LLaDA的掩码扩散训练方式，在部分掩码的响应上计算损失，仅对掩码token预测。

## 3. 实验设计

### 数据集与基准
- **数学推理**：GSM8K（多步数学问题）、MATH500（高中竞赛数学子集）。
- **规划任务**：4×4数独（Sudoku）、Countdown（3数字组合算术游戏）。
- **代码生成**：HumanEval、MBPP。
- **SFT数据**：s1K（1000个高质量推理问题及详细轨迹）。
- **RL训练数据**：各任务单独训练集（GSM8K、MATH500用训练分割；Countdown、Sudoku用合成数据集）；多任务统一模型时对数据子采样保持每任务样本数相等。

### 对比方法
- 基线：LLaDA-8B-Instruct（SOTA开源dLLM，未经过后训练）。
- 对比对象：
  - LLaDA+SFT（仅SFT）
  - LLaDA+diffu-GRPO（仅diffu-GRPO）
  - d1-LLaDA（SFT + diffu-GRPO）
- 额外比较：与Dream 7B、Qwen2.5 7B等类似规模的自回归和扩散模型对比。

### 评估设置
- 零样本提示、贪婪解码，生成序列长度分别为128、256、512。
- 每个RL任务训练独立的diffu-GRPO模型；另外训练统一多任务模型。

## 4. 资源与算力

- **SFT训练**：2块A6000 GPU，序列长度4096，有效batch size 8，训练2460步。
- **diffu-GRPO训练**（数学与规划任务）：8块NVIDIA A100-80G GPU，LoRA rank=128，序列长度256，batch size 6/GPU，梯度累积2步。GSM8K训练7700步，MATH500训练6600步，Countdown 5000步，Sudoku 3800步。
- **代码任务**：4块NVIDIA RTX A5000，训练7500-9000步。
- 使用Flash Attention 2和4-bit量化加速。

## 5. 实验数量与充分性

- **覆盖范围**：6个推理任务（4个主要用于主结果展示，2个代码任务作为扩展），每个任务3种序列长度，共18个设置。
- **对比**：每个设置下比较4种模型（LLaDA基线、SFT、diffu-GRPO、d1）。
- **消融实验**：
  - 随机掩码 vs 固定掩码（不同μ值2、12、24）对奖励和训练效率的影响。
  - 不同掩码概率 \( p_{\text{mask}} \)（0.0, 0.1, 0.3, 0.5, 0.7）对训练稳定性的影响。
- **多任务统一模型**：验证跨任务泛化能力。
- **代码任务**：进一步验证diffu-GRPO在编程领域的有效性。
- **定性分析**：提供生成示例，观察“aha moment”（自纠正行为）。
- **公平性**：所有模型使用相同推理解码策略，报告最佳性能（对RL模型每100步选取最佳）。但缺少多次运行误差条报告（由于算力限制）。

总体而言，实验数量充足，消融设计合理，对比全面，但缺少统计显著性检验。

## 6. 主要结论与发现

1. **diffu-GRPO始终优于基线和SFT**：在全部12个设置中，diffu-GRPO均超越LLaDA基线；SFT仅改善7/12设置；diffu-GRPO单独效果强于SFT。
2. **d1（SFT+diffu-GRPO）取得最佳性能**：在11/12设置中优于单独diffu-GRPO，显示两阶段协同效应。
3. **性能提升幅度因任务而异**：数学任务提升约4%，规划任务提升约10-26%，表明结构化约束任务受益更大。
4. **推理能力扩展到未见长度**：即使训练时固定256长度，在128和512长度上也有提升，表明学到一般性策略。
5. **随机掩码提供了有效正则化**：允许更高的内部更新次数（μ达到12或24），显著减少所需生成次数，加速收敛。
6. **多任务统一训练保持性能**：单个模型在多任务上不逊于单任务模型。
7. **代码任务也获得提升**：diffu-GRPO在HumanEval和MBPP上稳定改善。

## 7. 优点

- **方法创新**：首次将策略梯度RL应用于大规模掩码扩散LLM，提出实用的log概率估计算法diffu-GRPO，并利用随机掩码实现高效训练。
- **实验全面**：覆盖数学、规划、代码多种推理类型，评估多种序列长度，消融充分。
- **效率优势**：随机掩码正则化使每个在线生成批次可进行更多梯度更新，显著降低计算成本（图5右）。
- **开源贡献**：代码已发布，便于复现和后续研究。
- **定性洞察**：观察到SFT和d1模型出现自我纠正的“aha moment”，定性示例展示了推理增强。

## 8. 不足与局限

- **固定序列长度限制**：LLaDA生成需预设序列长度，diffu-GRPO训练时固定256，可能限制模型发现更优推理路径（如极短或极长链式思考），未来可尝试Block Diffusion等支持变长生成的模型。
- **无误差条报告**：受算力限制，未进行多次独立重复实验，无法评估结果统计稳定性。论文通过广泛实验设置（18个设置）部分缓解此问题。
- **SFT数据通用性**：s1K主要面向数学和规划，不包含代码数据，因此SFT+SFT+diffu-GRPO在代码任务上提升不稳定（SFT甚至有时起反作用）。最优SFT数据集探索留待未来。
- **推理时间成本**：扩散LLM生成速度较慢，制约了长序列在线采样，限制了RL训练中的序列长度扩展。
- **仅基于LLaDA-8B-Instruct**：方法仅在单一基础模型上验证，能否推广到其他dLLM（如Dream、Mercury）未知。
- **奖励函数设计**：每个任务需手动设计复合奖励函数（格式+正确性），可能需要在泛化时调整。

（完）
