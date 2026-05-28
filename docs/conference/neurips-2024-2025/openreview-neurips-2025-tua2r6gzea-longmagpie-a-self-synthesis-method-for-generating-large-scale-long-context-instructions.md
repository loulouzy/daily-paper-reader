---
title: "LongMagpie: A Self-synthesis Method for Generating Large-scale Long-context Instructions"
title_zh: "LongMagpie: 一种自合成大规模长上下文指令的方法"
authors: "Chaochen Gao, Xing W, Zijia Lin, Debing Zhang, Songlin Hu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tuA2R6gZEA"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 大语言模型实验室研究论文
tldr: 高质量长上下文指令数据缺乏且人工标注昂贵，LongMagpie提出自合成框架，利用已对齐的长上下文LLM自动生成文档-查询对，从而大规模制备高质量指令数据，解决了数据稀缺问题。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 705, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tua2r6gzea/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 728, \"height\": 420, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1372, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 967, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1138, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1350, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1368, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 995, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1003, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 759, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1330, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1335, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 799, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1230, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1390, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 663, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tua2r6gzea/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 869, \"height\": 608, \"label\": \"Table\"}]"
motivation: 长上下文大语言模型的高质量指令数据稀缺，人工标注成本高，现有模板合成方法规模与多样性不足。
method: 利用已对齐的长上下文LLM自动生成上下文相关的查询及响应，形成自合成框架。
result: 大规模生成了多样且高质量的长上下文指令数据，有效提升了模型对齐效果。
conclusion: 该自合成框架为长上下文LLM的指令微调提供了低成本、可扩展的数据方案。
---

## Abstract
High-quality long-context instruction data is essential for aligning long-context large language models (LLMs). Despite the public release of models like Qwen and Llama, their long-context instruction data remains proprietary. Human annotation is costly and challenging, while template-based synthesis methods limit scale, diversity, and quality. We introduce LongMagpie, a self-synthesis framework that automatically generates large-scale long-context instruction data. Our key insight is that aligned long-context LLMs, when presented with a document followed by special tokens preceding a user turn, auto-regressively generate contextually relevant queries. By harvesting these document-query pairs and the model's responses, LongMagpie produces high-quality instructions without human effort. Experiments on HELMET, RULER, and Longbench v2 demonstrate that LongMagpie achieves leading performance on long-context tasks while maintaining competitive performance on short-context tasks, establishing it as a simple and effective approach for open, diverse, and scalable long-context instruction data synthesis.

---

## 论文详细总结（自动生成）

# LongMagpie 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：高质量长上下文指令数据极度匮乏。虽然 Qwen、Llama 等开源长上下文模型权重已公开，但其使用的长上下文指令数据集仍属商业机密，无法获取。人工标注长上下文指令成本极高（标注员需阅读数千 token 的文档并构造问题），而基于模板（如 Self-Instruct）或种子问题的合成方法在规模、多样性和质量上均受限制。
- **研究动机**：提出一种无需人工标注、无需种子示例、无需复杂提示的**自合成（self-synthesis）方法**，大规模自动生成高质、多样化的长上下文指令数据，以推动长上下文能力的开放化和民主化。
- **整体含义**：该方法使研究者能够低成本地获取海量长上下文指令数据，对长上下文 LLM 的对齐训练和性能提升具有重要实际意义。

## 2. 论文提出的方法论

### 2.1 核心思想
- **关键观察**：经过长上下文指令微调的对齐 LLM（如 Qwen-2.5-Instruct、Llama-3-Instruct），当仅输入文档和紧随其后的特殊用户角色标识（如 `<|im_start|>user`）时，模型会自动回归地生成与该文档相关的上下文相关问题。这源于模型在训练中学到的“文档-查询”关系模式。
- **自合成流程**：直接利用该行为，从文档自动生成查询，再结合文档和查询生成回答，形成完整的指令三元组（文档, 查询, 回答）。

### 2.2 关键技术细节
1. **文档准备**：从公开语料库（如 FineWeb-Edu）收集多样化的文档，平均长度约 1.6k token，覆盖科学、历史、文学、技术等领域。
2. **查询生成**：将文档与预查询模板（特殊用户 token）拼接作为输入，从对齐 LLM 中采样生成查询，直至结束 token 或达到最大长度。每个文档可生成多个不同查询（通过不同采样参数）。
3. **回答生成**：将文档、查询和预回答模板拼接，生成对应回答。
4. **查询过滤**：
   - 规则过滤：保留以问号结尾的查询（确保是疑问句）。
   - 长度过滤：丢弃超过 1500 字符的生成文本（很可能是描述而非有效查询）。
5. **多文档扩展**：以一定概率将当前文档与 0~n 个随机抽取的负文档拼接（用特殊分隔符 `<|doc_sep|>`），生成多文档问答对，要求跨文档推理，增加难度和上下文长度。

### 2.3 p-Mix 策略（平衡长/短上下文能力）
- **问题**：仅用长上下文指令微调会降低模型在短上下文任务上的性能。
- **方法**：在每个训练序列起始处先放置一个短上下文指令样本，然后以概率 \(P_L\) 选择长上下文指令（LongMagpie 生成），以概率 \(1-P_L\) 选择另一个短上下文样本，循环直到接近最大序列长度 \(L_{\text{max}}\)。该策略使模型能同时处理长、短两类任务。
- **公式/算法**：见 Algorithm 1（通过循环和随机采样构建混合序列）。

## 3. 实验设计

### 3.1 使用的数据集与场景
- **文档来源**：FineWeb-Edu（教育类网页语料），平均文档长度约 1.6k token。
- **生成模型**：Qwen2.5-70B-Instruct（主要），也对比了 Qwen2.5-7B-Instruct。
- **训练基础模型**：Llama-3-8B-NExtLong-512K-Base（已进行长上下文预训练）。

### 3.2 评估 Benchmark
- **长上下文评估**：
  - **HELMET**：综合长上下文任务（Recall, RAG, ICL, Re-rank, LongQA, Cite, Summ.），上下文长度达 128k。
  - **RULER**：合成任务，评估细粒度长上下文推理。
  - **LongBench v2**：超长上下文理解（8k~2M 词），503 个专家验证问题，6 类任务。
- **短上下文评估**：7 个标准基准（HellaSwag, Lambada, ARC-Challenge, ARC-Easy, PIQA, WinoGrande, Logiqa）。

### 3.3 对比方法
- **长指令数据集**：ChatQA（1.5M 合成指令）、LongAlign（通过提示 LLM 生成问答）。
- **短指令数据集**：Tulu、Magpie、UltraChat（拼接后用作长上下文微调，参考 ProLong 方法）。
- **混合策略对比**：No Mix、Sequential Mix、Simple Mix 以及本文的 p-Mix。

## 4. 资源与算力

- **训练配置**（附录 A.1，Table 8）：
  - GPU：8 × NVIDIA H100（80 GB）。
  - 训练时间：约 10 小时。
  - 序列长度：65536 tokens。
  - 优化器：AdamW（β1=0.9, β2=0.95），学习率 2e-5，权重衰减 0.1，余弦学习率衰减。
  - 每批次 4M tokens，共 250 步（总计 1B tokens）。
  - 使用 FlashAttention-2 和 ZeRO 优化。
- **注**：论文明确给出了 GPU 类型、数量、训练时长和主要超参数，资源信息充分。

## 5. 实验数量与充分性

- **主要结果**：Table 1 展示了 6 种方法（3 种短指令+3 种长指令+3 种混合）在长、短上下文基准上的对比，共 9 组实验。
- **消融实验**：
  - 多文档设置下不同最大文档数 n（0,5,10,20,40,80）的影响（Table 2，6 组）。
  - 不同混合策略对比（Table 3，4 组）。
  - 不同数据规模（190k vs 450k，Table 4，2 组）。
  - 不同源模型大小（7B vs 70B，Table 5，2 组）。
  - 样本数量控制对比（190k 下与 ChatQA、LongAlign 对比，Table 6；450k 下与 LongAlign 对比，Table 7）。
  - 查询质量与多样性分析（奖励模型打分、t-SNE 可视化、相似度分布，Figure 2/3）。
  - 不同检索数据比例实验（附录 A.5，Table 12）。
  - 替换 Ultrachat 为 Magpie 的对比（附录 A.6，Table 13）。
  - p-Mix 超参数（NS, PL）消融（附录 A.9，Table 15）。
  - 安全分析（附录 A.7，Table 14）。
- **充分性评估**：实验覆盖了主要基准、多种消融（数据量、文档数、混合策略、源模型、查询质量），对比了多个公开数据集和方法，控制变量合理（如样本数量一致），结果具有统计可信度。实验设计较为充分、客观、公平。

## 6. 论文的主要结论与发现

1. **LongMagpie 数据显著优于现有长上下文指令数据**：在 HELMET、RULER、LongBench v2 上分别达到 62.10、91.17、34.4，LongAVG 62.56，超过 ChatQA (+2.28) 和 LongAlign (+6.44)。
2. **p-Mix 有效平衡长/短上下文性能**：在保持长上下文优势的同时，短上下文任务性能仅比最佳短指令模型低 0.33，优于其他混合策略。
3. **多文档扩展提升性能**：n=10 时最佳，过多文档（如 20,40,80）反而因难度过高导致性能下降。
4. **数据规模越大效果越好**：450k 样本优于 190k 样本（LongAVG +1.05）。
5. **更大源模型生成的数据质量更高**：Qwen-2.5-70B 优于 7B 版本。
6. **LongMagpie 生成的数据具有更高质量和更好多样性**：奖励模型打分更高（Figure 2a），查询嵌入分布更分散、相似度更低（Figure 2b, 3a/b）。
7. **样本效率极高**：每条指令平均 1.6k tokens（生成时），远低于 ChatQA 和 LongAlign（10-13×），却取得更好性能。

## 7. 优点

- **完全自动化**：无需人工标注、无需种子示例、无需复杂提示工程，仅利用对齐 LLM 的自回归特性。
- **高质量与多样性**：生成的问题自然、多样，覆盖多种任务类型（精准检索、摘要、规划、数学等），且奖励模型评分高。
- **可扩展性**：使用短文档（1.6k token）即可生成任意长度上下文（通过多文档拼接），节省生成成本。
- **p-Mix 策略创新**：有效缓解长上下文训练对短上下文能力的灾难性遗忘，且无需额外数据。
- **实验扎实**：在三大长上下文基准和七个短上下文基准上评估，进行了大量消融和对比，结论可靠。
- **安全风险低**：安全分析显示 99.86% 样本安全，管道本身不引入明显有害内容。

## 8. 不足与局限

1. **偏差继承**：生成的数据无法避免地继承源指令微调 LLM（如 Qwen2.5-70B-Instruct）的偏见，未来需检测和缓解。
2. **任务覆盖不足**：当前主要聚焦于“文档-查询”问答模式，对长输出任务（如长文生成、复杂推理、代码生成）支持不充分。虽然 Table 11 显示了一些其他任务类型，但整体仍以检索和问答为主。
3. **仅验证了 Llama-3-8B 基础模型**：未在其他尺寸或架构的模型上验证泛化性。
4. **多文档扩展中的随机负文档选择**：未探索更智能的负样本选择（如语义相似但无关的文档），可能影响跨文档推理的有效性。
5. **实验计算资源较大**：虽给出训练细节，但 8×H100 10 小时对于部分研究团队可能仍有一定门槛（不过相比人工标注成本已很低）。
6. **p-Mix 超参数需调优**：附录 A.9 显示不同 NS 和 PL 组合性能波动，实际应用时可能需针对任务调整。

（完）
