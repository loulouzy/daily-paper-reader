---
title: "Reliable Lifelong Multimodal Editing: Conflict-Aware Retrieval Meets Multi-Level Guidance"
title_zh: 可靠的多模态终身编辑：冲突感知检索与多级指导
authors: "Qiang Zhang, Fanrui Zhang, Jiawei Liu, Ming Hu, Junjun He, Zheng-Jun Zha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=hdJXzKZjY9"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型编辑
tldr: 多模态大语言模型（MLLM）需要持续的知识编辑以应对动态信息，但现有方法在精确检索和多级协调方面存在不足。本文提出CARML框架，通过引入模态内不确定性和模态间冲突量化进行动态检索，并结合多级隐式和显式指导实现可靠编辑。该方法提升了编辑的准确性和可靠性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1423, \"height\": 1062, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 655, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 316, \"label\": \"Table\"}]"
motivation: MLLM需持续知识更新，但现有编辑方法在检索精度和协调编辑方面效果不佳。
method: 提出CARML框架，包含冲突感知动态检索和多级隐式/显式指导，实现可靠的多模态编辑。
result: 实验证明该方法在终身编辑场景下优于现有方法，具有更高的可靠性。
conclusion: CARML为MLLM的持续知识更新提供了可靠方案。
---

## Abstract
The dynamic nature of real-world information demands efficient knowledge editing in multimodal large language models (MLLMs) to ensure continuous knowledge updates. However, existing methods often struggle with precise matching in large-scale knowledge retrieval and lack multi-level guidance for coordinated editing, leading to less reliable outcomes. To tackle these challenges, we propose CARML, a novel retrieval-augmented editing framework that integrates conflict-aware dynamic retrieval with multi-level implicit and explicit guidance for reliable lifelong multimodal editing. Specifically, CARML introduces intra-modal uncertainty and inter-modal conflict quantification to dynamically integrate multi-channel retrieval results, so as to pinpoint the most relevant knowledge to the incoming edit samples. Afterwards, an edit scope classifier discerns whether the edit sample semantically aligns with the edit scope of the retrieved knowledge. If deemed in-scope, CARML refines the retrieved knowledge into information-rich continuous prompt prefixes, serving as the implicit knowledge guide. These prefixes not only include static knowledge prompt that capture key textual semantics but also incorporate token-level, context-aware dynamic prompt to explore fine-grained cross-modal associations between the edit sample and retrieved knowledge. To further enhance reliability, CARML incorporates a "hard correction" mechanism, leveraging explicit label knowledge to adjust the model’s output logits. Extensive experiments across multiple MLLMs and datasets indicate the superior performance of CARML in lifelong multimodal editing scenarios.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在动态现实世界中需持续更新知识，但现有知识编辑方法在大规模知识检索中难以精确匹配，且缺乏多级协调指导，导致编辑结果不可靠。
- **背景**：
  - MLLMs（如BLIP-2、LLaVA）广泛用于视觉-语言任务，但其静态知识难以适应持续变化的信息环境。
  - 知识编辑技术可高效更新模型知识，避免重训练成本，但现有方法多针对单次或批量编辑，在终身编辑（lifelong editing）场景下易出现灾难性遗忘。
  - 已有检索增强方法（如SERAC、RECIPE、LiveEdit）虽能避免直接修改参数，但随着编辑知识库增长，检索精度下降，且仅使用单类型知识，缺乏多级知识协同指导。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
提出**CARML**（Conflict-Aware Retrieval meets Multi-Level guidance），一种检索增强的终身多模态编辑框架，通过**冲突感知动态检索**和**多级隐式+显式指导**实现可靠编辑。

### 关键技术细节

#### (1) 冲突感知动态检索（Conflict-Aware Dynamic Retrieval）
- **知识库构建**：为每个历史编辑请求存储视觉、文本、多模态三种嵌入（通过预训练多模态嵌入模型提取）。
- **多通道检索**：对新编辑样本，分别计算其视觉、文本、多模态嵌入与知识库中对应模态的余弦相似度，得到三个相似度分数向量。
- **冲突感知融合与重排序**：
  - 计算各模态相似度向量的信息熵（**模态内不确定性**）。
  - 计算各模态Top-K候选集合间的Jaccard相似度，定义**模态间冲突度**。
  - 基于不确定性及冲突度，动态为各模态分配权重（式5），加权融合得到最终相似度分数，选出最相关知识条目。
- **编辑范围分类器**：使用两个可训练MLP将编辑样本查询嵌入与检索知识嵌入映射到新语义空间，计算余弦相似度，若超过阈值β则判定为“在范围内”，触发后续编辑；否则跳过。分类器使用Focal Loss训练，正样本为可靠性/泛化性样本，负样本为局部性样本。

#### (2) 多级知识指导（Multi-Level Knowledge Guidance）
- **隐式指导：静态+动态提示**：
  - **静态知识提示**：将检索知识的文本嵌入通过MLP映射为固定长度的连续提示前缀，捕捉核心语义。
  - **上下文感知动态提示**：将检索知识的视觉和多模态嵌入也映射为提示，再通过**token级注意力融合**，以编辑样本嵌入为查询，动态融合三种模态提示的每个token，生成上下文相关动态提示。
  - 最终将静态提示、动态提示、原始图像/文本嵌入拼接输入MLLM。
- **显式指导：输出Logits增强**：
  - 计算MLLM输出概率分布与检索知识中理想标签的负对数相似度，若低于阈值η，则将理想标签对应位置的logits值加1（硬纠正），增强正确输出概率。

#### (3) 训练目标
总损失 = 编辑损失（可靠性+泛化性+局部性的负对数似然/KL散度） + λ×范围分类器损失，核心MLLM参数冻结，仅优化分类器和提示生成模块。

## 3. 实验设计

### 数据集与场景
- **MMEdit基准**：包含**E-VQA**（视觉问答编辑）和**E-IC**（图像描述编辑）两个子任务。
- **VLKEB数据集**：使用真实世界图像，基于多模态知识图谱构建，更贴近实际场景。
- **跨任务编辑**：将E-VQA和E-IC混合进行连续编辑，评估模型同时处理多任务的能力。

### 对比方法
- **FT-L**：微调MLLM最后一层。
- **TP**：内在知识编辑，注入可训练神经元。
- **MEND**：基于元学习的超网络梯度变换。
- **SERAC**：基于外部记忆的编辑，使用范围分类器。
- **LEMoE**：混合专家适配器。
- **RECIPE**：检索增强的连续提示学习。
- **LiveEdit**：专为MLLM设计的终身编辑方法，使用低秩专家路由。

### 评估指标
可靠性（Reliability）、泛化性（T-Generality、M-Generality）、局部性（T-Locality、M-Locality），准确率度量。

### 实验设置
- 两种基础MLLM：**BLIP-2 OPT (2.7B)** 和 **LLaVA-V1.5 (7B)**。
- 编辑数量T=1,100,1000，模拟终身编辑规模增长。
- 多模态嵌入模型：mexma-siglip2。
- 提示长度r=4，阈值β（E-IC:0.4, E-VQA/VLKEB:0.7），logits增强阈值η=6，损失权重λ=0.04。

## 4. 资源与算力

- **文中明确说明**：所有实验在**单个NVIDIA H100 GPU**上运行。
- 训练参数：Adam优化器，batch size=8，学习率1e-5，epoch数=120。
- 未明确提及总训练时长，但指出推理过程（包括单次编辑延迟和连续编辑后推理时间）在对比中进行了成本分析（图3(b)）。

## 5. 实验数量与充分性

- **实验组数**：
  - 主实验结果：在3个数据集×2种模型×3种编辑规模（T=1,100,1000）下共18个主要表格（表1-3）。
  - 跨任务编辑结果（表4）：在BLIP-2上混合1000次编辑。
  - 消融实验（表5）：在E-IC 1000次编辑下逐步替换组件，检验检索、分类器、动态提示、logits增强的效果。
  - 可视化分析（图3(a)）：t-SNE展示类别器语义空间；图3(b)展示准确率与时间权衡。
  - 附录中附加了平均结果表（表6）和可视化样例。
- **充分性与公平性**：
  - 覆盖了主流内在编辑、外部记忆、专用终身编辑等方法，对比全面。
  - 消融实验系统地验证了每个组件的贡献。
  - 实验设置（学习率、batch size、epoch等）在附录中给出，可复现。
  - 所有实验在同一GPU环境下执行，公平性较好。
  - 但未报告误差棒或统计显著性检验，可能影响结果稳定性认知。

## 6. 论文的主要结论与发现

- CARML在几乎所有设置下（3个数据集、2种模型、T=1/100/1000）均显著优于所有基线方法，尤其在T=1000时仍保持接近100%的可靠性、泛化性和局部性，而其他方法性能急剧下降。
- 消融实验证明冲突感知动态检索、编辑范围分类器、上下文感知动态提示、输出logits增强各组件均有效，其中检索和logits增强对可靠性提升最大。
- t-SNE可视化显示编辑范围分类器能有效区分范围内外样本，保障局部性。
- 在准确率与时间权衡上，CARML实现了高精度与低延迟的平衡。

## 7. 优点

- **方法创新**：
  - 首次将模态内不确定性和模态间冲突度引入检索融合，实现自适应精准定位。
  - 多级指导结合隐式（静态+动态提示）和显式（logits硬纠正），从“软提示”到“硬调整”增强编辑可靠性。
  - 编辑范围分类器巧妙利用语义距离过滤无关样本，保护模型原始能力。
- **实验全面**：覆盖多个数据集、两种主流MLLM、多种编辑规模，并与7种基线对比，消融清晰，可视化支撑机理。
- **实践实用性**：在相同算力下效率高，适合终身编辑场景。

## 8. 不足与局限

- **泛化能力有限**：当前实验限于VQA和图像描述任务，对复杂常识推理、多轮对话等抽象编辑场景未经测试。
- **模型规模受限**：仅评估了2.7B和7B的MLLM，未验证在更大模型（如InternVL2.5-78B）上的适应性（受限于计算资源）。
- **未报告统计显著性**：缺少多次运行的平均值和标准差，可能无法充分反映方法稳定性。
- **显式logits增强依赖检索精度**：若检索失败（虽概率低），硬纠正可能引入错误。
- **阈值依赖性**：分类器阈值β和logits阈值η需针对不同任务手动调节，泛化性有待检验。

（完）
