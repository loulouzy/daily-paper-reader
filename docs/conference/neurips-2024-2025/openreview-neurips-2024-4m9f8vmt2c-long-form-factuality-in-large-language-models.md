---
title: Long-form factuality in large language models
title_zh: 大语言模型的长文本事实性
authors: "Jerry Wei, Chengrun Yang, Xinying Song, Yifeng Lu, Nathan Zixia Hu, Jie Huang, Dustin Tran, Daiyi Peng, Ruibo Liu, Da Huang, Cosmo Du, Quoc V Le"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=4M9f8VMt2C"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 关于大语言模型长文本事实性的研究论文
tldr: 大语言模型在长文本生成中常出现事实错误。本文构建LongFact基准，并设计SAFE自动化评估器，利用大语言模型将响应分解为事实并通过搜索引擎验证，大幅降低人力成本。实验表明SAFE与人类判断高度一致。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1365, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1379, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1151, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 516, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 631, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 767, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 491, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1316, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1318, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1351, \"height\": 1247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1267, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1266, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 499, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1420, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 516, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1328, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-4m9f8vmt2c/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 490, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1365, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 707, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1326, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1219, \"height\": 1326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1353, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 1460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1331, \"height\": 2132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1361, \"height\": 1902, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1333, \"height\": 1824, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1333, \"height\": 1861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1351, \"height\": 1951, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1379, \"height\": 559, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1364, \"height\": 1646, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1393, \"height\": 1556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1273, \"height\": 1705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1433, \"height\": 1690, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1350, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1272, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1371, \"height\": 2036, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1361, \"height\": 1245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1345, \"height\": 1176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1383, \"height\": 1139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1433, \"height\": 1273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1403, \"height\": 1235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-4m9f8vmt2c/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1441, \"height\": 577, \"label\": \"Table\"}]"
motivation: LLM在开放主题上生成内容存在事实错误，缺乏长文本事实性基准。
method: 利用GPT-4生成LongFact问题集；提出SAFE方法，用LLM分解事实并搜索验证。
result: SAFE与人类评估一致，且成本更低。
conclusion: 自动事实性评估可规模化检测LLM生成内容的准确性。
---

## Abstract
Large language models (LLMs) often generate content that contains factual errors when responding to fact-seeking prompts on open-ended topics. To benchmark a model’s long-form factuality in open domains, we first use GPT-4 to generate LongFact, a prompt set comprising thousands of questions spanning 38 topics. We then propose that LLM agents can be used as automated evaluators for long-form factuality through a method which we call Search-Augmented Factuality Evaluator (SAFE). SAFE utilizes an LLM to break down a long-form response into a set of individual facts and to evaluate the accuracy of each fact using a multi-step reasoning process comprising sending search queries to Google Search and determining whether a fact is supported by the search results. Furthermore, we propose extending F1 score as an aggregated metric for long-form factuality. To do so, we balance the percentage of supported facts in a response (precision) with the percentage of provided facts relative to a hyperparameter representing a user’s preferred response length (recall).

Empirically, we demonstrate that LLM agents can outperform crowdsourced human annotators—on a set of∼16k individual facts, SAFE agrees with crowdsourced human annotators 72% of the time, and on a random subset of 100 disagreement cases, SAFE wins 76% of the time. At the same time, SAFE is more than 20 times cheaper than human annotators.  We also benchmark thirteen language models on LongFact across four model families (Gemini, GPT, Claude, and PaLM-2), finding that larger language models generally achieve better long-form factuality. LongFact, SAFE, and all experimental code are available at https://github.com/google-deepmind/long-form-factuality.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：大语言模型（LLM）在开放主题的事实性问答中，常生成包含事实错误的响应，尤其在需要多段落的长文本（long-form）回答时，错误更为突出。现有基准（如TruthfulQA、HaluEval）多针对短答案，缺乏覆盖多主题的长文本事实性评估数据集。
- **意义**：可靠的事实性评估对LLM在实际场景（如信息检索、内容生成）中的可信度至关重要。论文旨在建立系统化的长文本事实性基准、自动化评估方法和聚合指标。

## 2. 方法论

### 核心思想
- 提出 **LongFact**：使用GPT-4生成涵盖38个主题的2280个开放性问题，要求模型提供包含多个细节的长文本响应（分为概念版LongFact-Concepts和具体对象版LongFact-Objects）。
- 提出 **SAFE**（Search-Augmented Factuality Evaluator）：利用LLM将模型响应分解为原子事实，再通过多步推理，借助Google Search验证每个事实是否被支持。
- 提出 **F1@K**：结合精度（支持事实占比）和召回（支持事实数与超参数K的比例），综合量化长文本事实性。

### 关键技术细节

**SAFE流程**（如图1所示）：
1. **分解事实**：将响应按句拆分，再用LLM将每个句子分解为独立原子事实。
2. **修订自包含**：将每个事实中的模糊指代（如代词）替换为具体实体，使其脱离上下文仍可理解。
3. **判断相关性**：判断事实与提示是否相关（利用LLM推理，使用“Foo/Not Foo”标签），对不相关的事实标记为“irrelevant”并跳过验证。
4. **搜索验证**：对于相关事实，LLM生成最多5个搜索查询，每次返回3个搜索结果；最终LLM综合搜索结果判断事实为“supported”或“not supported”。

**F1@K公式**：
- 精度 \( \text{Prec} = \frac{S}{S+N} \)（S=支持事实数，N=不支持事实数）
- 召回 \( R_K = \min\left(\frac{S}{K}, 1\right) \)，K是用户期望的支持事实数
- F1@K = 0 若 S=0，否则 \( \frac{2\cdot\text{Prec}\cdot R_K}{\text{Prec}+R_K} \)

## 3. 实验设计

### 数据集与场景
- **LongFact**：自己生成，2280个提示，38个主题，覆盖STEM、社会科学、人文、其他。
- **FActScore数据集**（Min et al., 2023）：496个传记提示-响应对，含约16k个手动标注的原子事实，用于与人类标注对比。
- **基准测试**：从LongFact-Objects中随机抽取250个提示，添加后缀要求“提供尽可能多的具体细节”。

### 基准方法与对比对象
- **SAFE vs 众包人类标注**：在FActScore的16k个事实上计算一致率；在100个分歧案例上，使用研究者+全互联网作为ground truth。
- **模型基准**：13个模型（Gemini-Ultra/Pro, GPT-4-Turbo/GPT-4/GPT-3.5-Turbo, Claude-3-Opus/Sonnet/Haiku, Claude-2.1/2.0/Instant, PaLM-2-L-IT-RLHF/PaLM-2-L-IT）。
- **消融实验**：
  - 搜索范围（全互联网 vs 仅Wikipedia）
  - 搜索查询数量（1,5,10）
  - 每查询返回结果数（1,3,10）
  - LLM选择（GPT-3.5-Turbo vs Mixtral 8×7B）
  - 专业领域（法律、医学各3个额外问题）

### 评估指标
- SAFE输出：S（支持）、N（不支持）、I（无关）数量
- 聚合：精度、召回、F1@64（K=64为所有响应中位数事实数）、F1@178（最大事实数）

## 4. 资源与算力

- **未明确提及训练算力**：论文使用现有LLM（如GPT-3.5-Turbo、GPT-4、Gemini等）进行推理，未报告模型训练所需的GPU型号、数量或时长。
- **SAFE推理成本**：评估FActScore的496个响应总成本$96.31（GPT-3.5-Turbo API $64.57 + Serper API $31.74），平均每响应$0.19；相比之下，众包人类标注每响应$4.00，成本降低20倍以上。

## 5. 实验数量与充分性

- **主要实验**：
  - 与人类标注对比：16,011个独立事实（整体一致率72%）+ 100个分歧案例的深度分析。
  - 13个模型 × 250个提示 = 3250次评估（使用SAFE）。
  - 超参数消融：搜索查询数（1,5,10）、返回结果数（1,3,10）各一轮，共约6组实验。
  - 搜索范围消融：20个提示，手动检查146个差异事实。
  - Mixtral对比：20个提示，196个差异事实。
  - 专业领域：6个法律/医学问题，手动检查270个事实。
- **充分性评价**：实验覆盖全面，从自动评估与人类对比、模型规模、消融到专业领域。但250个提示样本量相对有限，可能不足以代表全部38个主题的多样性；对长尾主题的覆盖未单独分析。总体公平客观，使用了公开API和固定温度（temperature=0）确保可重复性。

## 6. 主要结论与发现

- **SAFE优于众包人类**：与人类标注一致率72%；在100个分歧案例中SAFE正确率76%，人类仅19%。成本降低20倍。
- **更大模型通常更准确**：同一族内，更大/更新模型（GPT-4-Turbo > GPT-4 > GPT-3.5-Turbo；Gemini-Ultra > Gemini-Pro；PaLM-2-L-IT-RLHF > PaLM-2-L-IT）在F1@K上表现更好。但Claude-3-Sonnet与Opus相近，Claude-3-Haiku反而落后。
- **RLHF提升事实性**：PaLM-2-L-IT-RLHF相比未强化学习版本在所有K上均显著提升F1，主要在于增加了支持事实的数量。
- **F1@K比纯精度更符合人类偏好**：与Chatbot Arena ELO的相关性（r=0.754, p=0.031）优于纯精度（r=0.502, p=0.205）。

## 7. 优点

- **首个多主题长文本事实性基准**：LongFact覆盖38个话题，填补了现有基准（如FActScore仅人物传记）在广度上的空白。
- **自动化、低成本、高准确率的评估器**：SAFE无需预定义答案，利用Google Search动态获取证据，成本仅为人类标注的1/20，且能处理人类容易出错的情况（如信息不在单一Wikipedia页面）。
- **引入召回维度的F1@K指标**：将事实覆盖度纳入考量，更贴近实际使用场景（用户希望获得多个正确事实），并可通过K调节评估偏好。
- **全面的模型对比**：涵盖13个主流模型，揭示规模、RLHF对长文本事实性的影响规律。

## 8. 不足与局限

- **对LLM能力的依赖**：SAFE的拆分、修订、推理等步骤依赖GPT-3.5-Turbo，当模型推理能力不足时（如Mixtral 8×7B）错误率上升；专业领域（法律、医学）中拆分和修订错误是主要失败原因。
- **搜索知识的局限性**：依赖Google Search，在极专业或罕见事实场景下可能找不到信息；搜索结果可能包含噪声或误导。
- **F1@K假设无重复事实**：未防范模型利用重复支持事实来提高分数；实际中可添加去重步骤但论文未实现。
- **实验样本量有限**：基准测试仅250个提示，对长尾话题覆盖面不够；消融实验中的手动分析样本较少（如100个分歧案例、20个对比实验）。
- **人类标注非专家**：用于对比的众包标注来自Min et al. (2023)，SAFE仅证明优于众包人类，未与领域专家全面比较。
- **LongFact生成偏差**：使用GPT-4生成提示，可能引入模型自身的知识偏好或语言风格偏差。

（完）
