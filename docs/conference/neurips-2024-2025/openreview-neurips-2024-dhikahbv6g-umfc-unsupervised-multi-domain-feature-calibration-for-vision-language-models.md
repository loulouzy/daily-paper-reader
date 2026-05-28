---
title: "UMFC: Unsupervised Multi-Domain Feature Calibration for Vision-Language Models"
title_zh: UMFC：无监督多域特征校准用于视觉语言模型
authors: "Jiachen Liang, RuiBing Hou, Minyang Hu, Hong Chang, Shiguang Shan, Xilin Chen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=dHIKahbV6G"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 提出针对视觉语言模型的无监督多域特征校准方法
tldr: 该论文针对视觉语言模型（如CLIP）在跨域迁移时性能下降的问题，提出无监督多域特征校准方法（UMFC）。作者发现CLIP的视觉编码器偏向编码域信息而非类别信息，文本编码器偏好域相关类别。UMFC通过无监督方式校准这些偏差，无需标注数据，显著提升了模型在多个下游任务上的域外泛化能力。该方法适用于多种预训练视觉语言模型，具有实用性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-dhikahbv6g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1407, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dhikahbv6g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1172, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dhikahbv6g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 994, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dhikahbv6g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 631, \"height\": 439, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1313, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 918, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 942, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 662, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 946, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 645, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 872, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 921, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 934, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 864, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 614, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 989, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dhikahbv6g/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 475, \"height\": 147, \"label\": \"Table\"}]"
motivation: 视觉语言模型在域迁移时性能下降，且通常需要标注数据进行适应，成本高昂。
method: 通过无监督多域数据校准CLIP视觉和文本编码器的固有偏差，增强特征判别性。
result: 在多个跨域任务上验证了UMFC的有效性，提升了零样本迁移能力。
conclusion: 无监督域校准是一种低成本高收益的视觉语言模型迁移增强方案。
---

## Abstract
Pre-trained vision-language models (e.g., CLIP) have shown powerful zero-shot transfer capabilities. But they still struggle with domain shifts and typically require labeled data to adapt to downstream tasks, which could be costly. In this work, we aim to  leverage unlabeled data that naturally spans multiple domains to enhance the transferability of vision-language models.  Under this unsupervised multi-domain setting, we have identified inherent model bias within CLIP, notably  in its visual and text encoders. Specifically, we observe that CLIP’s visual encoder tends to prioritize  encoding domain over discriminative category information, meanwhile its text encoder exhibits a preference for domain-relevant classes. To mitigate this model bias, we propose a training-free and label-free feature calibration method, Unsupervised Multi-domain Feature Calibration (UMFC). UMFC estimates image-level biases from domain-specific features and text-level biases from the direction of domain transition. These biases are subsequently   subtracted from original image and text features separately, to render them domain-invariant. We evaluate our method on multiple settings including transductive learning and test-time adaptation. Extensive experiments show that our method outperforms CLIP and performs on par with the state-of-the-arts that need additional annotations or optimization.
Our code is available at https://github.com/GIT-LJc/UMFC.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：预训练的视觉语言模型（如CLIP）具备强大的零样本迁移能力，但在面对域迁移（domain shift）时性能显著下降。传统的适应方法通常需要大量标注数据，成本高昂。
- **问题背景**：实际场景中，未标注数据通常天然包含多个域，这加剧了模型适应的难度。论文发现，CLIP存在两种固有偏差：
  - **视觉编码器偏差**：更倾向于编码域信息而非判别性类别信息，导致不同域特征分离。
  - **文本编码器偏差**：倾向于预测与域名称相关的类别（如“quickdraw”域中偏向“squiggle”、“line”类）。
- **整体目标**：利用多域无标签数据，以无监督、免训练的方式校准这些偏差，提升CLIP的域外泛化能力。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：从概率视角分析，域变量z影响后验概率p(y|x)通过两个项：类别条件分布p(x|y,z)和类别先验p(y|z)。UMFC通过校准图像特征和文本特征，使这两个分布独立于z。
- **关键技术细节**：
  - **图像特征校准（IFC）**：
    - 对未标注图像特征进行聚类（K-Means），得到M个簇及其均值向量μ_i。
    - 对于每个图像特征f，减去所属簇的均值并归一化：
      ```
      f' = (f - μ_i) / ||f - μ_i||_2
      ```
    - 目的：去除域特定信息，使特征更关注类别信息。
  - **文本特征校准（TFC）**：
    - 基于观察：图像域间转移方向在视觉和文本空间一致。
    - 利用图像聚类均值μ_i计算域转移向量：bt_i = μ_i - μ_avg（μ_avg为所有样本均值）。
    - 对每个类别文本特征t_j，减去各域转移向量并平均：
      ```
      t'_j = (1/M) * Σ_{i=1}^M (t_j - bt_i) / ||t_j - bt_i||_2
      ```
    - 目的：移除文本特征中对域相关类别的偏好。
  - **推理**：使用校准后的图像特征f'和文本特征t'_i计算余弦相似度，再经softmax得到预测概率。
- **算法流程**：
  - 无监督校准/直推学习：对整个未标注数据集提取特征 → K-Means聚类 → 计算IFC和TFC统计量 → 校准所有特征 → 分类。
  - 测试时适应：分批处理，第一批K-Means初始化，后续批次用原型分类分配簇，增量更新均值和转移向量。

## 3. 实验设计：数据集、Benchmark、对比方法
- **数据集**：
  - **DomainNet**：包含6个域（Clipart、Infograph、Painting、Quickdraw、Real、Sketch），共345类，约56.9万张图像。
  - **ImageNet Variants**：包括ImageNet-A、ImageNet-R、ImageNet-Sketch，类空间取IN-A和IN-R的并集。
- **评估场景**：
  - **无监督校准（UC）**：提供未标注训练集，测试集从多域混合采样。
  - **直推学习（TL）**：提供整个测试集，一次性校准。
  - **测试时适应（TTA）**：测试数据按批到达，动态更新校准统计量。
- **对比方法**：
  - **零样本基线**：CLIP（固定提示）、CLIP-E（集成提示）、CLIP-D（域特定提示，作为oracle）。
  - **少样本微调**：CoOp、CLIP-Adapter（使用不同shots的标注数据）。
  - **无监督微调**：MUST（基于掩码自训练）。
  - **域泛化/测试时适应**：MIRO、PromptStyler、TPT。
  - **更大规模模型**：OpenCLIP系列（不同架构和训练数据）。

## 4. 资源与算力
- **硬件**：单张GeForce RTX 3090 Ti GPU。
- **计算成本**：
  - 无监督校准场景：UMFC训练时间57.3秒，推理时间86秒，内存1887 MiB。
  - 对比：CoOp（6×1 shot）训练32分钟；MUST训练10小时（2 GPUs）；TPT推理197分钟（197倍于UMFC）。
  - 论文未明确说明使用的GPU数量（除MUST外推测为单卡），也未提及总的算力消耗（如总核时数）。

## 5. 实验数量与充分性
- **主要实验**：表1-6展示了在DomainNet和ImageNet Variants上，UMFC在三种场景下与10余种方法的对比结果。
- **消融实验**：表7单独验证IFC和TFC的有效性；表8-9和表11考察超参数M（簇数）和批大小的影响。
- **扩展验证**：附录A在OpenCLIP系列模型（不同架构、不同训练数据规模）上验证观察普适性和方法有效性（表10）。
- **计算成本对比**：附录E表12、13给出了训练/推理时间、内存等细节。
- **充分性分析**：实验覆盖了多个域、多种评估协议、多种基线（包括有监督和无监督），并提供了超参数敏感性分析。对比公平（如相同模型骨干、公平数据划分）。结论可靠。但缺少对更复杂域迁移场景（如连续域、开放域）的验证。

## 6. 主要结论与发现
- UMFC在无需任何标注和额外训练的条件下，显著提升CLIP在多域任务上的零样本性能。
- 在DomainNet上，UMFC在Quickdraw域提升约5%；在ImageNet Variants上，UMFC+CLIP-E在IN-Sketch上提升约3.5%。
- UMFC性能与使用标注数据的少样本方法（如CoOp、CLIP-Adapter）相当甚至更优，且计算成本低。
- IFC和TFC结合具有互补性，共同校准效果最佳。
- 方法对簇数M不敏感，对批大小在TTA设置下鲁棒。

## 7. 优点
- **训练免费、标签免费**：无需任何梯度更新或标注数据，仅需一次前向提取特征和简单统计。
- **通用性**：适用于多种预训练视觉语言模型（如CLIP、OpenCLIP），不同架构（ViT-B/16、ViT-H/14等）。
- **计算高效**：相比于TPT等测试时微调方法，推理时间降低约400倍，内存降低约3.8倍。
- **即插即用**：可作为CLIP推理的轻量插件，易部署。
- **理论清晰**：从概率视角分析偏差来源，方法设计有理论支撑。

## 8. 不足与局限
- **依赖无标签目标域数据**：虽然比标注数据易获取，但在某些场景（如无任何目标域样例）仍受限。
- **域信息假设**：方法有效性依赖于图像特征中域信息的可聚类性，对于域特征模糊的数据集（如ImageNet-A，自然对抗样本，域样式不明显）提升有限。
- **聚类质量影响**：K-Means的性能影响校准精度，且假设各簇内类别分布均匀（实际可能不成立），但实验显示该方法仍有效。
- **实验覆盖不足**：未在更多任务（如检索、分割）或更复杂的域迁移（如跨数据集、开放域）上验证；未与其他无监督域适应方法（如UDA）比较。
- **超参数选择**：簇数M需要先验知识（如域数量）或调优，虽然论文声称不敏感，但极端值可能影响性能。

（完）
