---
title: Are We on the Right Way for Evaluating Large Vision-Language Models?
title_zh: 我们是否走在评估大视觉语言模型的正确道路上？
authors: "Lin Chen, Jinsong Li, Xiaoyi Dong, Pan Zhang, Yuhang Zang, Zehui Chen, Haodong Duan, Jiaqi Wang, Yu Qiao, Dahua Lin, Feng Zhao"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=evP9mxNNxJ"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型评估论文：审视大视觉语言模型评测
tldr: 大视觉语言模型（LVLM）评估存在两个问题：许多样本无需视觉内容即可回答，以及无意数据泄露。本文分析了多个基准，发现即使无图像输入，模型表现仍远超随机。这质疑了当前评测的有效性。作者呼吁更严谨的评估设计。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 692, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1351, \"height\": 994, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 687, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1374, \"height\": 1960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1373, \"height\": 1935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1376, \"height\": 1960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 431, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 406, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 203, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 256, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 376, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 431, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 378, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 393, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 232, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 398, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 386, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 412, \"height\": 218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 416, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 414, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-evp9mxnnxj/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 358, \"height\": 263, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 1173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 1291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 980, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 1310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 314, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 416, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 1172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-evp9mxnnxj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 1917, \"label\": \"Table\"}]"
motivation: 当前LVLM评估中视觉内容不必要和数据泄露问题普遍。
method: 系统分析多个基准，通过无图像输入测试和泄露检测揭示问题。
result: 发现模型在无视觉输入时仍能取得高准确率，表明基准缺陷。
conclusion: 需要更严谨的LVLM评估方法，避免数据泄露和视觉无关问题。
---

## Abstract
Large vision-language models (LVLMs) have recently achieved rapid progress, sparking numerous studies to evaluate their multi-modal capabilities. However, we dig into current evaluation works and identify two primary issues: 1) Visual content is unnecessary for many samples. The answers can be directly inferred from the questions and options, or the world knowledge embedded in LLMs. This phenomenon is prevalent across current benchmarks. For instance, GeminiPro achieves 42.7% on the MMMU benchmark without any visual input, and outperforms the random choice baseline across six benchmarks near 24% on average. 2) Unintentional data leakage exists in LLM and LVLM training. LLM and LVLM could still answer some visual-necessary questions without visual content, indicating the memorizing of these samples within large-scale training data. For example, Sphinx-X-MoE gets 43.6% on MMMU without accessing images, surpassing its LLM backbone with 17.9%. Both problems lead to misjudgments of actual multi-modal gains and potentially misguide the study of LVLM. To this end, we present MMStar, an elite vision-indispensable multi-modal benchmark comprising 1,500 samples meticulously selected by humans. MMStar benchmarks 6 core capabilities and 18 detailed axes, aiming to evaluate LVLMs' multi-modal capacities with carefully balanced and purified samples. These samples are first roughly selected from current benchmarks with an automated pipeline, human review is then involved to ensure each curated sample exhibits visual dependency, minimal data leakage, and requires advanced multi-modal capabilities. Moreover, two metrics are developed to measure data leakage and actual performance gain in multi-modal training. We evaluate 16 leading LVLMs on MMStar to assess their multi-modal capabilities, and on 7 benchmarks with the proposed metrics to investigate their data leakage and actual multi-modal gain.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：近年来大视觉语言模型（LVLM）发展迅速，涌现出大量多模态评测基准（如MMMU、MMBench、ScienceQA、AI2D、SEED、MathVista等），用于评估LVLM的多模态能力。然而，作者深入分析现有评测工作后，发现两个普遍且严重的问题：
  - **视觉内容不必要**：许多样本无需图像即可直接回答。答案可以从问题本身、选项或LLM内在的世界知识中推断出来。例如，GeminiPro在MMMU上无图像输入仍达42.7%，在6个基准上平均比随机选择高出约24%。
  - **无意数据泄露**：LLM和LVLM在训练过程中可能记住了评测样本，导致在无视觉输入时也能正确回答原本需要图像的题目。例如，Sphinx-X-MoE在无图像下在MMMU上达43.6%，比其LLM骨干高17.9%。
- **整体含义**：这两个问题导致对LVLM实际多模态增益的误判，可能误导后续研究。因此，需要构建一个真正依赖视觉、无数据泄露的高质量评测基准。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：构建一个“视觉不可或缺”的多模态基准MMStar，包含1500个人工精选样本，覆盖6大核心能力和18个详细维度。同时提出两个新指标——多模态增益（MG）和多模态泄露（ML），用于量化LVLM的实际多模态能力增益和数据泄露程度。
- **关键技术细节**：
  - **数据筛选流程**：
    - 从6个现有基准（MMMU、MMBench、ScienceQA、AI2D、SEED、MathVista）收集原始样本共22401个。
    - **自动化粗筛**：使用8个强大LLM（2个闭源：GPT4-Turbo、GeminiPro；6个开源≥20B：LLaMA-70B、Qwen1.5-72B、Mixtral-8x7B等）作为检测器，以2-shot方式评估。保留命中次数≤2的样本（即至少6/8的LLM无法正确回答），粗筛后剩11607个。
    - **人工复核**：3名专家对每一样本进行审核，确保：答案必须依赖视觉内容；样本覆盖6大核心能力和18个详细维度；主要需要高级多模态能力。同时按16个LVLM的命中次数将样本分为4个难度等级（易、中、难、极难），最终精选1500个样本。
  - **MMStar结构**：6大核心能力——粗粒度感知(CP)、细粒度感知(FP)、实例推理(IR)、逻辑推理(LR)、科学与技术(ST)、数学(MA)；每个核心能力下含3个详细维度，共18个轴。
  - **两个新指标（公式）**：
    - **多模态增益 (MG)**：MG = S_wv - S_ov，其中S_wv为有视觉输入时的得分，S_ov为无视觉输入时的得分。
    - **多模态泄露 (ML)**：ML = max(0, S_ov - St)，其中St为对应LLM基座的得分（无多模态训练）。
  - **评估代码**：基于VLMEvalKit框架，所有问题统一为多选题形式，使用启发式匹配规则计算准确率，避免重复调用GPT-4提取答案。

## 3. 实验设计：数据集、Benchmark、对比方法

- **使用的数据集**：
  - 训练/评测基准：MMMU-Val、MMBench-EN-Dev、ScienceQA-Test、AI2D-Test、SEED-Image、MathVista-Mini（共6个流行基准）。
  - 新基准：MMStar（1500样本）。
- **Benchmark**：MMStar，覆盖6个核心能力维度，难度分层。
- **对比方法**：
  - **LLM**：22个模型，包括2个闭源（GPT4-Turbo、GeminiPro）和20个开源（Qwen1.5系列、Phi2、Yi系列、LLaMA2系列、Vicuna系列、Deepseek系列、InternLM2系列、Baichuan2系列、Mistral/Mixtral系列等），大小从1.8B到72B。
  - **LVLM**：16个模型，包括2个闭源（GPT4V、GeminiPro-Vision）和14个开源（TinyLLaVA、Yi-VL、LLaVA-1.5、ShareGPT4V、InternLM-XComposer2、Deepseek-VL、Qwen-VL-Chat、Monkey-Chat、CogVLM-Chat、LLaVA-Next、InternVL-Chat-v1.2、Sphinx-X-MoE等），参数从3B到57B。
- **评测策略**：LLM采用2-shot（减少拒答和格式对齐）或0-shot；LVLM采用0-shot；LVLM-text设置（无图像输入）通过移除图像token或替换为灰色图实现。

## 4. 资源与算力

- 文中未明确说明具体使用的GPU型号、数量和训练时长。仅在附录A.1中提到“所有非API评估使用NVIDIA A100 GPU”，但未量化总计算时间或资源消耗。因此，算力信息不充分。

## 5. 实验数量与充分性

- **实验数量**：
  - 对22个LLM在6个公共基准和MMStar上进行评测，并统计LLM命中率（图2、表1、表5）。
  - 对16个LVLM在6个公共基准和MMStar上进行评测，并计算无图像输入下的得分（表2、表7）。
  - 在MMStar上比较所有LLM和LVLM的全面结果（表3、表5）。
  - 对所有LVLM在7个基准（6个公共+MMStar）计算MG和ML指标（表4）。
  - 提供了大量定性案例（图1、图5-图10）说明视觉不必要和泄漏情况。
  - 附录中还包括0-shot对比、更多样本展示等。
- **充分性**：实验覆盖了主流的LLM和LVLM，跨越多个规模、架构，并在多个基准上进行了量化对比。但消融实验较少（例如未对不同筛选策略、不同LLM检测器组合做详细消融）。总体上结论有充分数据支撑，但可进一步加强消融分析。

## 6. 论文的主要结论与发现

- 现有LVLM评测基准中普遍存在视觉不必要问题（ScienceQA高达57.2%样本可通过LLM直接回答）和无意数据泄露问题（部分LVLM无图像输入时表现远超对应LLM骨干）。
- 构建的MMStar基准有效消除了这两个问题：LLM在MMStar上的表现接近随机猜测（平均约24%），表明样本真正依赖视觉，且无LLM级别泄露。
- GPT4V（高分辨率）在MMStar上以57.1%准确率排名第一，但仍远未达到60%的通过线；细粒度感知、逻辑推理、科学与技术、数学等维度对现有LVLM最具挑战性。
- 提出的MG和ML指标揭示了不同LVLM的差异：GPT4V的MG最高（25.9）且ML较低（5.3），表明其多模态训练有效且泄露少；而Monkey-Chat、Sphinx-X-MoE等模型ML较高，需引起重视。
- 在6个公共基准上，MMBench的平均MG最高（50.1），MMMU平均MG最低（5.8）。MMStar的平均ML仅为1.9，远低于其他基准，是最公平的评测平台。

## 7. 优点：方法或实验设计上的亮点

- **问题意识清晰**：精准识别并量化了LVLM评测中的两个关键漏洞（视觉依赖不足和数据泄露），并通过详实实验证明其普遍性和严重性。
- **数据筛选流程严谨**：自动化粗筛+人工复核相结合，利用多个强大LLM作为检测器，确保样本视觉依赖性和低泄露风险；同时考虑难度平衡和维度覆盖。
- **指标创新**：提出MG和ML指标，能够分离多模态训练带来的真实增益与记忆效应，为公平比较提供新工具。
- **实验全面**：涵盖了22个LLM和16个LVLM，包含多种架构和参数规模，结果具有代表性。
- **开源与可复现**：基于VLMEvalKit，公开代码和基准，便于社区使用和验证。

## 8. 不足与局限

- **算力资源未明确报告**：没有提供详细的GPU型号、数量和训练/推理时长，影响可复现性评估。
- **消融实验不足**：未对不同LLM检测器组合、不同筛选阈值（如命中次数≤2 vs ≤1）等进行系统性消融，难以评估筛选流程的鲁棒性。
- **时间局限性**：虽然当前筛选保证了样本未被现有LVLM训练数据泄露，但未来新模型可能仍会无意包含这些样本，需要持续更新。作者计划构建MMStar-Test在线测试集，但尚未完成。
- **样本量较小**：仅1500个样本，虽然精心挑选，但难以完全覆盖所有多模态场景，可能对某些细粒度能力评估不够充分。
- **可能的主观偏差**：人工复核由3位专家完成，虽经交叉验证，但仍可能引入主观偏好，尤其在对“视觉依赖”的判断上。
- **仅含多选题**：所有样本均为选择题，缺乏开放性问答、生成式任务等评估形式，可能限制对LVLM真实对话能力的测量。

（完）
