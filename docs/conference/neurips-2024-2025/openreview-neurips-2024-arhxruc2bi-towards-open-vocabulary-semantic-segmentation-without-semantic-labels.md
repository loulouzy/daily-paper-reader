---
title: Towards Open-Vocabulary Semantic Segmentation Without Semantic Labels
title_zh: 无需语义标签的开放词汇语义分割
authors: "Heeseong Shin, Chaehyun Kim, Sunghwan Hong, Seokju Cho, Anurag Arnab, Paul Hongsuck Seo, Seungryong Kim"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=aRhxruC2bi"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 视觉语言模型论文：适配CLIP进行开放词汇语义分割
tldr: 大规模视觉语言模型（如CLIP）在图像级任务表现出色，但缺乏像素级理解能力。本文提出PixelCLIP，利用无标注图像和SAM/DINO生成的分割掩码，通过在线聚类学习通用语义概念，将CLIP适配到语义分割任务。方法无需语义标签即可实现开放词汇分割。实验在多个基准上达到竞争性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1256, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1422, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1275, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-arhxruc2bi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 585, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 766, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 698, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 638, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 699, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 702, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-arhxruc2bi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 699, \"height\": 182, \"label\": \"Table\"}]"
motivation: CLIP等模型缺乏像素级定位能力，现有方法依赖昂贵语义标注。
method: 利用无标注图像和基础模型生成掩码，通过在线聚类和可学习类名适配CLIP。
result: 在多个语义分割数据集上取得优异开放词汇性能。
conclusion: PixelCLIP实现了无标签条件下的开放词汇语义分割。
---

## Abstract
Large-scale vision-language models like CLIP have demonstrated impressive open-vocabulary capabilities for image-level tasks, excelling in recognizing what objects are present. However, they struggle with pixel-level recognition tasks like semantic segmentation, which require understanding where the objects are located. In this work, we propose a novel method, PixelCLIP, to adapt the CLIP image encoder for pixel-level understanding by guiding the model on where, which is achieved using unlabeled images and masks generated from vision foundation models such as SAM and DINO. To address the challenges of leveraging masks without semantic labels, we devise an online clustering algorithm using learnable class names to acquire general semantic concepts. PixelCLIP shows significant performance improvements over CLIP and competitive results compared to caption-supervised methods in open-vocabulary semantic segmentation.

---

## 论文详细总结（自动生成）

# 论文《Towards Open-Vocabulary Semantic Segmentation Without Semantic Labels》中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大规模视觉语言模型（如CLIP）在图像级任务上表现出色，能识别“什么东西出现”，但在像素级语义分割任务中表现不佳，因为该任务同时需要理解“物体出现在哪里”。现有开放词汇语义分割方法通常依赖昂贵的像素级语义标签或图像级语义标签（如字幕），但字幕仅提供“什么”而不提供“哪里”，导致模型对物体位置的隐式学习不充分。
- **动机**：避免使用任何语义标签，转而利用无标注的掩码（masks）来提供“哪里”的指导。这些掩码可由视觉基础模型（如SAM、DINO）免费生成，从而以低成本获得位置监督信号。
- **整体含义**：提出PixelCLIP，通过在线聚类和可学习类提示，将CLIP图像编码器适配到像素级理解，实现无需语义标签的开放词汇语义分割。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：利用视觉基础模型生成的无标签掩码作为“where”的监督，同时通过在线聚类将语义相似的掩码分组为全局的语义簇，用可学习的类提示（learnable class prompts）表示每个簇，从而在不依赖语义标签的情况下学习密集的视觉-语言对齐。
- **关键技术细节**：
  - **掩码整合**：对CLIP图像特征图进行掩码池化（MaskPool）得到每个掩码的特征 $f_M$。
  - **在线聚类**：使用Sinkhorn-Knopp算法将batch内所有掩码特征分配到 $k$ 个簇中，分配矩阵 $Q$ 满足等分区约束（每个簇被平均分配掩码）。簇中心由可学习类提示经CLIP文本编码器编码得到。
  - **可学习类提示**：每个簇对应一个长度为 $l$ 的可学习token，输入固定模板“A photo of {} in the scene”获得文本特征 $f_C$。
  - **动量编码器**：为稳定训练，从动量更新的图像编码器提取掩码特征 $f_M$。
  - **预测与损失**：计算图像特征与类特征的余弦相似度 $M_{IC}$，通过轻量级解码器上采样，与根据分配矩阵 $Q$ 聚合后的掩码标注计算二元交叉熵损失。
- **算法流程（文字说明）**：
  1. 输入图像 $I$ 和预生成的无标签掩码 $M$。
  2. 通过CLIP图像编码器（或动量编码器）提取特征 $f_I$，对每个掩码提取 $f_M$。
  3. 通过可学习类提示经CLIP文本编码器得到 $k$ 个类特征 $f_C$。
  4. 计算 $f_M$ 与 $f_C$ 的相似度，经Sinkhorn-Knopp求解得到软分配 $Q$，并转化为硬分配将原始掩码合并为 $k$ 个簇掩码 $\bar{M}$。
  5. 计算 $f_I$ 与 $f_C$ 的相似度图 $M_{IC}$，解码后与 $\bar{M}$ 计算像素级二值交叉熵损失，联合优化图像编码器、轻量级解码器和可学习类提示。
  6. 推理时仅使用图像编码器和文本编码器，对任意文本类别进行零样本预测。

## 3. 实验设计
- **数据集**：
  - **训练**：SA-1B数据集（SAM的掩码标注），随机采样5%（约0.5M张图像）。也使用COCO-Stuff的掩码进行对比。
  - **评估**：COCO-Stuff、ADE-20K、PASCAL-Context、PASCAL VOC、CityScapes的验证集，用于零样本开放词汇语义分割。
- **Benchmark**：与多种方法对比：
  - 基线：原始CLIP（使用MaskCLIP适配）、OpenCLIP。
  - 使用图像级语义标签的方法：SegCLIP、TCL、SAM-CLIP。
  - 无需语义标签的方法：ZeroSeg、GroupViT、CLIPpy、OVSegmentor等。
  - 还评估了零样本掩码分类：将PixelCLIP替换到ZegFormer、FC-CLIP框架中，并在真实掩码上测试。
- **评价指标**：平均交并比（mIoU）。
- **公平性**：所有方法均采用零样本评估，不进行微调或后处理，对比设置一致。

## 4. 资源与算力
- 文中明确说明：使用4块NVIDIA A6000 GPU，训练约6小时（ConvNeXt-B主干，10000迭代，batch size 48）。对于ViT-B/16等其他主干，训练时长类似但未单独列出。训练数据为SA-1B的5%样本，整体计算资源需求适中。

## 5. 实验数量与充分性
- 实验充分且系统：
  - **主表**（Table 1）：在5个数据集上与多个基线对比，涵盖有/无语义标签的方法。
  - **零样本掩码分类**（Table 2）：在3种框架（ZegFormer、FC-CLIP、真实掩码）上验证通用性。
  - **消融实验**（Table 3）：包括组件分析（有无语义聚类、文本编码器、类提示、动量）、聚类数 $k$、提示长度 $l$、与固定类别对比。
  - **附加实验**（附录）：不同主干（Table 4）、提示集成策略（Table 5）、动量率 $\gamma$、训练数据集（Table 6）。
  - **定性结果**（Figure 4、8、9）可视化对比。
- 实验客观：所有对比方法均采用公平的设置，未引入不公平的后处理或额外数据。

## 6. 论文的主要结论与发现
- PixelCLIP在开放词汇语义分割上相比原始CLIP平均提升+16.2 mIoU，在5个数据集上均显著改进。
- 尽管未使用任何语义标签，PixelCLIP在多个基准上超越了依赖图像级语义标签（字幕）的方法（如TCL、SegCLIP），并与使用40M字幕的SAM-CLIP性能接近。
- 在零样本掩码分类任务中，PixelCLIP可直接替换现有框架中的CLIP，带来即插即用的性能提升。
- 全局语义聚类是关键组件：若不进行聚类，模型会丢失预训练知识（mIoU跌至个位数）。
- 可学习类提示能够学习到多样化的语义概念，并随着聚类数增加捕获更细粒度的语义。

## 7. 优点
- **新颖性**：首次提出仅用无标签掩码（来自SAM/DINO）作为弱监督，完全规避语义标签依赖，为开放词汇分割开辟了新路径。
- **简洁有效**：方法只需少量训练数据（5% SA-1B）和轻量级训练，即可显著提升CLIP的密集预测能力。
- **即插即用**：可直接替换现有基于CLIP的分割/检测模型中的CLIP编码器，提供立竿见影的改进。
- **全面消融**：对每个设计选择进行了详细分析，论证了聚类、动量、提示长度等的重要性。

## 8. 不足与局限
- **局限性**（作者自述）：
  - 掩码特征提取采用简单的掩码池化，在训练早期可能受噪声CLIP特征影响，导致次优性能。
  - 依赖预训练CLIP的知识，可能继承其数据集中的偏差（如互联网爬取数据的偏见）。
- **实验覆盖**：虽然评估了5个主流数据集，但未涉及更多样化的场景（如细粒度对象、跨域场景）或低分辨率/质量图像的鲁棒性。
- **资源开销**：尽管训练算力可接受，但需要预先生成SAM掩码（SA-1B已提供），推理时仍需要CLIP双编码器，计算量较大。
- **聚类数选择**：$k$ 值（默认64）对性能有影响，过大或过小均可能下降，需要调参，且缺乏自适应机制。

（完）
