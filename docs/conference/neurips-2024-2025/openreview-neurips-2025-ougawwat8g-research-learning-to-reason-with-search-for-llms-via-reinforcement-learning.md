---
title: "ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning"
title_zh: ReSearch：通过强化学习让大语言模型学会结合搜索进行推理
authors: "Mingyang Chen, Linzhuang Sun, Tianpeng Li, sunhaoze, ZhouYijie, Chenzheng Zhu, Haofen Wang, Jeff Z. Pan, Wen Zhang, Huajun Chen, Fan Yang, Zenan Zhou, Weipeng Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OuGAwwAT8G"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 使用强化学习训练LLM集成外部搜索
tldr: 本文提出ReSearch框架，通过强化学习训练大语言模型将外部搜索作为推理链的一部分。无需任何监督推理步骤，模型自动学习何时以及如何进行搜索，并利用搜索结果改进推理。在Qwen2.5模型上训练，证明了该方法在复杂多跳问答任务上的有效性。这项工作弥合了LLM推理与外部知识检索之间的鸿沟。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ougawwat8g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1298, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ougawwat8g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ougawwat8g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ougawwat8g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 322, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ougawwat8g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 1041, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ougawwat8g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1469, \"height\": 766, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ougawwat8g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 1428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ougawwat8g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 606, \"height\": 378, \"label\": \"Table\"}]"
motivation: 现有LLM推理难以有效整合外部搜索，尤其多跳问答需要多次检索。
method: 将搜索操作融入推理链，通过强化学习训练模型自主决定搜索时机与内容。
result: 在多项数据集上优于基线，无需监督推理步骤。
conclusion: RL可有效训练LLM将外部搜索作为推理环节，提升复杂问答能力。
---

## Abstract
Large Language Models (LLMs) have shown remarkable capabilities in reasoning, exemplified by the success of OpenAI-o1 and DeepSeek-R1. However, integrating reasoning with external search processes remains challenging, especially for complex multi-hop questions requiring multiple retrieval steps. We propose ReSearch, a novel framework that trains LLMs to Reason with Search via reinforcement learning without using any supervised data on reasoning steps. Our approach treats search operations as integral components of the reasoning chain, where when and how to perform searches is guided by text-based thinking, and search results subsequently influence further reasoning. We train ReSearch on Qwen2.5-7B(-Instruct) and Qwen2.5-32B(-Instruct) models and conduct extensive experiments. Despite being trained on only one dataset, our models demonstrate strong generalizability across various benchmarks. Analysis reveals that ReSearch naturally elicits advanced reasoning capabilities such as reflection and self-correction during the reinforcement learning process.

---

## 论文详细总结（自动生成）

# 论文总结：ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）虽然展现出强大的推理能力（如OpenAI-o1、DeepSeek-R1），但如何将推理与外部搜索过程有效整合仍是一大挑战，尤其是在需要多次检索的复杂多跳问答任务中。现有方法（如手动设计prompt或启发式策略）不仅劳动密集，而且难以扩展到更复杂的问题；标注多步RAG的推理步骤也不切实际（成本高、时间长）。
- **研究意义**：本文旨在通过强化学习（RL）训练LLM，使其能够自主地将搜索视为推理链的一部分，从而在无需监督推理步骤数据的情况下，学会何时搜索、如何搜索，并利用搜索结果指导后续推理。这弥合了LLM内部推理与外部知识检索之间的鸿沟。

## 2. 方法论

### 核心思想
- 将搜索操作作为推理链的有机组成部分，推理链包含三种要素：
  - **文本思考**（`<think>...</think>`）：模型内部的推理过程。
  - **搜索查询**（`<search>...</search>`）：由文本思考引导生成。
  - **检索结果**（`<result>...</result>`）：外部搜索引擎返回的信息，反过来影响后续思考。

### 关键技术细节
- **强化学习算法**：采用 **Group Relative Policy Optimization (GRPO)**，无需独立的critic模型，而是从一组rollout中估计baseline。训练目标最大化带KL散度惩罚的group相对奖励。
- **带搜索的Rollout过程**：
  1. 模型生成response，遇到`</search>`标签时暂停生成。
  2. 提取搜索查询，执行检索（本文使用Wikipedia作为知识库，FlashRAG工具包，E5-base-v2检索器，top-5结果）。
  3. 将检索结果用`<result>`标签包裹后拼接到当前rollout，继续生成，直到遇到结束标记（eos）。
- **检索结果masking**：在计算GRPO损失时，屏蔽检索结果对应的token，避免策略受检索结果影响（检索结果不是模型生成的）。
- **奖励建模**：仅使用规则化奖励，无需人工标注。包含两部分：
  - **答案奖励**：预测答案（`\boxed{}`内）与ground truth的F1分数。
  - **格式奖励**：检查是否遵循标签格式、是否有`\boxed{}`。
  - 最终奖励公式：若F1>0则等于F1；若F1=0但格式正确则0.1；否则0。

## 3. 实验设计

### 使用的数据集与场景
- **训练集**：仅使用 **MuSiQue** 的训练集（19938个样本），因为它包含多种类型的多跳问题且粒度控制好。
- **评估基准**（多跳问答）：
  - HotpotQA（7405个样本，全dev集）
  - 2WikiMultiHopQA（12576个样本）
  - MuSiQue（2417个样本）
  - Bamboogle（125个样本，测试集）
- **注意**：丢弃了原数据集中的上下文文档，仅使用问题-答案对，使用开放式的Wikipedia检索环境。

### 对比方法
- **Naive Generation**：无RAG，直接生成。
- **Naive RAG**：将检索结果与问题拼接后生成。
- **Iter-RetGen**：迭代检索-生成。
- **IRCoT**：检索与CoT交织。
- 所有基线均使用相同规模的指令微调模型（Qwen2.5-7B-Instruct或32B-Instruct）。

### 评估指标
- **Exact Match (EM)**：严格匹配。
- **LLM-as-a-Judge (LJ)**：使用gpt-4o-mini对答案正确性进行自动化评估（提供prompt）。

### 模型规模
- Qwen2.5-7B、Qwen2.5-7B-Instruct、Qwen2.5-32B、Qwen2.5-32B-Instruct。

## 4. 资源与算力

- **硬件**：训练在 **8×8 Nvidia H800 GPU** 上完成（即8个节点，每个节点8张H800，共64张）。
- **训练配置**：
  - 全参数优化，使用梯度检查点。
  - 学习率1e-6，训练batch size=256，训练epoch=2，rollout数量=5，rollout温度=1.0，KL损失系数0.001，裁剪比0.2。
- **框架**：基于 **verl** 进行强化学习，基于 **FlashRAG** 进行检索（Wikipedia数据库为2018年12月版本，E5-base-v2检索引擎）。
- **训练时间**：未明确给出具体时间，但根据GPU规模和epoch数可估算。

## 5. 实验数量与充分性

- **主要实验**：在4个不同基准上对比了4种基线方法（覆盖无RAG、简单RAG、多步RAG方法），并针对两种基础模型规模（7B/32B）及其指令微调版本分别进行了评估。
- **分析实验**：
  - 训练过程中响应长度、搜索次数随时间的变化曲线（图3）。
  - 训练奖励与验证奖励的变化曲线（图4）。
  - 一个详细的案例研究，展示了模型如何自我反思和纠正（表3）。
- **充分性与公平性**：
  - 实验较充分：覆盖了多跳问答主流的多个数据集，基线选择合理（包括prompt-based和迭代方法），并且所有baseline均使用相同的基础模型（保证公平）。
  - **客观性**：使用LLM-as-a-Judge辅助评估，减少主观偏差，但未报告多次运行的标准差（论文中未明确给出），可能影响统计显著性。不过论文提到“均值来自3次独立随机种子运行”（在神经元检查表中提及report error bars，但正文中未见具体误差线，可能存在不一致）。

## 6. 主要结论与发现

1. **有效性显著**：ReSearch在所有基准上相比最佳基线实现了大幅提升。平均EM提升7B模型约15.81%，32B模型约14.82%；LJ提升约17.56%和15.46%。
2. **泛化能力强**：仅使用MuSiQue训练集训练，但在HotpotQA、2Wiki、Bamboogle等不同构造的基准上均表现优异，说明学会的是通用的“推理+搜索”能力，而非记忆特定模式。
3. **训练动态揭示能力涌现**：训练过程中，模型响应长度和搜索次数逐渐增加，奖励稳步上升。特别是在32B模型中，初期响应长度下降、后又上升，说明模型从依赖内部知识转向主动利用搜索。
4. **自发的反思与自我纠错能力**：案例中模型在搜索无效后主动表示“I made a mistake”，并修改搜索词，这种能力是RL训练中自然涌现的，无需手工设计。
5. **指令微调模型优于基座模型**：基于Instruct版本训练的效果优于纯基座版本，说明指令微调有助于模型更快学习格式和任务。

## 7. 优点

- **无需监督推理步骤**：完全通过RL从最终答案奖励学习，避免了昂贵的标注成本。
- **简洁而强大的框架**：仅通过标签约定和简单的规则奖励，就能引导模型学会多步搜索与推理的协同。
- **自发的元认知能力**：模型在训练过程中自动发展出反思和纠错能力，这是传统有监督微调难以实现的。
- **良好的可扩展性**：方法在不同模型规模（7B/32B）和不同基座/指令微调版本上均有效，并且训练集与评估集分离，验证了通用性。
- **代码开源**：提供了GitHub仓库，有利于复现和后续研究。

## 8. 不足与局限

- **任务范围较窄**：仅适用于答案较简短、可用F1分数客观评估的多跳问答任务，对需要长文本生成、主观判断或复杂格式输出的任务可能不适用。
- **知识库单一**：仅使用Wikipedia作为搜索引擎（基于2018年12月版本），未探索专业领域或私有知识库，可能限制在特定场景下的应用。
- **计算资源需求高**：使用了64张H800 GPU进行训练，资源消耗较大，对于普通研究团队可能难以复现。
- **未提供误差线**：虽然检查表中声称报告了3次独立运行的平均值，但正文表格和图表中未给出标准差或置信区间，影响结果可靠性的判断。
- **缺乏更深入的消融实验**：未对比不同奖励设计（如是否使用格式奖励、不同权重）、不同搜索策略（如不同top-k）、不同RL算法（如PPO vs GRPO）等的影响。
- **潜在偏差风险**：检索结果可能包含偏见，模型可能会放大这些偏见；同时最终答案由F1决定，对等价但措辞不同的答案可能不友好（尽管使用了LLM-as-a-Judge缓解）。

（完）
