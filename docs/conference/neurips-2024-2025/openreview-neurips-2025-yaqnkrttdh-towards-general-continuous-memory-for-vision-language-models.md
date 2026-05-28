---
title: Towards General Continuous Memory for Vision-Language Models
title_zh: 面向视觉语言模型的通用连续记忆
authors: "Wenyi WU, Zixuan Song, Kun Zhou, Yifei Shao, Zhiting Hu, Biwei Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=YaQnKRtTdh"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型使用连续记忆增强多模态知识
tldr: 针对视觉语言模型在复杂推理任务中需要外部记忆但现有方法导致上下文过长的问题，本文提出使用连续记忆——一组紧凑的密集嵌入来表示多模态和多语言知识。该方法避免了图像文本令牌的长序列拼接，保持上下文长度可控，同时使VLM能够有效存取外部知识，在多项多模态推理任务上取得性能提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 662, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 545, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1378, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 647, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1425, \"height\": 1029, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 878, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1427, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 978, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 796, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1338, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaqnkrttdh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 837, \"height\": 565, \"label\": \"Table\"}]"
motivation: 现有VLM在复杂多模态推理中需外部记忆，但简单拼接图像文本令牌会急剧增加上下文长度。
method: 提出连续记忆（密集嵌入）作为紧凑的知识表示，集成到VLM中，无需长序列。
result: 在多个多模态推理基准上，连续记忆方法以更低计算成本取得更好或相当的性能。
conclusion: 连续记忆为VLM提供了一种高效、可扩展的外部知识整合方式。
---

## Abstract
Language models (LMs) and their extension, vision-language models (VLMs), have achieved remarkable performance across various tasks. However, they still struggle with complex reasoning tasks that require multimodal or multilingual real world knowledge. To support such capabilities, an external memory system that can efficiently provide relevant multimodal information is essential. Existing approaches generally concatenate image and text tokens into a long sequence as memory, which, however, may drastically increase context length and even degrade performance. In contrast, we propose using continuous memory-a compact set of dense embeddings-to more effectively and efficiently represent multimodal and multilingual knowledge. Our key insight is that a VLM can serve as its own continuous memory encoder. We empirically show that this design improves performance on complex multimodal reasoning tasks. Building on this, we introduce a data-efficient and parameter-efficient method to fine-tune the VLM into a memory encoder, requiring only 1.2\% of the model’s parameters and a small corpus of 15.6K self-synthesized samples. Our approach CoMEM utilizes VLM's original capabilities to encode arbitrary multimodal and multilingual knowledge into just 8 continuous embeddings. Since the inference-time VLM remains frozen, our memory module is plug-and-play and can be flexibly integrated as needed. Extensive experiments across eight multimodal reasoning benchmarks demonstrate the effectiveness of our approach. Code and data is publicly released here https://github.com/WenyiWU0111/CoMEM.

---

## 论文详细总结（自动生成）

好的，这是对论文《Towards General Continuous Memory for Vision-Language Models》的详细中文总结：

### 论文核心问题与整体含义（研究动机和背景）

*   **研究背景**：尽管大型语言模型（LLM）和视觉语言模型（VLM）性能优异，但在需要多模态或多语言世界知识的复杂推理任务中仍面临挑战。这是因为模型内部知识有限。
*   **核心问题**：为VLM引入外部记忆是解决方案之一，但现有方法（如RAG）将图像和文本直接拼接为长序列，这会导致：
    *   输入上下文长度急剧增加。
    *   内容过长，模型难以有效利用，甚至性能下降。
    *   基于离散令牌的记忆表示效率低下。
*   **研究动机**：探索一种更高效、更紧凑的记忆表示方式，即**连续记忆**（一组密集的嵌入向量），以替代传统的离散令牌拼接。

### 论文提出的方法论：核心思想、关键技术细节

1.  **核心思想**：提出 **CoMEM** 方法，核心洞察是 **VLM 自身可以作为其连续记忆编码器**。无需额外训练一个独立的巨型编码器，利用VLM强大的语义理解和压缩能力，将外部知识编码成紧凑的连续向量。
2.  **关键技术细节**：
    *   **VLM 作为记忆编码器**：给定一个外部知识项（图片+文本），直接使用目标VLM进行编码，提取其最后一层的隐藏状态（连续嵌入）作为该知识的表示。论文通过实验验证，即使不训练，这种简单的“VLM即记忆”方法也能提升性能。
    *   **高效压缩（Q-Former）**：为达到更高的压缩率，引入一个轻量级的 **Q-Former** 模块。该模块使用少量可学习的查询向量（论文中设为8个），通过交叉注意力机制从VLM编码的大量隐藏状态中提取关键信息，最终将每个知识项压缩成**仅8个连续嵌入向量**。
    *   **即插即用机制**：在推理时，将压缩后的8×N个连续记忆向量拼接起来，直接插入到冻结的VLM的输入嵌入序列之前。VLM像处理正常输入一样处理这些连续向量，无需修改模型参数。
    *   **高效训练策略**：
        *   **参数高效微调**：仅对VLM中少量**LoRA**矩阵和Q-Former模块进行微调，总共只更新模型 **1.2%** 的参数（约200M）。
        *   **数据高效自合成**：训练数据全部由VLM自身合成。从InfoSeek、EVQA等数据集中选取问题，用CLIP检索相关WIT知识，构成RAG输入并让VLM生成答案，保留正确样本。最终只用了 **15.6K** 自合成样本。

### 实验设计：数据集、基准与方法对比

*   **数据集与基准（Benchmark）**：在 **8个** 知识密集型多模态推理基准上进行评估：
    *   **英语基准（6个）**：InfoSeek, OVEN, MRAG-Bench, OK-VQA, A-OKVQA, ViQuAE.
    *   **多语言基准（2个）**：CVQA, 多语言版本的InfoSeek（翻译为5种语言）。
*   **对比方法**：
    *   **基线VLM**：LLaVA-v1.5/1.6, LLaMA3, InternLM2.5vl, mPLUG-Owl3, Qwen2/2.5-VL。
    *   **传统RAG方法**：上述基线VLM加上简单的拼接式RAG。
    *   **高级RAG方法**：当前先进工作，如Wiki-LLaVA, RORA-VLM, EchoSight, ReflectiVA。
*   **消融与深入分析**：
    *   验证“VLM即记忆”的有效性（与RAG、令牌剪枝FastV对比）。
    *   研究不同压缩率下的性能变化。
    *   长上下文理解能力实验（测试Top-3到Top-50的检索数量）。
    *   迁移性实验（将VLM编码的视觉记忆迁移到纯文本LLM中使用）。
    *   图像描述（COCO Captioning）和纯推理任务（MMMU, MathVista）上的泛化性测试。
    *   不同嵌入数量（4, 8, 16, 24）的消融实验。

### 资源与算力

*   **训练资源**：论文明确说明，整个训练过程可在一块 **NVIDIA H100 GPU** 上完成，耗时约 **20小时**。这得益于其参数和数据的高效性。

### 实验数量与充分性

*   **实验数量**：实验非常丰富，覆盖了：
    *   8个主要基准的主实验结果。
    *   1组“VLM即记忆”的预研实验。
    *   1组针对多语言的详细结果（5种语言）。
    *   多组深入分析（长上下文、迁移性、压缩率影响）。
    *   2项额外的泛化性实验（图像描述、推理任务）。
    *   1组嵌入大小消融实验。
    *   1组训练数据/参数量的效率实验。
*   **充分性与公平性**：实验设计非常充分且客观。对比了三大类、18种不同模型，基准覆盖全面。实验设置（如检索知识库、检索数量）保持公平。同时验证了模型在未见过的数据集（如OVEN, A-OKVQA）上的泛化能力，增强了结论的可靠性。

### 论文的主要结论与发现

1.  **VLM可作为自身编码器**：VLM自身产生的连续嵌入具有良好的语义对齐性和可压缩性，略加利用即可提升性能。
2.  **高效性**：CoMEM能以极低的代价（1.2%参数，15.6K数据）进行训练，并获得显著性能提升。
3.  **有效性**：在8个多模态推理基准上，CoMEM一致地优于基线VLM、传统RAG及多数先进方法。在英语言语数据集上平均提升约 **8%**，在多语言任务上提升约 **5%**。
4.  **长上下文鲁棒性**：与RAG方法性能随上下文增长而下降不同，CoMEM在长上下文（Top-50检索）下性能依然稳定出色。
5.  **跨模型迁移性**：VLM编码的视觉连续记忆可以有效迁移到纯文本LLM，使其具备一定的视觉知识理解能力。
6.  **强泛化性**：在图像描述、MMMU、MathVista等未见任务上也能带来性能提升，表明记忆向量具有通用性。

### 优点：方法或实验设计上的亮点

1.  **方法简洁高效**：核心思路“VLM作自身编码器”非常优雅，避免了大规模预训练和复杂的模型对齐。参数和数据的极致高效性是其最大亮点。
2.  **即插即用**：推理时VLM完全冻结，记忆模块可随意插拔，部署灵活，应用友好。
3.  **高压缩率**：将每个知识项压缩至极致的8个向量，远超传统方法，解决了上下文过长问题。
4.  **多语言支持**：在数据自合成阶段引入多语言样本，使模型天然支持多语言记忆，这一点是很多现有工作忽略的。
5.  **实验全面客观**：实验设计逻辑清晰，从验证性实验到主结果，再到深入分析和泛化性测试，环环相扣，论据充分。对不同方法的特性（如长上下文处理能力）进行了针对性剖析。

### 不足与局限（包含原文中提到的和可推断的）

1.  **评估基准的局限**：论文指出，虽然评估了8个基准，但大多数是静态的、合成的。在真实世界动态、嘈杂的输入（如网络数据、实时视频）场景下的表现尚待验证。
2.  **多智能体场景的未探索**：当前工作仅在单个VLM上验证。在需要多个模型或多智能体协作的复杂真实应用中，该连续记忆模块是否能在不同模型间有效传递和共享知识，还尚未研究。
3.  **模型的依赖**：该方法依赖于选定的VLM本身作为编码器。如果VLM本身能力不足（编码视觉信息能力差），记忆编码的有效性是否会打折扣？论文未讨论这种边界情况。
4.  **对检索质量的依赖**：该方法依赖于一个高质量的外部检索器（论文中使用CLIP）。如果检索到的知识本身不相关，那么即使编码得再好，也无法保证性能。论文对检索失败或噪声较大的情况未有太多分析。
5.  **“连续记忆”可解释性**：将知识压缩为8个连续向量，极大地提升了效率，但也牺牲了可解释性。相比于RAG直接显示的文本，我们无法直观地知道这些向量里到底“存”了什么知识。

（完）
