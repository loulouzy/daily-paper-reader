---
title: "GenRL: Multimodal-foundation world models for generalization in embodied agents"
title_zh: GenRL：用于具身智能体泛化的多模态基础世界模型
authors: "Pietro Mazzaglia, Tim Verbelen, Bart Dhoedt, Aaron Courville, Sai Rajeswar"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=za9Jx8yqUA"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态强化学习论文：基础世界模型用于具身智能
tldr: 强化学习（RL）在具身智能中面临奖励设计复杂和领域差距大等挑战。本文提出GenRL，利用多模态基础世界模型连接视觉语言模型（VLM）表示与RL，实现跨任务的通用具身智能体。通过世界模型对齐，无需精细调整即可迁移VLM知识。实验证明GenRL在多个具身任务上实现高效泛化。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1418, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1425, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1288, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 944, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1459, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-za9jx8yqua/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1453, \"height\": 199, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 747, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1104, \"height\": 1349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-za9jx8yqua/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1038, \"height\": 252, \"label\": \"Table\"}]"
motivation: RL难以扩展且依赖复杂奖励设计，VLM领域差距大。
method: 构建多模态基础世界模型，对齐VLM表示与RL环境。
result: 在多个具身任务上实现高效泛化，减少奖励设计成本。
conclusion: GenRL为RL与VLM融合提供了有效范式。
---

## Abstract
Learning generalist embodied agents, able to solve multitudes of tasks in different domains is a long-standing problem. Reinforcement learning (RL) is hard to scale up as it requires a complex reward design for each task. In contrast, language can specify tasks in a more natural way. Current foundation vision-language models (VLMs) generally require fine-tuning or other adaptations to be adopted in embodied contexts, due to the significant domain gap. However, the lack of multimodal data in such domains represents an obstacle to developing foundation models for embodied applications. In this work, we overcome these problems by presenting multimodal-foundation world models, able to connect and align the representation of foundation VLMs with the latent space of generative world models for RL, without any language annotations. The resulting agent learning framework, GenRL, allows one to specify tasks through vision and/or language prompts, ground them in the embodied domain’s dynamics, and learn the corresponding behaviors in imagination.
As assessed through large-scale multi-task benchmarking in locomotion and manipulation domains, GenRL enables multi-task generalization from language and visual prompts. Furthermore, by introducing a data-free policy learning strategy, our approach lays the groundwork for foundational policy learning using generative world models. 
Website, code and data: https://mazpie.github.io/genrl/

---

## 论文详细总结（自动生成）

# GenRL：用于具身智能体泛化的多模态基础世界模型 - 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：强化学习（RL）在具身智能领域面临两大挑战：一是每个任务都需要精心设计奖励函数，难以扩展；二是视觉-语言模型（VLM）在具身领域存在显著的领域差距，且缺乏多模态标注数据，难以直接应用。
- **研究动机**：如何在不依赖语言标注数据的情况下，有效利用大规模预训练的基础模型实现具身智能体的多任务泛化？现有方法要么需要微调VLM，要么在动态任务中表现不稳定。
- **整体含义**：本文提出GenRL框架，通过构建“多模态基础世界模型”（MFWM），将基础VLM的表示空间与生成式世界模型的隐空间连接并对齐，仅使用视觉数据即可实现从语言或视觉提示指定任务，并在世界模型的“想象”中学习对应行为，为构建通用具身智能体奠定基础。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：学习一个任务无关的生成式世界模型（基于DreamerV3架构，离散潜空间），然后通过“连接器”（connector）和“对齐器”（aligner）网络，将预训练的VLM（InternVideo2）的嵌入表示映射到世界模型的潜状态空间，实现多模态对齐。任务通过视觉或语言提示编码为潜目标序列，智能体在想象中通过RL最大化与目标的余弦相似度来学习行为。
- **关键技术细节**：
  - **世界模型**：使用编码器、序列模型（GRU）、动力学预测器和解码器，训练损失包括KL散度（动态损失）和重构损失。
  - **连接器**：从VLM嵌入预测世界模型潜状态，训练时最小化与编码器分布之间的KL散度。
  - **对齐器**：学习一个映射函数，将语言嵌入映射到视觉嵌入附近，以解决多模态对比学习中的“模态间隙”，仅用噪声采样的视觉数据训练，无需语言标注。
  - **任务学习**：给定提示，通过连接器生成目标潜状态序列；策略（actor-critic）在想象中通过RL优化，奖励函数为余弦相似度：\( r_{\text{GenRL}} = \cos(g_{\phi}(s^{\text{dyn}}_{t+1}), g_{\phi}(s^{\text{task}}_{t+1})) \)，其中g是解码器第一线性层。
  - **时间对齐**：采用“最佳匹配轨迹”技术，通过滑动窗口对齐初始状态，解决初始状态不匹配问题。
- **算法流程**（文字说明）：
  1. 预训练阶段：在无奖励、无文本标注的视觉数据集上训练世界模型（编码器、动力学、解码器）和连接器、对齐器。
  2. 任务指定阶段：输入语言或视频提示，用VLM提取嵌入，经对齐器映射后，连接器生成目标潜序列。
  3. 行为学习阶段：在想象中采样初始潜状态，策略与环境动力学交互，使用上述奖励函数，通过DreamerV3风格的actor-critic优化。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集/场景**：
  - 4个运动（locomotion）环境：Walker、Cheetah、Quadruped、新增的Stickman（基于Walker，增加上肢关节）。
  - 1个操作（manipulation）环境：Kitchen。
  - 共35个任务（包括站立、行走、奔跑、跳跃、翻转、高踢、做饭等）。
  - 训练数据：每个域约1.8M~3.6M观测，混合结构化任务数据（专家策略收集）和非结构化探索数据（Plan2Explore收集），无奖励、无文本标注。
- **benchmark**：离线RL设置，用语言或视频提示指导行为，评估标准化后的回合奖励（随机策略为0，专家策略为1）。
- **对比方法**：
  - **图像-语言奖励**：SigLIP-B模型，单帧图像与文本的余弦相似度作为奖励。
  - **视频-语言奖励**：InternVideo2模型（与GenRL相同），多帧视频与文本的余弦相似度。
  - **RL算法**：IQL、TD3+BC、TD3（模型无关）；WM-CLIP（模型基线，反向连接世界模型到VLM）。
  - 所有方法均训练500k梯度步，模型基线和GenRL先训练世界模型（每个域一次），再为每个任务训练actor-critic（50k步）。

## 4. 资源与算力

- **明确说明**：使用V100 GPU（16GB显存）集群。
- **训练时间**：
  - 预训练MFWM（世界模型+连接器/对齐器）约5天（500k步）。
  - 每个任务训练actor-critic在离线模式下少于5小时（50k步），数据自由模式下少于3小时。
  - 模型无关基线每个任务约7小时（500k步）。
- **优势**：当使用世界模型训练超过60个任务/种子时，GenRL效率更高；数据自由模式无需数据加载，减半训练时间。

## 5. 实验数量与充分性

- **实验数量**：
  - 语言到动作（in-distribution）：14个任务在5个域上，每个方法10个种子，报告均值±标准误。
  - 语言到动作（泛化）：21个未见任务，同样10个种子。
  - 视频到动作：6个任务，10个种子。
  - 数据自由策略学习：35个任务，10个种子。
  - 训练数据分布分析：walker域9个任务，对比不同数据子集。
  - 消融实验：时间对齐策略、对齐器有效性、与LIV对比（Kitchen域）。
- **充分性**：实验覆盖了多个域、多种任务类型（静态/动态）、多种提示模态（语言/视频），以及完整的消融和对比，统计显著性通过10个种子体现，总体设计充分、客观、公平。但仅在仿真环境，未在真实机器人上验证。

## 6. 论文的主要结论与发现

- GenRL在大多数任务上显著优于所有基线，尤其在动态任务（奔跑、跳跃）上优势明显，总体平均分数0.80（in-distribution）和0.76（泛化任务），而最佳基线WM-CLIP-V分别为0.41和0.67。
- 数据自由策略学习（完全在想象中采样，无需任何数据）性能与离线模式接近（0.76 vs 0.80），仍优于所有基线，证明了预训练模型的泛化能力。
- 视频-语言奖励优于图像-语言奖励；模型基方法优于模型无关方法；连接-对齐机制优于“反向连接”方式。
- 训练数据分布分析表明：多样化探索数据最关键，任务专用数据效果有限；完全依赖单一静态数据（如仅站立）会限制泛化。

## 7. 优点：方法或实验设计上的亮点

- **无需语言标注**：仅用视觉数据即可对齐多模态表示，解决了具身领域缺乏多模态数据的问题。
- **可解释性**：GenRL可以解码潜目标为图像，方便可视化提示理解，快速进行提示调整。
- **数据自由范式**：首个支持完全在想象中学习新策略的RL基础模型框架，无需接触预训练数据，降低数据依赖和隐私风险。
- **系统消融**：验证了连接器、对齐器、时间对齐等每个组件的重要性，实验设计严谨。
- **广泛对比**：涵盖了多种奖励范式（图像/视频）、多种强化学习算法（IQL、TD3、TD3+BC等），以及模型基基线WM-CLIP，比较公平。

## 8. 不足与局限

- **VLM固有缺陷**：模态间隙、对提示敏感，需要人工调优提示；虽然GenRL提供了可视化帮助，但仍无法完全避免。
- **世界模型依赖重构**：在复杂观测（如Minecraft）中重构质量较差，导致目标不精确；简单GRU架构可能不足，未来需要更强大的生成模型。
- **静态任务弱点**：对于完全静态任务（如厨房的“打开微波炉”），GenRL可能因目标序列含有微小运动而略逊于其他方法。
- **精确操作技能不足**：在操作域（Kitchen）中，新任务泛化困难，因为探索数据无法覆盖所有物体交互；训练数据需要包含多样化行为才能有效。
- **仅限仿真环境**：实验在dm_control等模拟器上进行，未在真实机器人上验证，与真实世界的领域差距未解决。
- **标称计算资源**：V100 GPU训练5天对于大规模应用仍较高。

（完）
