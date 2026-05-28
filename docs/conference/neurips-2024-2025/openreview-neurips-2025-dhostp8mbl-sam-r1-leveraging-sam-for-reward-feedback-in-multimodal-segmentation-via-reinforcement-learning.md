---
title: "SAM-R1: Leveraging SAM for Reward Feedback in Multimodal Segmentation via Reinforcement Learning"
title_zh: "SAM-R1: 利用SAM的奖励反馈在强化学习中实现多模态分割"
authors: "Jiaqi Huang, Zunnan Xu, Jun Zhou, Ting Liu, Yicheng Xiao, Mingwen Ou, Bowen Ji, Xiu Li, Kehong Yuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dHOSTp8MBl"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态上下文中大语言模型的强化学习
tldr: 针对多模态图像分割依赖人工推理标注的问题，SAM-R1首次将细粒度分割引入多模态推理模型训练，利用SAM提供奖励反馈，通过强化学习使模型具备推理能力，无需推理过程标注。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dhostp8mbl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dhostp8mbl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dhostp8mbl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 1189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dhostp8mbl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dhostp8mbl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 631, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 920, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1032, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 605, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dhostp8mbl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1209, \"height\": 293, \"label\": \"Table\"}]"
motivation: 多模态大模型在图像分割中依赖显式推理标注，成本高且难以获取。
method: 集成任务特定奖励（如SAM分割质量），通过强化学习训练多模态推理模型。
result: 无需推理标注即可实现细粒度推理分割，性能优于传统方法。
conclusion: 强化学习结合任务奖励可有效赋予多模态模型推理能力，降低标注依赖。
---

## Abstract
Leveraging multimodal large models for image segmentation has become a prominent research direction. However, existing approaches typically rely heavily on manually annotated datasets that include explicit reasoning processes, which are costly and time-consuming to produce. Recent advances suggest that reinforcement learning (RL) can endow large models with reasoning capabilities without requiring such reasoning-annotated data. In this paper, we propose SAM-R1, a novel framework that enables multimodal large models to perform fine-grained reasoning in image understanding tasks. Our approach is the first to incorporate fine-grained segmentation settings during the training of multimodal reasoning models. By integrating task-specific, fine-grained rewards with a tailored optimization objective, we further enhance the model's reasoning and segmentation alignment. We also leverage the Segment Anything Model (SAM) as a strong and flexible reward provider to guide the learning process. With only 3k training samples, SAM-R1 achieves strong performance across multiple benchmarks, demonstrating the effectiveness of reinforcement learning in equipping multimodal models with segmentation-oriented reasoning capabilities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于多模态大模型的图像分割方法（如推理分割）严重依赖包含显式推理过程的人工标注数据集，这种数据获取成本高昂、耗时费力，且模型容易过拟合、泛化能力差。
- **背景**：近期研究表明，强化学习（RL）可以通过奖励反馈机制赋予大模型推理能力，而无需推理标注数据。DeepSeek-R1等工作的成功验证了规则奖励在语言任务中的有效性，但将其推广到多模态细粒度分割任务仍面临挑战。
- **整体含义**：本文首次将细粒度分割设置引入多模态推理模型的训练过程，通过将分割模型（SAM）作为奖励信号的提供者，结合强化学习实现端到端的推理增强，从而降低对人工推理标注的依赖，提升模型在复杂场景中的推理与分割对齐能力。

## 2. 方法论

### 核心思想
- 利用强化学习框架，让多模态大模型在生成推理链（chain-of-thought）后再输出分割所需的边界框和关键点，然后输入SAM产生像素级掩码；将SAM的输出与真值掩码计算IoU，作为细粒度奖励反馈给模型，驱动模型自我改进。

### 关键技术细节
1. **基础架构**：
   - 以Qwen2.5VL-7B作为多模态大模型，SAM2-Large作为分割模型。
   - 模型输出格式：先输出 `<think>...</think>` 推理过程，再输出 `<answer>{bounding box, points}</answer>`。

2. **强化学习算法改进（基于GRPO）**：
   - **非对称裁剪（Asymmetric Clipping）**：保留原有的下界 `1 - ε`，但提高上界至 `1 + ε_high`（设置为0.3），鼓励模型对有高优势的action进行更大胆的探索，以获得更细粒度的理解。
   - **Token级损失归一化**：对同一组内的所有响应，按总token数平均损失，使每个token受到的惩罚一致，避免长而低信息量的响应浪费token。
   - **目标函数**（公式4）：在GRPO基础上保留KL惩罚项，替换裁剪阈值为不对称形式，并采用token级归一化。

3. **奖励函数设计**：
   - **分层分割精度奖励（Tiered Segmentation-accuracy Reward）**：
     - 由SAM提供掩码预测，计算与真值的IoU，按区间给予不同奖励（IoU>0.8得4分；0.7-0.8得3分；0.5-0.7得2分；否则0分）。
   - **推理格式奖励**：要求输出包含 `<think>` 和 `<answer>` 标签，符合格式得正奖励，否则惩罚。
   - **分割格式奖励**：要求输出JSON格式的边界框和关键点，符合格式得正奖励，否则惩罚。

### 算法流程（文字说明）
- 训练阶段：对每个输入问题，从旧策略中采样G个响应 → 每个响应解析输出，将边界框和关键点输入SAM → SAM生成掩码，计算IoU得到分割精度奖励 → 结合格式奖励 = 总奖励 → 计算组内优势（归一化） → 用修改后的GRPO目标更新策略模型，同时施加KL约束。

## 3. 实验设计

### 使用的数据集与场景
- **训练**：从RefCOCOg训练集随机采样3000个样本（共104560个表达式）。
- **评估**：
  - **In-domain**：RefCOCOg测试集。
  - **Out-of-domain（OOD）**：RefCOCO和RefCOCO+的testA子集。
  - **复杂推理**：ReasonSeg（零样本评估，val/test）。
  - **额外评估**：LISA-Grounding基准（Referring Expression Comprehension，零样本）。

### Benchmark
- 指标：gIoU（逐图像IoU平均）和cIoU（累积IoU）。

### 对比方法
- **ReasonSeg**：OVSeg、ReLA、Grounded-SAM、LISA-7B/13B、SAM4MLLM、Seg-Zero。
- **Referring Expression Segmentation**：LAVT、ReLA、LISA-7B、PixelLM-7B、PerceptionGPT-7B、Seg-Zero。
- **REC任务**：GroundedSAM、OV-Seg、X-Decoder、Visual-RFT。

## 4. 资源与算力

- **硬件**：8 × NVIDIA A100 GPU。
- **超参数**：有效批次中采样8个响应/问题，学习率1e-6，图像统一缩放至840×840。
- **训练时长**：文中未明确说明总训练时长或步数。

## 5. 实验数量与充分性

- **主实验**（表1、2）：在ReasonSeg和三个Referring Expression数据集上对比多个方法，展现出零样本竞争力。
- **消融实验**：
  - 阈值策略（表3）：比较固定阈值（0.5, 0.7, 0.8）与分层阈值，证明分层设计的优势。
  - 算法组件（表4）：逐步加入Token级CLIP提高、非对称裁剪，验证每个改进的有效性。
- **额外实验**：REC任务（表5）零样本效果远超对比方法；数据效率分析（表6）对比3k vs 10k样本，证明3k已足够。
- **可视化分析**：包含成功案例（图3）和失败案例（图5），提供深入定性理解。
- **消融失败分析**：包括去除KL约束导致训练崩溃（图4a）、鼓励负参考点但效果不佳（图4b/4c）。
- **充分性评价**：实验覆盖了in-domain和OOD多种场景、零样本设置、消融全面，对比方法均为公开权威基线，且提供详细分析。实验设计客观、公平。

## 6. 主要结论与发现

- 强化学习结合任务特定奖励（尤其是SAM提供的细粒度分割奖励）可以有效激发多模态大模型的推理能力，无需人工推理标注。
- 仅用3000个训练样本，SAM-R1即在ReasonSeg零样本上达到60.2% gIoU（超越Seg-Zero的58.3%），在RefCOCO+ OOD上提升至74.7% cIoU。
- 修改后的GRPO（非对称裁剪、token级损失归一化）在稳定性与探索能力之间取得了更好的平衡。
- 模型具有很强的数据效率和泛化能力，即使在不相关任务（REC）上也表现出显著提升。
- 该方法避开昂贵的推理标注，为数据稀缺领域（如机器人感知、医学图像）提供可推广范式。

## 7. 优点

- **端到端整合**：首次将SAM作为活跃的奖励提供者纳入强化学习训练循环，使优化目标直接对齐最终分割任务，降低reward hacking风险。
- **奖励设计精细**：分层分割奖励鼓励模型从低IoU逐步提升；格式奖励确保输出规范性。
- **算法改进有效**：非对称裁剪和token级归一化显著提升性能，且无需额外的critic模型，降低复杂度。
- **数据高效**：仅用3k样本即达到饱和性能，远少于传统需要大量人工标注的方法。
- **通用性强**：零样本在REC任务上大幅超越以往方法，展示了跨任务迁移能力。
- **分析深入**：包含详细消融、失败案例、负参考点尝试等，揭示方法局限并指引未来方向。

## 8. 不足与局限

- **模型结构局限**：SAM参数冻结，形成单向信息流，无法与推理模型协同适应；联合优化两者（计算昂贵）是未来方向。
- **负参考点生成失败**：模型无法内生地生成有区分力的负关键点（即背景点），虽然尝试通过奖励鼓励但未成功，导致无法在复杂场景中实现判别性推理。
- **像素级映射不足**：可视化失败案例显示模型在语义理解正确的情况下，仍会出现不完整分割（只覆盖部分目标）或过度分割（如将整个车标为引擎盖），说明从推理到像素级映射的精细度有待提升。
- **训练稳定性**：去除KL约束会导致训练崩溃（图4a），表明当前方法对KL依赖性强，未来需探索更稳定的探索策略。
- **实验覆盖**：未涉及医学图像、机器人视觉等实际应用场景的验证；仅测试单一大模型（Qwen2.5VL-7B）和单一分割模型（SAM2-Large），架构通用性有待扩展。
- **公开资源**：代码暂未开放，可能影响可复现性。

（完）
