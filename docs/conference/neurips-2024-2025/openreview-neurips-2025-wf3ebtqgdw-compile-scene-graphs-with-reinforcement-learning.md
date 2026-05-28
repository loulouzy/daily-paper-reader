---
title: Compile Scene Graphs with Reinforcement Learning
title_zh: 基于强化学习的场景图编译
authors: "Zuyao Chen, Jinlin Wu, Zhen Lei, Marc Pollefeys, Chang Wen Chen"
date: 2025-04-18
pdf: "https://openreview.net/pdf?id=Wf3EbtqGdw"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型结合强化学习用于场景图生成
tldr: 本文针对多模态大语言模型在端到端结构化视觉表示提取中的不足，提出R1-SGG方法：先对M-LLM进行场景图数据的监督微调，再使用强化学习精炼，使模型能够准确生成对象及关系三元组。实验表明，RL阶段显著提升了场景图生成的精确性和结构一致性，为多模态LLM在视觉理解中的应用提供了新思路。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1245, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1409, \"height\": 1990, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1413, \"height\": 2015, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 1400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1394, \"height\": 2133, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wf3ebtqgdw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1345, \"height\": 2062, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wf3ebtqgdw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1158, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wf3ebtqgdw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1161, \"height\": 741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wf3ebtqgdw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1238, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wf3ebtqgdw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wf3ebtqgdw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 446, \"label\": \"Table\"}]"
motivation: 现有LLM难以端到端提取结构化视觉表示如场景图，需要生成三元组而非逐步文本。
method: 提出R1-SGG，先监督微调多模态LLM，再通过强化学习优化其场景图生成能力。
result: 在场景图生成基准上，RL精炼后的模型在准确性上超越纯监督方法。
conclusion: 强化学习可有效增强多模态LLM的结构化输出能力，推动视觉场景理解。
---

## Abstract
Next token prediction is the fundamental principle for training large language models (LLMs), 
and reinforcement learning (RL) further enhances their reasoning performance.
As an effective way to model language, image, video, and other modalities, 
the use of LLMs for end-to-end extraction of structured visual representations, such as scene graphs, remains underexplored.
It requires the model to accurately produce a set of objects and relationship triplets, rather than generating text token by token.
To achieve this, 
we introduce  R1-SGG, 
a multimodal LLM (M-LLM) initially trained via supervised fine-tuning (SFT) on the scene graph dataset and subsequently refined using reinforcement learning  to enhance its ability to generate scene graphs in an end-to-end manner.
The SFT follows a conventional prompt-response paradigm, 
while RL requires the design of effective reward signals. 
We design a set of graph centric rewards, including three recall based variants—Hard Recall, Hard Recall+Relax, and Soft Recall—which evaluate semantic and spatial alignment between predictions and ground truth at the object and relation levels.
A format consistency reward further ensures that outputs follow the expected structural schema.
Extensive experiments on the VG150 and PSG benchmarks show that R1-SGG substantially reduces failure rates and achieves strong performance in Recall and mean Recall, surpassing traditional SGG models and existing multimodal language models.

---

## 论文详细总结（自动生成）

# 论文总结：基于强化学习的场景图编译（R1-SGG）

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：场景图（Scene Graph）是一种结构化视觉表示，将图像中的对象及其关系组织为节点和边的有向图。传统场景图生成（SGG）方法通常将任务解耦为对象检测和关系识别两个子任务，依赖人工标注数据集，存在对长尾分布的过拟合、偏向头部谓词（如“on”“of”）等问题。
- **问题**：尽管多模态大语言模型（M-LLM）在视觉-语言理解上表现出色，但用于端到端提取结构化视觉表示（如场景图）的研究仍不充分。现有M-LLM在直接生成场景图时存在指令跟随失败（如输出缺少“objects”或“relationships”）、重复预测、位置不准确等问题。单纯使用监督微调（SFT）无法有效纠正这些结构错误，因为所有输出令牌在损失函数中被同等加权，缺乏针对场景图结构（如IoU、三元组匹配）的直接优化信号。
- **核心意义**：探索如何利用强化学习（RL）使多模态LLM具备生成准确、完整、结构有效的场景图的能力，推动结构化视觉理解的发展。

## 2. 方法论：核心思想、关键技术细节

### 2.1 整体框架：R1-SGG

- **两阶段训练**：
  - **阶段一：监督微调（SFT）**：在场景图数据集上采用常规的提示-响应对进行交叉熵损失训练，使模型学习输出格式和基础对象/关系识别。
  - **阶段二：强化学习（RL）**：使用Group Relative Policy Optimization（GRPO）算法对M-LLM进行在线策略优化，通过图中心奖励信号指导模型生成更准确的场景图。
- **基模型**：Qwen2-VL-2B/7B-Instruct。

### 2.2 奖励函数设计

论文设计了四种基于规则的奖励信号，包括一种格式奖励和三种图中心奖励变体。

- **格式一致性奖励**：检查输出是否遵循`<think>...</think><answer>...</answer>`格式，且`<answer>`段内包含“objects”和“relationships”关键词，符合则得1分，否则0分。
- **Hard Recall**（硬召回）：与标准SGDET评估指标对齐。一个预测的三元组`<subject, predicate, object>`被视为正确当且仅当：
  1. 主语、谓词、宾语标签与真实值完全匹配；
  2. 主语和宾语的边界框与真实框的IoU均大于0.5。
  优点：与评价指标对齐；缺点：奖励信号稀疏。
- **Hard Recall + Relax**（硬召回+放松）：放松标签精确匹配约束，用词嵌入的余弦相似度代替精确匹配，提供更多梯度信号。
- **Soft Recall**（软召回）：将节点匹配建模为二分图匹配问题（类似DETR），计算匹配后的节点奖励（对象类别相似度+IoU+边界框距离）和边奖励（subject/object/predicate嵌入相似度乘积），最终奖励为匹配节点/边奖励的平均值。

### 2.3 强化学习算法

采用GRPO（Group Relative Policy Optimization）：
- 对于每个输入图像，从旧策略`π_old`中采样G个候选输出`{o_i}`；
- 计算每个候选的优势值`A_i = (r_i - mean)/std`（组内归一化）；
- 优化目标包含裁剪的概率比和KL散度约束，防止策略更新过大。

## 3. 实验设计：数据集、基准、对比方法

### 3.1 数据集

- **VG150**：Visual Genome的子集，150个对象类别、50个关系类别，训练集56,224对、验证集5,000对。
- **PSG（Panoptic Scene Graph）**：基于COCO，80个“thing”类别、53个“stuff”类别、56个关系类别，训练集46,563对、测试集2,186对。

### 3.2 评估指标

- **SGDET协议**：模型直接从图像生成场景图，无预定义对象框。
  - Recall：预测的三元组中，主语和宾语框IoU≥0.5且三个标签均匹配的比例。
  - mRecall：按关系类别平均的Recall。
  - AP@50：对象检测的平均精度（IoU阈值0.5）。
  - Failure Rate：输出格式不合法或缺失关键字段的比例。

### 3.3 对比方法

- **传统SGG模型**：IMP、MOTIFS、VCTree、OvSGTR、GPSNet、PSGFormer等。
- **商业M-LLM**：GPT-4o、Gemini 1.5 Flash、Gemini 2.0 Flash。
- **开源M-LLM**：LLaVA v1.5 (7B)、Qwen2-VL-2B/7B-Instruct、TextPSG、ASMv2 (13B)、LLaVA-SpaceSGG (13B)。
- **本方法变体**：R1-SGG-Zero（仅RL无SFT）、R1-SGG（SFT+RL）。

### 3.4 主要实验结果

- **VG150验证集**（表1）：
  - R1-SGG (7B) 达到 Failure Rate 0.08%、AP@50 19.47、Recall 23.75%、mRecall 11.43%，显著优于纯SFT模型和所有零样本M-LLM。
  - RL大幅降低Failure Rate（SFT 7B：39.54% → R1-SGG 7B：0.08%）。
  - 相比传统SGG模型（如MOTIFS Recall 27.21%），R1-SGG的Recall略低但mRecall更高（11.43% vs 7.84%），说明生成的场景图更少偏向头类。
- **PSG测试集**（表2）：
  - R1-SGG (7B) 达到 Failure Rate 0%、AP@50 42.05、Recall 43.48%、mRecall 33.71%，大幅超越所有基线。
- **跨数据集泛化**（表3）：
  - SFT存在强领域特异性（VG150训练的模型在PSG上Recall仅3.03%）；R1-SGG-Zero（无SFT）跨域泛化更鲁棒。
  - RL初始化使用SFT检查点优于零样本RL。

## 4. 资源与算力

- **SFT阶段**：4块NVIDIA A100 (80GB) GPU，训练3个epoch，batch size 128，学习率1e-5，优化器AdamW。
- **RL阶段**：16块NVIDIA GH200 (120GB) GPU，训练1个epoch，batch size 32，每个样本生成8个候选（group size=8），学习率6e-7。
- 未明确报告总训练时长，但提供了分布式的配置细节。

## 5. 实验数量与充分性

- **核心实验**：VG150和PSG两大数据集上的SGDET性能对比，覆盖传统方法、商业/开源M-LLM、本方法变体。
- **消融实验**（表4）：
  - 比较三种奖励变体（Hard Recall、Hard Recall+Relax、Soft Recall），结论是Hard Recall最优，说明与评价指标对齐比奖励平滑更重要。
- **超参数分析**（图5）：
  - KL正则化：移除KL分化可进一步降低Failure Rate，但可能损失稳定性。
  - 采样长度：1024 vs 2048，未带来提升。
  - Group size：8 vs 16，增加组大小稳定训练，但计算成本更高。
- **VQA关系推理能力评估**（表7）：对比四种M-LLM在不同视觉/文本变体下的表现，显示M-LLM在视觉关系推理上的局限性。
- **定性结果**（图6、图7）：展示不同方法生成场景图的差异，体现RL+RL结合带来的质量提升。
- **长尾分析**：图3、图4展示头/尾谓词的Recall，证明R1-SGG显著提升尾类性能。
- **充分性评价**：实验设计较为全面，覆盖了多种基线、多个数据集、奖励消融、超参数分析、跨域泛化、定性可视化，足以支撑主要结论。但缺少标准误差/置信区间报告，且仅做了单次运行（未明确说明随机种子或重复实验），可重复性略受影响。

## 6. 主要结论与发现

1. **强化学习显著提升M-LLM的场景图生成能力**：RL将Failure Rate从SFT的~40%降至接近0%，并大幅提升Recall和mRecall。
2. **SFT+RL优于仅SFT或仅RL**：R1-SGG（结合SFT+RL）在多数指标上优于R1-SGG-Zero（仅RL），说明SFT提供了良好的初始化。
3. **奖励函数设计至关重要**：Hard Recall虽然稀疏但与评价指标对齐，效果最好；Soft Recall等密集奖励反而导致mRecall下降。
4. **模型规模优势**：7B模型全面优于2B模型。
5. **跨域泛化**：SFT模型在域外表现差，而RL模型（R1-SGG-Zero）泛化更强；提示中包含预定义类别可改善开放集场景下的表现。
6. **M-LLM在视觉关系推理上存在固有困难**：VQA实验显示即使简单的关系选择任务，M-LLM也容易受文本偏置影响。

## 7. 优点

1. **创新性**：首次探索使用RL训练多模态LLM以端到端方式生成场景图，填补了该方向空白。
2. **奖励设计巧妙**：提出三种图中心奖励变体，尤其是Hard Recall直接对齐评估指标，且设计了格式奖励保证结构化输出。
3. **性能提升显著**：在VG150和PSG上均大幅降低Failure Rate（降至接近0%），且Recall/mRecall显著超过传统SGG模型和已有的M-LLM方法。
4. **消融系统完整**：对奖励、KL、采样长度、group size、预定义类别等多个因素进行了深入分析。
5. **开源意愿**：承诺释放代码和模型，有利于社区复现和进一步研究。

## 8. 不足与局限

1. **未报告统计显著性**：实验均为单次运行，未提供误差棒或置信区间，结果稳定性存疑。
2. **计算资源消耗较大**：RL阶段需要16块GH200 GPU，每个样本采样多个候选，训练成本高，可能限制在资源受限场景的实用性。
3. **跨域泛化仍有限**：虽然RL模型泛化强于SFT，但跨数据集性能仍远低于同域训练的结果，提示领域适应问题未根本解决。
4. **对“思考”过程的利用不充分**：论文尝试使用`<think>`标签引导推理链（CoT），但模型难以生成有效思考过程，说明仅靠规则奖励不足以诱导复杂推理。
5. **商业模型对比不公平**：GPT-4o等闭源模型在零样本下表现极差，但无法排除其内部拒绝机制或安全策略的影响。
6. **语义理解粒度有限**：Soft Reward依赖SpaCy嵌入，可能无法捕获细粒度语义差异；Hard Reward无法处理同义词或语义等价的表述。
7. **缺少现实应用场景测试**：仅实验在VG150和PSG上，未在机器人操作、导航等下游任务中验证实用性。

（完）
