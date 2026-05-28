---
title: Grounding Multimodal Large Language Models in Actions
title_zh: 多模态大语言模型的动作接地
authors: "Andrew Szot, Bogdan Mazoure, Harsh Agrawal, R Devon Hjelm, Zsolt Kira, Alexander T Toshev"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=0Gl5WxY6es"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型动作接地
tldr: 本文研究如何将多模态大语言模型有效嵌入不同具身智能体的动作空间。通过七种动作接地方法和五个环境的114项任务实验，发现连续动作需学习多分辨率词元化，离散动作需语义对齐输出空间，为MLLM在具身场景中的应用提供了系统性指导。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1371, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1416, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1156, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1135, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 712, \"height\": 157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 703, \"height\": 152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 711, \"height\": 156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-0gl5wxy6es/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 706, \"height\": 148, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1086, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 926, \"height\": 1191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 750, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-0gl5wxy6es/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 997, \"height\": 1912, \"label\": \"Table\"}]"
motivation: 需要将MLLM接地到不同具身智能体和动作空间中。
method: 系统对比七种动作接地方法，包括连续动作词元化和离散动作语义对齐。
result: 连续动作上多分辨率词元化最优，离散动作上语义对齐输出空间最强。
conclusion: 为MLLM在具身AI的应用提供了重要的接地指南。
---

## Abstract
Multimodal Large Language Models (MLLMs) have demonstrated a wide range of capabilities across many domains including Embodied AI. In this work, we study how to best ground a MLLM into different embodiments and their associated action spaces, including both continuous and discrete actions. For continuous actions, a set of learned tokenizations that capture an action at various resolutions allows for sufficient modeling precision, yielding the best performance on downstream tasks. For discrete actions, semantically aligning these actions with the native output token space of the MLLM leads to the strongest performance. We arrive at these lessons via a thorough study of seven action grounding approaches on five different environments, encompassing over 114 embodied tasks.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

多模态大语言模型（MLLM）在多种领域展现强大能力，但在具身智能（Embodied AI）任务中，其**输出空间（自然语言）与代理人动作空间（连续控制或离散技能）之间存在巨大鸿沟**，限制了MLLM直接用于低级控制或决策。现有工作各自采用不同的动作空间适配器（Action Space Adapter, ASA），但缺乏系统性比较。本文旨在通过统一架构和跨环境的大量实验，系统研究如何最佳地将MLLM接地（grounding）到多种具身智能体和动作空间中，以有效利用MLLM的多模态世界知识。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 统一架构

- 采用LLaVA-1.5-7B作为基础MLLM。
- 输入：文本指令 + 历史RGB观测（经Perceiver下采样）。
- 输出：通过ASA将MLLM隐藏状态映射为动作。
- ASA由三部分组成：适配器头（adapter head）、适配器嵌入（adapter embedding）、适配器解码器（adapter decoder）。

### 2.2 连续动作适配器（七种方法）

1. **Continuous Regression (Pred)**：直接用MLP回归连续动作。
2. **Uniform Action Tokenization (Uniform)**：将每个维度均等量化成K个bin，预测对应token。
3. **Vector Quantized Tokenization (VQ)**：用VQ-VAE学习一个动作码本，将连续动作映射为单个token。
4. **Residual Vector Quantized Tokenization (RVQ)**：使用残差VQ-VAE，用多个码本逐步建模残差，得到多个token（如2个码本），精度更高。

### 2.3 离散动作适配器（三种方法）

1. **Categorical Prediction (Pred)**：MLP直接预测离散动作的logits。
2. **Semantic Language (SemLang)**：将每个离散动作映射为语义相关的自然语言描述（如“pick apple”），用MLLM原生token空间预测。
3. **Non-Semantic Language (Lang)**：将动作映射为无语义的数字字符串（如“5 3”）。

### 2.4 训练方式

- **监督微调（SFT）**：在专家演示数据上训练，冻结视觉编码器和LLM主干，仅微调LoRA、下采样器和ASA（约140M参数）。
- **强化学习（RL）**：在Language Rearrangement任务中使用PPO，并引入**token筛选器**防止生成无效动作序列。

## 3. 实验设计

- **环境与任务**：5个环境，共计114个语言指定任务。
  - 连续动作：CALVIN (34任务)、Meta-World ML-45 (45任务)、Habitat Pick (20任务)。
  - 离散动作：BabyAI (5任务)、Language Rearrangement (LangR, 10评估集)。
- **基准（Baselines）**：对比七种ASA，以及两种非LLM基线（Scratch 300M transformer、RT-Inspired）。
- **评估指标**：平均成功率（success rate）。

## 4. 资源与算力

- 使用**LLaVA-1.5-7B**作为基础MLLM。
- 训练设备：
  - CALVIN、Meta-World、Habitat Pick：**4×A40 GPU**。
  - Language Rearrangement、BabyAI：**8×A100-80GB GPU**。
- 采用LoRA（rank=128, alpha=32）微调约140M参数。
- 训练**基于SFT**：CALVIN 3 epoch，Meta-World 3 epoch，HabPick 20 epoch，BabyAI 20 epoch。
- **RL训练**：LangR训练约20M步收敛（SemLang），使用2个随机种子。

## 5. 实验数量与充分性

- **实验规模大**：覆盖114个任务，七种ASA，五种环境。
- **消融全面**：
  - 连续动作：对比不同码本大小（16~2048）、不同码本数量（1~6）。
  - 离散动作：对比SemLang、Lang、Pred；添加token筛选器消融。
  - 迁移学习：在Meta-World的5个新任务上测试RVQ的迁移能力。
  - 与不同策略架构对比：MLLM vs Scratch vs RT-Inspired，验证RVQ对MLLM的特殊增益。
- **客观公平**：所有ASA在相同MLLM、相同训练条件下比较；报告了RL实验的标准差（2种子）。
- **不足**：主要基于单种子SFT（7B模型训练成本高），未多次重复；对比的基线方法均在同一框架下复现，与原始论文可能有实现差异。

## 6. 论文的主要结论与发现

- **连续动作**：**RVQ（残差VQ）** 性能最佳。
  - 在CALVIN上达到72%（vs Pred 68%、Uniform 28%、VQ 56%）。
  - 在Meta-World上84%（vs Pred 61%、Uniform 75%、VQ 58%）。
  - 原因：通过多个残差码本精确建模连续动作分布，且MLLM能利用其语言序列知识更好地预测动作token。
- **离散动作**：**SemLang（语义语言映射）** 性能最佳。
  - 在LangR上51%（vs Pred 42%、Lang 27%）。
  - 在BabyAI上40%（vs Pred 35%、Lang 24%）。
  - 原因：利用MLLM已有的语义知识，语义映射比随机数字映射更有效。
- **关键因素**：码本大小和数量需要适当（过大过小均有害）；token筛选器对语言动作空间RL至关重要。
- **增益来源**：RVQ带来的提升**独特于MLLM**——非LLM基线的Scratch策略使用RVQ反而下降，表明MLLM能更好利用token序列先验。

## 7. 优点

- **系统性**：首次在同一框架下系统比较多种ASA，涵盖连续和离散动作。
- **统一架构**：将各种接地方法纳入Action Space Adapter范式，便于分析和推广。
- **多环境验证**：覆盖5个差异巨大的环境（桌面前抓取、导航、网格世界、移动操作），保证结论泛化性。
- **深入分析**：通过消融、迁移、与非LLM对比、可视化任务组失败案例等，深入解释RVQ和SemLang为何有效。
- **结果先进**：在Meta-World ML-45上达到新SOTA（84%）；在LangR上超越LLaRP（51% vs 42%）。

## 8. 不足与局限

- **单一基础模型**：仅使用LLaVA-1.5-7B，未测试其他MLLM（如BLIP-2、InstructBLIP、GPT-4V等）。
- **单种子SFT**：除RL实验外，大多数结果仅基于单次训练（受限于计算成本），缺少统计显著性。
- **RVQ需要额外训练**：需要离线数据集预训练VQ-VAE，增加步骤；且VQ模型固定后无法适应后续策略微调。
- **性能仍有限**：最佳ASA在简单BabyAI上仅40%，在复杂机器人任务上仍有失败案例，离安全部署有差距。
- **仅探索BC和on-policy RL**：未研究off-policy RL或离线RL下ASA的选择是否变化。
- **环境局限性**：所有环境均为仿真，未在真实机器人上验证。
- **计算成本高**：7B参数模型微调需要多GPU资源，可能限制可重复性。

（完）
