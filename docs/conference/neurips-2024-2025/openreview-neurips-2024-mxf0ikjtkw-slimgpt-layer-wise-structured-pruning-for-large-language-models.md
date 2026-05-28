---
title: "SlimGPT: Layer-wise Structured Pruning for Large Language Models"
title_zh: SlimGPT：大型语言模型的逐层结构化剪枝
authors: "Gui Ling, Ziyang Wang, YuliangYan, Qingwen Liu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=MxF0IKJtKW"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 实验室的大语言模型研究：结构化剪枝
tldr: 大型语言模型（LLM）参数规模大，结构化剪枝是平衡性能与效率的有效手段。本文提出SlimGPT，一种基于最优脑外科医生框架的低成本快速结构化剪枝方法。通过批处理贪心剪枝和动态分组策略，提升剪枝精度和效率。实验表明SlimGPT在多种LLM上实现了高压缩比下的性能恢复。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-mxf0ikjtkw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 712, \"height\": 917, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mxf0ikjtkw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 714, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mxf0ikjtkw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1185, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mxf0ikjtkw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 646, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-mxf0ikjtkw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 433, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 876, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1299, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 710, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 550, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 684, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 983, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 721, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1402, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1433, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1402, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1389, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 549, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-mxf0ikjtkw/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1455, \"height\": 1992, \"label\": \"Table\"}]"
motivation: 现有结构化剪枝方法在资源约束下性能恢复困难。
method: 基于最优脑外科医生框架，引入批处理贪心剪枝和动态分组优化。
result: 在多个LLM上取得高压缩比和良好性能恢复。
conclusion: SlimGPT提供了一种高效且低成本的LLM结构化剪枝方案。
---

## Abstract
Large language models (LLMs) have garnered significant attention for their remarkable capabilities across various domains, whose vast parameter scales present challenges for practical deployment. Structured pruning is an effective method to balance model performance with efficiency, but performance restoration under computational resource constraints is a principal challenge in pruning LLMs. Therefore, we present a low-cost and fast structured pruning method for LLMs named SlimGPT based on the Optimal Brain Surgeon framework. We propose Batched Greedy Pruning for rapid and near-optimal pruning, which enhances the accuracy of head-wise pruning error estimation through grouped Cholesky decomposition and improves the pruning efficiency of FFN via Dynamic Group Size, thereby achieving approximate local optimal pruning results within one hour. Besides, we explore the limitations of layer-wise pruning from the perspective of error accumulation and propose Incremental Pruning Ratio, a non-uniform pruning strategy to reduce performance degradation. Experimental results on the LLaMA benchmark show that SlimGPT outperforms other methods and achieves state-of-the-art results.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

大型语言模型（LLM）参数规模巨大，虽然能力卓越，但导致推理成本高、部署困难。模型压缩中的**结构化剪枝**是平衡性能与效率的关键技术，通过系统性地移除权重矩阵的列或行来降低参数量和推理延迟，且不需要特殊的硬件框架支持。然而，结构化剪枝对模型性能的影响比非结构化剪枝更严重，且现有方法在资源受限的条件下（缺少大量后训练数据）难以有效恢复性能。因此，本文提出一种低开销、快速的结构化剪枝方法 **SlimGPT**，基于经典的最优脑外科医生（OBS）框架，旨在资源受限环境下获得高压缩率且性能损失较小的LLM。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
将OBS框架从细粒度（单个权重）扩展到结构化剪枝（列/注意力头），并解决两个关键挑战：
- OBS每次迭代只能压缩一个参数，而结构化剪枝的最小粒度是列或头，直接应用会导致数值误差大。
- OBS是逐层（layer-wise）方法，缺乏全局信息，无法合理分配各层的剪枝率。

### 关键技术细节

1. **批处理贪心剪枝（Batched Greedy Pruning）**  
   - 对注意力头：提出**分组Cholesky分解**。将Hessian逆矩阵沿主对角线分割为对应每个注意力头的子矩阵，并行进行Cholesky分解，从而一次性计算所有头的剪枝误差，避免重复矩阵求逆和Cholesky分解。再通过列重排实现头级剪枝。  
   - 对FFN层：提出**动态组大小**策略。因FFN中间维度大，一次剪一列低效。初始用较大组大小（如1024）一次剪多列，后续逐步减小组大小（至8），在接近最优解的同时提升效率。  
   - 算法流程：先计算头误差选择要剪的头，再将该头对应的列重排到前面，用全局Cholesky分解逐列剪枝，最后恢复列顺序。

2. **递增剪枝率（Incremental Pruning Ratio）**  
   - 分析逐层剪枝中的**误差累积**现象：浅层剪枝误差会被深层放大，导致最终性能显著下降。  
   - 提出对数递增的非均匀剪枝策略：`ri = r0 + (rn-1 - r0) * log(i+1) / log(n)`，其中`i`为层索引。浅层保留较少剪枝率以抑制误差扩散，深层允许更高剪枝率。此策略无需额外操作，仅改变目标剪枝率分布。

### 公式关键点
- 使用OBS扩展公式：`W:,p = argmin (W²:,p / H⁻¹_p,p)`，补偿矩阵 `Δ = -W:,p / H⁻¹_p,p * H⁻¹_p,:`。
- 通过分组Cholesky分解预计算对角线元素，加速误差估计。

## 3. 实验设计

### 数据集与评估场景
- **校准数据集**：C4（通用预训练语料），随机选取256条2048-token序列。
- **语言建模**：WikiText2验证集（困惑度PPL）。
- **常识推理（零样本）**：7个子任务：BoolQ、PIQA、HellaSwag、WinoGrande、ARC-easy、ARC-challenge、OpenbookQA，报告平均准确率。
- **其他任务**：MMLU（5-shot）、LongBench（长文本理解）。
- **微调恢复**：使用Alpaca指令数据集，LoRA微调1个epoch。

### 基准方法对比
- LLM-Pruner（梯度剪枝）、Compresso（L0正则化+LoRA）、LoRAPrune（基于LoRA梯度重要性）。
- 所有方法均在相同LoRA微调设置下复现（标注*的结果为复现结果）。

### 模型规模
- 主要实验：LLaMA-7B，剪枝率20%/25%/33%/50% → 5.4B/5B/4.5B/3.4B。
- 扩展：LLaMA-13B/30B（20%/50%），Vicuna-7B，LLaMA2-7B，Baichuan-7B，Mistral-7B-Instruct。

## 4. 资源与算力

- **剪枝阶段**：使用单张A100 GPU（显存40GB）。  
  - LLaMA-7B：20%剪枝耗时约678秒（~11分钟），50%约1074秒（~18分钟），内存占用约7.4GB。  
  - LLaMA-13B：20%剪枝约1417秒（~24分钟），50%约2475秒（~41分钟），内存约11.6GB。  
- **微调阶段**：使用两张A100 GPU，LoRA微调1个epoch，批次大小64，序列长度256。
- 文中明确指出可在单卡A100上完成剪枝，内存开销远小于加载整个模型（逐层处理）。

## 5. 实验数量与充分性

实验非常充分，包括：
- **主对比实验**：LLaMA-7B四个比率（表1），LLaMA-13B/30B两个比率（表2），Vicuna-7B（表8），LLaMA2-7B（表9），Baichuan-7B（表11）。
- **消融实验**：
  - 批处理贪心剪枝组件：去掉动态组大小（-DGS）和分组Cholesky（-GCD）对PPL和平均得分的影响（表5）。
  - 剪枝率策略比较：对数递增 vs 线性递增 vs 均匀 vs 递减（共6种策略，表6）。
  - 校准样本数量（128~2048）和序列长度（64~2048）的影响（图3）。
  - 校准数据集类别：C4 vs Alpaca vs GPT4-Alpaca（表14）。
- **其他评估**：MMLU（LLaMA2-7B和Baichuan-7B），LongBench（Mistral-7B-Instruct）。
- 生成样例定性展示（附录表15）。

实验设计客观公平：与基准方法在相同微调设置下复现对比，使用广泛接受的基准数据集。消融实验完整验证了各关键组件的贡献。

## 6. 主要结论与发现

1. **SlimGPT在所有剪枝率下均优于现有SOTA方法**。例如LLaMA-7B 20%剪枝后，PPL 16.68 vs 16.80（LoRAPrune），零样本平均65.07 vs 61.50（LLM-Pruner）。50%剪枝时优势更大（PPL 31.07 vs 40.64，平均53.76 vs 48.35）。  
2. **无需微调（w/o tune）时已显著超越基准**，说明OBS参数补偿的有效性。  
3. **递增剪枝率关键**：均匀或递减策略导致PPL剧增（均匀时PPL 123.05 vs 38.83），证实误差累积危害。对数递增在语言建模上最佳，线性递增在常识推理上略好。  
4. **大模型冗余度更高**：LLaMA-13B/30B在20%剪枝后性能几乎无损，甚至略有提升（30B平均72.56 vs 71.92）。  
5. **校准数据影响**：使用指令数据集（Alpaca）更有利于保留常识推理能力，预训练数据集（C4）则保持语言建模更好。

## 7. 优点

- **低资源高效**：仅需单GPU、几百条校准数据、约1小时即可完成结构化剪枝，无需全量后训练。  
- **任务无关**：仅使用通用预训练语料作为校准集，不需要下游任务数据。  
- **通用性**：适用于所有基于Transformer的LLM，实验验证了LLaMA、Vicuna、LLaMA2、Baichuan、Mistral多种架构。  
- **技术创新**：分组Cholesky分解和动态组大小巧妙解决了OBS框架扩展到结构化剪枝时的效率和精度问题；递增剪枝率从误差分析出发，简单有效。  
- **推理加速明显**：50%剪枝后推理显存降至51%，延迟降至69%。

## 8. 不足与局限

1. **高剪枝率下性能损失仍不可忽视**：50%剪枝后PPL和常识推理精度下降显著，复杂任务（如LongBench、MMLU）甚至下降更严重。  
2. **递增剪枝率策略非最优**：当前使用简单对数递增，文中承认此策略具有一般性但非最优，更精确的非均匀策略有待探索。  
3. **微调恢复依赖低秩适应**：仅使用LoRA微调1个epoch，对于高剪枝率或复杂任务效果有限，若允许全参数微调或更多数据可能更好，但资源受限。  
4. **对校准数据分布敏感**：不同校准集导致不同任务偏好（如C4 vs Alpaca），如何自动选择最优校准集未讨论。  
5. **伦理安全风险**：提到剪枝后的模型可能存在负面社会影响，但未给出具体缓解措施。  
6. **实验未包含误差线**：由于算力限制，未报告多次实验的统计误差，结果可能存在一定波动。

（完）
