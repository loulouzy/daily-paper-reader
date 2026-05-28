---
title: Towards Self-Refinement of Vision-Language Models with Triangular Consistency
title_zh: 基于三角一致性的视觉语言模型自精炼方法
authors: "Yunlong Deng, Guangyi Chen, Tianpei Gu, Lingjing Kong, Yan Li, Zeyu Tang, Kun Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Ou30gzTLJe"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 视觉语言模型自精炼
tldr: 本论文研究了视觉语言模型在没有监督指令情况下的自精炼能力。提出基于三角一致性的自精炼框架，在图像-查询-答案三元组内重建被遮罩元素，验证了VLM可以不依赖外部监督数据自主产生高质量训练数据，实现自学习。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 753, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 587, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 696, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 690, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 514, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 518, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ou30gztlje/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1349, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 558, \"height\": 120, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 725, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 591, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 829, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1451, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 901, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ou30gztlje/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 752, \"height\": 190, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型依赖监督指令调优，未监督的潜力未被探索。
method: 提出三角一致性原则，在图像-查询-答案三元组内重建遮罩元素以激发自精炼能力。
result: 验证了VLM具有内在自精炼能力，不需要外部输入即可生成高质量监督数据。
conclusion: 该框架使VLM能够自主学习，降低对标注数据的依赖。
---

## Abstract
Vision-Language Models (VLMs) integrate visual knowledge with the analytical capabilities of Large Language Models (LLMs) through supervised visual instruction tuning, using image-question-answer triplets. However, the potential of VLMs trained without supervised instruction remains largely unexplored. This study validates that VLMs possess inherent self-refinement capabilities, enabling them to generate high-quality supervised data without external inputs and thereby learn autonomously. Specifically, to stimulate the self-refinement ability of VLMs, we propose a self-refinement framework based on a Triangular Consistency principle: within the image-query-answer triangle, any masked elements should be consistently and accurately reconstructed. The framework involves three steps: (1) We enable the instruction generation ability of VLMs by adding multi-task instruction tuning like image$\rightarrow$question-answer or image-answer$\rightarrow$question. (2) We generate image-query-answer triplets from unlabeled images and use the Triangular Consistency principle for filtering. (3) The model is further updated using the filtered synthetic data. 
To investigate the underlying mechanisms behind this self-refinement capability, we conduct a theoretical analysis from a causal perspective. 
Using the widely recognized LLaVA-1.5 as our baseline, our experiments reveal that the model can autonomously achieve consistent, though deliberately modest, improvements across multiple benchmarks without any external supervision, such as human annotations or environmental feedback.
We expect that the insights of this study on the self-refinement ability of VLMs can inspire future research on the learning mechanism of VLMs. Code is available at https://github.com/dengyl20/SRF-LLaVA-1.5.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉语言模型（VLM）是否具备**自精炼（Self-Refinement）**的能力，即在不依赖任何外部监督信号（如人类标注、更强教师模型或环境反馈）的情况下，仅凭自身生成的合成数据来提升性能？
- **研究背景**：
  - 当前VLM（如LLaVA-1.5）的成功依赖于大量高质量的图像-问题-答案（IQA）三元组进行监督视觉指令调优。
  - 高质量标注数据获取成本高、存在版权问题，且难以直接来源于网络。
  - 现有合成数据方法（如ShareGPT4V、MLLM-DataEngine）依赖更高级的VLM（GPT-4V）或LLM（GPT-4）作为教师，存在使用限制、成本高、难以找到更优教师等瓶颈。
  - 少数方法尝试利用环境反馈（如评估性能）提供信号，但效率较低。
- **研究意义**：探索VLM自主从无标注图像中学习的能力，有望降低对标注数据和外部模型的依赖，推动多模态模型持续自主进化。

## 2. 论文提出的方法论

### 核心思想

- **三角一致性原则（Triangular Consistency Principle）**：在图像-查询-答案（IQA）三元组中，任意遮罩其中一个或两个元素后，VLM应能一致且准确地重建被遮罩的内容。基于此原则，可以筛选出高质量的自生成指令数据。
- **自精炼框架**：包含三个阶段，形成一个循环迭代过程。

### 关键技术细节

#### 阶段一：增强指令生成能力（Enhancing Instruction Generation）
- 在原始VLM基础上进行**多任务指令调优**，引入三个特定任务：
  1. **I → QA**：给定图像，生成对应的问答对。
  2. **IQ → A**：给定图像和问题，生成答案（即标准视觉指令调优任务）。
  3. **IA → Q**：给定图像和答案，生成问题。
- 训练数据来源于原始调优数据集（如llava_v1_5_mix665k），通过随机遮罩问题（Q）和/或答案（A）构造不同任务样本。遮罩比例：50%数据同时遮罩Q和A，20%仅遮罩Q，30%仅遮罩A。
- 损失函数为三个任务交叉熵损失之和：\(L_{\text{all}} = L_{\text{qa}} + L_{\text{a}} + L_{\text{q}}\)。

#### 阶段二：三角一致性过滤（Triangular Consistency Filtering）
- 利用阶段一增强后的VLM（记作\(M^{(0)}_g\)）为无标注图像生成IQA三元组，得到合成数据集\(D_{\text{synthetic}}\)。
- 对每个三元组\((I_i, Q_i, A_i)\)：
  - 用模型基于\((I_i, Q_i)\)预测答案\(A'_i\)；
  - 用模型基于\((I_i, A_i)\)预测问题\(Q'_i\)；
  - 计算一致性分数：\(S = \sqrt{\text{Sim}(Q_i, Q'_i) \times \text{Sim}(A_i, A'_i)}\)。
- 相似度度量根据数据类型灵活选择：短文本用Sentence Transformer，长文本用BERTScore，坐标用IoU，选择题/判断题直接比较答案是否一致。
- 按数据类型分别选取分数前20%的样本，组成过滤后的高质量合成数据集\(D_{\text{filtered}}\)。

#### 阶段三：指令调优与迭代（Instruction Tuning & Iteration）
- 将\(D_{\text{filtered}}\)与原始种子数据集合并，用于对原始VLM（\(M^{(0)}\)）进行视觉指令调优（与标准LLaVA-1.5相同训练策略），得到精炼后的模型\(M^{(1)}\)。
- 该三阶段流程可迭代应用于新的无标注图像，逐步实现持续自精炼。

### 算法流程（文字说明）
1. 输入：初始VLM \(M_0\)，人工标注数据集\(D_0\)，无标注图像集\(U\)。
2. 迭代\(k=1\)到\(K\)：
   a. 在\(D_0\)上多任务微调得到\(M^{\text{gen}}_0\)。
   b. 用\(M^{\text{gen}}_0\)为\(U\)中每张图像生成IQA三元组\(S\)。
   c. 对\(S\)中每个三元组，重建Q'和A'，计算一致性分数，选出高分样本组成\(F\)。
   d. 合并\(D_0\)和\(F\)作为新训练集，在\(M_0\)上执行指令调优得到\(M_1\)。
3. 返回最终模型。

## 3. 实验设计

### 数据集与场景
- **原始训练集**：LLaVA-1.5使用的 llava_v1_5_mix665k。
- **无标注图像**：从LAION-400M中随机选取**280万张**图像，用于生成合成数据（实际阶段一使用100万张进行生成，过滤后保留约20万张）。
- **评估基准**（8个）：
  - 传统VQA：VQAv2、GQA、ScienceQA-IMG
  - 视觉感知与推理：MMBench、MMBench-Chinese、MME（Cognition）、MM-Vet
  - 视觉对话：LLaVA-Bench (In-the-Wild)
- **额外评估**：MMMU、MMMU-Pro（更挑战性基准）

### 对比方法
- **基线**：LLaVA-1.5 (7B和13B)
- **强基线**：Recap-LLaVA-1.5（使用相同的100万无标注图像，但仅用冻结的LLaVA-1.5-7B生成详细标题，不做过滤，直接合并训练）
- **其他SOTA VLM**：InstructBLIP、IDEFICS-9B、Qwen-VL、Qwen-VL-Chat等
- **跨框架验证**：MobileVLM-1.7B、QWen2.5-VL 3B、LLaVA-1.5 13B

## 4. 资源与算力

- **训练硬件**：8块NVIDIA H100-NVL GPU（96GB显存）或8块NVIDIA A100 GPU（大部分消融实验在A100上完成）。
- **训练时间**：
  - LLaVA-1.5原始训练：约7小时 wall-clock time，56 GPU-hour。
  - SRF-LLaVA-1.5完整训练：约12小时 wall-clock time，96 GPU-hour。
  - 精炼过程额外增加约40 GPU-hour（约0.7倍）。
- **阶段一和阶段三各约20小时**（A100 8卡）。

## 5. 实验数量与充分性

- **主要实验结果**（表1）：在8个基准上对比了LLaVA-1.5 7B/13B、Recap-LLaVA-1.5及其他SOTA，报告了平均值。
- **消融实验**（表5、表A2）：
  - 多轮迭代（Round-2）
  - 一致性阈值（Top 5%、20%、50%、80%、100%）
  - 不同类型指令（VQA、Caption、Visual Chat、REG&REC、Multiple-Choice/Judgment）
  - 数据分布调整（移除长描述、匹配原始数据分布）
  - 遮罩比例敏感性（表A5）
- **跨框架验证**（表3、表4）：在MobileVLM、QWen2.5-VL、LLaVA-1.5 13B上验证泛化性。
- **定性分析**（图4、图A4、图A5）：展示真实案例，分析改进与失败案例。
- **人类评估**（表7）：12名志愿者对100个样本进行3人评分，验证过滤效果。
- **误差线报告**（表A6）：对SRF-LLaVA-1.5 7B进行3次独立重复实验，计算均值±标准差。
- **充分性与公平性**：
  - 设置了强基线Recap-LLaVA-1.5排除更多数据带来的增益。
  - 使用了与LLaVA-1.5完全相同的训练策略、提示模板、评估流程。
  - 覆盖了不同规模（7B、13B）、不同架构（MobileVLM、QWen2.5-VL）的VLM。
  - 实验设计较为全面，消融实验覆盖了各个关键组件。

## 6. 论文的主要结论与发现

1. **VLM具有内在自精炼能力**：在不使用任何外部监督（人类标注、更强模型、环境反馈）的情况下，通过三角一致性原则可以激发模型的自精炼，在多个基准上获得一致且稳定的提升。
2. **三角一致性原则有效**：过滤出的高质量合成数据明显优于未过滤或低分数据，GPT-4o评估准确率85.3% vs 59.9%，人类评估89.0% vs 83.0%。
3. **多轮迭代可带来进一步收益**：第二轮精炼在部分基准上仍有所提升，但增幅减小，表明信号有限，需要更多新数据才能持续进步。
4. **跨模型架构通用**：在LLaVA-1.5 7B/13B、MobileVLM、QWen2.5-VL上均观察到改进，说明方法具有泛化性。
5. **不同类型指令贡献不同**：Visual Chat类型数据带来的平均提升最大（2.3%），Multiple-Choice/Judgment提升最小。
6. **因果视角理论解释**：从因果角度论证了利用无标注图像优化\(P(Y)\)可改善\(P(X|Y)\)，为自精炼提供了理论基础。

## 7. 优点

- **完全自给自足**：不依赖任何外部教师模型或人工标注，仅使用模型自身和大量无标注图像，范式新颖。
- **理论支持**：从因果角度分析了自精炼的有效性，提供了理论保证（虽然基于简化假设）。
- **灵活的过滤机制**：针对不同数据类型设计了不同的相似度度量，使得一致性分数计算合理且高效。
- **强基线对比**：设计了Recap-LLaVA-1.5作为公平对比，排除了仅靠更多数据或更长训练带来的增益。
- **泛化验证充分**：在多个VLM架构和参数规模上进行了验证，展示了方法的通用性。
- **开源可复现**：代码和合成数据集将公开发布。

## 8. 不足与局限

- **改进幅度有限**：虽然多个基准有提升，但整体改进属于“deliberately modest”，并非突破性飞跃。
- **迭代收益递减**：第二轮精炼提升较小，表明自精炼过程存在饱和，需要更大量或更多样的无标注数据才能持续改进。
- **理论假设简化**：理论分析基于加性噪声模型和独立机制假设，这些假设在真实VLM中难以严格验证，仅作为理论工具。
- **计算成本**：相比于原始训练，精炼过程额外增加约40 GPU-hour（约0.7倍），对资源要求仍然较高。
- **偏差和幻觉风险**：使用模型自身生成的合成数据可能强化预训练模型中的偏差或幻觉，且缺少人工审核，难以追溯意外行为。
- **未与最强教师模型对比**：论文明确不进行与使用GPT-4V等方法对比，因此无法直接比较自精炼与教师蒸馏的相对优势。
- **失败案例**：在处理需要深层逻辑推理（如理解meme）的任务上，性能与基线类似，说明当前方法对复杂推理帮助有限。

（完）
