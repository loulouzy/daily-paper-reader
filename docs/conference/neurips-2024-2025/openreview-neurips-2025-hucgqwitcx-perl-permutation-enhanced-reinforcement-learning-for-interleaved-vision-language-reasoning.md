---
title: "PeRL: Permutation-Enhanced Reinforcement Learning for Interleaved Vision-Language Reasoning"
title_zh: PeRL：面向交织视觉语言推理的排列增强强化学习
authors: "Yizhen Zhang, Yang Ding, Shuoshuo Zhang, Xinchen Zhang, Haoling Li, Zhong-Zhi Li, Peijie Wang, Jie Wu, Lei Ji, Yeyun Gong, yelong shen, Yujiu Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=hUCgQWItCX"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 提出针对交织视觉语言推理的强化学习方法
tldr: 该论文针对现有多模态强化学习方法局限于单图像空间推理、无法处理多图像位置推理的问题，提出PeRL方法。受DeepSeek-R1启发，PeRL通过排列增强策略和多阶段训练，使视觉语言模型具备多图像关系理解能力。实验证明PeRL在需要跨图像位置推理的任务上显著优于现有方法，扩展了强化学习在多模态推理中的应用范围。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 670, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 686, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 604, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 567, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 496, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 435, \"height\": 150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 432, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1458, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hucgqwitcx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 610, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hucgqwitcx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hucgqwitcx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hucgqwitcx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hucgqwitcx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 526, \"label\": \"Table\"}]"
motivation: 现有多模态强化学习局限于单图像空间推理，无法处理多图像位置推理。
method: 提出排列增强的强化学习框架，通过多阶段训练实现交织多模态推理。
result: 在多个多图像推理基准上取得领先性能。
conclusion: 强化学习可有效推广到复杂多图像视觉语言任务。
---

## Abstract
Inspired by the impressive reasoning capabilities demonstrated by reinforcement learning approaches like DeepSeek-R1, recent emerging research has begun exploring the use of reinforcement learning (RL) to enhance vision-language models (VLMs) for multimodal reasoning tasks. However, most existing multimodal reinforcement learning approaches remain limited to spatial reasoning within single-image contexts, yet still struggle to generalize to more complex and real-world scenarios involving multi-image positional reasoning, where understanding the relationships across images is crucial. To address this challenge, we propose a general reinforcement learning approach PeRL tailored for interleaved multimodal tasks, and a multi-stage strategy designed to enhance the exploration-exploitation trade-off, thereby improving learning efficiency and task performance. 
Specifically, we introduce permutation of image sequences to simulate varied positional relationships to explore more spatial and positional  diversity. Furthermore, we design a rollout filtering mechanism for resampling to focus on trajectories that contribute most to learning optimal behaviors to exploit learned policies effectively. We evaluate our model on 5 widely-used multi-image benchmarks and 3 single-image benchmarks. Our experiments confirm that PeRL trained model consistently surpasses R1-related and interleaved VLM baselines by a large margin, achieving state-of-the-art performance on multi-image benchmarks, while preserving comparable performance on single-image tasks.

---

## 论文详细总结（自动生成）

# PeRL 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

当前多模态强化学习（RL）方法大多局限于**单图像空间推理**，难以应对真实世界中常见的**多图像位置推理**任务——即需要理解多幅图像之间空间、位置、时序等关系。现有视觉语言模型（VLM）在处理多图像输入时存在显著的**位置偏差**：改变图像输入顺序会导致推理结果错误，且模型无法稳定地维护跨图像的指代关系。因此，论文提出一种**面向交织多模态任务的通用强化学习方法 PeRL**，旨在通过强化学习增强 VLM 的多图像理解与推理能力，弥补现有方法在复杂多图像场景中的不足。

## 2. 方法论

- **核心思想**：通过**图像序列排列**（permutation）模拟多样的空间/位置关系，迫使模型学习**顺序不变**的表示；同时设计**rollout 过滤机制**，依据响应准确率筛选样本，聚焦高价值轨迹，提升学习效率。
- **关键技术细节**：
  - **排列增强（Permutation）**：对每个训练样本，随机置换图像顺序，并同步修改文本指代（如选项编号）以保持语义一致。引入**线性衰减因子 α_t** 控制批次中应用排列的概率，训练早期使用较多排列，后期逐渐减少，以稳定训练。
  - **Rollout 过滤**：利用 Qwen2.5-VL-7B 对每个问题进行 10 次生成，计算平均准确率作为难度分数，滤除易样本（准确率过高），保留中等难度样本以平衡分布。
  - **GRPO 框架**：采用 Group Relative Policy Optimization，对同一输入的多组响应计算归一化优势，并优化策略。将原始样本与其排列副本的响应合并，统一计算基线及优势。
  - **算法流程**（Algorithm 1）：每个训练步，对批次中每个样本生成 ns 个排列副本（原文 ns=1），每个副本生成 n 个 rollout（n=6），共 12 个响应；然后合并计算 reward 均值和标准差，得到每个响应的优势，更新策略。
- **公式说明**：论文给出了 Permutation GRPO 的损失函数，其中优势计算基于合并后的所有响应，而非仅基于每个排列组。

## 3. 实验设计

- **训练数据**：22K 多图像指令数据（来自 Mantis-Instruct 721K 的子集）+ 36K 单图像数据（K12 数学数据集），仅用于 RL 训练。
- **基准（Benchmark）**：
  - **多图像**（5 个）：Mantis-Eval、BLINK、MMIU、Remi、MV-MATH
  - **单图像**（3 个）：MathVista、MathVerse、MathVision
- **对比方法**：
  - **基座模型**：LLaVA-OneVision、Qwen2.5-VL、InternVL2.5、Mantisi 等
  - **RL 方法**：R1-VL-7B、R1-OneVision-7B、MM-Eureka、Noisy-K12 等
- **评估方式**：使用 VLMEvalKit 或官方代码进行 greedy decoding。

## 4. 资源与算力

- **硬件**：8 × H100 GPU
- **框架**：基于 veRL 框架的 GRPO 实现
- **超参数**：训练 batch size 128，微批大小 4/GPU，最大 prompt 长度 8192，response 长度 2048，KL 系数 0.01，学习率 1e-6，训练 2 个 epoch。
- **总花销**：论文未给出精确的 GPU 小时数，但提及计算成本较高，因此未报告误差棒。

## 5. 实验数量与充分性

- **主要实验**（表 1）：在 8 个基准上评测，对比了 10 余种方法，涵盖域内（多图像自然场景）和域外（多图像数学推理）任务。
- **消融实验**（表 2、表 3）：探究排列强度 ns（0/1/2/3）以及单/多图像数据解耦的影响。
- **附加分析**（图 5）：比较 Naive GRPO 与 Permutation GRPO 的奖励曲线和输出多样性。
- **案例研究**（图 6、图 8）：定性展示位置偏差及模型改进。
- **充分性评价**：实验覆盖了多图像和单图像的多类任务，消融设计合理，结果统计显著趋势明显。但缺少多次运行的误差棒或显著性检验，且代码暂未公开，可复现性有待验证。整体而言，实验较为充分且结论可信。

## 6. 主要结论与发现

1. PeRL 在**多图像自然场景理解基准**上达到 SOTA（Mantis-Eval 76.39，BLINK 58.53），显著超越原有基线和 RL 方法。
2. 在**单图像数学推理**上保持竞争力（MathVista 73.0，MathVerse 49.56），接近专用模型。
3. 在多图像数学推理（OOD）基准上同样表现优异，验证了**良好的泛化能力**。
4. **排列增强**有效降低位置偏差，使模型对图像顺序更鲁棒；**rollout 过滤**提升了训练稳定性与效率。
5. 排列 GRPO 相比普通 GRPO 输出多样性更高、训练曲线更平滑。

## 7. 优点

- **方法新颖**：首次将图像排列引入多模态 RL 训练，针对位置偏差提供了简单有效的解决方案。
- **训练效率高**：rollout 过滤减轻了困难度不平衡导致的学习无效问题，使梯度信号更有信息量。
- **通用性强**：同时适用于多图像和单图像任务，且无需额外 SFT 数据。
- **实验全面**：覆盖 8 个公开基准，对比方法涵盖多种类型，消融实验充分。
- **理论支撑**：附录提供了关于位置偏差降低的归纳论证，增强说服力。

## 8. 不足与局限

- **计算成本**：8×H100 训练对资源要求较高，难以在较小 GPU 集群复现。
- **未报告方差**：缺少多次实验的误差分析，结果波动性未知。
- **排列强度敏感**：ns=2 时部分基准性能下降，且增加训练成本。
- **模型规模单一**：仅在 7B 参数模型上验证，更大/更小模型效果未知。
- **代码未及时公开**：虽承诺发布，但评审时可复现性受限。
- **应用限制**：方法依赖规则化奖励（正确性+格式），对开放生成任务的适应性有限；数据预处理中使用了 GPT-4o，引入额外成本和依赖性。

（完）
