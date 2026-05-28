---
title: Vision-Language Models are Strong Noisy Label Detectors
title_zh: 视觉语言模型是强大的噪声标签检测器
authors: "Tong Wei, Hao-Tian Li, Chun-Shu Li, Jiang-Xin Shi, Yu-Feng Li, Min-Ling Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=haUnEiXgQ7"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 视觉语言模型用于噪声标签检测
tldr: 本文提出DeFT框架，利用视觉语言模型的图文对齐能力检测噪声标签：通过为每个类别学习正负文本提示，区分特征明显的样本与噪声样本。该方法无需额外标注即可滤除数据集中错误标签，使下游模型微调性能提升。实验在多个分类数据上验证了有效性，尤其在高噪声率下优势显著。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1362, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 327, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 1090, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1044, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 721, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1460, \"height\": 1218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1368, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1020, \"height\": 210, \"label\": \"Table\"}]"
motivation: 现实数据集常有噪声标签，阻碍VLM微调。
method: 提出DeFT框架，通过正负提示学习建立噪声检测器，利用预训练的图文对齐过滤噪声。
result: 在多个噪声标签数据集上，DeFT显著提高了微调模型的准确率。
conclusion: VLM的内在图文对齐能力可有效用于噪声标签检测与净化。
---

## Abstract
Recent research on fine-tuning vision-language models has demonstrated impressive performance in various downstream tasks. However, the challenge of obtaining accurately labeled data in real-world applications poses a significant obstacle during the fine-tuning process. To address this challenge, this paper presents a Denoising Fine-Tuning framework, called DeFT, for adapting vision-language models. DeFT utilizes the robust alignment of textual and visual features pre-trained on millions of auxiliary image-text pairs to sieve out noisy labels. The proposed framework establishes a noisy label detector by learning positive and negative textual prompts for each class. The positive prompt seeks to reveal distinctive features of the class, while the negative prompt serves as a learnable threshold for separating clean and noisy samples. We employ parameter-efficient fine-tuning for the adaptation of a pre-trained visual encoder to promote its alignment with the learned textual prompts. As a general framework, DeFT can seamlessly fine-tune many pre-trained models to downstream tasks by utilizing carefully selected clean samples. Experimental results on seven synthetic and real-world noisy datasets validate the effectiveness of DeFT in both noisy label detection and image classification. Our source code can be found in the supplementary material.

---

## 论文详细总结（自动生成）

# 论文《Vision-Language Models are Strong Noisy Label Detectors》详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机与背景**：视觉-语言模型（如CLIP）在下游任务中展现出优秀性能，但实际应用中获取精准标注数据困难，噪声标签普遍存在。直接在含噪数据集上微调会显著降低模型性能。现有方法多基于单模态（图像）的样本选择或鲁棒学习，未充分利用多模态对齐能力。本文旨在利用视觉-语言模型预训练所获得的强图文对齐能力，构建一个通用的去噪微调框架，解决含噪声标签下游数据集的微调问题。

## 2. 论文提出的方法论

- **核心思想**：提出DeFT（Denoising Fine-Tuning）框架，分为两阶段：
  1. **噪声标签检测阶段**：为每个类别学习一对正负文本提示（positive/negative prompts），通过比较图像与正/负提示的相似度来判断样本是否为干净样本（若与正提示相似度高于负提示则视为干净）。利用参数高效微调（PEFT）适配视觉编码器，以保持预训练特征鲁棒性。
  2. **模型适应阶段**：在检测出的干净子集上，移除PEFT模块，进行全参数微调（FFT），并学习线性分类器，以进一步提升分类性能。

- **关键技术细节**：
  - 正提示：`prompt^+_k = [V^+_1][V^+_2]...[V^+_M][CLS]_k`
  - 负提示：`prompt^-_k = [V^-_1][V^-_2]...[V^-_M][CLS]_k`
  - 可学习阈值：`φ_i = sim(I_i, T^-_k)`，用于判断样本是否干净。
  - 优化目标包含两部分：
    - 二元分类损失 `L_dp`：利用原始标签和随机互补标签训练正负提示。
    - 对比对齐损失 `L_sim`：对齐图像嵌入与正提示文本嵌入，仅在干净子集上计算（预热期后）。
  - 总体损失：`L = L_dp + L_sim`。
  - 第二阶段使用交叉熵损失全微调模型。

## 3. 实验设计

- **数据集与场景**：
  - **合成噪声数据集**：CIFAR-100、Tiny-ImageNet、Stanford-Cars、CUB-200-2011。噪声类型包括对称噪声（噪声比例0.2、0.4、0.6）和实例依赖噪声（0.2、0.3、0.4）。
  - **真实噪声数据集**：CIFAR-100N（r≈0.4）、Clothing1M（r≈0.4）、WebVision（前50类，r≈0.2）。
- **基准方法**：
  - 噪声标签检测对比：标签匹配（Label-match）、小损失策略（Small-loss）。
  - 图像分类对比：CE（交叉熵）、SCE（对称交叉熵）、ELR（早学习正则化）、GMM（高斯混合模型）以及近年方法RoLT、UNICON、LongReMix、ProMix。
  - 预训练模型泛化性测试：ResNet-50、MAE-ViT-B、ViT-B/16、ConvNeXt-T。
- **评估指标**：精确率（Precision）、召回率（Recall）、F1-score（噪声检测）；测试准确率（图像分类）。

## 4. 资源与算力

- 文中明确说明：所有实验在**单个NVIDIA GeForce RTX 3090 GPU**上完成。
- 训练阶段：噪声标签检测阶段和模型适应阶段各10个epoch，学习率分别3×10⁻²和5×10⁻⁴，batch size 64。未提供总时长具体数值。

## 5. 实验数量与充分性

- **实验数量**：非常充分，涵盖：
  - 4个合成噪声数据集 × 6种噪声设置（对称3种+实例依赖3种）= 24组主实验结果（表2）。
  - 3个真实噪声数据集（表3）。
  - 噪声检测性能对比（表1，共24组设置，外加附录更多设置）。
  - 消融实验：模型适应阶段必要性（图3）、不同PEFT方法对比（附录图4）、不同视觉骨干网络（表4）、超参数敏感性（附录表9）。
  - 额外对比：VPT/FFT在不同噪声率下的表现（图1）、多种PEFT技术鲁棒性（附录图4）。
- **公平性**：对比方法均使用相同的CLIP基座和微调策略（FFT或PEFT），并遵循已有论文的设置。代码已开源。
- **结论**：实验设计覆盖了多种噪声类型、多个数据集、多种预训练模型，且进行了充分的消融分析，客观性强。

## 6. 论文的主要结论与发现

- **噪声标签检测**：DeFT的检测方法（正负提示）在精确率和召回率上显著优于标签匹配和小损失策略，尤其在细粒度数据集和高噪声率下提升明显（如CUB-200-2011在60%对称噪声下F1提升14%以上）。
- **图像分类**：DeFT在合成和真实噪声数据集上均超过所有对比方法，尤其Stanford-Cars和CUB-200-2011上平均提升4.34%和更高。
- **关键发现**：
  - 参数高效微调（PEFT）在含噪数据下优于全参数微调（FFT）。
  - 文本分类器（如CoOp）对噪声标签具有鲁棒性。
  - 在干净数据上，FFT优于PEFT。
  - DeFT可推广至多种预训练视觉骨干（ResNet、MAE、ConvNeXt等）。

## 7. 优点

- **方法创新**：首次利用视觉-语言模型的多模态对齐能力进行噪声标签检测，设计正负提示作为可学习阈值，无需预先知道噪声比例。
- **框架通用性**：两阶段解耦，第一阶段可独立使用于任何预训练模型，第二阶段可灵活选用不同骨干。
- **实验充分**：涵盖多种噪声类型、多个数据集、多种预训练模型，并提供了详尽的消融分析和超参数敏感性分析。
- **计算高效**：仅需10个epoch即可完成检测和微调，额外计算成本低。
- **代码开源**：便于复现和后续研究。

## 8. 不足与局限

- **任务范围局限**：目前仅处理单标签多类分类任务中的图像-标签噪声，尚未扩展到多标签分类、图像-文本对噪声或更复杂的噪声类型。
- **对预训练模型依赖**：性能依赖于CLIP等视觉-语言模型的预训练质量，若预训练图文对齐不佳，检测效果可能下降。
- **真实场景验证有限**：虽然使用CIFAR-100N、Clothing1M、WebVision，但真实噪声模式复杂，可能无法完全覆盖所有实际场景（如开集噪声、长尾噪声等）。
- **未报告标准误差**：文中未给出多次重复实验的误差棒，统计显著性不明确。
- **潜在社会影响**：若技术广泛采用，可能减少数据标注需求，影响数据标注从业者的就业。

（完）
