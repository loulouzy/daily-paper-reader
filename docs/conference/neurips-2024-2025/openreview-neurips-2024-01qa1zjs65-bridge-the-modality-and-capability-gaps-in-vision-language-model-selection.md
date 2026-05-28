---
title: Bridge the Modality and Capability Gaps in Vision-Language Model Selection
title_zh: 弥合视觉语言模型选择中的模态与能力差距
authors: "Chao Yi, Yuhang He, De-Chuan Zhan, Han-Jia Ye"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=01qa1ZJs65"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型选择
tldr: 视觉语言模型在零样本分类中表现优异，但如何从众多预训练VLM中选择最合适的模型是难题。本文分析了语言-only VLM选择中的模态差距和能力评估问题，提出弥合这些差距的方法。实验表明仅凭文本数据即可有效预测VLM性能，为VLM复用提供指导。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1368, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1367, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1016, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1398, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-01qa1zjs65/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1396, \"height\": 572, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 685, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 713, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 688, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 706, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 682, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 1287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1459, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-01qa1zjs65/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 326, \"label\": \"Table\"}]"
motivation: 从大量预训练VLM中选择适合任务的模型缺乏有效方法。
method: 分析模态差距和能力评估挑战，设计基于文本数据的选择策略。
result: 提出的选择方法在多个分类任务上准确筛选出最佳VLM。
conclusion: 仅依赖文本数据可有效实现VLM选择，降低对目标图像的需求。
---

## Abstract
Vision Language Models (VLMs) excel in zero-shot image classification by pairing images with textual category names. The expanding variety of Pre-Trained VLMs enhances the likelihood of identifying a suitable VLM for specific tasks. To better reuse the VLM resource and fully leverage its potential on different zero-shot image classification tasks, a promising strategy is selecting appropriate Pre-Trained VLMs from the VLM Zoo, relying solely on the text data of the target dataset without access to the dataset’s images. In this paper, we analyze two inherent challenges in assessing the ability of a VLM in this Language-Only VLM selection: the “Modality Gap”—the disparity in VLM’s embeddings across two different modalities, making text a less reliable substitute for images; and the “Capability Gap”— the discrepancy between the VLM’s overall ranking and its ranking for target dataset, hindering direct prediction of a model’s dataset-specific performance from its general performance. We propose VLM Selection With gAp Bridging (SWAB) to mitigate the negative impact of two gaps. SWAB first adopts optimal transport to capture the relevance between open-source and target datasets with a transportation matrix. It then uses this matrix to transfer useful statistics of VLMs from open-source datasets to the target dataset for bridging two gaps. By bridging two gaps to obtain better substitutes for test images, SWAB can accurately predict the performance ranking of different VLMs on the target task without the need for the dataset’s images. Experiments across various VLMs and image classification datasets validate SWAB’s effectiveness. Code is available at: https://github.com/YCaigogogo/SWAB.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

视觉语言模型（VLM）在零样本图像分类中表现出色，但不同VLM在不同数据集上的性能差异巨大。随着预训练VLM数量激增，如何从“VLM动物园”（VLM Zoo）中为特定目标任务选出最合适的模型成为一个关键问题。实际场景中，用户往往没有目标数据集的图像（例如非机器学习研究者），只能通过文本描述任务需求。因此，本文聚焦于**语言仅VLM选择（Language-Only VLM Selection, LOVM）**——仅利用目标数据集的文本数据（如类名和LLM生成的辅助文本）来预测各VLM在目标数据集上的性能排名，从而选出最佳模型。

论文识别并分析了该任务中两个固有挑战：
- **模态差距（Modality Gap）**：VLM提取的图像特征和文本特征在特征空间中形成两个分离的簇，直接用文本数据作为图像代理估算模型性能会引入较大偏差。
- **能力差距（Capability Gap）**：一个VLM在不同数据集上的性能排名变化很大，其整体平均排名无法反映在特定目标数据集上的排名，因此依赖通用能力排名进行选择不可靠。

## 2. 方法论

### 核心思想
利用开源数据集中可计算的VLM统计量（类别级模态差距向量、类别级排名），通过最优运输（Optimal Transport）建立开源数据集类别与目标数据集类别之间的语义相关性矩阵，将统计量从开源数据集迁移到目标数据集，从而同时弥合模态差距和能力差距，最终实现仅基于文本的准确VLM排名预测。

### 关键技术细节
1. **构建运输矩阵**  
   - 使用预训练文本编码器（如MPNet）提取开源数据集类别名和目标数据集类别名的文本特征。
   - 计算余弦相似度得到成本矩阵：`cost_ij = 1 - cos_sim(ϕ(cS_i), ϕ(cT_j))`，并做指数放大。
   - 求解最优运输问题，得到运输矩阵γ* ∈ R^{kS×kT}，其中γ*_ij表示开源类别i对目标类别j的相关权重。

2. **弥合模态差距**  
   - 在开源数据集上，对每个VLM每个类别计算平均模态差距向量：`gS_m,k = mean( fI(x)/||fI(x)|| - fT(cS_k)/||fT(cS_k)|| )`。
   - 通过运输矩阵估计目标数据集每个类别的差距向量：`ĝT_m,j = |CT| * (γ*_{:,j})^T * GS_m`。
   - 将估计的差距向量加到ChatGPT生成的辅助文本特征上，得到修正后的文本特征，作为更好的图像代理。
   - 使用修正后的文本特征计算ModelGPT中的多种指标（如Top-1准确率、Fisher准则等），输入到学习好的排名器（ranker model）中获得第一个排名预测 ˆrT,(1)_m。

3. **弥合能力差距**  
   - 在开源数据集的每个类别上，计算各VLM的零样本分类准确率排名，得到类别级排名矩阵 rS_m ∈ ℤ^{kS}。
   - 利用运输矩阵加权求和，预测目标数据集上每个类别的VLM排名：`ˆrT_m = rS_m * γ*`（结果向量长度kT）。
   - 对目标数据集所有类别取平均，得到第二个排名预测 ˆrT,(2)_m。

4. **集成最终排名**  
   使用加权Borda Count融合两个排名：`ˆrT,ens_m = α * ˆrT,(1)_m + (1-α) * ˆrT,(2)_m`，其中α=0.5。

## 3. 实验设计

### 数据集与Benchmark
- 遵循LOVM [73] 提供的基准，包含23个图像分类数据集：ImageNet, SUN397, Country211, Stanford Cars, Flowers102, CIFAR100, DTD, RESISC45, GTSRB, Oxford Pets, VOC2007, STL10, EuroSAT, MNIST, SVHN, CLEVR-C, CLEVR-D, FER2013, DMLab, Retinopathy, KITTI, PCam, Rendered SST2 等，覆盖自然图像、卫星、OCR、医学等多种领域。
- VLM Zoo：原35个模型 + 额外加入BLIP和BEiT-3的变体，共43个预训练VLM，差异覆盖架构（ResNet, ViT, ConvNeXt, CoCa等）、预训练数据集（OpenAI WIT, LAION-400M/2B等）、训练方法。
- 评估指标：Top-5 Recall (R5) 和 Kendall's Rank Correlation (τ)，以及两者的和R5+τ。

### 对比方法
- 非学习方法：H-Score, NCE, LEEP, LogME（基于生成文本计算迁移性指标）。
- 基于通用能力的方法：ImageNet上的排名（INB）、平均排名（Avg Rank）。
- 学习方法：ModelGPT（[73]）。
- 消融变体：SWAB-C（仅弥合能力差距）、SWAB-M（仅弥合模态差距）、完整SWAB。

## 4. 资源与算力

论文**未明确说明**使用的GPU型号、数量及训练时长。仅在附录提到使用CPU计算最优运输（因现有工具包多在CPU上运行）。由于实验涉及43个VLM在23个数据集上的零样本评估以及排名器训练，推测需要一定GPU资源（如单卡或少量卡），但作者未披露具体硬件配置。

## 5. 实验数量与充分性

- **主要实验**：在43个VLM×23个数据集上评估，共989个评价（Table 1），对比7种基线方法。
- **消融实验**（Table 2）：验证弥合每个差距的必要性。
- **组件分析**（Table 3-6）：包括能力差距桥接有效性、模态差距桥接有效性、类级 vs 数据集级差距向量选择、数据标准化影响等。
- **附加实验**：在原始35个VLM上重复实验（Table 9），结果趋势一致。
- **每个数据集的表现**（Table 10）：逐数据集对比SWAB与ModelGPT的R5和τ。
- **可视化验证**（Figure 4）：展示模态差距桥接后文本特征与真实图像特征一致性提升；UMAP和相似度分布图（Appendix E.2）验证BLIP/BEiT-3也存在模态差距。

**充分性与客观性评价**：实验设计较为全面，覆盖多种VLM和数据分布，消融和组件分析充分，多次重复实验报告均值和标准差，结果统计显著且可复现。但缺乏在更极端领域（如医学、遥感）的单独详细分析，且依赖ChatGPT生成文本的质量未做鲁棒性测试。

## 6. 主要结论与发现

1. 传统的非学习迁移性指标（H-Score等）在LOVM中表现极差，表明直接使用生成文本无法有效反映VLM的零样本分类能力。
2. 仅基于VLM通用能力（如ImageNet排名或平均排名）的选择方法效果有限，证实了能力差距的存在。
3. SWAB通过同时弥合模态差距和能力差距，在所有评估指标上显著优于现有最佳方法ModelGPT（R5+τ从0.716提升至0.822，提升14.8%）。
4. 类级模态差距向量比数据集级差距向量更一致，使用类级差距向量能带来更好的效果。
5. 最优运输矩阵能有效捕捉开源和目标数据集间的类别语义相关性，是实现统计量迁移的关键桥梁。

## 7. 优点

- **问题定义清晰**：首次系统性地将LOVM中两个核心差距（模态差距、能力差距）分离出来并给出定量分析。
- **方法创新**：将最优运输引入VLM选择任务，优雅地解决了跨数据集类别语义对齐和统计量迁移问题。
- **完全无图像依赖**：所选方法完全不需要目标数据集的图像，仅靠文本和开源数据即可得到可靠的排名，具有实际应用价值。
- **实验充分**：在大型VLM Zoo和多样化数据集上验证，结果稳健，消融实验与组件分析支撑核心方法。
- **代码开源**：提供完整的代码仓库，便于复现和扩展。

## 8. 不足与局限

- **依赖LLM生成的文本质量**：方法依赖ChatGPT生成辅助文本，若生成文本与目标领域不符或质量差，可能影响模态差距估计效果。论文未评估不同LLM或生成策略的鲁棒性。
- **开源数据集覆盖有限**：开源数据集仅包含23个分类数据集，若目标任务与这些数据集语义分布差异极大（如高度专业化的医学图像），运输矩阵可能难以有效迁移。
- **计算开销**：求解最优运输（尤其是当开源类别数量较大时）需要一定时间，且需为每个目标数据集重新计算运输矩阵；排名器训练也需遍历VLM在开源数据集上的零样本评估（43×23次）。
- **未处理极端情况**：文中提到对于某些数据集（如CLEVR、KITTI等）R5和τ为0，说明方法在某些任务上完全失效，论文未深入分析原因。
- **未探讨排名器泛化性**：ModelGPT的排名器在开源数据集上训练后直接用于目标数据集，若目标数据集与开源数据集分布差异大，排名器可能产生偏差。SWAB部分缓解了该问题，但仍未完全消除。
- **未考虑计算资源**：论文未报告训练和推理的硬件成本，不利于实际应用中的资源规划。

（完）
