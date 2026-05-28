---
title: "SCOPE: Saliency-Coverage Oriented Token Pruning for Efficient Multimodel LLMs"
title_zh: SCOPE：面向高效多模态LLM的显著性与覆盖性导向的标记剪枝
authors: "Jinhong Deng, Wen Li, Joey Tianyi Zhou, Yang He"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oUghNi5XWc"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型论文：基于显著性与覆盖性的视觉标记剪枝
tldr: 多模态大语言模型（MLLM）处理大量冗余视觉标记导致计算开销。现有剪枝方法只关注显著性，导致语义不完整。本文提出SCOPE策略，联合建模所选视觉标记的显著性和覆盖性，通过集合覆盖理论保留语义完整性。实验表明SCOPE在效率与性能之间取得更好平衡。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 649, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oughni5xwc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1433, \"height\": 1451, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 1363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 987, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 767, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 880, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 991, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1019, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oughni5xwc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 969, \"height\": 396, \"label\": \"Table\"}]"
motivation: 现有视觉标记剪枝仅根据注意力分数选择，丢失语义完整性。
method: 引入集合覆盖概念，联合优化所选标记的显著性和覆盖度。
result: 在多个MLLM上实现更高效的推理，性能损失更小。
conclusion: SCOPE通过覆盖性约束提升了视觉标记剪枝的语义保留。
---

## Abstract
Multimodal Large Language Models (MLLMs) typically process a large number of visual tokens, leading to considerable computational overhead, even though many of these tokens are redundant. Existing visual token pruning methods primarily focus on selecting the most salient tokens based on attention scores, resulting in the semantic incompleteness of the selected tokens. In this paper, we propose a novel visual token pruning strategy, called **S**aliency-**C**overage **O**riented token **P**runing for **E**fficient MLLMs (SCOPE), to jointly model both the saliency and coverage of the selected visual tokens to better preserve semantic completeness. Specifically, we introduce a set-coverage for a given set of selected tokens, computed based on the token relationships. We then define a token-coverage gain for each unselected token, quantifying how much additional coverage would be obtained by including it. By integrating the saliency score into the token-coverage gain, we propose our SCOPE score and iteratively select the token with the highest SCOPE score. We conduct extensive experiments on multiple vision-language understanding benchmarks using the LLaVA-1.5 and LLaVA-Next models. Experimental results demonstrate that our method consistently outperforms prior approaches.

---

## 论文详细总结（自动生成）

# 论文总结：SCOPE: Saliency-Coverage Oriented Token Pruning for Efficient Multimodal LLMs

## 1. 核心问题与整体含义

**研究动机**：多模态大语言模型（MLLMs）在视觉理解任务中通常将图像编码为大量视觉token（例如ViT处理448×448图像产生超过1000个token），这些token与文本token一起输入LLM，导致自注意力计算复杂度随token数平方增长，推理开销巨大。然而，大量视觉token是冗余的（如背景、重复图案），因此需要有效的token剪枝策略来减少计算量同时保持性能。

**现有局限**：当前主流的剪枝方法（如FastV、SparseVLM、VisionZip）仅基于注意力分数选择“最显著”的视觉token（如CLS token的注意力权重）。这会产生两个问题：
- **语义完整性不足**：聚焦于少数突出对象而忽略上下文信息，导致丢失关键视觉线索（如图1a）。
- **注意力分布高度偏斜**：只有少数token获得高注意力，其余token的注意力值近乎均匀，难以区分有信息量token和真正冗余的token（如图1b）。

**本文目标**：提出一种同时建模**显著性（saliency）**和**覆盖性（coverage）**的剪枝策略，在保留最信息性token的同时最大化所选token集合的语义覆盖范围，从而保持视觉表示的完整性。

## 2. 方法论

### 核心思想
SCOPE基于集合覆盖理论，定义了一个“token覆盖增益”，衡量将一个未选择token加入当前已选集合后能带来的额外覆盖量。再将此增益与token的显著性分数（基于CLS注意力）相乘，得到**SCOPE分数**。通过迭代选择SCOPE分数最高的token，最终得到一个既高显著又高覆盖的紧凑token子集。

### 关键技术细节
- **θ覆盖度（θ-Coverage）**：对于已选子集V'，定义θ覆盖度为全集中有多少比例的token与V'中至少一个token的余弦相似度≥θ。该指标量化了已选token对全局语义空间的代表程度。
- **集合覆盖函数**：定义已选集合S的覆盖度f(S) = ∑_{u∈V} max_{s∈S} sim(u, s)，即全集中每个token与S中最相似token的相似度之和。
- **token覆盖增益**：对于候选token v，边际增益Δ(v; S) = f(S∪{v}) - f(S) = ∑_{u∈V} (max(C(u,S), sim(u,v)) - C(u,S))，即v加入后能提升多少覆盖总分。
- **SCOPE分数**：将显著性分数A_v（CLS注意力值）融入覆盖增益：Δ(v, A_v^α; S) = Δ(v; S) · A_v^α，其中α为缩放因子（默认=1）。迭代选择使该分数最大的token。

### 算法流程（文字说明）
1. 初始化S为空，对每个全量token u设置当前最佳覆盖度c_u=0。
2. 对于t=1到K（目标保留token数）：
   - 对每个未选token v，计算边际覆盖增益Δ(v; S)。
   - 计算SCOPE分数=Δ(v; S)×A_v^α。
   - 选择分数最高的v*加入S。
   - 更新所有u的c_u = max(c_u, sim(u, v*))。
3. 返回S作为剪枝后的token子集。

该方法无需训练，可即插即用。

## 3. 实验设计

### 数据集/场景
- **图像理解**：GQA、MMBench、MME、POPE、ScienceQA、TextVQA、SEEDBench、MMVet。
- **视频理解**：TGIF、MSVD、MSRVTT、ActivityNet（使用Video-LLaVA）。
- **OCR相关**：DocVQA、ChartQA、OCRBench（附录C.4）。
- **高分辨率**：LLaVA-Next（2880个初始token）用于评估高分辨率场景。

### 基准方法
- FastV (ECCV'24)：基于早期层文本到视觉注意力。
- SparseVLM (ICML'25)：利用重要文本词作为评分器。
- VisionZip (CVPR'25)：基于CLS注意力进行top-k选择。
- PDrop (CVPR'25)：金字塔式冗余减少。
- DivPrune (CVPR'25)：基于多样性的选择（附录C.3）。
- 随机选择、仅显著、仅覆盖等消融基线。

### 评估方式
- 对每个benchmark报告原始准确率或F1分数。
- 以“相对于full token上界（100%）的相对百分比”为主要比较指标，使跨benchmark结果可比。

## 4. 资源与算力

论文明确提到：
- GPU：**4×A100 GPU**。
- 推理batch size设为1。
- 未说明训练时长（因方法无需训练，仅推理阶段剪枝）。
- 效率分析（表5）：在LLaVA-NeXT 7B上，将2880 token剪枝至160后，POPE性能保持81.3%（原始86.4%），推理延迟从601.9秒降至188.8秒，加速约3.2倍。

## 5. 实验数量与充分性

- **主要实验**：在LLaVA-1.5 7B、LLaVA-1.5 13B、LLaVA-Next 7B、LLaVA-Next 13B上评估了不同token保留比例（192/128/64或640/320/160），覆盖总计超过7个benchmark。
- **视频实验**：Video-LLaVA上保留136 token。
- **极端压缩实验**：图4展示在8 token下仍保持性能。
- **消融实验**：表4对比随机、仅显著、仅覆盖、完整SCOPE，证明各组件有效性。
- **超参数分析**：图6探索α在0~2范围内的灵敏度。
- **附加实验**：Qwen2-VL（表8）、OCR benchmark（表9）。

**充分性评价**：实验覆盖了多种模型规模（7B/13B）、多种架构（LLaVA系列、Qwen2-VL）、多种任务（VQA、分类、OCR、视频QA）、多种压缩率（最高减少94.4%）。对比方法均为近年SOTA，消融实验合理，统计结果清晰。但未报告多次运行的标准差或置信区间（论文未提供误差线），这是常见做法但可能影响统计可靠性。

## 6. 主要结论与发现

- **SCOPE显著优于现有方法**：在所有token预算下，SCOPE的相对性能均高于FastV、SparseVLM、VisionZip、PDrop等。例如在LLaVA-1.5 7B保留64 token时，SCOPE保持96.0%性能，而VisionZip为93.5%，SparseVLM仅85.1%。
- **联合建模显著性与覆盖性至关重要**：消融实验显示仅显著或仅覆盖均不如完整SCOPE。
- **覆盖性弥补显著性不足**：仅显著法在θ覆盖率上甚至低于随机，而SCOPE大幅提升覆盖率（图2）。
- **极端压缩下鲁棒性更强**：在8 token时，SCOPE性能下滑远小于VisionZip（图4）。
- **无训练即插即用**：无需微调或额外训练，可直接应用于多种MLLM。
- **视频理解中同样有效**：在Video-LLaVA上保留136 token时几乎保持100%性能。

## 7. 优点

1. **方法创新**：将集合覆盖理论引入视觉token剪枝，首次联合考虑显著性和覆盖性，解决现有方法语义不完整问题。
2. **理论清晰**：明确定义θ覆盖度和边际增益，公式严谨，算法简单高效。
3. **实验结果全面且优异**：在多个benchmark、多种模型、多种压缩率下一致超越SOTA，尤其在高压缩率下优势明显。
4. **无训练、即插即用**：适用于现有MLLM架构，无需额外训练成本，实际部署友好。
5. **可视化直观**：图5展示SCOPE在选择token时既保留高显著区域（如物体）又覆盖背景，比仅显著法更全面。
6. **鲁棒性分析**：超参数α实验（图6）表明默认α=1已接近最优，方法对参数不敏感。

## 8. 不足与局限

1. **实验模型范围有限**：主要基于LLaVA-1.5和LLaVA-Next系列，仅在附录中补充了Qwen2-VL。对更多MLLM（如InternVL、MiniGPT-4等）的泛化性未充分验证。
2. **评估指标局限性**：未报告多次运行的标准差或置信区间，缺乏统计显著性检验。部分benchmark（如POPE使用F1）可能掩盖细粒度差异。
3. **细粒度信息可能丢失**：极端压缩下（如保留8 token），尽管SCOPE优于对比方法，但仍存在性能损失，可能丢失对细粒度细节（如小物体、文字）的表示。
4. **计算开销**：虽然剪枝后推理加速，但剪枝过程本身需要计算全量token对的余弦相似度（O(N^2)），对于原始token数较大的情况（如视频多帧）可能产生额外开销。论文未详细讨论剪枝阶段的时间成本。
5. **未测试训练感知的剪枝**：SCOPE是推理时无训练方法，但能否与训练阶段联合优化或微调，论文未探讨。
6. **应用限制**：需获取CLS注意力分数和token嵌入，对不提供CLS token的视觉编码器（如某些ViT变体）可能不直接适用。
7. **冗余定义依赖相似度**：覆盖增益基于余弦相似度，假设语义空间是欧几里得结构，可能不完美反映真实语义关系。

（完）
