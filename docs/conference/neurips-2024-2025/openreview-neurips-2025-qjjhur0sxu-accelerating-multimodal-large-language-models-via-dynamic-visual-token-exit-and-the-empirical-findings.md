---
title: Accelerating Multimodal Large Language Models via Dynamic Visual-Token Exit and the Empirical Findings
title_zh: 通过动态视觉令牌退出加速多模态大语言模型及其实证发现
authors: "Qiong Wu, Wenhao Lin, Yiyi Zhou, Weihao Ye, Zhanpeng Zeng, Xiaoshuai Sun, Rongrong Ji"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QjJHUR0sXU"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型加速方法
tldr: 多模态大语言模型（MLLM）的视觉冗余问题影响推理效率。本文通过实证研究揭示了MLLM的三个推理阶段，并发现视觉令牌在文本令牌获得足够图像信息后会停止贡献。基于此提出动态视觉令牌退出（DyVTE）方法，在推理中动态移除冗余视觉令牌，显著提升效率而不影响性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1403, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1413, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 177, \"height\": 144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 183, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1414, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1383, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1387, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1383, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1379, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1353, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1354, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1382, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1383, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjjhur0sxu/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1381, \"height\": 483, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 749, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjjhur0sxu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 383, \"label\": \"Table\"}]"
motivation: MLLM中存在视觉冗余，影响推理效率，需要在不牺牲性能的前提下加速。
method: 基于对MLLM注意力行为的观察，提出动态视觉令牌退出方法，在推理中移除无贡献的视觉令牌。
result: 实验证实该方法在多个任务上加速推理，且保持任务性能不变。
conclusion: DyVTE是一种正交且高效的MLLM加速方案，可与其他方法互补。
---

## Abstract
In this paper, we study the visual redundancy problem of multimodal large language models (MLLMs) from the perspective of attention behaviors. 
Via extensive empirical experiments, we observe and conclude three main inference stages of MLLMs:
(i) Early fusion between tokens is first accomplished quickly. 
(ii) Intra-modality modeling then comes to play. 
(iii) Multimodal reasoning resumes and lasts until the end of inference. 
In particular, we reveal that visual tokens will stop contributing to reasoning when the text tokens receive enough image information.
Based on this observation, we propose an effective method to improve the efficiency of MLLMs, termed dynamic visual-token exit (DyVTE), which is orthogonal but collaborative to previous token-wise visual compression methods.
To validate the efficacy of DyVTE, we apply it to a set of MLLMs, including LLaVA, VILA, EAGLE and InternVL.
The experimental results not only show the effectiveness of our DyVTE in improving MLLMs' efficiency, e.g., DyVTE reduces the computation overhead of LLaVA-1.5 by up to 45.7% without performance drop, but also reveal a general pattern across multiple MLLMs, well facilitating the in-depth analysis of MLLMs. 
Our code is anonymously released at https://anonymous.4open.science/r/AnonymousDyVTE-26AB/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多模态大语言模型（MLLMs）在处理高分辨率图像时需要大量视觉令牌（visual tokens），导致计算开销巨大（例如 LLaVA-NeXT 比 LLaVA-1.5 多约 1728 个视觉令牌，FLOPs 增加约 4 倍）。已有工作指出这些视觉令牌存在明显冗余，但多为令牌级别的剪枝或合并，缺乏对 MLLM 内在推理行为的深入理解。
- **动机**：从注意力行为角度研究 MLLM 如何利用视觉令牌，揭示其推理过程中的通用模式，并基于此设计更高效的加速方法。
- **核心发现**：通过大量实证实验，论文总结了 MLLM 推理的三个阶段：
  1. **早期融合（Early Fusion）**：浅层快速完成多模态信息交换。
  2. **模态内建模（Intra-modality Modeling）**：同模态令牌间的自注意力主导。
  3. **多模态推理（Multimodal Reasoning）**：视觉令牌向文本令牌重新传播信息，但影响有限，且当文本令牌获得足够图像信息后，视觉令牌停止贡献。
- **整体含义**：揭示了视觉令牌在深层实际上“不再必要”，为动态提前移除所有视觉令牌提供了理论基础；不同样本、任务的最优退出层不同，需要自动化策略。

## 2. 方法论：动态视觉令牌退出（DyVTE）

- **核心思想**：在推理过程中，利用轻量级超网络感知文本令牌状态，动态决定何时移除所有视觉令牌，从而加速后续层的计算，同时保持文本令牌继续推理。
- **关键技术细节**：
  - **超网络（Hyper-network）**：一个简单的 MLP，输入为当前层文本令牌的两种表示：
    - `avg(T_{1:t-1})`：所有先前文本令牌的平均，代表整体状态。
    - `T_t`：最后一个文本令牌，在单向自注意力中对解码至关重要。
  - **决策公式**：
    ```
    p = Softmax(GELU([avg(T_{1:t-1}), T_t] * W1) * W2)
    ```
    输出二元预测 p（exit 或 keep）。
  - **退出机制**：当预测为 exit 时，在该层之后移除所有视觉令牌，文本令牌继续通过剩余层推理。
  - **训练方式**：冻结预训练 MLLM，仅训练超网络。使用对比有无 DyVTE 的模型输出（回答字符串是否相同）作为监督信号，并加入预测不确定性正则化（交叉熵低于阈值 τ），生成标签 y。损失为交叉熵损失。
  - **效率**：训练仅使用 LLaVA-665k 指令集的 1% 样本，训练 1 个 epoch，计算开销远低于微调整个 MLLM。

## 3. 实验设计

- **数据集/Benchmark**：
  - 传统 VL 基准：VQAv2、GQA、ScienceQA（SQA）、TextVQA。
  - MLLM 基准：POPE（幻觉评估）、MME、MMBench、SEED、MM-Vet（细粒度推理）。
- **对比方法**：
  - **基线**：原始 MLLM（无加速）。
  - **令牌级方法**：FastV（基于注意力分数的剪枝）、ToMe（令牌合并）。
  - **组合**：DyVTE + FastV。
- **测试的 MLLM**：LLaVA-1.5 (7B/13B)、VILA 7B、EAGLE-X5 7B、InternVL 7B，涵盖不同家族和规模。
- **评估指标**：准确率（Accuracy）和计算开销（TFLOPs），同时报告推理延迟（Latency）。

## 4. 资源与算力

- 论文未明确说明使用的 GPU 型号、数量及训练总时长。仅提及超网络训练使用 1% LLaVA-665k 数据训练 1 个 epoch，学习率 4×10⁻⁵，隐藏维度 2048。所有 MLLM 参数冻结，计算需求较低。
- 推理延迟在单 GPU 环境下测量（具体型号未说明）。

## 5. 实验数量与充分性

- **主要实验数量**：约 10+ 组对比实验，覆盖 4 个 VL 基准和 5 个 MLLM 基准，测试了 5 个不同 MLLM，并进行了：
  - DyVTE 与基线及令牌剪枝方法的对比（表 1、2、5）。
  - 实际推理延迟对比（表 3）。
  - 注意力熵可视化分析（图 5）。
  - 消融实验（表 4）：不同令牌状态对 DyVTE 的影响。
  - 跨模型泛化实验（表 6）：DyVTE 在不同 MLLM 之间迁移。
  - 退出层分布统计（附录图 7）。
  - 多模型注意力分布可视化（附录图 8-17）。
- **充分性**：实验较为充分，覆盖了主流 MLLM 架构、多变任务、多维度分析（性能、效率、注意力模式、泛化性）。但缺少统计显著性检验（如误差棒）。

## 6. 主要结论与发现

- DyVTE 显著降低计算开销：例如 LLaVA-1.5 7B 在 SEED 上减少 45.7% TFLOPs 且性能无损；13B 模型在 SQA 上减少 55.9% TFLOPs，准确率仅下降 0.8%。
- DyVTE 可与令牌剪枝方法（如 FastV）协同工作，进一步加速（组合后平均减少 51.5% 计算，性能仅降 0.7%）。
- DyVTE 的退出层因任务而异（如 SQA 早期即可退出，TextVQA 需更晚退出），验证了动态策略的必要性。
- DyVTE 的注意力熵分析表明：移除视觉令牌后，文本自注意力的分布几乎不变，说明不影响文本建模。
- DyVTE 在不同 MLLM 间具有良好泛化能力（训练于 LLaVA，直接用于 VILA 和 InternVL 效果接近自训练）。
- 使用“平均文本 + 最后一个文本令牌”作为状态表示是最有效的组合。

## 7. 优点

- **方法论创新**：从全局退出视角（而非令牌级别剪枝）处理视觉冗余，与现有令牌压缩方法正交且互补。
- **高效训练**：无需微调整个 MLLM，仅训练极轻量超网络，训练成本极低。
- **动态决策**：根据文本状态自适应决定退出时机，适配不同任务和样本。
- **通用性验证**：在多个主流 MLLM（LLaVA、VILA、EAGLE、InternVL）上验证有效，且能跨模型迁移。
- **丰富分析**：从注意力行为、注意力熵、退出层分布等多个角度提供深入洞察，支撑方法和结论。

## 8. 不足与局限

- **仅可执行全局退出**：目前 DyVTE 只能一次性移除所有视觉令牌，可能在某些需要部分视觉信息在后期继续交互的场景下不够最优（论文自身已提及）。
- **缺乏统计学显著性测试**：实验未报告误差棒或置信区间，难以判断结果波动范围。
- **资源信息不完整**：未明确说明训练和测试用的 GPU 型号、数量、时间等，影响可复现性。
- **未考虑视频/动态输入**：实验仅基于静态图像任务，未测试视频或 streaming 场景。
- **超网络训练依赖固定数据集**：使用 LLaVA-665k 的 1% 训练，可能对不同分布的数据泛化性未知。
- **超参数未深入讨论**：如阈值 τ 的设置、MLP 隐藏维度的影响等未做消融。

（完）
