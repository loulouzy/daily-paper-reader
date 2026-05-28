---
title: Unveiling the Tapestry of Consistency in Large Vision-Language Models
title_zh: 揭示大视觉语言模型的一致性图景
authors: "Yuan Zhang, Fei Xiao, Tao Huang, Chun-Kai Fan, Hongyuan Dong, Jiawen Li, Jiacong Wang, Kuan Cheng, Shanghang Zhang, Haoyuan Guo"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=tu1oC7zHGW"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 研究大视觉语言模型的一致性基准
tldr: 本文针对大视觉语言模型（LVLM）在不同答案空间下的不一致性问题，提出了多模态基准ConBench。研究发现，在判别任务中，答案空间越大，模型一致性越差。通过系统分析，揭示了LVLM在推理一致性的关键规律。该基准为评估和改进LVLM的可靠性提供了工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 665, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1426, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 635, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 444, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 444, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 389, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 267, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 316, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 389, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 392, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 434, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 305, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 403, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 339, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-tu1oc7zhgw/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 329, \"height\": 358, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-tu1oc7zhgw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 904, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-tu1oc7zhgw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1264, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-tu1oc7zhgw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1281, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-tu1oc7zhgw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 989, \"height\": 280, \"label\": \"Table\"}]"
motivation: LVLM在不同答案空间下回答不一致，损害信任。
method: 构建多模态基准ConBench，分析不同答案空间对一致性的影响。
result: 发现答案空间越大，一致性越差；揭示了具体规律。
conclusion: 该基准有助于深入理解和改善LVLM的一致性。
---

## Abstract
Large vision-language models (LVLMs) have recently achieved rapid progress, exhibiting great perception and reasoning abilities concerning visual information. However, when faced with prompts in different sizes of solution spaces, LVLMs fail to always give consistent answers regarding the same knowledge point. This inconsistency of answers between different solution spaces is prevalent in LVLMs and erodes trust. To this end, we provide a multi-modal benchmark ConBench, to intuitively analyze how LVLMs perform when the solution space of a prompt revolves around a knowledge point. Based on the ConBench tool, we are the first to reveal the tapestry and get the following findings: (1) In the discriminate realm, the larger the solution space of the prompt, the lower the accuracy of the answers. 
(2) Establish the relationship between the discriminative and generative realms: the accuracy of the discriminative question type exhibits a strong positive correlation with its Consistency with the caption. (3) Compared to open-source models, closed-source models exhibit a pronounced bias advantage in terms of Consistency. Eventually, we ameliorate the consistency of LVLMs by trigger-based diagnostic refinement, indirectly improving the performance of their caption. We hope this paper will accelerate the research community in better evaluating their models and encourage future advancements in the consistency domain.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大视觉语言模型（LVLM）在面对不同答案空间大小的提示时，针对同一知识点往往给出不一致的回答。这种**不一致性**在主流LVLM中普遍存在，损害了用户对模型的信任。
- **研究背景与动机**：
  - 现有多模态基准（如MME、SeedBench、MMBench等）仅使用单一种类的提示（如True/False、多项选择或有限VQA），未能考察模型在不同问题格式下的回答一致性。
  - 用户在实际使用中提问方式多样，模型需要具备跨格式的正确且一致的响应能力。
  - 前期工作在纯语言模型（LLM）中初步研究了不一致性，但针对LVLM的视觉-语言跨模态不一致性尚无专门基准和分析。
- **整体含义**：本文旨在系统定义和评估LVLM的一致性，通过构建基准ConBench，揭示不一致性的规律，并提出改进方法，从而提升模型的可靠性和用户体验。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过构建多类型、同知识点的提示对（包括True/False、多项选择、有限VQA以及生成式描述），评估LVLM输出的一致性。基于分析结果，提出触发式诊断精炼（Trigger-based Diagnostic Refinement, TDR）方法，利用低置信度词触发自我校准，改善生成质量。
- **关键技术细节**：
  - **ConBench构建**：
    - 从MME、SeedBench、MMBench、MMMU中人工挑选1000张图片，每张图片围绕同一知识点构造三种判别式问题（True/False、多项选择、有限VQA）以及一个生成式描述提示。
    - 提示生成借助ChatGPT/GPT-4，并经过人工审核。
    - 严格平衡选项分布（True/False中Yes/No各50%，多项选择中四个选项正确概率各25%）。
  - **评估指标**：
    - **ConScore[D]**：同一case中三个判别式问题全部回答正确得1分，满分1000分，转为百分比。
    - **ConScore[C]**：利用GPT将生成式描述与每个判别式答案进行一致性判断（基于MRC任务），取三个一致性得分的平均值。
  - **触发式诊断精炼（TDR）**：
    - 先让LVLM生成描述并记录每个token的概率。
    - 过滤无信息词（保留名词、形容词、量词），对概率低于阈值τ=0.85的词，构建True/False判别式问题（如“图中有猫吗？”），强制模型自我验证。
    - 将诊断问题和答案整合到新提示中，重新生成描述。
    - 无需额外训练，可迭代多轮。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：使用ConBench（1000张图片，4000个提示，3000个判别式答案的ground truth）。
- **基准**：ConBench本身作为评估基准，提供两个度量（ConScore[D]和ConScore[C]）。
- **对比方法**：评估了14个流行LVLM，包括：
  - **闭源模型**：GPT-4V、GPT-4-Omni、Gemini-Pro-Vision、Gemini-Ultra-Vision、Qwen-VL-Plus、Qwen-VL-Max。
  - **开源模型**：
    - 7B：LLaVA-v1.5-7B、Qwen-VL-Chat。
    - ~13B：LLaVA-v1.5-13B、MiniGemini-13B、InternVL-v1.5-26B。
    - ~34B：LLaVA-NeXT-34B、MiniGemini-34B、InternVL-v1.2P-40B。
- **TDR方法验证**：在LLaVA-NeXT-34B和MiniGemini-34B上进行实验，报告ConScore[C]及其各子指标提升。

## 4. 资源与算力

- 论文在实验部分提到：“The evaluation in our paper only needs an A100-80GB GPU.” 但未明确说明使用的GPU数量、训练时长或总计算量。对于TDR方法，由于是推理阶段微调（无需训练），计算开销相对较低，但具体算力细节未提供。

## 5. 实验数量与充分性

- **实验组数**：
  - 主实验：在14个模型上报告ConScore[D]和ConScore[C]（表1和表2）。
  - 附加分析：
    - 计算正确/错误答案的一致性比例（表3）。
    - 分析置信度与logits（图5），基于随机抽取的50个一致和50个不一致样本。
    - 可视化判别准确率与生成一致性之间的关系（图6、图7），包含皮尔逊相关系数（>0.85）。
    - TDR方法在两个模型上的对比实验（表4）。
  - 消融实验：未明确提出消融，但TDR方法中仅使用True/False问题，文中提及可扩展为多问题多轮迭代。
- **充分性评价**：
  - **优点**：覆盖多种模型规模、架构、来源（闭源/开源）；评估维度包括感知、认知、知识三个层次；指标区分判别与生成两个域；统计分析充分（置信度、相关性）。
  - **客观性**：使用GPT进行生成一致性判断时，人工抽样验证准确率达95%，较为可靠。但依赖GPT可能引入偏差；TDR方法仅在两个模型上验证，泛化性证据不足。

## 6. 论文的主要结论与发现

1. **判别域**：
   - 答案空间越大（True/False → 多项选择 → 有限VQA），准确率越低。
   - 所有三种问题都答错的情况下，一致性的错误（即错误但一致的情况）极少（不超过0.50%）。
   - 错误答案的置信度随答案空间增大而显著下降。

2. **生成域**：
   - 判别答案的准确率与其与生成描述的一致性呈强正相关（皮尔逊相关系数>0.85）。
   - 答案空间越大，判别答案与生成描述的一致性越强（Con[T] < Con[C] < Con[V]成立）。

3. **一致性偏差**：
   - 闭源模型在相同准确率下，与生成描述的一致性明显优于开源模型（偏差更大），解释了闭源模型在实际应用中常提供更好用户体验的现象。

4. **方法效果**：
   - TDR方法在LLaVA-NeXT-34B上ConScore[C]提升9.1%，在MiniGemini-34B上提升9.6%，表明通过低置信度词触发自我验证可有效提高描述质量。

## 7. 优点

- **新颖性**：首个专门评估LVLM一致性的基准，填补了空白；首次系统揭示答案空间与一致性、准确率之间的关系。
- **全面性**：涵盖多种问题类型、三种核心能力层次、14个模型，分析维度丰富（置信度、logits、偏差）。
- **实用性**：提出的TDR方法无需额外训练，轻量级提升生成质量，具有实际应用潜力。
- **开源**：数据集和评估代码将公开，可复现。

## 8. 不足与局限

- **生成一致性评估依赖GPT**：论文自己指出“assessing the consistency between captions and discriminative answers is judged by GPT, posing a risk of inaccurate evaluations”，尽管人工抽样准确率95%，但仍有偏差和成本。
- **TDR方法局限性**：
  - 增加了推理时的计算开销（额外调用模型进行自我验证）。
  - 方法受限于LVLM本身能力，如果模型无法正确回答诊断问题，则改进有限。
  - 目前仅在两个34B模型上验证，未探索小模型或更多模型。
- **实验覆盖**：
  - 未进行消融研究（如不同阈值τ、不同诊断问题类型的影响）。
  - 未与现有一致性增强方法（如对比学习、正则化）进行对比。
- **数据集规模**：1000张图片在数量上相对较小，可能不足以覆盖所有复杂场景。

（完）
