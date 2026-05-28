---
title: "Planning without Search: Refining Frontier LLMs with Offline Goal-Conditioned RL"
title_zh: 无需搜索的规划：使用离线目标条件RL精炼前沿大语言模型
authors: "Joey Hong, Anca Dragan, Sergey Levine"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kuoD6G0Suq"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 大语言模型的强化学习
tldr: 针对多轮强化学习训练大语言模型计算成本高、API限制等问题，本文提出离线目标条件强化学习方法，在不进行在线交互的情况下提升模型在谈判、说服等交互任务中的长程推理与规划能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1363, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kuod6g0suq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 865, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1100, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1105, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 737, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 739, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kuod6g0suq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 740, \"height\": 469, \"label\": \"Table\"}]"
motivation: 多轮RL训练大语言模型面临高内存成本和API限制，难以规模化。
method: 采用离线目标条件强化学习，利用静态数据提升LLM的规划能力。
result: 在多种交互任务上显著提升了LLM的推理和规划性能。
conclusion: 离线RL为提升LLM规划能力提供了可扩展的替代方案。
---

## Abstract
Large language models (LLMs) excel in tasks like question answering and dialogue, but complex tasks requiring interaction, such as negotiation and persuasion, require additional long-horizon reasoning and planning. Reinforcement learning (RL) fine-tuning can enable such planning in principle, but suffers from drawbacks that hinder scalability. In particular, multi-turn RL training incurs high memory and computational costs, which are exacerbated when training LLMs as policies. Furthermore, the largest LLMs do not expose the APIs necessary to be trained in such manner. As a result, modern methods to improve the reasoning of LLMs rely on sophisticated prompting mechanisms rather than RL fine-tuning. To remedy this, we propose a novel approach that uses goal-conditioned value functions to guide the reasoning of LLM agents, that scales even to large API-based models. These value functions predict how a task will unfold given an action, allowing the LLM agent to evaluate multiple possible outcomes, both positive and negative, to plan effectively. In addition, these value functions are trained over reasoning steps rather than full actions, to be a concise and light-weight module that facilitates decision-making in multi-turn interactions. We validate our method on tasks requiring interaction, including tool use, social deduction, and dialogue, demonstrating superior performance over both RL fine-tuning and prompting methods while maintaining efficiency and scalability.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：大型语言模型（LLMs）在问答、对话等任务中表现优异，但在谈判、说服等需要多轮交互的复杂任务中，需要长期推理和规划能力。传统方法使用多轮强化学习（RL）微调LLM，但面临高内存和计算成本、训练复杂度高、样本需求大等问题，且前沿模型（如GPT-4、Claude 3）不开放API进行端到端RL训练。
- **动机**：现有替代方案主要依赖推理时的提示技术（如思维链、自我反思、树搜索），但受限于模型的固有直觉或昂贵的搜索预算，难以实现数据驱动的决策。
- **核心目标**：提出一种可扩展的方法，在不直接微调LLM的前提下，通过离线RL学习一个轻量级的自然语言批评器（critic），用于在推理时引导LLM agent进行规划和推理，从而兼顾性能与效率。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：学习一个**目标条件值函数**（goal-conditioned value function）\(Q(s, a^{tht}, g)\)，其中\(s\)是状态（交互历史摘要），\(a^{tht}\)是agent的高层策略思考（thought），\(g\)是未来可能的目标状态（正/负）。该值函数预测在当前状态下采取某思考后达到目标\(g\)的概率。推理时，利用该值函数对agent提出的思考进行自然语言评估（包括正负未来情景的概率），然后让LLM agent自我改进思考。
- **关键技术细节**：
  - **抽象层次**：在高层策略思考（thought）层面而非底层环境动作上建模，降低决策空间复杂度。
  - **离线训练**：从离线数据集（由次优agent生成）中提取样本，对状态和思考进行摘要和嵌入（使用GPT-3等轻量模型），然后训练一个2隐藏层MLP作为值函数。
  - **损失函数**：修改IQL（Implicit Q-learning）的目标条件版本：
    \[
    L_Q = \mathbb{E}_{(s, a^{tht}, s', g) \sim D} \left[ \left( r(s,g) + \gamma V(s', g) - Q(s, a^{tht}, g) \right)^2 \right]
    \]
    \[
    L_V = \mathbb{E}_{(s, a^{tht}, g) \sim D} \left[ L_{\tau_2} \left( Q(s, a^{tht}, g) - V(s, g) \right) \right]
    \]
    其中\(r(s,g)\)是指示当前状态是否达到目标\(g\)的二元奖励。
  - **推理流程**：
    1. LLM agent提出一个思考（thought）。
    2. 自然语言批评器生成n个正负目标（n=4，2正2负），通过值函数计算每个目标的概率。
    3. 将这些目标与概率组合成自然语言值（如“有40%概率用户感到放心，30%概率用户不信任”）。
    4. LLM agent根据反馈进行最多m轮（m=2）自我改进，最终选择改进后的思考。
  - **优势**：无需推理时搜索，仅需一次前向传播评估值函数，计算开销小。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集/场景**（三个多轮交互基准）：
  - **WebShop**：在线购物环境，agent根据用户需求从爬取的亚马逊描述中购买产品，奖励为0-1相似度。
  - **AvalonBench**：社交推理游戏（抵抗组织），agent扮演梅林角色，需引导好人阵营胜利，同时隐藏身份。
  - **Persuasion**：目标导向对话，agent说服参与者向“救助儿童会”捐款（最多$2），使用GPT-3.5模拟怀疑的捐赠者。
- **Benchmark**：每个任务有独立的评估指标（WebShop：得分和成功率；Avalon：胜率；Persuasion：平均捐款额）。
- **对比方法**：
  - **RL微调**：ArCHer（离线/在线变体），使用GPT-2策略。
  - **LLM推理**：ReAct、Reflexion、LATS（n=5/30）、Self-Plan（n=5），均基于GPT-4。
  - **任务特定方法**：Agent Q（WebShop，基于Mixtral-7B）、Strategist（Avalon，n=5/30）、GDP-Zero（Persuasion，n=5/30）。

## 4. 资源与算力

- **未明确说明**：论文未提供训练值函数MLP所需的GPU型号、数量或具体训练时长。但提及值函数仅为2隐藏层MLP，训练成本极低。推理时，PNLC每次决策仅需约5-6秒（WebShop和Avalon），而对比方法（如Agent Q n=30约46秒，Strategist n=30约62秒）。离线数据生成使用了GPT-3.5/3等模型，但未详细说明计算资源。

## 5. 实验数量与充分性

- **实验数量**：在三个不同场景（工具使用、社交游戏、对话）上进行了评估，每个场景100次独立测试。包含完整的消融实验（去掉目标条件、去掉推理时自我改进）。对比了多种主流方法（共12种变体），包括任务特定方法。
- **充分性**：实验覆盖了不同复杂性、不同领域的交互任务，对比了RL微调、推理搜索、提示等多种范式。消融实验验证了两个核心组件的必要性。结果报告为均值（无误差条），但100次独立测试足够稳定。总体实验设计较为充分、客观、公平。但作者承认不同方法使用的基座模型大小不一致（如GPT-2 vs GPT-4 vs Mixtral-7B），这构成一个局限性。

## 6. 主要结论与发现

- PNLC在所有三个任务上均取得最优性能：WebShop得分78.2、成功率48%；Avalon胜率47%；Persuasion平均捐款0.87美元。
- 在相近推理预算下，PNLC显著优于所有对比方法，包括RL微调（ArCHer）、推理搜索方法（LATS、Agent Q、Strategist、GDP-Zero）以及自我反思方法（Reflexion、Self-Plan）。
- 消融实验表明：同时需要目标条件值函数（提供自然语言描述）和推理时利用该描述进行自我改进，二者缺一不可；去掉任何一部分，性能退化至与简单提示法（如ReAct）相当。
- 方法在推理效率上优势明显：仅需约5-6秒/决策，比搜索方法（n=30）快一个数量级。

## 7. 优点

- **创新性**：首次将离线目标条件RL扩展至LLM agent的规划，无需直接微调LLM，可适用于API-only的前沿模型。
- **轻量化**：值函数为2隐藏层MLP，训练成本极低；推理时仅需一次前向传播，计算效率高。
- **自然语言批评**：通过生成多个正负目标并给出概率，提供丰富、可解释的反馈，而非单一标量值，更利于LLM agent进行自我改进。
- **鲁棒性**：在三个差异化的交互场景中均取得一致最优，且消融实验证实设计的必要性。
- **可扩展性**：无需在线交互或搜索，仅需离线数据集，适合真实部署。

## 8. 不足与局限

- **任务特定性**：需要为每个新任务训练单独的值函数，缺乏通用性。未来方向是开发通用批评器。
- **依赖LLM的直觉**：在生成未来目标（goals）时依赖于LLM的推理能力，对于LLM知识范围之外的任务（如医学诊断）可能不可靠。
- **离线数据质量**：方法效果依赖于离线数据的多样性和质量（论文使用的数据集来自次优agent），对极端数据分布或噪声的鲁棒性未探讨。
- **实验对比的异质性**：不同方法使用不同大小的基座模型（GPT-2、Mixtral-7B、GPT-4），未严格控制变量，可能影响比较的公平性。
- **缺少统计显著性报告**：仅报告100次测试的均值，未提供误差棒或置信区间，无法评估结果的波动性。
- **未讨论推理时的限制**：尽管效率高，但生成目标和评估值函数仍需多次调用LLM（n=4），可能对某些实时应用仍有开销。
- **未涉及安全性或伦理影响**：虽然论文在讨论中提及，但实验未评估方法在有害对话或偏见场景下的表现。

（完）
