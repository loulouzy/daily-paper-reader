---
title: "Vision as a Dialect: Unifying Visual Understanding and Generation via Text-Aligned Representations"
title_zh: 视觉即方言：通过文本对齐表示统一视觉理解与生成
authors: "Jiaming Han, Hao Chen, Yang Zhao, Hanyu Wang, Qi Zhao, Ziyan Yang, Hao He, Xiangyu Yue, Lu Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ILr4UNiZcQ"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 通过文本对齐分词器统一视觉理解与生成的多模态大语言模型
tldr: 现有多模态模型需要单独设计不同模态接口。本文提出Tar模型，利用文本对齐分词器将图像映射为离散令牌，与文本共享词汇空间，实现统一跨模态处理。实验表明该方法在理解和生成任务上均取得优异效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 568, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1435, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1434, \"height\": 250, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 602, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 704, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 487, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1387, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1023, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1112, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1229, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1452, \"height\": 958, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1233, \"height\": 804, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型需要模态特定设计，缺乏统一的跨模态接口。
method: 提出文本对齐分词器将图像转化为离散令牌，与LLM词汇表对齐，实现统一空间。
result: 在视觉理解和生成任务上达到先进性能。
conclusion: 统一离散表示可有效桥接视觉与语言模态，简化模型设计。
---

## Abstract
This paper presents a multimodal framework that attempts to unify visual understanding and generation within a shared discrete semantic representation. At its core is the Text-Aligned Tokenizer (TA-Tok), which converts images into discrete tokens using a text-aligned codebook projected from a large language model's (LLM) vocabulary. By integrating vision and text into a unified space with an expanded vocabulary, our multimodal LLM, **Tar**, enables cross-modal input and output through a shared interface, without the need for modality-specific designs. Additionally, we propose scale-adaptive encoding and decoding to balance efficiency and visual detail, along with a 
generative de-tokenizer to produce high-fidelity visual outputs. To address diverse decoding needs, we utilize two complementary de-tokenizers: a fast autoregressive model and a diffusion-based model. To enhance modality fusion, we investigate advanced pre-training tasks, demonstrating improvements in both visual understanding and generation. Experiments across benchmarks show that **Tar** matches or surpasses existing multimodal LLM methods, achieving faster convergence and greater training efficiency. All code, models, and data will be made publicly available.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 当前多模态大语言模型（MLLM）在视觉理解和生成任务上通常采用不同的表示方法：理解使用连续的语义特征（如CLIP），生成使用像素级的离散令牌（如VQVAE）。这种分离限制了跨模态的统一推理，也增加了模型设计的复杂性。
- 论文希望实现一个**共享的、离散的、语义对齐的表示**，使视觉理解和生成能在同一框架内无缝协作，无需模态特定组件，从而简化模型、提升可扩展性并改善跨模态任务（如交替式生成、多轮编辑）。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过文本对齐分词器（TA-Tok）将图像转化为离散令牌，这些令牌与LLM的文本词汇表共享同一个语义空间，使MLLM（Tar）能够用统一的接口处理图像和文本的输入输出。
- **关键技术细节**：
  - **TA-Tok**：
    - 使用SigLIP2编码器提取连续特征，通过**尺度自适应池化**（Scale-Adaptive Pooling）获得多粒度特征（81、169或729个令牌）。
    - 使用**文本对齐码本**（Text-Aligned Codebook）：从预训练LLM的嵌入中选取top-k个代表性嵌入，通过可学习的投影矩阵映射得到码本。码本与LLM词嵌入共享维度，可直接作为视觉嵌入。
    - 训练时使用特征重建损失（与冻结的SigLIP2教师对齐）和码本损失（含stop-gradient操作）。
  - **生成式去分词器**（Generative De-Tokenizers）：
    - **自回归去分词器**（AR-DTok）：将TA-Tok的离散令牌作为条件，自回归预测VQVAE的像素令牌。
    - **扩散去分词器**（Dif-DTok）：将TA-Tok令牌作为条件输入扩散模型（基于SANA-0.6B微调）。
  - **统一MLLM建模**（Tar）：
    - 扩展LLM词嵌入矩阵，加入TA-Tok码本中的视觉令牌作为新增词汇。
    - 使用标准交叉熵损失，输入输出序列中包含文本和视觉令牌。
    - 预训练任务除常见的图像到文本（I→T）、文本到图像（T→I）、纯文本外，额外引入**图像到图像（I→I）**和**文本-图像到图像（TI→I）**任务，以加强模态融合。
- **训练流程**：
  - 先训练TA-Tok（200M图像），然后训练去分词器（AR-DTok从零训练，Dif-DTok微调），最后端到端训练MLLM（预训练+监督微调）。

## 3. 实验设计：数据集、基准、对比方法

- **理解任务基准**：POPE、MME、MMB、SEED、GQA、MMMU。
- **生成任务基准**：GenEval、DPG Bench。
- **对比方法**：
  - 仅理解模型：LLaVA系列、Qwen-VL-Chat、Emu3-Chat等。
  - 统一模型：Show-o、Janus/Janus-Pro、Chameleon、LWM、ILLUME、UniTok、VILA-U、MetaMorph等。
- **训练数据**：
  - TA-Tok：LAION-5B中100M原始+100M美学过滤图像。
  - 去分词器：50M美学图像（256px）、23M合成图像（512px/1024px）。
  - MLLM预训练：32M I2T（LLaVA-Recap+DataComp）、23M T2I（合成图像）、15M I2I/TI2I（合成）、28.5M文本（Magpie等）。监督微调：1.6M I2T、1.6M T2I、1M文本。
- **消融实验**：
  - 对比不同视觉表示方法（VQVAE、Janus、Hybrid、TA-Tok）在理解和生成上的表现（图5）。
  - 码本初始化方式（随机 vs. 预对齐 vs. TA-Tok码本，表3）。
  - 去分词器类型与规模（表4）。
  - 尺度自适应池化对理解和生成的影响（表5）。
  - 共享表示 vs. 分离表示对联合训练的影响（表6）。
  - 预训练任务（I2I、TI2I）的增益（表7）。
  - 自我反思策略（Self-Reflect）的消融（表10）。
  - 码本设置（大小、维度）的影响（表9）。

## 4. 资源与算力

- 论文附录（表8）给出了各阶段的**训练参数**（学习率、batch size、epoch数等），但**未明确说明使用的GPU型号、数量及总训练时长**。例如：
  - TA-Tok：batch size 512，总样本200M，cosine学习率。
  - MLLM预训练：batch size 1024，总样本100M。
- 从模型规模（最大7B）和训练数据量推测，算力需求较大，但论文未提供具体算力成本信息。这是论文的一个信息缺口。

## 5. 实验数量与充分性

- **实验数量**：丰富。包含主结果（表1、2）、7组以上消融实验（图5、表3-10）、多个生成可视化示例（图1、图8）。
- **充分性与公平性**：
  - 控制变量：在比较不同表示方法时，使用相同子集数据（10M/20M等）和相同训练配置。
  - 基准覆盖广：理解7个、生成2个（含细粒度子指标）。
  - 消融实验系统：逐一验证每个关键组件（码本初始化、去分词器、尺度、联合训练、预训练任务、自我反思）。
  - 对比方法全面，包括近期统一模型（Janus-Pro、ILLUME等）和专用模型。
  - **局限性**：部分消融仅在小数据量（10M-20M）下进行，可能不能完全反映大规模性能；未报告多次运行的标准差，但论文声明了低方差。

## 6. 论文的主要结论与发现

- **主要结论**：
  1. 使用离散、语义、文本对齐的表示（TA-Tok）可以统一视觉理解和生成，在理解任务上匹配甚至超越连续语义表示方法，在生成任务上显著优于像素级或混合表示。
  2. 共享表示使理解和生成相互促进：联合训练相比单独训练在生成任务上提升5.3%-8.1%，理解任务也略有提升。
  3. 尺度自适应池化可兼顾不同任务对精度的需求：理解需要更多令牌，生成中等令牌即可。
  4. 自回归和扩散两种去分词器各有优势，均能有效重建高质量图像。
  5. 引入图像到图像和文本-图像到图像预训练任务能进一步缩小理解与生成的差距。
  6. 自我反思策略（利用自身理解能力评估生成质量）可提升生成对齐度。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - **文本对齐码本**：直接将LLM词嵌入投影为视觉码本，无需额外对齐阶段，简化训练。
  - **尺度自适应机制**：灵活控制视觉令牌数量，适应不同任务的计算-精度权衡。
  - **生成式去分词器双路线**：AR和Diffusion结合，兼顾速度和保真度。
  - **新增预训练任务（I2I, TI2I）**：增强模态融合，提升生成质量。
- **实验设计**：
  - 系统比较不同视觉表示范式（VQVAE、Janus、Hybrid、TA-Tok）的优势，控制变量充分。
  - 消融实验覆盖广泛，逐项验证每个组件有效性。
  - 提供自我反思推理策略，利用自身能力实现无需外部模型的生成后改进。

## 8. 不足与局限

- **实验覆盖**：
  - 未在更大规模（如13B/70B）的LLM上验证，结论的泛化性有待确认。
  - 未报告多次运行的统计误差（标准差），影响结果可靠性评估。
  - 未明确指出计算资源（GPU型号、数量、训练时长），不利于可重复性。
- **方法局限**：
  - **量化误差**：向量量化导致信息损失，在细粒度任务（如OCR）上表现不佳，论文承认这一点并提出未来用更长序列缓解。
  - **重建精度**：生成式去分词器虽能生成高质量图像，但输入图像的重建保真度不如专用VAE（如VQVAE），论文指出可通过训练超分辨率模型改进。
  - **推理速度**：扩散去分词器计算开销大，虽可并行但整体仍比AR慢。
- **偏差风险**：
  - 合成数据依赖：23M合成图像由FLUX生成，可能引入模型偏好和分布偏差。
  - 自我反思策略依赖模型自身理解能力，若理解存在偏见，可能放大错误。
- **应用限制**：当前模型为研究原型，未进行安全过滤、偏见测试，直接部署需额外防护。

（完）
