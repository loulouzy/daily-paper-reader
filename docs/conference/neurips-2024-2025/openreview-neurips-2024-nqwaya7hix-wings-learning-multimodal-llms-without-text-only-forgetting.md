---
title: "Wings: Learning Multimodal LLMs without Text-only Forgetting"
title_zh: Wings：无纯文本遗忘的多模态大语言模型学习
authors: "Yi-Kai Zhang, Shiyin Lu, Yang Li, YanQing Ma, Qing-Guo Chen, Zhao Xu, Weihua Luo, Kaifu Zhang, De-Chuan Zhan, Han-Jia Ye"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=nqWaya7hiX"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型无文本遗忘学习
tldr: 多模态大语言模型在继续训练时容易遗忘纯文本指令。本文发现该遗忘与注意力偏移有关，提出Wings模型，通过添加低秩残差注意力块作为模态学习者，补偿注意力偏移，使模型在图文和纯文本任务上均保持优良表现。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1579, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1475, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1033, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1530, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 828, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1111, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nqwaya7hix/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 831, \"height\": 502, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nqwaya7hix/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 928, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nqwaya7hix/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1462, \"height\": 1041, \"label\": \"Table\"}]"
motivation: MLLM在多模态训练中会灾难性遗忘纯文本指令。
method: 分析注意力层发现文本遗忘源自图文注意力偏移，设计低秩残差注意力块以补偿偏移。
result: Wings在纯文本和图文指令上都表现出色，有效解决了遗忘问题。
conclusion: 为MLLM同时处理图文和纯文本任务提供了有效解决方案。
---

## Abstract
Multimodal large language models (MLLMs), initiated with a trained LLM, first align images with text and then fine-tune on multimodal mixed inputs. However, during the continued training, the MLLM catastrophically forgets the text-only instructions that the initial LLM masters. In this paper, we present Wings, a novel MLLM that excels in both text-only and multimodal instructions. By examining attention across layers of MLLM, we find that *text-only forgetting* is related to the attention shifts from pre-image to post-image text. From that, we construct an additional Low-Rank Residual Attention (LoRRA) block that acts as the "modality learner" to expand the learnable space and compensate for the attention shift. The complementary learners, like "wings" on either side, are connected in parallel to each layer's attention block. The LoRRA mirrors the structure of attention but utilizes low-rank connections to ensure efficiency. Initially, image and text inputs are aligned with visual learners operating alongside the main attention, balancing focus on visual elements. Later, textual learners are integrated with token-wise routing, blending the outputs of both modality learners collaboratively. Our experimental results demonstrate that Wings outperforms equally-scaled MLLMs in both text-only and visual question-answering tasks. Wings with *compensation of learners* addresses text-only forgetting during visual modality expansion in general MLLMs.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLM）在继视觉对齐与多模态微调之后，会灾难性地遗忘纯文本（text-only）指令能力，即“文本遗忘”现象。例如，原本强大的 LLM 在加入视觉模块训练后，在 MMLU、CMMLU 等纯文本基准上的性能显著下降。
- **背景意义**：实际应用中用户常先进行纯文本对话，再插入图像（交错对话），因此 MLLM 需要同时保持纯文本和多模态问答能力。现有方法（如回放纯文本/交错数据、切换 LLM 与 MLLM）存在额外计算开销或部署内存问题。本文旨在提出一种高效、不依赖大量回放数据的方案，在保持纯文本能力的同时提升多模态性能。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过分析 MLLM 各层注意力权重，发现文本遗忘与图像前后文本段落的注意力分布偏移（attention shift）相关。为此，在每层注意力模块旁并联两个低秩残差注意力（LoRRA）模块——视觉学习者（visual learner）和文本学习者（textual learner），作为“模态学习者”补偿注意力偏移。
- **关键技术细节**：
  - **MLLM-LAWS 指标**：定义层级别注意力权重比例，计算图像前后文本段落的注意力相关度（Pearson 相关系数）。发现正相关越强，纯文本性能越好。
  - **Low-Rank Residual Attention (LoRRA)**：类似于交叉注意力结构，但使用低秩矩阵（通过 W_a·W_b 分解）降低参数量。初始输出为零，确保训练开始时不影响主分支。
  - **视觉学习者**：输入为当前层隐藏状态（query）和原始视觉特征（key/value），在第一步对齐阶段单独训练。
  - **文本学习者**：输入为隐藏状态和原始文本特征，在第二步与视觉学习者一起联合训练。
  - **路由机制**：根据主分支的注意力权重，通过一个单层动态 MLP 生成每个 token 下视觉和文本学习者的加权系数，将两者输出加权相加到主分支注意力输出上。
- **训练流程**：
  - 第一阶段：冻结视觉编码器，仅训练投影层和视觉学习者（对齐图文）。
  - 第二阶段：加入文本学习者和路由，联合训练 LLM、投影层及两类学习者（指令微调）。
  - 推理时：纯文本指令关闭视觉学习者的路由权重；多模态指令则同时激活两类学习者。

## 3. 实验设计

- **使用的数据集与基准**：
  - 纯文本基准：MMLU、CMMLU、ARC-E/ARC-C、WinoGrande、OpenbookQA、RACE-M/H、WSC、CHID、HellaSwag、SIQA、PIQA、OCNLI、GSM8K、MBPP 等 16 个数据集。
  - 通用多模态基准：MMMU、MME、MMBench（中英文）、ScienceQA、SEED-Bench、AI2D、HallusionBench 等 8 个数据集。
  - 自建交错图像-文本（IIT）基准：从 MMLU、CMMLU、OpenbookQA、HellaSwag、MMMU、MMBench、SEED-Bench、AI2D 中采样，构建 6 种多轮对话配置（如纯文本、文本+图像等）。
- **对比的方法**：
  - 同等规模开源 MLLM：LLaVA v1.5、LLaVA-Next、DeepSeek-VL、Qwen-VL、InstructBLIP、ShareGPT4V、Monkey、IDEFICS、O-Flamingo v2 等 9 个 7B 级模型。
  - 高效小模型：DeepSeek-VL 1.3B、MiniCPM-V 2.4B。
  - 私有 API 模型：GPT-4、GPT-4V、Gemini Pro Vision。
- **消融实验**：对比不同学习率策略（统一大/小、分区）、不同训练组件（仅视觉学习者、仅文本学习者、完整 Wings）、不同参数高效模块（LoRA、Prefix-tuning）等。

## 4. 资源与算力

- **训练环境**：Wings base 和 Wings pro 使用 8×A100 GPU，分别训练约 1.5 天和 6 天。
- **Wings 1.8B** (小模型版)：使用 4×A100 GPU，训练约 5 天。
- **数据量**：Wings base 第一阶段约 1M 数据，第二阶段约 0.6M 指令；Wings pro 第一阶段相同，第二阶段约 2M 数据（含部分纯文本 QA 和多模态数据）。

## 5. 实验数量与充分性

- **实验数量**：论文共进行了三大类实验（纯文本、多模态、IIT 基准），包含 20 个纯文本数据集、8 个多模态数据集、6 种 IIT 配置。消融实验涉及学习率、训练组件、参数高效模块对比。
- **充分性与公平性**：
  - 在纯文本对比中，与相同骨干网络（Qwen1.5+SigLIP）的基线（普通 MLLM、LoRA 微调等）在相同数据下公平比较。
  - 在多模态对比中，涵盖了几乎所有主流开源 7B 级 MLLM，并与更大规模私有模型对比，体现性能定位。
  - 消融实验系统分析了各组件贡献，实验设计比较全面。
  - 不足：未提供多次运行的标准差或置信区间；未在更多 MLLM 骨干上验证通用性（仅用 Qwen1.5+SigLIP）。

## 6. 主要结论与发现

- Wings 在纯文本任务上显著优于同等骨干的基线 MLLM（如 MMLU 提升 9.37%，CMMLU 提升 9.36%，RACE-H 提升 11.90%），同时在多模态任务上也达到或超越当前 SOTA（如 MMBench 中英文、MMMU、ScienceQA 等）。
- 自建 IIT 基准中，Wings 在所有交错对话配置下均优于 LLaVA 系列，尤其在文本密集场景下优势更明显。
- 消融实验表明：分区学习率（投影层高 LR、其余低 LR）最佳；同时使用视觉和文本学习者比单独使用效果更好；LoRRA 比 LoRA/Prefix-tuning 更有效。

## 7. 优点

- **方法创新**：从注意力偏移角度解释文本遗忘，并提出轻量级并联 LoRRA 模块进行补偿，无需额外训练数据或模型切换。
- **高效性**：LoRRA 参数量仅为主分支的极小部分（三个数量级低于 MoE），且训练仅需少量额外资源。
- **通用性**：可作为插件集成到任何基于注意力的 MLLM 中；提供不同规模版本（7B、1.8B），兼顾性能与效率。
- **评估全面**：涵盖纯文本、多模态、交错对话多种场景，且构建了专门针对交错对话的基准。

## 8. 不足与局限

- **实验覆盖不足**：仅在 Qwen1.5+SigLIP 骨干上测试，未验证在其他 LLM（如 LLaMA、Mistral）或视觉编码器（如 CLIP）上的泛化性。
- **偏差风险**：部分纯文本数据集（如 CHID、OCNLI）在 MLLM 训练后性能反而提升，可能归因于训练数据语言多样性覆盖，而非 Wings 特有贡献。
- **局限性（自述）**：
  - 集成视觉学习者需要从对齐阶段开始重新训练，对于已有 MLLM 迁移成本较高。
  - 小规模模型（Wings 1.8B）性能仍有妥协。
  - 仍需少量纯文本数据进行回放以提升整体性能，并非完全零回放。
- **未提供统计显著性**：所有结果未给出标准差或置信区间，难以判断改进的稳定性。

（完）
