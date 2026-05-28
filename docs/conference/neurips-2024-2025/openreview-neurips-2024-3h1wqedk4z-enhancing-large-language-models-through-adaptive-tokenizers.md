---
title: Enhancing Large Language Models through Adaptive Tokenizers
title_zh: 通过自适应分词器增强大语言模型
authors: "Mengyu Zheng, Hanting Chen, Tianyu Guo, Chong Zhu, Binfan Zheng, Chang Xu, Yunhe Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=3H1wqEdK4z"
tags: ["query:llm-vlm"]
score: 6.0
evidence: 大语言模型分词器改进
tldr: 传统分词器依赖静态频率统计，与LLM架构不完全同步。本文提出一种简单有效的方法，通过监控训练过程中模型困惑度的变化来迭代优化分词器，使其与模型动态对齐。实验表明自适应分词器提升了LLM在多种任务上的性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-3h1wqedk4z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 709, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1382, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1145, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1313, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1369, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 749, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 490, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 975, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 943, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 515, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-3h1wqedk4z/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1207, \"height\": 221, \"label\": \"Table\"}]"
motivation: 传统分词器与LLM架构不匹配，限制了模型性能。
method: 从初始词汇开始，根据模型困惑度变化选择最优分词器，进行迭代优化。
result: 自适应分词器在多个语言任务上降低了困惑度并提高了生成质量。
conclusion: 与模型动态对齐的分词器能有效提升LLM性能。
---

## Abstract
Tokenizers serve as crucial interfaces between models and linguistic data, substantially influencing the efficacy and precision of large language models (LLMs). Traditional tokenization methods often rely on static frequency-based statistics and are not inherently synchronized with LLM architectures, which may limit model performance. In this study, we propose a simple but effective method to learn tokenizers specifically engineered for seamless integration with LLMs. Initiating with a broad initial vocabulary, we refine our tokenizer by monitoring changes in the model’s perplexity during training, allowing for the selection of a tokenizer that is closely aligned with the model’s evolving dynamics. Through iterative refinement, we develop an optimized tokenizer. Our empirical evaluations demonstrate that this adaptive approach significantly enhances accuracy compared to conventional methods, maintaining comparable vocabulary sizes and affirming its potential to improve LLM functionality.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统分词器（如 BPE、WordPiece、Unigram）依赖静态频率统计，无法与大型语言模型（LLM）的动态学习过程对齐，导致模型性能受限。
- **动机**：分词器作为模型与文本数据之间的关键接口，其质量直接影响 LLM 的理解和生成能力。现有方法要么优先压缩词汇量（忽视准确性），要么引入端到端可学习分词器（计算开销大、灵活性差）。
- **目标**：提出一种既能保持推理速度又能提升准确性的自适应分词器（ADAT），通过与 LLM 训练过程耦合来动态优化词汇表。

## 2. 方法论

- **核心思想**：基于 Unigram 模型的概率框架，引入 LLM 的损失（交叉熵）作为额外反馈，迭代地修剪词汇表，使分词器适应模型动态。
- **关键技术细节**：
  - **初始词汇表**：从一个较大的初始词汇（如 150k 词）开始，使用 Subword 算法（如 Unigram 或 BytePiece）生成。
  - **LLM 驱动损失**：训练一个随机初始化的 LLM（Pythia），计算每个 token 的交叉熵损失 \( L_M(x_i) = \sum_{x_i \in T} \text{CE}(M(x_{i-1}), x_i) \)。
  - **组合损失**：将 Unigram 的频率损失 \( L_P(x_i) \) 与 LLM 损失结合，使用平衡函数 \( L(x_i) = \frac{a}{\lambda \log(b+1)} \)，其中 a 为频率分数，b 为损失值。
  - **迭代过程**：重复 5 轮，每轮训练 LLM 约 0.3B tokens → 在 0.1B tokens 上进行推理计算 token 损失 → 基于组合损失修剪最低贡献的 tokens，从 150k 剪至 50k。
  - **随机采样**：采用 Viterbi 算法对训练数据进行随机分词，确保各 token 均匀训练。
  - **损失动量**：引入动量更新损失 \( L_j^{\text{momentum}}(x_i) = \beta L_{j-1}^{\text{momentum}}(x_i) + L_j(x_i) \)，稳定词汇更新。

## 3. 实验设计

- **数据集**：
  - 训练语料：The Pile 的子集（56 GB，91 个文件，排除 DM_Mathematics 和 Github），约 16B tokens，分词后用 Unigram 生成 50k 词汇表。
  - 评估数据集：PG19（困惑度测试集），以及 8 个语言基准（Lambada, PIQA, WinoGrande, ARC-Easy, ARC-Challenge, SciQ, LogiQA, SST-2）。
- **Benchmark**：使用 Language Model Evaluation Harness 进行 5-shot 评测。
- **对比方法**：BytePiece、BPE、Unigram（基线），以及 ADAT 使用不同初始词汇（BytePiece 或 Unigram）。
- **实验场景**：
  - 主实验：Pythia-70M 模型，训练 15B tokens，对比四种分词方法。
  - 可扩展性实验：Pythia-70M/160M/410M，比较 ADAT vs Unigram。
  - 跨模型适应性：将 70M 和 410M 模型生成的词汇应用于不同大小的模型。
  - 词汇大小影响：50k vs 30k 词汇量。
  - 消融实验：推理数据量、初始词汇大小、动量策略、平衡函数。

## 4. 资源与算力

- **硬件**：8× NVIDIA A100 GPU，Intel 8378A CPU，PyTorch 2.1.2，CUDA 12.1。
- **训练时长**：
  - 分词器优化：约 2 GPU 小时（5 轮，每轮训练 0.3B + 推理 0.1B + 剪枝 90 秒）。
  - 完整模型训练（Pythia-70M on 15B tokens）：约 48 GPU 小时（使用 FlashAttention）。
  - 对比：Pythia-70M 在完整 Pile 上需 510 GPU 小时，分词器优化成本仅占约 4.17%（16B 训练）或 1.04%（60B 训练）。

## 5. 实验数量与充分性

- **实验组数**：约 7 大类实验，包含多个子实验：
  - 主实验（4 种分词方法对比）
  - 规模实验（3 种模型大小）
  - 跨模型适应性（2×2 组合）
  - 词汇大小实验（2 种词汇大小 × 2 种模型）
  - 消融实验（4 个维度：推理数据量、初始词汇大小、动量、平衡函数）
  - 附加实验：1B 模型、60B 语料、词汇重叠分析、训练轮数影响。
- **充分性与公平性**：实验设计较为全面，覆盖不同模型规模、不同词汇大小、跨模型迁移、多个基准任务（8 个下游任务），并报告误差棒（标准差）。消融实验验证了各组件贡献。对比方法均为标准实现，且控制词汇大小一致（50k）。但未在所有实验中使用相同训练数据量（大规模模型使用更多训练数据计算损失），可能引入少许不一致，但整体公平。

## 6. 主要结论与发现

- ADAT 在 70M 模型上平均准确率比 Unigram 提升 2.29%（44.51 vs 42.22），比 BPE 提升 2.6%。
- 在 160M 和 410M 模型上，ADAT 分别比 Unigram 提升 2.01% 和 1.92%，且性能随模型规模增长持续提升。
- 70M 模型的 ADAT 性能甚至超过 Unigram 160M 模型约 5%，表明可弥补参数差距。
- 跨模型适应性：优化后的词汇应用至不同大小模型仍有提升，但特定模型优化的词汇更适合自身。
- 词汇大小缩减至 30k 时，ADAT 仍优于 Unigram 50k，显示鲁棒性。
- 动量策略和除法平衡函数（\( a/\lambda\log(b+1) \)）是关键贡献因素。
- 计算成本可忽略（仅占总训练时间的 1%~4%）。

## 7. 优点

- **新颖性**：首次将 LLM 训练反馈直接融入传统 Unigram 剪枝过程，实现自适应分词。
- **简洁高效**：无需端到端梯度传播，计算开销低，易于集成到现有 LLM 训练流程。
- **鲁棒性强**：在不同初始词汇（Unigram/BytePiece）、不同模型大小、不同词汇大小下均显著提升。
- **实验充分**：涵盖多种模型、任务、消融分析，且公开数据集和评估工具，可重复性高。
- **实用价值**：能有效提升 LLM 性能，且不增加推理延迟（保持词汇大小相同）。

## 8. 不足与局限

- **词汇不一致性**：不同模型大小生成不同词汇表，导致知识蒸馏、推测解码等需统一词汇的任务复杂化（论文明确承认）。
- **依赖初始词汇质量**：实验显示以 BytePiece 为初始词汇时提升幅度较小（+2.70%），可能对低质量初始词汇敏感。
- **训练数据偏见**：仅使用 The Pile 子集，未涵盖多语言或特定领域，泛化性有待验证。
- **评估偏差**：基准任务均为英文，缺乏中文或其他语言评测；且仅测试 Pythia 架构，未验证其他模型（如 BLOOM、LLaMA）。
- **风险**：分词器可能分割敏感信息（如姓名、地址），需配合隐私保护措施（论文提及但未深入讨论）。
- **超参数敏感**：平衡函数中的 λ 设置为 1，未探索最优值；训练轮数和动量系数 β 可能需调优。

（完）
