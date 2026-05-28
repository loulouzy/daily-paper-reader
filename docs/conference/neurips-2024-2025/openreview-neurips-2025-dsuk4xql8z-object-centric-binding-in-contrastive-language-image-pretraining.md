---
title: Object-centric binding in Contrastive Language-Image Pretraining
title_zh: 对比语言-图像预训练中的以对象为中心的绑定
authors: "Rim Assouel, Pietro Astolfi, Florian Bordes, Michal Drozdzal, Adriana Romero-Soriano"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dsUK4Xql8Z"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 视觉语言模型论文：以对象为中心的绑定方法
tldr: 现有视觉语言模型（如CLIP）在理解复杂组合场景（多个对象及其空间关系）方面存在局限。本文提出一种新颖的绑定模块，将文本描述的场景图与视觉槽表示连接，在预训练中集成归纳偏置。该方法无需细粒度硬负样本增强，即可提升模型的组合理解能力。实验表明该模块显著改善了对象绑定和关系推理性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1354, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 989, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1409, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 1309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 1603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 1317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 627, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 628, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1219, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1221, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1218, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1221, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1434, \"height\": 1310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1453, \"height\": 1326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1449, \"height\": 1314, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 724, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1464, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1406, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 820, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1460, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1461, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1147, \"height\": 801, \"label\": \"Table\"}]"
motivation: CLIP等对比模型难以理解复杂组合场景中的多对象空间关系。
method: 设计绑定模块，将文本场景图与视觉槽表示对齐，在预训练中注入归纳偏置。
result: 在组合理解基准上取得显著提升，无需复杂数据增强。
conclusion: 以对象为中心的绑定有效增强了VLM的组成性理解。
---

## Abstract
Recent advances in vision language models (VLM) have been driven by contrastive models such as CLIP, which learn to associate visual information with their corresponding text descriptions. However, these models have limitations in understanding complex compositional scenes involving multiple objects and their spatial relationships. To address these challenges, we propose a novel approach that diverges from commonly used strategies that rely on the design of finegrained hard-negative augmentations. Instead, our work focuses on integrating inductive biases into the pretraining of CLIP-like models to improve their compositional understanding. To that end, we introduce a binding module that connects a scene graph, derived from a text description, with a slot-structured image representation, facilitating a structured similarity assessment between the two modalities. We also leverage relationships as text-conditioned visual constraints, thereby capturing the intricate interactions between objects and their contextual relationships more effectively. Our resulting model not only enhances the performance of CLIP-based models in multi-object compositional understanding but also paves the way towards more accurate and sample-efficient image-text matching of complex scenes.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：现有的对比视觉-语言模型（如 CLIP）虽然在图文匹配上取得了巨大成功，但它们在理解**多对象复杂场景**（包括空间关系、属性绑定等组合性语义）时表现不佳，常表现出“词袋”行为——例如无法区分“红方块和蓝圆”与“蓝方块和红圆”，也无法理解“猫在垫子左边”与“猫在垫子右边”的差别。
- **问题背景**：这一问题被称为 **“绑定问题”** （binding problem），包括分离（segregation）、表示（representation）和组合（composition）三个子问题。已有改进方法主要依赖**细粒度硬负样本增强**（hard-negative augmentations）——在文本空间或图像空间中构造细微差异的负样本——但这些方法未能从根本上解决绑定问题，且泛化能力有限。
- **整体贡献**：本文提出 **OC-CLIP（Object-Centric CLIP）**，通过引入**以对象为中心的归纳偏置**（object-centric inductive biases）来增强 CLIP 模型的组合理解能力，而**不依赖**复杂的硬负样本构造。其核心在于设计了一个**绑定模块**（binding module）和一个**结构化的相似度评分**（structured similarity score），使模型能够动态地将文本描述中的对象节点与图像中的视觉槽（slots）对齐，并显式建模关系约束。

## 2. 方法论

- **核心思想**：从场景图（scene graph）中提取文本的对象和关系，利用**倒置交叉注意力**（inverted cross-attention）机制，将文本节点作为查询（queries），图像 Patch 作为键值（keys/values），学习一组**视觉槽**（visual slots）。这些槽被强制与文本节点一一对应，同时引入**默认槽**（default slots）吸收图像中未被文本描述的部分。最后，通过**结构化相似度评分**计算图文匹配程度，该评分包括对象评分（节点与对应槽的余弦相似度）和关系评分（关系嵌入与对应主/宾视觉槽的映射函数）。

- **关键技术细节**：
  - **场景图解析**：使用 LLM（如 LLaMA3-8B）从文本描述中提取对象节点和关系边，形成 `[N, R]` 结构。
  - **绑定模块**：公式化为 `Q = W_q N`，`K, V = W_k ¯x, W_v ¯x`，`Q' = [Q; Q_default]`，然后对 `Q'` 在查询维度上做 softmax（竞争机制），输出视觉槽 `S` 和默认槽 `S_default`（默认槽后续丢弃）。
  - **结构化相似度**：`S(x, G) = (α * Σ cosine(N_i, S_i) + β * Σ f_ϕ(r_i, S_si, S_oi)) / (αM + βP)`。其中 `f_ϕ` 定义为 `cosine(r, f_s([r, S_s]) + f_o([r, S_o]))`，`f_s` 和 `f_o` 为 MLP，降低维度并保持有序性。
  - **损失函数**：总损失 `L = L_ITC + L_rel`。`L_ITC` 是标准对比损失（将图像与对应场景图视为正对，与其他场景图视为负对）；`L_rel` 是局部图对比损失，强制模型对交换主/宾关系或随机打乱节点的负场景图输出更低相似度。

- **算法流程**（文字说明）：
  1. 输入图像 `x`，通过 ViT 编码器得到 Patch 嵌入 `¯x`。
  2. 输入文本 `t`，通过 LLM 解析器获得场景图 `G = (N, R)`。
  3. 用文本编码器对节点和关系分别编码（使用较小的文本编码器，如 6 层 Transformer）。
  4. 绑定模块：将节点嵌入作为查询，图像 Patch 作为键值，经倒置交叉注意力得到视觉槽 `S`。
  5. 计算结构化相似度 `S(x, G)`，包含对象评分和关系评分。
  6. 对比损失：拉近正对（`x, G`），推远负对（`x, G_j` 和 `x_j, G`）。
  7. 额外局部关系对比损失：对同一场景图，构造交换主/宾或随机打乱的负图，强制关系评分更低。

## 3. 实验设计

- **数据集与场景**：
  - **合成数据集**：基于 **PUG** 三维环境，构建包含单个或成对纹理动物、不同背景的封闭词汇数据集，用于评估属性绑定和空间关系理解。属性绑定任务：区分“红色猫+白色鹿”与“白色猫+红色鹿”。空间关系任务：区分“X 在 Y 左边”与“Y 在 X 左边”。
  - **真实世界组合理解**：训练数据来自 **COCO Captions**、**Visual Genome** 和 **GQA**。评估基准包括：
    - 属性绑定：**SugarCrepe**（swap-attribute, swap-object, replace-attribute, replace-object, replace-relation 等拆分）、**ARO-Attribution**。
    - 空间关系理解：**COCO-spatial**、**GQA-spatial**（来自 Whatsup Benchmark）、**ARO-Relation**。
  - **从零训练 & 缩放实验**：使用 **CC3M**、**CC12M** 及其合并（15M）进行从零训练，评估 **ImageNet 零样本分类** 和 SugarCrepe、Winoground 零样本组合理解。

- **对比方法**：
  - 零样本 & 领域内微调基线：OpenCLIP、BLIP、XVLM。
  - 硬负样本增强方法：NegCLIP、CE-CLIP、CC-CLIP、CLIP-SVLC、MOSAICLIP。
  - 大规模稠密重标注方法：DAC-LLM、DAC-SAM。
  - 从零训练基线：OpenCLIP、NegCLIP、IL-CLIP。

- **实验数量**：共进行三大类实验（合成数据、真实世界组合理解、缩放实验），每类实验包含多个数据集、多个模型变体（B-32, B-16, B-14 等），并报告3次随机种子的均值和标准差。消融实验：对竞争注意力、局部图对比损失、注意力层数、默认槽数量、评分维度、ViT 特征层选择等进行系统分析。总计实验组数超过 20 组（含各数据集拆分）。

## 4. 资源与算力

- **领域内微调实验**：使用 4×8 V100 GPU（局部 batch size 128），训练 100 epochs（OC-CLIP 绑定模块从头训练，主干低学习率微调）。
- **从零训练实验**：使用 4×8 V100 GPU（局部 batch size 128），训练 5/15/25 epochs，batch size 4096（全局），学习率 1e-3，2k 步 warmup，余弦衰减。使用 AdamW 优化器（β2=0.98，weight decay=0.5）。
- **场景图解析**：使用 LLaMA3.1-8B 服务在 V100 GPU 上，COCO（50万标题）约 3.5 小时，CC12M 约 3 天（可通过更优 GPU 加速）。
- **计算开销分析**：OC-CLIP 相比 CLIP 有额外交叉注意力开销，但当 ViT 主干从 Base 增大到 Large 时，额外开销占比下降（从约 2.2x 降到约 1.3x）。

## 5. 实验数量与充分性

- **充分性**：实验覆盖了从合成数据到真实世界、从微调到从零训练、从属性绑定到空间关系、从组合理解到总体分类（ImageNet）的多个维度，且与主流方法（包括大规模稠密重标注方法）进行了对比。消融实验全面，验证了每个关键组件（竞争注意力、局部损失、默认槽、评分维度等）的重要性。
- **客观性与公平性**：所有实验均报告多次运行结果，对比方法采用同一骨干初始化（OpenCLIP checkpoints），超参数设置符合前人惯例。但是，部分对比方法（如 NegCLIP、IL-CLIP）在从零训练实验中仅使用默认超参数，可能未完全优化。此外，OC-CLIP 在领域内微调后仅能保留训练集覆盖的词汇（无法保持原始 CLIP 的开放词汇零样本能力），作者明确承认这一限制并与同类方法公平比较（均在领域内微调后评估）。

## 6. 主要结论与发现

1. **硬负样本方法效率有限**：在合成数据上，即使增加大量硬负样本，CLIP 的性能仍远低于 OC-CLIP（后者不依赖硬负样本）。OC-CLIP 在未见对象对的属性绑定任务上达到 97%+ 准确率，而 CLIP 仅约 81%。
2. **显著提升组合理解**：
   - **SugarCrepe swap-attribute**：OC-CLIP (B-14) 比 OpenCLIP FT 提高 16.5%，比最强硬负样本方法 DAC-LLM 提高 13.6%。
   - **SugarCrepe swap-object**：提高 20.4%。
   - **COCO-spatial**：从 45.6% 提升至 89.7%（B-14）。
   - **GQA-spatial**：从 49.1% 提升至 92.7%。
   - **ARO-Relation**：从 50.1% 提升至 84.9%。
3. **从零训练可扩展**：在 CC3M+CC12M（15M）上从零训练，OC-CLIP 在 ImageNet 零样本分类上相对 OpenCLIP 提升 12.8%，在 SugarCrepe swap-attribute 提升 12.7%，swap-object 提升 6.6%，同时保持更好的样本效率。
4. **对象中心表示的有效性**：验证了在 CLIP 中引入对象中心归纳偏置（竞争注意力、默认槽、结构化评分）能够有效缓解“词袋”问题，提升绑定和关系推理能力。

## 7. 优点

- **方法论创新**：将无监督对象中心表示学习的归纳偏置成功迁移到视觉-语言对比预训练中，设计简洁而有效，避免了复杂的硬负样本工程。
- **实验设计全面**：从合成数据的可控实验到真实世界的多层次基准，从微调到从零训练，消融实验系统，结论可靠。
- **显式建模关系**：提出非对称关系评分函数，结合局部图对比损失，有效防止关系评分崩溃，使模型能够理解主-宾顺序。
- **计算效率可扩展**：当 ViT 规模增大时，绑定模块的额外开销占比下降，说明该方法具备向更大模型扩展的潜力。

## 8. 不足与局限

- **依赖外部解析器**：场景图解析依赖于预训练的 LLM，解析质量直接影响模型性能。不同 LLM 的偏见和差异有待进一步研究。
- **开放词汇能力受限**：在领域内微调后，OC-CLIP 只能泛化到训练集覆盖的词汇，无法保持原始 CLIP 的完全零样本能力。作者在附录中展示了线性探测结果以验证视觉主干未退化，但开放词汇能力仍需进一步缩放实验验证。
- **缩放规模有限**：最大仅训练到 15M 数据（CC12M），而现代 CLIP 通常使用 400M+ 数据。OC-CLIP 在更大规模下的性能未验证。
- **计算开销**：在小型 ViT 上，绑定模块引入约 2.2x 的 GFLOPs 增加，对资源敏感场景可能不够友好。
- **空间关系基准覆盖**：ARO-Relation 中大部分测试样例为左右关系，模型在非空间关系（如“holding”）上的表现未充分分析。
- **部分对比方法未完全公平**：例如 BLIP、XVLM 使用了额外的语言建模损失或边界框监督，而 OC-CLIP 仅使用对比损失 + 局部关系损失，两者比较时模型容量和训练目标不完全对等。作者对此有说明，但读者需注意。

（完）
