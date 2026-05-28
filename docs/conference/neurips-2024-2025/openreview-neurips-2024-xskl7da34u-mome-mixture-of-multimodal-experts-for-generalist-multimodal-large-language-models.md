---
title: "MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models"
title_zh: MoME：面向通用多模态大语言模型的多模态专家混合
authors: "Leyang Shen, Gongwei Chen, Rui Shao, Weili Guan, Liqiang Nie"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Xskl7Da34U"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 提出多模态专家混合架构以实现通用多模态大语言模型
tldr: 该论文针对通用多模态大语言模型（MLLM）在不同任务间存在干扰从而导致性能不及专用模型的问题，提出了多模态专家混合（MoME）架构。MoME包含视觉专家混合（MoVE）和语言专家混合（MoLE）两部分，MoVE自适应调整来自多个视觉编码器的特征，MoLE通过稀疏门控在语言模型中引入专家。实验表明，MoME在不增加额外参数负担的同时，显著缓解了任务干扰，使通用MLLM在多项视觉语言任务上达到甚至超越专用模型水平。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 949, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 507, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xskl7da34u/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1725, \"height\": 2331, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xskl7da34u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1369, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xskl7da34u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1101, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xskl7da34u/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xskl7da34u/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1324, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xskl7da34u/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1511, \"height\": 1027, \"label\": \"Table\"}]"
motivation: 通用多模态大语言模型因任务干扰而性能低于专用模型。
method: 设计视觉专家混合和语言专家混合模块，通过自适应特征调制和稀疏门控减轻任务干扰。
result: 在多项视觉语言任务上，通用MLLM性能超越专用模型。
conclusion: 专家混合策略可有效提升MLLM的通用性而无额外开销。
---

## Abstract
Multimodal large language models (MLLMs) have demonstrated impressive capabilities across various vision-language tasks. However, a generalist MLLM typically underperforms compared with a specialist MLLM on most VL tasks, which can be attributed to task interference. In this paper, we propose a mixture of multimodal experts (MoME) to mitigate task interference and obtain a generalist MLLM. Our MoME is composed of two key components, a mixture of vision experts (MoVE) and a mixture of language experts (MoLE). MoVE can adaptively modulate the features transformed from various vision encoders, and has a strong compatibility in transformation architecture. MoLE incorporates sparsely gated experts into LLMs to achieve painless improvements with roughly unchanged inference costs. In response to task interference, our MoME specializes in both vision and language modality to adapt to task discrepancies. Extensive experiments show that MoME significantly improves the performance of generalist MLLMs across various VL tasks.

---

## 论文详细总结（自动生成）

# 论文总结：MoME: Mixture of Multimodal Experts for Generalist Multimodal Large Language Models

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：通用多模态大语言模型（MLLM）在训练过程中面临**任务干扰（task interference）**问题，即同时学习多个视觉-语言（VL）任务时，模型性能往往低于针对单一任务训练的专用模型。作者通过统计可视化发现，不同VL任务在视觉模态和语言模态的特征分布存在显著差异，而现有工作仅关注语言模态的任务差异（如LLM中的混合专家MoE），忽视了视觉模态同样重要的任务干扰。
- **核心含义**：提出**MoME（混合多模态专家）**架构，同时在视觉编码器和语言模型端引入专家混合机制，动态适应不同任务的需求，从而缓解任务干扰，使通用MLLM在多个VL任务上达到甚至超越专用模型水平。

## 2. 方法论

- **核心思想**：通过两个模块分别处理视觉和语言模态的任务差异：
  - **视觉专家混合（MoVE）**：融合多个异构视觉编码器（CLIP-ViT、DINOv2、Pix2Struct）的特征，利用可变形注意力对齐特征并自适应聚合。
  - **语言专家混合（MoLE）**：在LLM的每个FFN层并行插入多个轻量低秩适配器（adapter），通过稀疏门控选择最适配的专家。

- **关键技术细节**：
  - **自适应可变形变换（ADT）**：对每个视觉编码器的特征图进行2D自适应平均池化得到粗特征，然后通过可变形交叉注意力（Deformable Attention）从原始特征图中采样细粒度信息，输出统一长度（L）的特征序列。公式：  
    \(\hat{f} = D^M(D(f), f)\)，其中 \(D\) 为可变形层，包含自注意力、可变形交叉注意力和FFN。
  - **实例级软路由器（MoVE路由器）**：基于指令的句子嵌入（Sentence-BERT），通过MLP和SoftMax生成融合权重，加权求和各视觉专家的特征：  
    \(F = \sum_{i=1}^N G_s(I)_i \times \hat{f}_i\)。
  - **MoLE模块**：每个FFN层并行多个低秩适配器（bottleneck结构：down-projection → ReLU → up-projection，输出乘以可学习标量\(s\)）。基于句子嵌入的稀疏路由器（top-1门控）选择激活一个适配器：  
    \(o = \sum_{k=1}^K G_h(I)_k \times y_k\)，其中\(y_k\)为第k个适配器的输出。

- **训练流程**：两阶段训练。第一阶段训练MoVE + 单个适配器；第二阶段加载第一阶段检查点，复制适配器权重初始化MoLE，保持其他参数不变。

## 3. 实验设计

- **数据集与场景**：收集24个数据集，划分为四个任务组：
  - **通用（General）**：COCOCap、Flickr30K、NoCaps、OKVQA、AOKVQA、GQA、VSR、IconQA
  - **REC（指代表达理解）**：RefCOCO、RefCOCO+、RefCOCOg
  - **REG（指代表达生成）**：RefCOCO、RefCOCO+、RefCOCOg
  - **文档（Document）**：ChartQA、TabFact、DeepForm、DocVQA、InfographicsVQA、WikiTableQuestions、TextCaps、TextVQA
- **评估指标**：按各数据集标准指标（Accuracy、CIDEr、ANLS等），按组取平均。
- **对比方法**：与主流MLLM（如Shikra、Ferret、InstructBLIP、LLaVA-v1.5、LION、DocPedia、MoE-LLaVA、MixLoRA、MoCLE、LLaVA-MoLE）在相似资源消耗下进行比较。

## 4. 资源与算力

- 论文明确说明：使用 **单节点8×A800 80GB GPU**，整个训练（包括第一阶段和第二阶段）在 **一天内完成**。
- 训练细节：第一阶段30k步，batch size 64，学习率预热后余弦衰减；第二阶段基于第一阶段检查点微调MoLE。

## 5. 实验数量与充分性

- **主要实验组数**：
  - **MoVE消融实验**：6组（单编码器基线3组 + 不同聚合策略3组），验证ADT和路由器的有效性。
  - **MoLE消融实验**：8组（不同路由器输入、负载均衡策略、与MoVE联合），验证最佳配置。
  - **与SOTA对比**：在12个数据集上对比了9种方法，覆盖所有四个任务组。
  - **路由结果可视化**：展示MoVE和MoLE在不同任务上的专家选择分布。
  - **额外消融**：可变形机制的有无对比（附录表4）。
- **充分性与公平性**：
  - 消融实验全面，分别拆解了MoVE和MoLE各组件的贡献。
  - 对比方法均采用公开结果或官方实现，且控制资源消耗相近。
  - 所有实验基于统一的数据划分和评估指标，保障公平。
- 未报告误差棒（如多次重复），但MLLM领域通常如此，可接受。

## 6. 主要结论与发现

- MoVE和MoLE单独都能提升性能，两者结合（MoME）达到最佳。
- MoVE中ADT比简单平均池化+加法平均提升约4个点，路由器比加法平均提升约6.5个点。
- MoLE使用基于句子嵌入的路由器优于基于token或混合输入，且无需额外负载均衡策略。
- 路由可视化表明：各专家在训练后自发地针对不同任务组产生专业化分工（如Pix2Struct主导文档任务，DINOv2主导REC任务，CLIP主导通用任务）。
- MoME在多个数据集上超越现有通用MLLM和MoE变体，尤其在TextCaps、Flickr30K、IconQA上表现突出。

## 7. 优点

- **创新性**：首次同时考虑视觉和语言模态的任务差异，设计双模态专家混合，突破了仅关注语言专家的局限。
- **高效性**：MoLE使用低秩适配器作为专家，在几乎不增加推理成本的前提下提升性能；ADT通过可变形注意力高效对齐异构特征。
- **可解释性**：通过路由分布的可视化，清晰展示专家自动适应任务，提供对模型行为的深入理解。
- **实验全面**：覆盖24个数据集、4个任务组，消融实验细致，对比方法多且公平。

## 8. 不足与局限

- **计算资源限制**：作者承认受限于计算资源，未能在更大规模数据或多模态（如音频、视频）上进行实验。
- **专家数固定**：MoVE使用三个固定视觉编码器，未探索更多或更优的视觉专家组合。
- **未报告统计误差**：缺乏多次重复实验的误差棒，结果可能存在随机波动。
- **仅评估视觉-语言任务**：未扩展到其他多模态场景（如图文检索、视觉推理等），通用性验证不够广泛。
- **依赖预训练LLM**：性能受基础LLM（Vicuna-7B）能力上限影响，未尝试更大规模LLM。

（完）
