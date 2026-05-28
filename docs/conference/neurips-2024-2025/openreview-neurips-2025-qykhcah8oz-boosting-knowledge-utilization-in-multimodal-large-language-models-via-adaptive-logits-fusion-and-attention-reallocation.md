---
title: Boosting Knowledge Utilization in Multimodal Large Language Models via Adaptive Logits Fusion and Attention Reallocation
title_zh: 通过自适应Logits融合和注意力重分配提升多模态大语言模型的知识利用
authors: "Wenbin An, Jiahao Nie, Feng Tian, Haonan Lin, mingxiang cai, Yaqiang Wu, QianYing Wang, Xiaoqin Zhang, Shijian Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=qYkhCah8OZ"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型知识利用
tldr: 多模态大语言模型在知识密集型任务中常受限于参数知识有限且过时。本文针对多模态检索增强生成中模型未能充分利用检索知识的问题，提出自适应logits融合和注意力重分配方法，缓解注意力偏置和参数知识与检索知识之间的冲突。实验表明该方法显著提升了MLLM的知识利用效率和任务性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 618, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 754, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 816, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qykhcah8oz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 747, \"height\": 447, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 840, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 1741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 1218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 694, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 845, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 718, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 834, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 711, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qykhcah8oz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 699, \"height\": 238, \"label\": \"Table\"}]"
motivation: 现有MLLM在知识密集型任务中难以充分利用检索到的上下文知识，存在注意力偏置和知识冲突问题。
method: 设计自适应logits融合模块平衡参数知识和检索知识的贡献，同时通过注意力重分配机制调整模型对不同token的关注。
result: 在多个知识密集型基准上，该方法显著优于现有MLLM，提升了答案准确性和知识利用率。
conclusion: 自适应融合和注意力重分配是提升MLLM知识利用的有效手段，可推广至其他多模态场景。
---

## Abstract
Despite their recent progress, Multimodal Large Language Models (MLLMs) often struggle in knowledge-intensive tasks due to the limited and outdated parametric knowledge acquired during training. Multimodal Retrieval Augmented Generation addresses this issue by retrieving contextual knowledge from external databases, thereby enhancing MLLMs with expanded knowledge sources. 
However, existing MLLMs often fail to fully leverage the retrieved contextual knowledge for response generation. We examine representative MLLMs and identify two major causes, namely, attention bias toward different tokens and knowledge conflicts between parametric and contextual knowledge. To this end, we design Adaptive Logits Fusion and Attention Reallocation (ALFAR), a training-free and plug-and-play approach that improves MLLM responses by maximizing the utility of the retrieved knowledge. Specifically, ALFAR tackles the challenges from two perspectives. First, it alleviates attention bias by adaptively shifting attention from visual tokens to relevant context tokens according to query-context relevance. Second, it decouples and weights parametric and contextual knowledge at output logits, mitigating conflicts between the two types of knowledge. As a plug-and-play method, ALFAR achieves superior performance across diverse datasets without requiring additional training or external tools. Extensive experiments over multiple MLLMs and benchmarks show that ALFAR consistently outperforms the state-of-the-art by large margins. Our code and data are available at https://github.com/Lackel/ALFAR.

---

## 论文详细总结（自动生成）

# 论文总结：Boosting Knowledge Utilization in Multimodal Large Language Models via Adaptive Logits Fusion and Attention Reallocation

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在知识密集型任务（如视觉问答）中表现不佳，主要原因有二：
  - **参数知识有限且过时**：MLLMs 在训练中获取的知识存在局限性和时效性问题。
  - **检索知识利用不足**：尽管多模态检索增强生成（MRAG）可以引入外部知识，但现有 MLLMs 仍难以充分利用检索到的上下文知识。
- **具体瓶颈**：
  - **注意力偏置（Attention Bias）**：模型在浅层对图像 token 的注意力远高于上下文 token，且对上下文 token 的注意力分布均匀，无法聚焦于查询相关部分。
  - **知识冲突（Knowledge Conflicts）**：参数知识与检索到的上下文知识不一致时，模型倾向于依赖参数知识，导致对上下文的利用不足；但当上下文噪声大时，参数知识又有帮助，需动态平衡。
- **研究目标**：设计一种无需训练、即插即用的方法，最大化检索知识的利用，同时平衡参数知识与上下文知识。

## 2. 方法论：ALFAR（Adaptive Logits Fusion and Attention Reallocation）

- **核心思想**：通过两个轻量级模块协同工作，无需额外训练或外部工具：
  1. **注意力重分配（Attention Reallocation）**：缓解注意力偏置。
  2. **自适应 logits 融合（Adaptive Logits Fusion）**：缓解知识冲突。

### 2.1 注意力重分配

- **针对图像 token 注意力过高**：根据检索相似度 α（公式1）动态降低对图像 token 的注意力权重。  
  公式：`Â_ni = (1 - β) · A_ni`，其中 `β = k·α`，`k` 为缩放因子（设为0.4）。
- **针对上下文 token 注意力均匀**：计算每个上下文 token 与查询的关联度 ω_j（基于注意力权重），然后增强相关 token 的注意力。  
  公式：`Â_nj = (1 + γ_j) · A_nj`，其中 `γ_j = k·ω_j`。
- 修改后的注意力矩阵经 softmax 重新归一化，用于后续计算。

### 2.2 自适应 logits 融合

- **解耦参数知识与上下文知识**：
  - 参数知识 logits：仅用图像和查询作为输入，无上下文。
  - 上下文知识 logits：使用带有上下文的输入（经过注意力重分配）。
- **动态权重**：利用模型对图像和上下文 token 的注意力分布作为可靠性的代理度量（λ_tv 和 λ_tc）。
- **融合公式**（公式11）：  
  `p(y_t) ~ softmax( (1 + λ_tc/λ_tv) · logit_c - (1 - λ_tv/λ_tc) · logit_p )`  
  该公式使模型在上下文可靠时更多依赖上下文，参数知识可靠时更多依赖参数知识，同时保持互补。

## 3. 实验设计

### 3.1 数据集与基准

- **自由生成数据集**：
  - Human（高质量信息搜索数据集）
  - INFOSEEK wiki（Validation 集）
- **多选判别数据集**：
  - InfoSeek（多选知识密集型）
  - ViQuAE（多选）
- **基于知识的数据集**：
  - OK-VQA、AOK-VQA、Encyclopedic VQA（E-VQA）
- **知识库**：Wikipedia dumps（含图像）、GPT-3.5 生成的 OK-VQA/AOK-VQA 知识库、iNaturalist 数据等。

### 3.2 对比方法

- **MLLM 基线**：LLaVA-1.5（7B/13B）、InstructBLIP（7B/13B）、Shikra（7B）、MiniGPT-4（7B）、LLaVA-Next（7B）、Qwen2.5-VL（3B）。
- **训练无关解码方法**：Regular、Parametric、CD、AdaCAD、Entropy、CAD、COIECD、VCD、AGLA（共9种对比方法）。

### 3.3 实现细节

- 使用 CLIP-ViT-L/14-336 作为检索器，取 top-1 知识作为上下文。
- 缩放因子 k=0.4，自适应合理性约束 β=0.7。
- 多模态采样解码策略，并在不同解码策略（Top-p、Top-k、温度、贪心等）下验证鲁棒性。
- 每组实验运行3次报告均值和方差。

## 4. 资源与算力

- **文中明确提及**：所有实验在四块 NVIDIA RTX 3090 GPU 上进行。
- **训练时长**：未明确给出具体训练时间，但方法为训练无关（training-free），因此无训练开销；推理时间与对比方法相当（表7显示单样本约0.62-0.73秒，约1.35-1.46倍于Regular方法）。

## 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 主实验：在3大类共7个数据集上，使用6种不同 MLLM 骨干（含不同尺寸），对比9种方法。
  - 消融实验：针对注意力重分配、logits 融合、自适应权重三个组件进行消融（表5）。
  - 鲁棒性实验：不同检索器（6种CLIP变体）、不同解码策略（6种）、不同知识数量（1-4个）、不同干预层（浅/中/深层）。
  - 可扩展性实验：更大模型（13B）以及不同MLLM。
  - 定性分析：注意力分布可视化、生成示例对比。
- **公平性**：所有对比方法根据官方代码或论文复现，采用相同的自适应合理性约束，报告三次运行均值和方差，实验设置透明。

## 6. 主要结论与发现

- ALFAR **在所有数据集和所有 MLLM 骨干上一致优于 Regular 解码**，并大幅超越现有 SOTA 解码方法，提升约 2%~15% VQA 准确率。
- 消融实验验证了每个组件的有效性：注意力重分配和 logits 融合单独即可提升性能，自适应权重进一步增益。
- 方法对**检索质量**和**解码策略**均具有鲁棒性：即使低质量检索也能通过自适应融合保持性能。
- **可扩展性强**：在更大模型（13B）上同样有效。
- 定性分析显示：ALFAR 能够纠正因注意力偏置或知识冲突导致的错误回答，使模型聚焦于正确上下文。

## 7. 优点

- **训练无关、即插即用**：无需微调或外部工具，可直接应用于任意 MLLM。
- **高效**：推理时间与现有最先进方法相当（约1.35-1.46倍于基线），但性能显著提升。
- **设计直观、理论清晰**：基于对注意力偏置和知识冲突的实证分析，提出针对性解决方案。
- **全面实验验证**：覆盖多种 MLLM、数据集、解码策略、检索设置，证实通用性和鲁棒性。
- **开源代码和数据**：促进可复现性。

## 8. 不足与局限

- **需要访问模型参数**：无法应用于黑盒 API 模型（如 GPT-4），因为方法需要获取注意力权重和 logits。
- **对长上下文利用有限**：当检索多个知识（如4个）时，性能提升变缓，表明 MLLM 在长上下文中提取相关信息的瓶颈仍未完全解决。
- **缩放因子 k 为固定超参（0.4）**：虽然实验显示鲁棒，但在极端噪声或高质量检索场景下，自适应机制可能不够精细。
- **实验仅覆盖英文知识和问答**：未在多语言或领域特定任务上测试。
- **未讨论安全与公平性风险**：虽然提及了潜在正面影响（如医疗、自动驾驶），但未深入分析模型增强后可能产生的偏见或错误传播风险。

（完）
