---
title: Progress Reward Model for Reinforcement Learning via Large Language Models
title_zh: 通过大语言模型实现强化学习的进度奖励模型
authors: "Xiuhui Zhang, Ning Gao, Xingyu Jiang, Yihui Chen, Yuheng Pan, Mohan Zhang, Yue Deng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TJhHb6CscW"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 利用大语言模型生成进度奖励以增强强化学习
tldr: 该论文针对传统强化学习在长周期稀疏奖励任务中的局限性，提出进度奖励模型（PRM4RL）。框架利用大语言模型进行高层规划，将复杂任务分解为一系列简单子任务，并生成密集的进度奖励信号，从而指导底层控制策略的学习。PRM4RL无需预定义技能库或人工反馈，通过LLM的世界知识自动生成奖励，在多个困难任务上显著提升了强化学习样本效率和最终性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 886, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1404, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 372, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1422, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tjhhb6cscw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1345, \"height\": 880, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 613, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 574, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1279, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tjhhb6cscw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1293, \"height\": 300, \"label\": \"Table\"}]"
motivation: 传统强化学习难以处理长周期稀疏奖励任务。
method: 利用大语言模型分解任务并生成密集进度奖励，结合高层规划与低层策略学习。
result: 在多个长周期任务上提升强化学习样本效率和最终性能。
conclusion: 大语言模型可作为强化学习奖励设计的有效知识源。
---

## Abstract
Traditional reinforcement learning (RL) algorithms face significant limitations in handling long-term tasks with sparse rewards. 
Recent advancements have leveraged large language models (LLMs) to enhance RL by utilizing their world knowledge for task planning and reward generation. 
However, planning-based approaches often depend on pre-defined skill libraries and fail to optimize low-level control policies, while reward-based methods require extensive human feedback or exhaustive searching due to the complexity of tasks.
In this paper, we propose the Progress Reward Model for RL (PRM4RL), a novel framework that integrates task planning and dense reward to enhance RL. 
For high-level planning, a complex task is decomposed into a series of simple manageable subtasks, with a subtask-oriented, fine-grained progress function designed to monitor task execution progress. 
For low-level reward generation, inspired by potential-based reward shaping, we use the progress function to construct a Progress Reward Model (PRM), providing theoretically grounded optimality and convergence guarantees, thereby enabling effective policy optimization.
Experimental results on robotics control tasks demonstrate that our approach outperforms both LLM-based planning and reward methods, achieving state-of-the-art performance.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统强化学习（RL）在长周期、稀疏奖励的复杂任务中面临严重局限，表现为反馈信号不足、探索效率低下。
- **现有方法不足**：
  - **LLM as planner**：将任务分解为子任务，但依赖预定义技能库或传统运动规划，无法优化底层策略，且非端到端。
  - **LLM as rewarder**：利用LLM生成密集奖励，但缺少子任务分解，导致奖励函数设计复杂，需要大量人工反馈或进化搜索。
- **核心动机**：同时整合高层任务规划与低层密集奖励，解决上述单一方法的缺陷。

## 2. 方法论

### 2.1 核心思想
- 利用LLM将复杂任务分解为一系列短周期、可管理的子任务，并为每个子任务构建细粒度的**进度函数**。
- 基于势能奖励塑造（potential-based reward shaping），将进度函数作为势能函数，构造**进度奖励模型（PRM）**，提供具有理论最优性和收敛保证的密集奖励信号。

### 2.2 关键技术细节
- **子任务分解**：
  - 将任务描述、状态空间、环境信息以Python类形式输入LLM，采用程序辅助的Chain-of-Thought（PAL）格式。
  - LLM输出子任务列表（`plan_list`，每个子任务为“动词+名词”格式），以及**子任务判定函数** Ψ(s)（基于当前状态返回当前子任务索引）。
- **进度函数生成**：
  - LLM为每个子任务定义子进度指标（如归一化距离、高度差），并整合为整体进度函数 Φ(s)（范围0~1）。
- **奖励模型构建**：
  - PRM奖励：\( R_{PRM}^t = \gamma \cdot \Phi(s_{t+1}) - \Phi(s_t) + I(s_{t+1}) \cdot r_{bonus} \)，其中 \(I\) 为任务成功指示函数。
  - **理论保证**：
    - 策略不变性（Theorem 4.1）：PRM不改变最优策略，不引入欺骗性行为。
    - 收敛效率（Theorem 4.3）：势能奖励等价于Q值初始化，加速收敛。
- **策略增强**：
  - 使用SimCSE将当前子任务先验嵌入为向量，附加到状态空间。
  - 增强后的MDP：\( \mathcal{M}' = \langle S+P, A, T, R_{PRM}, \gamma, \rho_0 \rangle \)。
  - 采用标准RL算法（SAC或PPO）进行优化。

## 3. 实验设计

- **基准场景**：
  - **MetaWorld**（10个任务）：button-press、door-close、drawer-close、faucet-open、window-open、sweep-into、pick-place、pick-out-of-hole、sweep、push。
  - **ManiSkill**（5个任务）：LiftCube、PullCube、PushCube、PickCube、LiftPegUpright。
- **对比方法**：
  - **ELLM**（ICML 2023）：LLM作为规划器，提供子任务先验。
  - **Text2Reward（T2R）**（ICLR 2024）：LLM作为奖励器，生成密集奖励函数。
  - **Oracle**：环境自带的专家密集奖励函数。
- **评估指标**：成功率（success rate）。
- **实现细节**：基于Stable-Baselines3框架，采用SAC或PPO，超参数统一。LLM使用GPT-4o。

## 4. 资源与算力

- **硬件配置**：4块NVIDIA RTX 3090 GPU，128核CPU，256 GiB内存。
- **训练时长**：
  - MetaWorld任务：约1小时/任务（5个随机种子并行）。
  - ManiSkill任务：1~10小时/任务（视难度而定）。
- **注意**：文中未明确说明单次训练的总GPU小时数，但给出了上述估算。

## 5. 实验数量与充分性

- **数量**：
  - 主实验：在15个任务（10+5）上对比4种方法（含本方法），每个任务5个随机种子，共约300次独立训练。
  - 消融实验：在3个MetaWorld任务上对3个变体（w.o. PRM奖励、w.o. 子任务先验、w.o. 势能奖励）进行对比。
  - 泛化实验：在2个源任务上训练，在4个未见任务上测试，各5个种子，每种子100次评估。
- **充分性与公平性**：
  - 消融实验覆盖了框架的两个核心组件，证实其协同效果（1+1>2）。
  - 泛化实验验证了子任务先验对迁移能力的贡献。
  - 所有方法共享相同的RL算法和超参数，确保公平比较。
  - 使用多个随机种子降低偶然性。

## 6. 论文的主要结论与发现

- PRM4RL在几乎所有任务上优于ELLM、T2R和Oracle，尤其在困难任务（如pick-out-of-hole、LiftPegUpright）上成功率从<15%提升至接近100%。
- 消融实验表明：同时使用PRM奖励和子任务先验才能达到最佳性能；缺少任一部分都会导致收敛速度下降或性能退化。
- 泛化实验中，PRM4RL在未见任务上性能下降最小，子任务先验的“动词+名词”格式有效捕获了任务共性的先验知识。
- 理论分析证实PRM奖励具有策略不变性和收敛加速特性，保障了学习的稳定性和最优性。

## 7. 优点

- **方法创新性**：首次将高层规划与低层势能奖励塑造有机融合，利用LLM自动生成进度函数和子任务判定函数，无需预定义技能库或人工反馈。
- **理论扎实**：提供了奖励塑造的策略不变性和Q值初始化等价性证明，避免奖励欺骗，保证收敛。
- **实用性**：
  - 使用程序辅助Chain-of-Thought降低LLM生成错误。
  - 子任务判定函数仅基于状态，无需每步调用LLM，大幅降低计算开销。
- **实验充分**：覆盖多类型机器人任务，消融与泛化实验设计合理，验证了各组件贡献。

## 8. 不足与局限

- **依赖LLM生成质量**：可能受LLM幻觉影响，导致子任务分解或进度函数不准确。
- **应用范围有限**：仅在机器人控制领域（MetaWorld、ManiSkill）验证，未探索其他领域（如游戏、自动驾驶）。
- **Prompt设计需一定专家知识**：需要将环境信息抽象为Python类格式，可能对非专家不友好。
- **未讨论生成失败的鲁棒性**：若LLM生成的功能存在错误，如何检测和修复未提及。
- **计算成本**：虽然单次训练时长可接受，但LLM推理（生成函数）仍需额外开销。

（完）
