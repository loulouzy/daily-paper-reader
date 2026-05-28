---
title: "VisionLLM v2: An End-to-End Generalist Multimodal Large Language Model for Hundreds of Vision-Language Tasks"
title_zh: VisionLLM v2：面向数百项视觉语言任务的端到端通用多模态大语言模型
authors: "Jiannan Wu, Muyan Zhong, Sen Xing, Zeqiang Lai, Zhaoyang Liu, Zhe Chen, Wenhai Wang, Xizhou Zhu, Lewei Lu, Tong Lu, Ping Luo, Yu Qiao, Jifeng Dai"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=nvYDPF4LJK"
tags: ["query:llm-vlm"]
score: 10.0
evidence: 端到端通用多模态大语言模型
tldr: 传统MLLM仅限于文本输出。本文提出VisionLLM v2，通过超链接机制连接MLLM与任务特定解码器，统一视觉感知、理解和生成，支持数百项视觉语言任务，展示了通用多模态模型的能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1384, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 589, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 716, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 500, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 713, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 714, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 701, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 434, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 431, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 701, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 522, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 429, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1434, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 857, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 504, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1452, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1444, \"height\": 2380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 356, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 708, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 355, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 710, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1422, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1440, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1428, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1423, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1422, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nvydpf4ljk/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1408, \"height\": 570, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 780, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 583, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 543, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 826, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1408, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 546, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1428, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 832, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1440, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1445, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 461, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1445, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1327, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1426, \"height\": 998, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1496, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nvydpf4ljk/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1450, \"height\": 547, \"label\": \"Table\"}]"
motivation: 现有MLLM局限于文本输出，无法处理开放视觉任务。
method: 提出超链接机制实现MLLM与任务解码器之间的灵活信息与梯度传递。
result: 在目标定位、姿态估计、图像生成等任务上达到先进水平。
conclusion: 单一框架可支持丰富多样的视觉语言任务，向通用多模态智能迈进。
---

## Abstract
We present VisionLLM v2, an end-to-end generalist multimodal large model (MLLM) that unifies visual perception, understanding, and generation within a single framework. Unlike traditional MLLMs limited to text output, VisionLLM v2 significantly broadens its application scope. It excels not only in conventional visual question answering (VQA) but also in open-ended, cross-domain vision tasks such as object localization, pose estimation, and image generation and editing. To this end, we propose a new information transmission mechanism termed ``super link'', as a medium to connect MLLM with task-specific decoders. It not only allows flexible transmission of task information and gradient feedback between the MLLM and multiple downstream decoders but also effectively resolves training conflicts in multi-tasking scenarios. In addition, to support the diverse range of tasks, we carefully collected and combed training data from hundreds of public vision and vision-language tasks. In this way, our model can be joint-trained end-to-end on hundreds of vision language tasks and generalize to these tasks using a set of shared parameters through different user prompts, achieving performance comparable to task-specific models. We believe VisionLLM v2 will offer a new perspective on the generalization of MLLMs.

---

## 论文详细总结（自动生成）

# 中文总结：VisionLLM v2

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有多模态大语言模型（MLLM）仅能输出文本，无法处理开放式的视觉感知与生成任务（如目标检测、姿态估计、图像生成/编辑）。目前虽有一些方法通过文本消息或可学习嵌入连接外部工具，但存在信息传递效率低、无法端到端优化、难以扩展至多任务场景、任务冲突等问题。
- **研究动机**：开发一个端到端的通用MLLM，使其能统一视觉感知、理解和生成，覆盖数百种视觉语言任务，且性能接近专用模型。
- **整体含义**：VisionLLM v2首次在单一框架内实现从文本输出到多种视觉输出（框、掩码、关键点、图像）的扩展，为通用多模态智能提供了新范式。

## 2. 论文提出的方法论

- **核心思想**：采用**超链接（Super Link）**技术连接中心MLLM与多个任务特定解码器，实现灵活的信息传输和梯度回传，同时避免多任务冲突。
- **关键技术细节**：
  - **模型架构**：由图像编码器（CLIP-L/14）、区域编码器（处理视觉提示）、LLM（Vicuna-7B）以及多个任务解码器（Grounding DINO用于检测/分割、UniPose用于姿态估计、Stable Diffusion v1.5用于生成、InstructPix2Pix用于编辑）组成。
  - **超链接机制**：
    - **路由令牌（Routing Token）**：在LLM词表中添加特殊令牌（如`[DET]`、`[POSE]`、`[GEN]`），LLM预测该令牌时触发选择对应解码器。
    - **超链接查询（Super-Link Queries）**：随机初始化的可学习嵌入，绑定到路由令牌后送入LLM，提取任务特定信息，经MLP投影后传入解码器作为条件。不同解码器使用独立的查询集，避免任务冲突。
  - **训练策略**（三阶段）：
    - **阶段1（多模态训练）**：先预训练对齐（冻结LLM），再指令微调（全参数），构建强视觉对话模型（VisionLLM v2-Chat）。
    - **阶段2（多能力微调）**：加入任务解码器，同时使用对话数据和视觉任务数据联合训练，仅微调LLM输入/输出嵌入和解码器，保留对话能力。
    - **阶段3（解码器专用微调）**：冻结LLM和编码器，仅训练解码器和超链接查询（12 epochs），使其充分收敛。
- **算法流程**（文字说明）：用户输入图像/文本/视觉提示后，LLM解析指令并生成文本响应；若需执行视觉任务，LLM输出对应路由令牌，超链接查询自动追加并提取条件特征，送入指定解码器；解码器输出（框、掩码、关键点、图像等）作为最终结果。

## 3. 实验设计

- **数据集**：从数百个公开数据集中精心收集整理。阶段1使用ShareGPT4V、All-Seeing、VQAv2、Visual Genome等；阶段2/3增加COCO、RefCOCO/+/g、ADE20K、LAION-Aesthetics、MMIC（自定义多模态上下文数据集）等，覆盖自然场景、医学、遥感、工业等多个领域。
- **Benchmark**：评估涵盖多模态对话（VQAv2、GQA、MME、MMBench等）、区域识别（COCO、LVIS、PACO）、视觉常识推理（VCR）、目标检测（COCO、CrowdHuman）、实例分割（COCO）、姿态估计（COCO、CrowdPose、AP-10K等）、图像生成/编辑、零样本检测（OdinW13）、上下文分割/标注等。
- **对比方法**：包括InstructBLIP、LLaVA-1.5/NeXT、Shikra、Qwen-VL-Chat、InternVL、Grounding DINO、UniPose、GLEE、LISA、PSALM等任务专用或通用模型。

## 4. 资源与算力

- **阶段1**：预训练64块A100（80G），微调64块A100，总batch size 1024，耗时约5天。
- **阶段2**：128块A100，batch size 256，耗时约3天。
- **阶段3**：128块A100，batch size 256，12 epochs，耗时约10天。
- 均采用DeepSpeed bf16混合精度训练。

## 5. 实验数量与充分性

- 共进行了**10余组主要实验**（各基准测试）和**6组以上消融实验**（超链接查询数量、共享vs独立查询、多任务相互影响、一阶段vs三阶段训练、超链接查询vs令牌嵌入等）。
- 实验覆盖了**视觉感知、理解、生成三大类**任务，并包含**常见域和长尾域**（医学、遥感、工业）、**弱交互到强交互**（封闭集到开放集、视觉提示+语言提示）。
- 对比了**当前最先进的专用模型和通用模型**，结果充分展示了方法的有效性。
- 实验设计**公平**：使用相同骨干（Swin-T）对比，报告单参数通用模型结果；消融实验控制变量，分析合理。

## 6. 论文的主要结论与发现

- VisionLLM v2是首个端到端支持**数百个视觉语言任务**的通用MLLM，在多数任务上达到或接近专用模型水平。
- **超链接技术**有效解决了多任务场景下的解码器选择、信息传递和任务冲突问题。
- **三阶段训练策略**在保持基础对话能力的同时，赋予模型丰富的新能力。
- 模型具有**开放性**（开放集检测/分割/姿态）和**多模态上下文能力**（通过少量示例即可推广到新任务）。

## 7. 优点

- **端到端统一框架**：将感知、理解、生成集成于一处，无需外部工具串联。
- **超链接机制巧妙**：同时实现路由、信息提取和梯度回传，并自然避免多任务冲突。
- **训练数据系统整合**：从数百个数据集中规范化构建指令模板，支撑大规模多任务学习。
- **通用性与可扩展性**：支持多种输入/输出模态（文本、框、掩码、关键点、图像），用户可通过多轮对话灵活组合任务。
- **实验全面且具有说服力**：覆盖丰富任务和领域，消融实验深入，结论可靠。

## 8. 不足与局限

- **训练阶段复杂**：三阶段流程需分别调整超参数，实施成本较高。
- **下游工具集成尚浅**：仅初步验证了与Grounding DINO、UniPose、Stable Diffusion等工具的连接，更多工具（如视频理解、3D任务）未探索。
- **某些任务性能略逊于专用模型**：如语义分割（ADE20K）上因联合训练比例低，不如专门训练模型；交互分割在冻结区域编码器情况下落后于PSALM。
- **计算资源需求大**：需128块A100 GPU进行阶段2/3训练，对资源要求较高。
- **未讨论模型偏见、安全性等社会影响问题**；同时缺乏对错误传播（如LLM误触发错误解码器）的鲁棒性分析。
- **未报告实验误差线**，结果的统计显著性未明确。

（完）
