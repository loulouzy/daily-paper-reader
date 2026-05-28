---
title: Unified Generative and Discriminative Training for Multi-modal Large Language Models
title_zh: 多模态大语言模型的统一生成式与判别式训练
authors: "Wei Chow, Juncheng Li, Qifan Yu, Kaihang Pan, Hao Fei, Zhiqi Ge, Shuai Yang, Siliang Tang, Hanwang Zhang, Qianru Sun"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=w67vRHZF13"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型的统一训练方法
tldr: 本文针对多模态大语言模型（MLLM）提出一种统一生成式与判别式训练方法。针对现有生成式训练幻觉和判别式训练对复杂场景区分能力弱的问题，将交叉图像-文本序列作为通用输入格式，引入结构诱导训练策略。该方法结合了两种范式的优势，在多个任务上提升了性能。这项工作为MLLM训练提供了新视角。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1325, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1312, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1434, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 139, \"height\": 107, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 137, \"height\": 109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 65, \"height\": 81, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1438, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 2081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1442, \"height\": 1362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 311, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 176, \"height\": 134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 178, \"height\": 140, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 137, \"height\": 138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 135, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 140, \"height\": 141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1280, \"height\": 190, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 138, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 133, \"height\": 134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 81, \"height\": 88, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 76, \"height\": 80, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 672, \"height\": 143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 518, \"height\": 139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 137, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 190, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 194, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 196, \"height\": 129, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 169, \"height\": 122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 110, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1431, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 152, \"height\": 135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 225, \"height\": 131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 198, \"height\": 133, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1256, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 235, \"height\": 131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 101, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 92, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 105, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1261, \"height\": 199, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1398, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 886, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 399, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 514, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 366, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 461, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 798, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1404, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 653, \"height\": 384, \"label\": \"Table\"}]"
motivation: 生成式训练存在幻觉，判别式训练对复杂场景区分能力弱。
method: 统一生成与判别训练，采用交错图像文本序列和结构诱导策略。
result: 在多个多模态基准上取得更好性能。
conclusion: 统一生成和判别范式可提升MLLM的鲁棒性和判别能力。
---

## Abstract
In recent times, Vision-Language Models (VLMs) have been trained under two predominant paradigms. Generative training has enabled Multimodal Large Language Models (MLLMs) to tackle various complex tasks, yet issues such as hallucinations and weak object discrimination persist. Discriminative training, exemplified by models like CLIP, excels in zero-shot image-text classification and retrieval, yet struggles with complex scenarios requiring fine-grained semantic differentiation. This paper addresses these challenges by proposing a unified approach that integrates the strengths of both paradigms. Considering interleaved image-text sequences as the general format of input samples, we introduce a structure-induced training strategy that imposes semantic relationships between input samples and the MLLM’s hidden state. This approach enhances the MLLM’s ability to capture global semantics and distinguish fine-grained semantics. By leveraging dynamic sequence alignment within the Dynamic Time Warping framework and integrating a novel kernel for fine-grained semantic differentiation, our method effectively balances generative and discriminative tasks. Extensive experiments demonstrate the effectiveness of our approach, achieving state-of-the-art results in multiple generative tasks, especially those requiring cognitive and discrimination abilities. Additionally, our method surpasses discriminative benchmarks in interleaved and fine-grained retrieval tasks. By employing a retrieval-augmented generation strategy, our approach further enhances performance in some generative tasks within one model, offering a promising direction for future research in vision-language modeling.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有视觉-语言模型（VLM）主要分为两种范式：**生成式训练**（如MLLM）和**判别式训练**（如CLIP）。生成式训练能处理复杂任务，但存在幻觉、物体判别能力弱等问题；判别式训练在零样本分类和检索上表现优异，但在复杂场景（如交错图像-文本检索）和细粒度语义区分上能力不足。两者之间存在鸿沟，且已有尝试将判别能力注入生成模型时，往往牺牲生成性能或仅支持单一判别任务。
- **核心问题**：如何在一个模型中同时发挥两种范式的优势，使MLLM既能保持强大的生成能力，又能获得全局语义捕获和细粒度语义区分能力，从而在生成和判别任务上协同增益。
- **整体含义**：本文提出了一种统一生成与判别训练的结构诱导方法（Sugar），通过在MLLM隐藏状态上施加语义关系约束，使模型在生成任务（尤其是需认知和判别能力的任务）和判别任务（尤其是交错检索和细粒度检索）上均达到领先水平，并支持检索增强生成（RAG）而无需额外检索模块。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将交错图像-文本序列视为通用输入格式，通过**动态序列对齐**（Dynamic Sequence Alignment）在MLLM的隐藏状态上施加结构诱导约束，鼓励模型捕获全局语义和细粒度语义。具体利用动态时间规整（DTW）框架下的全局对齐核（GAK）计算两个输入序列间的相似度，并引入**三重核（Triple Kernel）** 以增强细粒度区分能力。
- **关键技术细节**：
  - **动态序列对齐**：对于两个交错序列（由多个图像/文本片段组成），定义对齐路径π，利用全局对齐核K(x,y) = ∑_{π∈A(x,y)} ∏_{i=1}^{|π|} e^{-φσ}，其中φσ结合了片段间距离和log(2 - e^{-distance})，σ基于序列长度自适应计算。
  - **三重核（TK）**：将每个片段编码为两个部分（来自不同预训练模型）：对图像使用DINOv2和CLIP ViT-L/14拼接；对文本使用BGE和CLIP。根据模态（单模态/跨模态）选择不同的距离计算方式，确保核的正定性。
  - **训练损失**：总损失L = L_g（生成损失）+ α L_d（判别损失）。L_d通过最小化MLLM隐藏状态（最后一token经MLP映射）之间的相似度矩阵与标签矩阵（由GAK计算得到）之间的MSE实现。标签矩阵中，来自同一序列的片段间设为1，来自不同序列的片段间相似度由GAK计算。
- **算法流程**：输入交错序列 → MLLM编码 → 取关键token（图像用所有token平均池化，文本用最后一token） → MLP映射到嵌入 → 计算GAK相似度矩阵 → 计算MSE损失L_d → 与生成损失L_g联合优化。

### 3. 实验设计：数据集、Benchmark、对比方法

- **生成任务**：
  - **11个常见基准**：VQA-v2, GQA, VizWiz, ScienceQA-IMG, TextVQA, POPE, MME（感知/认知）, MMBench, LLaVA-Bench（In-the-Wild）-Detail, MM-Vet。
  - **复杂多模态理解**：DEMON基准（7大类29个子任务，如文本丰富图像QA、视觉关系推理等）。
- **判别任务**：
  - **图像-文本检索**：MSCOCO（标准任务）。
  - **交错检索**：VIST数据集（图文故事，5c+4i等配置）。
  - **细粒度检索**：Winoground（评估视觉-语言组合推理能力）。
- **检索增强生成（RAG）**：VizWiz和ScienceQA-IMG，使用LLaVA-1.5 SFT子集+hold-in数据作为知识库。
- **对比方法**：生成任务对比了BLIP-2、InstructBLIP、Shikra、IDEFICS、Qwen-VL、LLaVA-1.5、VILA等；判别任务对比了FROMAGe、CLIP、BLIP-2、FLAVA、ViLT等。

### 4. 资源与算力

- 论文附录E.2明确说明：训练在**8×A800 GPU**上进行，时长约**12小时**。采用LoRA（rank=128，α=256），优化器为AdamW，学习率1e-4，warm-up ratio 0.03。

### 5. 实验数量与充分性

- **实验数量**：涵盖了3大类（生成、判别、RAG）共超过15个不同数据集/基准，生成任务中包含11个通用基准和29个子任务的DEMON；判别任务包含3种检索场景（标准、交错、细粒度）；消融实验包含5种变体（w/o data_d, w/o data_g, w/o GAK, w/o TK, w/o AvgPool）及额外知识型VQA比较（FVQA、WebQA）。
- **充分性与公平性**：实验设计较为全面，对比了多个SOTA方法，并控制相同基础模型（VILA-7B）。消融实验验证了各组件的必要性。数据集和评估指标均遵循前人设置（如VILA、FROMAGe），结果报告客观。但仅在7B模型上验证，未探索更大模型（如13B、80B）的性能。

### 6. 论文的主要结论与发现

1. **联合训练增益显著**：引入判别损失后，MLLM在需要认知和区分能力的生成任务（如VizWiz、SQA、POPE）上提升明显，同时判别任务（尤其是交错和细粒度检索）也达到SOTA。
2. **全局对齐核（GAK）有效**：相比直接平均切片相似度，GAK能更好地捕获全局语义，提升交错检索和KGQA性能。
3. **三重核（TK）关键**：对于细粒度区分（Winoground），TK带来大幅提升（Image分数从20.5%升至36.3%），证明多预训练模型融合的必要性。
4. **自包含RAG可行**：利用Sugar自身的判别能力进行检索增强，无需外部检索模块，且优于或持平于CLIP/BLIP-2等外部检索器。
5. **生成与判别任务相互促进**：减少生成数据会损害判别性能（如VIST），减少判别数据也会影响生成性能（如POPE），表明两者存在协同作用。

### 7. 优点

- **方法创新性**：首次将动态时间规整框架引入MLLM训练，通过动态序列对齐显式建模序列间语义关系，弥补了因果LLM全局信息捕获不足的缺陷。
- **细粒度区分能力**：三重核设计巧妙地融合了CLIP、DINOv2、BGE等不同预训练模型的优势，在小样本细粒度区分任务上效果显著。
- **统一框架**：一个模型同时支持生成、检索、RAG，避免了传统方案中检索器与生成器不兼容的问题，简化了系统优化。
- **实验全面**：涵盖生成、判别、RAG三大类任务，消融实验充分，并在多个基准上取得SOTA。

### 8. 不足与局限

- **模型规模局限**：实验仅在7B参数量级进行，未验证在更大模型（如13B、70B）上的可扩展性和收益。
- **训练数据潜在噪声**：交错训练数据（如MMC4、COYO）可能存在图文错配，论文承认但未深入分析其影响。
- **计算开销**：动态序列对齐需要计算序列间所有片段对的核，复杂度为O(n m d²)，在处理长序列时可能成为瓶颈。
- **任务覆盖**：虽然覆盖了多个基准，但未涉及视频理解、视觉定位等更复杂的多模态任务。
- **偏差与风险**：模型继承自CLIP和Vicuna，可能隐含视觉和语言上的偏见，论文在附录中提到了但未进行量化评估或去偏尝试。
- **可重复性**：代码尚未开源（仅提及项目仓库），但实验设置描述较详细，理论上可复现。

（完）
