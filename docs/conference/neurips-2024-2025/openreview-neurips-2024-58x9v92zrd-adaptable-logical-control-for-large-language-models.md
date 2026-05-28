---
title: Adaptable Logical Control for Large Language Models
title_zh: 大语言模型的可适应逻辑控制
authors: "Honghua Zhang, Po-Nien Kung, Masahiro Yoshida, Guy Van den Broeck, Nanyun Peng"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=58X9v92zRd"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 大语言模型控制框架（学术研究）
tldr: 大语言模型（LLM）在遵循逻辑约束方面面临挑战。本文提出Ctrl-G，一种神经符号框架，将LLM与隐马尔可夫模型结合，通过确定性有限自动机表示逻辑约束，实现在推理时可靠控制。在文本编辑任务中，TULU2-7B搭配2B参数HMM即超越GPT-4。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 534, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1291, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1336, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-58x9v92zrd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1372, \"height\": 495, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-58x9v92zrd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1277, \"height\": 528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-58x9v92zrd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-58x9v92zrd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1392, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-58x9v92zrd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1010, \"height\": 673, \"label\": \"Table\"}]"
motivation: LLM生成难以在推理时严格遵循逻辑约束，现有方法不够可靠。
method: 提出Ctrl-G神经符号框架，将LLM与HMM结合，用DFA表示约束并引导生成。
result: "在逻辑约束文本编辑任务上，Ctrl-G（TULU2-7B）超越GPT-4达30%以上。"
conclusion: Ctrl-G为LLM的逻辑控制提供了高效可适应的方案。
---

## Abstract
Despite the success of Large Language Models (LLMs) on various tasks following human instructions, controlling model generation to follow strict constraints at inference time poses a persistent challenge. In this paper, we introduce Ctrl-G, a neuro-symbolic framework that enables tractable and adaptable control of LLM generation to follow logical constraints reliably. Ctrl-G combines any production-ready LLM with a Hidden Markov Model (HMM), guiding LLM outputs to adhere to logical constraints represented as deterministic finite automata. We show that Ctrl-G, when a TULU2-7B model is coupled with a 2B-parameter HMM, outperforms GPT4 in text editing: on the task of generating text insertions/continuations following logical constraints, our approach achieves over 30% higher satisfaction rate in human evaluation. When applied to medium-size language models (e.g., GPT2-large), Ctrl-G also beats its counterparts on standard benchmarks by large margins. Additionally, as a proof-of-concept study, we use Ctrl-G to assist LLM reasoning on the GSM benchmark, foreshadowing the application of Ctrl-G, as well as other constrained generation approaches, beyond traditional language generation tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机与背景）

- **核心问题**：大型语言模型（LLM）在遵循人类指令方面表现优异，但在推理时严格遵循逻辑约束（如关键词包含、长度控制、禁止词等）仍然非常困难。现有方法（如搜索式解码、辅助分类器、近似推理）要么扩展性差、要么无法保证约束满足、要么需要为每个新约束重新训练。
- **整体含义**：作者提出 Ctrl-G，一种神经符号框架，将 LLM 与隐马尔可夫模型（HMM）结合，利用确定性有限自动机（DFA）紧凑表示逻辑约束，通过在推理时近似计算条件概率 `p(α | x<t)` 来引导 LLM 生成，从而可靠、可扩展且可适应地实现逻辑约束控制。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：使用 HMM 作为 LLM 的白盒近似，通过 HMM 可以高效计算在给定部分生成序列下满足逻辑约束 α 的后验概率 `p(α | x_{<t}, x_t)`，并用该概率对 LLM 的下一 token 分布进行重加权，以保证生成序列最终满足约束。
- **关键技术细节**：
    1. **蒸馏（Distillation）**：从目标 LLM 中采样大量文本，训练一个 HMM 来最小化与 LLM 分布之间的 KL 散度。
    2. **约束表示**：将逻辑约束 α 转化为确定有限自动机（DFA），DFA 可以表示关键词包含、顺序、长度、逻辑与、或、非等任意组合约束，且可以通过自动机交、并、补等操作组合。
    3. **推理（Inference）**：在自回归生成每一步，使用动态规划算法（公式 4）高效计算 `p(α | x_{≤t}, s_t)`（其中 `s_t` 是 DFA 当前状态），然后按 `p(xt | x<t) · p(α | xt, x<t)` 采样下一个 token。
- **算法流程**（文字说明）：
    - 预计算每个时间步 t、每个 HMM 隐藏状态 z_t 和每个 DFA 状态 s_t 下的未来满足概率 `p(S_n ∈ F | z_t, s_t)`（基于 HMM 转移矩阵和 DFA 边）。
    - 生成时初始化 DFA 状态为初始状态，对每个时间步 t：
        - 用前向算法计算 `p(α | x_{<t}, x_t)`（公式 3）。
        - 对每个候选 token x_t，计算 `p(α | x_{<t}, x_t) · p_LLM(x_t | x_{<t})`，归一化后采样。
        - 更新 DFA 状态 `s_t = δ(s_{t-1}, x_t)`。
    - 重复直到生成结束。

## 3. 实验设计：数据集、场景与基准方法

- **数据集与场景**：
    - **CommonGen**（常识生成）：给定 3-5 个概念关键词，要求生成包含所有关键词的句子。评估自动指标（BLEU-4, ROUGE-L, CIDEr, SPICE）和约束满足率。
    - **文本填充（Text Infilling）**：基于 ROC Stories 构建不同掩码率的测试集，要求填充掩码部分。评估 BLEU-4 和 ROUGE-L。
    - **交互式文本编辑**（人机协作写作）：基于 CoAuthor 数据集构建 800 个示例，包含续写和插入两种场景，施加关键词和/或字数约束。使用人类评估（质量、约束满足率、总体满意度）。
    - **GSM 数学推理**：辅助 LLM 推理，通过强制生成问题中所有数字来提高准确性。
- **基准方法**：
    - CommonGen：FUDGE、NADO、NeuroLogic A*esque、GeLaTo。
    - 文本填充：ILM（监督训练）。
    - 文本编辑：GPT-3.5、GPT-4、TULU2-7B（纯指令微调）。
    - 均使用相同基础模型（GPT2-large 或 TULU2-7B）进行公平对比。

## 4. 资源与算力

- 论文明确提到使用 **NVIDIA-A100 GPU (80GB)** 进行运行时分析。
- HMM 蒸馏训练：从 LLM 采样 4M（CommonGen）或 5M（文本编辑）样本，进行 40 个 EM 步，每步 100K 样本。
- 生成时采样 128 个候选，选择最高概率输出。
- 未明确给出总训练时长，但提供了推理时间对比（如表 2 和图 5），显示 Ctrl-G 比 GeLaTo 快一个数量级以上。

## 5. 实验数量与充分性

- **实验数量**：覆盖 4 个不同任务/场景，每个任务有多个细分设置（CommonGen：有无监督、3/4/5 概念；文本填充：4 种掩码率；文本编辑：8 种设置（续写/插入 × 无约束/关键词/字数/关键词+字数）；GSM：消融实验）。
- **充分性与公平性**：
    - CommonGen 与所有主流方法对比，并报告了有/无监督两种设置。
    - 文本编辑使用了人类评估（3 人独立评分，计算 Kendall 系数 0.449），且与 GPT-3.5/4 等强基线对比，生成数相同候选数。
    - 消融实验：CommonGen+（扩展更多关键词）、GSM 消融。
    - 总体上实验充分、客观、公平。

## 6. 主要结论与发现

- Ctrl-G 在 **所有逻辑约束下实现 100% 约束满足率**（CommonGen、文本编辑）。
- 在文本编辑任务中，Ctrl-G（TULU2-7B + 2B 参数 HMM）在总体满意度上 **超越 GPT-4 超过 30%**（当存在约束时）；在无约束续写上质量与 GPT-4 相当。
- 在 CommonGen 上，Ctrl-G 在自动指标上 **显著优于所有现有方法**（包括监督训练）。
- Ctrl-G **适应复杂约束**：当约束数量增加时，GPT-4 质量下降，而 Ctrl-G 保持稳定。
- 作为概念验证，Ctrl-G 可在推理任务中辅助提高准确率（GSM 提升 3.4%）。

## 7. 优点

- **100% 约束满足保证**：基于 HMM 的精确条件概率计算，而非启发式近似。
- **无需重训**：蒸馏好的 HMM 可复用于任意 DFA 约束，适应性强。
- **表达力强**：DFA 可表示任意（有界）逻辑约束，支持组合（与、或、非、连接）。
- **推理高效**：时间复杂度 O(n m h²)，且可完全并行在 GPU 上，比 GeLaTo 快数十倍。
- **可扩展性**：适用于小模型（GPT2）到 7B 大模型（TULU2-7B），且能超越 GPT-4 在约束任务上的表现。

## 8. 不足与局限

- **约束类型限制**：仅适用于可表示为 DFA 的约束，对于连续空间或概率性约束（如风格、情感）不直接适用。
- **HMM 近似误差**：蒸馏后的 HMM 可能无法完美逼近 LLM 分布，可能导致条件概率估计有偏，但实验表明足够有效。
- **计算开销**：HMM 隐藏状态数 h 较大时，推理复杂度 O(n m h²) 可能成为瓶颈，尤其是当 h=32768 时。作者通过 GPU 并行化缓解，但仍比纯 LLM 推理慢。
- **未涵盖所有场景**：实验主要聚焦文本生成，对其他任务（如对话、代码生成）的泛化性未验证。
- **蒸馏成本**：需要大量采样和 EM 训练，资源消耗较大。

（完）
