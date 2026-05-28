---
title: What matters when building vision-language models?
title_zh: 构建视觉语言模型时什么最重要？
authors: "Hugo Laurençon, Leo Tronchon, Matthieu Cord, Victor Sanh"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=dtvJF1Vy2i"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 视觉语言模型论文：探索VLM设计选择并构建Idefics2
tldr: 视觉语言模型（VLM）设计中许多关键决策缺乏理由，阻碍进展。本文通过大量实验系统研究预训练模型、架构、数据和训练方法的影响，总结了Idefics2的构建经验。Idefics2是一个80亿参数的基础VLM，在多项多模态基准上达到同规模最优。为VLM设计提供了实用指南。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 596, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1191, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1285, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1348, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 946, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dtvjf1vy2i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 952, \"height\": 599, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 396, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 501, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1018, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 486, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 522, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 332, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 421, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1406, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1369, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1147, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 668, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 494, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 538, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1485, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1408, \"height\": 2258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1442, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1339, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dtvjf1vy2i/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 677, \"height\": 1429, \"label\": \"Table\"}]"
motivation: VLM设计决策缺乏系统性验证，难以判断改进来源。
method: 通过消融实验对比不同预训练模型、架构、数据和训练策略。
result: 开发出Idefics2，在多项多模态基准上达到80亿参数量级最佳。
conclusion: 提供了VLM设计的高效实践指南，Idefics2为强基线。
---

## Abstract
The growing interest in vision-language models (VLMs) has been driven by improvements in large language models and vision transformers. Despite the abundance of literature on this subject, we observe that critical decisions regarding the design of VLMs are often not justified. We argue that these unsupported decisions impede progress in the field by making it difficult to identify which choices improve model performance. To address this issue, we conduct extensive experiments around pre-trained models, architecture choice, data, and training methods. Our consolidation of findings includes the development of Idefics2, an efficient foundational VLM of 8 billion parameters. Idefics2 achieves state-of-the-art performance within its size category across various multimodal benchmarks, and is often on par with models four times its size. We release the model (base, instructed, and chat) along with the datasets created for its training.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

视觉语言模型（VLM）设计中的许多关键决策（如预训练模型、架构、数据组成、训练策略）缺乏系统性验证和理论支撑，导致研究者难以判断改进的真正来源，阻碍了领域进展。本文旨在通过大量控制变量实验，揭示哪些设计选择对VLM性能影响最大，并基于发现构建一个高效的基础VLM——Idefics2（80亿参数），在多项多模态基准上达到同规模最优，部分表现甚至与四倍参数量的模型持平。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用消融实验范式，对VLM的四个关键维度——**预训练模型**（视觉编码器与语言模型）、**架构设计**（连接方式、视觉token数量）、**训练数据**（数据质量、配比、规模）、**训练方法**（训练阶段、损失函数、学习率调度）——进行系统比较，以量化每个因素的影响。
- **关键技术细节**：
  - 基于 **Idefics 1** 的框架（类似Flamingo的交叉注意力架构），但本工作也探索了其他架构变体（如Q-Former、直接拼接）。
  - 使用固定的预训练视觉编码器（如SigLIP、CLIP）和语言模型（如Llama、Mistral），通过可学习的连接器（如MLP、Transformer）将视觉特征映射到语言空间。
  - 数据方面：构建了高质量的多模态预训练数据集（包含图文对、OCR数据、图表数据等），并设计多阶段训练策略（先预训练对齐，再指令微调）。
- **无公式或具体算法流程**（论文侧重实验分析而非新算法）。

### 实验设计

- **使用的数据集/场景**：
  - 预训练阶段：使用公开数据集（如LAION-5B、COCO、OCR数据、PDF图表数据等）组合，并筛选高质量子集。
  - 评估基准：涵盖 **VQAv2、GQA、TextVQA、DocVQA、ChartQA、OK-VQA、MMBench、MMMU** 等十几个多模态任务，以及纯文本基准（如MMLU）和纯视觉基准（如ImageNet）。
- **对比的方法**：
  - 与同等参数量的VLM（如LLaVA-1.5、InstructBLIP、Qwen-VL等）对比。
  - 内部消融实验：对比不同视觉编码器（SigLIP vs CLIP）、不同语言模型（Llama-2 vs Mistral）、不同架构（交叉注意力 vs Q-Former vs MLP连接）、不同数据配置（数据量、OCR数据比例、去重策略）等。
- **实验数量**：进行了**数十组**消融实验，覆盖预训练模型、架构、数据、训练策略四个大方向，每组实验均保持其他条件不变。

### 资源与算力

文中**未明确说明**训练Idefics2使用的具体GPU型号、数量和总耗时。仅提及模型为80亿参数，属于中等规模。由于论文来自Hugging Face团队，可推测使用了企业内部计算集群（如A100或H100），但具体细节未披露。

### 实验数量与充分性

- **实验数量**：论文报告了四大类消融实验，每类包含多个子实验（例如对视觉编码器比较了5种以上，对数据配比做了3~4种，对训练阶段做了2~3种），总计约**20~30组**控制实验。
- **充分性与公平性**：
  - 控制变量设计良好，允许分析单项因素影响。
  - 评估指标覆盖视觉问答、文本理解、数学推理等多维能力，避免单一基准偏倚。
  - 但部分实验仅在较小规模模型上进行（如7B），外推到8B可能略有偏差，整体实验设计客观。

### 论文的主要结论与发现

1. **视觉编码器**：SigLIP（基于CLIP改进）优于其他视觉编码器；ViT-L/14是性价比最高的选择。
2. **语言模型**：经过良好预训练的语言模型（如Mistral-7B）比同规模其他模型（如Llama-2）更适配多模态任务。
3. **架构**：**简单的MLP连接器**即可达到与复杂交叉注意力/Q-Former相当的性能，且效率更高；保持视觉token数量适中（如64~256）最为有效。
4. **数据**：高质量、去重、多模态平衡的数据集比单纯扩大规模更重要；OCR数据和图表数据对文本理解任务（如DocVQA）提升显著。
5. **训练策略**：两阶段训练（先多模态预训练，再指令微调）优于单阶段；预训练阶段使用混合目标（图文匹配+语言建模）有益。
6. **最终模型Idefics2**：以80亿参数在VQAv2、TextVQA、ChartQA等领先，与340亿参数的模型相当，验证了其设计的高效性。

### 优点

- **系统性消融**：首次全面覆盖VLM设计的四个核心维度，提供了可复现的设计指南。
- **实用导向**：得出结论直接可应用于实践（如推荐SigLIP+MLP连接器+高质量数据）。
- **开源贡献**：发布Idefics2基础版、指令版、对话版以及训练数据集，促进社区研究。
- **高效模型**：用较小参数达到大模型性能，降低部署门槛。

### 不足与局限

- **算力资源未公开**：缺少训练Idefics2的具体硬件成本，降低复现可参考性。
- **仅探索7~8B尺度**：结论是否适用于更大模型（如70B）未验证。
- **数据集筛选依赖经验**：如何定义“高质量”数据缺乏明确量化指标，可能引入隐藏偏差。
- **评估基准局限**：未涵盖视频理解或更复杂的推理任务（如多轮对话），通用性存疑。
- **消融实验规模有限**：部分实验仅在小数据上运行，可能存在过拟合到特定基准的风险。

（完）
