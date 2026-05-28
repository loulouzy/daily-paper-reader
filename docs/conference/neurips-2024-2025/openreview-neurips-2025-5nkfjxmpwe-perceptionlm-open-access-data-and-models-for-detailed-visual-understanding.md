---
title: "PerceptionLM: Open-Access Data and Models for Detailed Visual Understanding"
title_zh: "PerceptionLM: 面向详细视觉理解的开源数据与模型"
authors: "Jang Hyun Cho, Andrea Madotto, Effrosyni Mavroudi, Triantafyllos Afouras, Tushar Nagarajan, Muhammad Maaz, Yale Song, Tengyu Ma, Shuming Hu, Suyog Jain, Miguel Martin, Huiyu Wang, Hanoona Abdul Rasheed, Peize Sun, Po-Yao Huang, Daniel Bolya, Nikhila Ravi, Shashank Jain, Tammy Stark, Seungwhan Moon, Babak Damavandi, Vivian Lee, Andrew Westbury, Salman Khan, Philipp Kraehenbuehl, Piotr Dollar, Lorenzo Torresani, Kristen Grauman, Christoph Feichtenhofer"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5NkfjxMpWe"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型论文
tldr: 针对高性能视觉语言模型封闭源码阻碍科学进步的问题，PerceptionLM完全开源数据、设计和训练流程，在不依赖黑盒蒸馏的情况下，构建了面向图像和视频详细理解的感知语言模型，推动了可复现研究。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 580, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 286, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1423, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 1400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1451, \"height\": 163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1433, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1451, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 808, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 521, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 866, \"height\": 112, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1500, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1493, \"height\": 189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 465, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1462, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1312, \"height\": 220, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 419, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 374, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 198, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 303, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 475, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1455, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1455, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1462, \"height\": 223, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 726, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 584, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 708, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 684, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1045, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1314, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 692, \"height\": 1200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 744, \"height\": 1399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 684, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 907, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 911, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 465, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 477, \"height\": 842, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1015, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1400, \"height\": 1326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 698, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1157, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 945, \"height\": 636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 468, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5nkfjxmpwe/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1075, \"height\": 91, \"label\": \"Table\"}]"
motivation: 高性能视觉语言模型多闭源，阻碍了科学可复现性。
method: 完全开源框架下构建感知语言模型，避免使用专有模型蒸馏。
result: 在图像与视频理解任务上取得了与闭源模型可比的性能。
conclusion: 开源透明的研究范式可促进视觉语言模型领域的可复现进步。
---

## Abstract
Vision-language models are integral to computer vision research, yet many high-performing models remain closed-source, obscuring their data, design and training recipe. The research community has responded by using distillation from black-box models to label training data, achieving strong benchmark results, at the cost of measurable scientific progress. However, without knowing the details of the teacher model and its data sources, scientific progress remains difficult to measure. In this paper, we study building a Perception Language Model (PLM) in a fully open and reproducible framework for transparent research in image and video understanding.  We analyze standard training pipelines without distillation from proprietary models and explore large-scale synthetic data to identify critical data gaps, particularly in detailed video understanding. To bridge these gaps, we release 2.8M human-labeled instances of fine-grained video question-answer pairs and spatio-temporally grounded video captions. Additionally, we introduce PLM–VideoBench, a suite for evaluating challenging video understanding tasks focusing on the ability to reason about ''what'', ''where'', ''when'', and ''how'' of a video. We make our work fully reproducible by providing data, training recipes, code & models.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前高性能视觉语言模型（VLM）多为闭源，其数据、设计和训练细节不公开，阻碍了科学进步的可测量性。研究社区为追赶性能，普遍采用从黑盒模型（如 GPT-4V）进行蒸馏来标注训练数据，但这种方式模糊了真正的科研进展——无法区分性能提升是来自模型/训练创新，还是仅仅因为蒸馏了包含评测集数据的教师模型。
- **整体意义**：论文致力于在**完全开源、可复现**的框架下构建感知语言模型（Perception Language Model, PLM），避免使用任何专有模型蒸馏，并探索大规模合成数据与人工标注数据的结合，填补视频细粒度理解的数据空白，推动 VLM 研究的透明性和可复现性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
- 采用三阶段训练方式（预热、大规模中间训练、监督微调），全部基于开源组件（视觉编码器 Perceptual Encoder、语言解码器 Llama 3、MLP 投影器）。
- 数据完全来自开源数据集或自研的合成数据引擎（不使用任何专有模型生成的数据）。
- 发现合成数据在基础任务上具有良好扩展性，但在**细粒度视频理解**（如运动方向、物体状态、空间关系、时序定位）上扩展性极差（幂律指数仅 -0.03）。
- 为此收集 **2.8M 高质量人工标注**的细粒度视频 QA（PLM–FGQA）和时空视频描述（PLM–STC）数据，并构建新评测集 **PLM–VideoBench**。

### 2.2 关键技术细节
- **模型架构**：PE L/14 或 G/14 视觉编码器 + Llama 3（1B/3B/8B） + 2层 MLP 投影器。
- **图像输入**：动态分块（最多 36 个 448×448 块），每个块进行 2×2 平均池化压缩视觉 token。
- **视频输入**：32 帧 448×448，同样进行 2×2 空间池化。
- **三阶段训练**：
  - Stage 1：冻结视觉编码器和 LLM，仅训练投影器（1M 合成图像，预热）。
  - Stage 2：训练全参数，使用 66.1M 合成数据 + 6.5M 开源人工标注数据，最大 16 块/帧。
  - Stage 3：监督微调，使用 19.1M 高质量数据（含自有的人工标注），最大 36 块/32 帧。
- **数据引擎**：全部基于开源模型（Llama 3、SAM 2、场景检测器等）生成合成数据，覆盖图像/视频的标题、QA 等。

## 3. 实验设计

- **Benchmarks**：共 40+ 图像和视频基准，涵盖 OCR/文档/图表（DocVQA、ChartQA、TextVQA 等）、自然图像 QA（VQAv2、OK-VQA、VizWiz 等）、图像描述（COCO、nocaps、Flickr）、图像幻觉（POPE）、视频 QA（MVBench、NExT-QA、Video-MME、ActivityNet-QA 等）、细粒度视频 QA（TemporalBench、TOMATO、MotionBench、TempCompass）、视频定位（Charades-STA）、视频幻觉（VideoHallucer、EventHallusion）、长视频理解（LVBench、LongVideoBench、MLVU），以及自建的 PLM–VideoBench（含 FGQA、SGQA、RCap、RTLoc、RDCap 五个子任务）。
- **对比方法**：闭源模型（GPT-4o、Gemini 1.5 Pro、Gemini 2.0 Flash）和开源模型（Molmo-7B-O、LLaVA-OneVision-7B、Qwen2-VL 系列、InternVL2.5 系列等），均在同一推理协议下评估。
- **数据集使用**：训练数据包括合成数据（66.1M）、现有开源数据（6.5M）和自有人工标注（2.87M）。消融实验分别评估合成数据、PLM–STC、PLM–FGQA 的影响。

## 4. 资源与算力

- 训练使用 **H100 GPU**（128 或 256 卡）：
  - PLM-3B：Stage 1 约 4 小时（8 GPU），Stage 2 约 3 天（128 GPU），Stage 3 约 2.5 天（128 GPU），合计约 5.5 天。
  - PLM-1B：更短时间。
  - PLM-8B：Stage 2 和 Stage 3 各约 2.5-3 天（256 GPU）。
- 推理阶段：1B 模型可在 24GB GPU 运行，3B 在 40GB，8B 在 80GB。

## 5. 实验数量与充分性

- **数量**：在 40+ 图像和视频基准上进行了全面评估，包括标准任务和挑战任务；此外还进行了详细消融（表 6）、扩展性分析（图 2-3、9-11）、多模型尺度比较（1B/3B/8B）。
- **充分性**：实验覆盖了大部分主流 VLM 评估场景（OCR、图表、自然图像、视频 QA、细粒度理解、幻觉、长视频、时空定位等），对比了同尺度开源模型和更大规模的闭源模型。消融实验验证了合成数据和两类人工标注数据各自贡献。实验设计客观公平，采用了统一的推理协议和公开评测工具。

## 6. 论文的主要结论与发现

- 合成数据在基础任务（OCR、图表、一般图像 QA）上具有良好的幂律扩展性（α ≈ -0.15 ~ -0.20），但在细粒度视频任务（α ≈ -0.03）上几乎无效。
- 自有的人工标注数据（PLM–FGQA 和 PLM–STC）显著提升了细粒度视频理解、时空定位和视频描述性能。
- PLM 在多数基准上超越了同尺度开源模型（如 InternVL2.5、Qwen2.5-VL），并在部分任务上接近或超越闭源模型。
- 完全开源、无蒸馏的训练范式可以达到有竞争力的性能，且可复现性更强。

## 7. 优点

- **完全开源透明**：模型、数据、训练代码、评测集均开源，不使用任何专有模型蒸馏，有利于科学进步的可测量性。
- **大规模人工标注数据**：2.4M 细粒度视频 QA + 476K 时空视频描述，显著大于现有同类数据集，填补了社区空白。
- **全面的评测体系**：PLM–VideoBench 包含五个子任务，覆盖“是什么、在哪里、何时、如何”的细粒度理解，弥补了现有视频基准的不足。
- **详尽的消融与扩展性分析**：揭示了合成数据在不同任务上的缩放规律，并量化了不同数据组件的贡献。

## 8. 不足与局限

- **长视频理解性能较弱**：未使用长视频建模组件（如 token 压缩、动态时间分辨率），在 LVBench、LongVideoBench 等长视频基准上竞争力不足。
- **依赖 LLM 能力**：在需要语言知识或复杂推理的任务（如 MMMU、SGQA、Video-MME）上，受限于 Llama 3 的基础能力，与 GPT-4o 等闭源模型存在差距。
- **数据偏置与安全风险**：尽管采取了过滤措施，模型仍可能隐藏偏见或生成不当内容；人工标注数据可能带有标注者主观性。
- **实验未提供误差棒**：由于训练成本高，未重复实验统计显著性，但通过多任务、多尺度验证增强可靠性。

（完）
