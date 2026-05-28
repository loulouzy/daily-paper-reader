---
title: Unveiling Chain of Step Reasoning for Vision-Language Models with Fine-grained Rewards
title_zh: 揭示视觉语言模型的逐步骤链式推理与细粒度奖励
authors: "Honghao Chen, Xingzhou Lou, Xiaokun Feng, Kaiqi Huang, Xinlong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=D8nHwexHNv"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 视觉语言模型推理的强化学习，细粒度奖励
tldr: 链式推理在视觉语言推理中的适配面临挑战，现有方法使用粗粒度推理链难以评估中间步骤质量。本文提出细粒度的逐步骤推理框架，能够精确评估推理步骤质量，并利用细粒度奖励进行有效的强化学习和推理时扩展。该方法提升了VLM的结构化推理能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 778, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 898, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 903, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1147, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d8nhwexhnv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1402, \"height\": 684, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 833, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1288, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1102, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1422, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1090, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d8nhwexhnv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 885, \"height\": 242, \"label\": \"Table\"}]"
motivation: 现有VLM链式推理缺乏细粒度，中间步骤质量难以评估，阻碍强化学习应用。
method: 提出细粒度逐步骤推理框架，包含步骤质量评估和基于奖励的强化学习优化。
result: 实验证明该方法在多个推理任务上优于粗粒度方法，并展示了推理时扩展的有效性。
conclusion: 细粒度奖励策略为VLM推理和强化学习结合提供了有效方案。
---

## Abstract
Chain of thought reasoning has demonstrated remarkable success in large language models, yet its adaptation to vision-language reasoning remains an open challenge with unclear best practices. Existing attempts typically employ reasoning chains at a coarse-grained level, which struggles to perform fine-grained structured reasoning and, more importantly, are difficult to evaluate the reward and quality of intermediate reasoning. In this work, we delve into chain of step reasoning for vision-language models, enabling assessing reasoning step quality accurately and leading to effective reinforcement learning and inference-time scaling with fine-grained rewards. We present a simple, effective, and fully transparent framework, including the step-level reasoning data, process reward model (PRM), and reinforcement learning training. With the proposed approaches, our models set strong baselines with consistent improvements on challenging vision-language benchmarks. More importantly, we conduct a thorough empirical analysis and ablation study, unveiling the impact of each component and several intriguing properties of inference-time scaling. We believe this paper serves as a baseline for vision-language models and offers insights into more complex multimodal reasoning. Our dataset, PRM, and code at https://github.com/baaivision/CoS.

---

## 论文详细总结（自动生成）

# 论文总结：Unveiling Chain of Step Reasoning for Vision-Language Models with Fine-grained Rewards

## 一、核心问题与整体含义

### 研究动机
- **核心问题**：链式推理（CoT）在大型语言模型中取得了显著成功，但将其适配到视觉-语言模型（VLM）仍面临挑战。现有方法通常使用粗粒度推理链，难以进行细粒度结构化推理，更关键的是，难以评估中间推理步骤的奖励和质量。
- **根本矛盾**：人类的系统化、结构化思维与当前VLM的模糊、无结构输出之间存在鸿沟，导致无法高效选择高质量推理轨迹用于训练或推理。

### 整体含义
本文提出了**Chain-of-Step（CoS）** 推理框架，旨在实现细粒度的逐步骤推理，精确评估推理步骤质量，并将细粒度奖励用于有效的强化学习和推理时扩展，从而系统性地提升VLM的结构化推理能力。

---

## 二、方法论

### 核心思想
将整个推理链分解为逻辑连贯、渐进的多步骤，每个步骤包含三部分：名称（摘要）、思路（详细推理）、反思（与视觉内容和前序步骤建立连接）。基于此结构，训练过程奖励模型（PRM）以提供细粒度奖励信号，再通过迭代偏好学习优化模型推理能力。

### 关键技术细节
1. **结构化推理模板**：
   - 整个推理过程以特殊token结构进行编码：`<|reasoning_start|>` ... `<|reasoning_end|>`
   - 每个步骤通过`<|reasoning_step_start|>` ... `<|reasoning_step_end|>`界定，步骤间用`<|reasoning_proceed|>`连接
   - 每个步骤内部包含名称、思路、反思三个子部分，每个子部分也有对应的特殊token

2. **数据集构建**（ShareGPT-Step-300K）：
   - 利用GPT-4o，以问题和参考答案为参考，生成结构化逐步骤推理
   - 数据来源涵盖17个数据集、四类任务：数学推理、科学推理、图表/文档分析、世界知识
   - 经过严格清洗和格式过滤，最终获得300K高质量样本

3. **过程奖励模型（PRM）训练**：
   - 使用两种方法标注步骤质量：蒙特卡洛估计（Math-Shepherd，N=16）和LLM-as-Judge（GPT-4o，三档评级：Good/Neutral/Bad）
   - 共收集200K步骤级标注数据
   - 训练目标：二元交叉熵损失函数，对每个部分解进行正确性估计

4. **迭代直接偏好优化（DPO）**：
   - 基于SFT模型初始化策略模型和参考模型
   - 每次迭代采样16条推理路径，用PRM计算步骤平均分和答案分的加权和作为最终分数
   - 设置阈值t确保正负样本区分度，避免边际差异过小
   - 迭代多轮，渐进提升推理能力

---

## 三、实验设计

### 使用的数据集/场景
- **训练阶段**：ShareGPT-Step-300K（300K条结构化推理数据）、200K步骤级标注数据用于PRM训练、约20K偏好对用于迭代DPO
- **评估基准**（共6个）：
  - MathVista：多模态数学推理
  - MMStar：依赖视觉内容的多模态问题
  - MMMU：大学级别多学科多模态理解
  - M3CoT：多领域多步多模态链式推理
  - AI2D：科学知识与推理
  - ChartQA：图表逻辑推理

### 对比方法
与多种开源VLM对比：
- LLaVA-1.5、IXC-2.5、Ovis1.5-LLaMA3、LLaVA-CoT、LlamaV-o1、Vision-R1-LlamaV、R1-VL、R1-Onevision、MiniCPM-V-2-6、LLaVA-OneVision、Qwen2-VL、Insight-V、InternVL-2.5、LLaVA-NeXT-LLaMA3、InternVL2.5-MPO等

---

## 四、资源与算力

- **训练硬件**：SFT和迭代DPO在单台8×NVIDIA-A800 GPU节点上进行
- **PRM训练**：在16×NVIDIA-A800 GPU上进行
- **训练时间**：
  - SFT：约9小时（基于InternVL-2.5-MPO-8B）
  - 三轮迭代DPO：约6小时（总计时长）
  - PRM训练：未明确时长，但在200K数据上训练2个epoch

（论文明确提供了GPU型号、数量、训练时长，但未提供总算力成本估算）

---

## 五、实验数量与充分性

### 实验组数（约10组以上）
1. **主实验结果**（表1）：在6个基准上将方法应用于LLaVA-NeXt和InternVL-2.5-MPO，与15+种基线对比
2. **推理步骤重要性消融**（图3）：逐步增加步骤权重（0%-100%），报告best-of-16准确率
3. **推理时扩展实验**（图5）：在M3CoT和MMStar上比较Pass@N、Self-Consistency、PRM、PRM-BS四种方法，N从1到64
4. **RL训练方法消融**（表2）：比较Outcome、Answer（PRM）、Step&Answer（PRM）三种奖励设置
5. **PRM基座模型消融**（表3）：比较LLaVA-NeXt-8B、InternVL-2.5-8B、InternVL-2.5-38B在Seen/Unseen数据上的步骤和答案准确率
6. **推理长度分析**（图6）：追踪Outcome DPO和PRM DPO逐轮推理步骤长度变化
7. **推理模式消融**（表4）：比较No Reason、Direct Prompt、CoS三种模式在SFT和RL下的表现
8. **近期算法GRPO消融**（表5）：在LLaVA-NeXt-SFT上比较Outcome GRPO和CoS GRPO
9. **逐步骤DPO尝试**（附录表9）：尝试更细粒度的逐步骤偏好对构建

### 充分性评价
实验设计较为全面：覆盖主流基准、多模型基座、多维度消融、推理时扩展分析。但所有实验均基于特定VLM架构（LLaVA-NeXt和InternVL系列），对更广泛VLM的泛化性验证有限；计算资源仅使用单类GPU，复现门槛仍存在。

---

## 六、主要结论与发现

1. **细粒度奖励比答案级奖励更有效**：同时考虑步骤质量和答案质量（Step&Answer权重为20%时）可获得最优性能，单独依赖任一方均非最佳（见图3、表2）

2. **强化学习比监督微调更关键**：对强模型（InternVL-2.5-MPO），SFT改进有限，但迭代DPO带来显著提升；对弱模型两者均重要（见表1）

3. **推理长度并非越长越好**：Outcome DPO使步骤长度逐渐增加，PRM DPO则先缩短后缓慢增长，而PRM DPO表现更好——质量比长度更重要（见图6）

4. **PRM结合步级束搜索可有效扩展推理时的能力**：PRM-BS在相同采样效率下优于Best-of-N和Self-Consistency（见图5）

5. **推理模式选择影响重大**：CoS的结构化设计比简单无结构和直接提示产生更大改进，在RL阶段尤其显著（见表4）

---

## 七、优点

1. **结构化设计创新**：首次明确将VLM推理分解为三层结构（名称、思路、反思），并利用特殊token确保输出稳定，支持后续步骤评估和束搜索。

2. **细粒度奖励的有效性**：通过PRM实现步骤级质量评估，为RL提供更精确的奖励信号，比传统答案级方法更优。

3. **框架通用性**：在两种不同基座模型（LLaVA-NeXt和InternVL-2.5-MPO）上验证了方法的可迁移性。

4. **公开数据集与代码**：计划开源数据集、PRM和代码，提升可复现性和社区贡献。

5. **全面实证分析**：除性能对比外，还深入分析了推理步骤权重、推理长度动态、PRM基座选择等消融问题，提供了丰富洞见。

---

## 八、不足与局限

1. **数据质量依赖与标注噪声**：过程标注数据（MC估计和GPT-4o评估）无法保证100%正确，且未采用人类标注，标注质量限制了下限。

2. **逐步骤DPO探索失败**：尝试构建更细粒度的逐步骤偏好数据（每步构建正负对）时，因选定步骤与拒绝步骤差异性小导致训练反效果（附录表9），表明方法对偏好数据差异性敏感。

3. **PRM性能的初步解释**：针对表3中38B PRM答案准确率低于8B PRM的异常现象，论文给出了“短路径优先优化”的推测，但未提供严格的机理分析或交叉验证。

4. **实验覆盖局限**：
   - 仅基于两类特定VLM架构，对更广泛VLM族（如多模态融合方式不同的架构）的泛化性未验证。
   - 基准数据集可能未全面覆盖真实世界复杂多模态推理场景（如动态视频、3D场景等）。

5. **计算资源门槛**：训练需多节点A800 GPU，对于资源受限的研究机构复现困难。

6. **潜在偏差风险**：SFT数据由GPT-4o生成，PRM数据也依赖GPT-4o评估，可能导致“蒸馏偏差”或自我强化效应，且未评估对分布外样本的鲁棒性。

（完）
