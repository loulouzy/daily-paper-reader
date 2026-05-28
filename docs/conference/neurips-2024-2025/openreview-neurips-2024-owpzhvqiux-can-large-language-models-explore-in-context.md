---
title: Can large language models explore in-context?
title_zh: 大语言模型能否在上下文中进行探索？
authors: "Akshay Krishnamurthy, Keegan Harris, Dylan J Foster, Cyril Zhang, Aleksandrs Slivkins"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=OWPzhVqIux"
tags: ["query:llm-vlm"]
score: 7.0
evidence: LLM在强化学习中的探索能力
tldr: 本文研究了当前大语言模型是否具备强化学习中的探索能力。通过在简单多臂赌博机环境中将LLM作为智能体，完全在上下文中进行交互，发现模型在没有显著干预的情况下无法稳健地进行探索。仅当使用GPT-4结合思维链推理和外部总结历史时，才表现出满意的探索行为。这项工作揭示了LLM在决策中探索的局限性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1509, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 745, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1431, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1423, \"height\": 1284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 1000, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1435, \"height\": 1822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1435, \"height\": 1822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 1823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 1823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1439, \"height\": 1514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1439, \"height\": 1514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-owpzhvqiux/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1439, \"height\": 491, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1016, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-owpzhvqiux/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 648, \"height\": 339, \"label\": \"Table\"}]"
motivation: 探索大语言模型在强化学习情境中是否具备内在探索能力。
method: 将LLM作为智能体部署在多臂赌博机环境中，通过提示设计进行上下文交互实验。
result: 仅GPT-4配合思维链和外部历史摘要才表现出满意探索，其他配置均不佳。
conclusion: 当前LLM在不加干预时缺乏稳健的探索能力。
---

## Abstract
We investigate the extent to which contemporary Large Language Models (LLMs) can engage in exploration, a core capability in reinforcement learning and decision making. We focus on native performance of existing LLMs, without training interventions. We deploy LLMs as agents in simple multi-armed bandit environments, specifying the environment description and interaction history entirely in-context, i.e., within the LLM prompt. We experiment with GPT-3.5, GPT-4, and Llama2, using a variety of prompt designs, and find that the models do not robustly engage in exploration without substantial interventions: i) Only one configuration resulted in satisfactory exploratory behavior: GPT-4 with chain-of-thought reasoning and an externally summarized interaction history; ii) All other configurations did not result in robust exploratory behavior, including those with chain-of-thought reasoning but unsummarized history. While these findings can be interpreted positively, they suggest that external summarization—which may not be possible in more complex settings—is essential for desirable LLM behavior. We conclude that non-trivial algorithmic interventions, such as fine-tuning or dataset curation, may be required to empower LLM-based decision making agents in complex settings.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当代大语言模型（LLM）是否具备在上下文中进行**探索**的能力？探索是强化学习和决策制定的核心能力，即在短期内可能次优但为了获取信息而做出的决策。
- **研究背景**：LLM的上下文学习能力已被广泛研究，但主要集中在预测或监督学习。决策制定需要探索和规划，现有工作（如Lee et al. 2023）通过显式训练来产生探索行为，但尚未回答通用LLM是否天生具备这一能力。
- **整体含义**：若LLM缺乏探索能力，则其在复杂决策场景中的应用将受限，可能需要额外训练或算法干预。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将LLM直接部署为**多臂赌博机（MAB）**环境中的智能体，通过提示（prompt）描述环境和交互历史，不修改模型参数，观察其探索行为。
- **关键技术细节**：
  - **环境**：随机伯努利赌博机，每个臂有固定未知均值，目标最大化总奖励。
  - **提示设计**：组合5种独立变量：场景（按钮/广告）、框架（中性/暗示探索）、历史表示（原始列表/按臂汇总）、输出格式（单臂/概率分布）、是否使用链式思维（CoT）。共32种提示设计。
  - **诊断指标**：提出两个**替代统计量**用于检测长期探索失败：
    - **后缀失败频率（SuffFailFreq）**：在时间区间[t, T]内从未选择最优臂的重复次数占比。
    - **均匀失败（MinFrac）**：所有臂被选中的最小比例，用于检测是否近乎均匀地选择所有臂。
  - 无需公式或算法流程，实验为主。

### 3. 实验设计：数据集、场景、基准方法
- **场景**：
  - **硬实例**：K=5个臂，最优臂均值=0.5+Δ/2，其他臂=0.5-Δ/2，Δ=0.2。
  - **易实例**：K=4，Δ=0.5（作为稳健性检查）。
- **基准方法**：
  - UCB（置信上界）
  - Thompson Sampling (TS)
  - Greedy（仅利用，不探索）
  - ε-Greedy（不同ε值）
- **对比方法**：不同LLM（GPT-3.5, GPT-4, Llama2）和各种提示配置的组合，以及温度参数（0或1）。

### 4. 资源与算力
- **文中说明**：实验主要通过API调用GPT-3.5和GPT-4（按token计费）。Llama2-13B-CHAT量化版本地部署。
- **估算**：GPT-3.5约200K次查询，GPT-4约50K次，Llama2免费（本地）。未明确给出GPU型号、数量或训练时长（因为不涉及训练）。文中提到成本和时间是主要约束。

### 5. 实验数量与充分性
- **实验数量**：
  - GPT-3.5：48种提示配置 × 20重复（硬/易实例，两种场景）→约200K查询。
  - GPT-4：10种主要配置 × 10重复（部分T=200实验有20-40重复）→约50K查询。
  - Llama2：32种配置 × 10重复（仅硬实例）。
  - 稳健性：额外T=500实验（20重复）和T=200实验（40重复）。
- **充分性评价**：
  - 实验覆盖了多种提示设计、两个实例难度、多个LLM，设计较系统。
  - 但重复数较少（10-20），在纯奖励上无法达到统计显著，依赖替代统计量来弥补。论文承认这一局限，但认为替代统计量能可靠诊断长期失败。
  - 总体客观公平，但实验规模受限于成本和时间。

### 6. 论文的主要结论与发现
- **主要结论**：当代LLM在不加干预时**不稳健地具备探索能力**。仅有一组配置成功：**GPT-4 + 按钮场景 + 暗示性框架 + 汇总历史 + 强化链式思维 + 温度0**（代码BSS eC0）。
- **失败模式**：
  - **后缀失败**（多数配置）：很大比例重复从未在后期选择最优臂，类似Greedy算法。
  - **均匀失败**（少数配置）：近乎均匀选择所有臂，未能聚焦于优臂。
- **关键发现**：外部总结历史是成功的关键；即使使用链式思维但未总结历史的配置仍然失败。这表明当前LLM在复杂环境中可能无法自行有效总结，需要外部干预。

### 7. 优点
- **提出替代统计量**：SuffFailFreq和MinFrac能在低成本下诊断长期失败，无需超长时间或大量重复，是一种方法论创新。
- **系统性探索提示空间**：覆盖32种提示组合，识别出关键影响因素（历史汇总、链式思维）。
- **清晰定义失败模式**：区分后缀失败和均匀失败，为后续研究提供分析框架。
- **实验设计严谨**：使用稳定基准（UCB、TS、Greedy），并加入ε-Greedy展示权衡。

### 8. 不足与局限
- **实验规模受限**：重复数少（N=10-20），时间步短（T=100），纯奖励差异不显著，依赖替代统计量，可能遗漏细微行为差异。
- **环境简单**：仅针对无上下文的多臂赌博机，无法推广到复杂RL（如上下文赌博机、马尔可夫决策过程）。外部总结在复杂场景不可行。
- **提示设计有限**：仅测试了5种变量组合，存在未探索的提示变体可能改善性能。
- **未测试微调或工具增强**：论文明确指出当前结论仅限于零样本上下文学习，未涉及显式训练或外部工具（如计算器、随机数生成器）。
- **模型时效性**：实验使用2023年发布的模型（GPT-3.5-0613, GPT-4-0613, Llama2-13B），后续更强模型可能表现不同。
- **成本限制**：无法进行大规模重复和长时间实验，限制了统计效力。

（完）
