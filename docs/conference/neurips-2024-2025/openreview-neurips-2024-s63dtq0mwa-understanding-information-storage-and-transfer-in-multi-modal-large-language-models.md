---
title: Understanding Information Storage and Transfer in Multi-Modal Large Language Models
title_zh: 理解多模态大语言模型中的信息存储与传输
authors: "Samyadeep Basu, Martin Grayson, Cecily Morrison, Besmira Nushi, Soheil Feizi, Daniela Massiceti"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=s63dtq0mwA"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 研究多模态大语言模型中的信息存储与传输机制
tldr: 该论文针对多模态大语言模型（MLLM）的信息存储与传输机制展开研究，特别是事实性视觉问答场景。现有工作主要关注纯文本大语言模型，尚未深入分析多模态情景下的信息流。作者采用基于约束的公式，通过分析和实验揭示了MLLM如何处理视觉问题中的信息。这项工作加深了我们对多模态模型内部机制的理解，为未来MLLM的改进提供了理论基础。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1489, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1333, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1483, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 660, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 659, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1497, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1483, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1478, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1508, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1481, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1498, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1492, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 792, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1464, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1512, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1464, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 343, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-s63dtq0mwa/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 647, \"height\": 903, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-s63dtq0mwa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 205, \"label\": \"Table\"}]"
motivation: 已有研究揭示了大语言模型中的信息存储与流动机制，但这些研究尚未扩展到多模态大语言模型。
method: 采用基于约束的公式来分析MLLM在事实性视觉问答中如何处理信息。
result: 实验揭示了MLLM在视觉问答任务中的信息存储与传输模式。
conclusion: 该工作将模型理解研究从纯文本扩展到多模态，为更透明的MLLM设计奠定基础。
---

## Abstract
Understanding the mechanisms of information storage and transfer in Transformer-based models is important for driving model understanding progress. Recent work has studied these mechanisms for Large Language Models (LLMs), revealing insights on how information is stored in a model's parameters and how information flows to and from these parameters in response to specific prompts. However, these studies have not yet been extended to Multi-modal Large Language Models (MLLMs). Given their expanding capabilities and real-world use, we start by studying one aspect of these models -- how MLLMs process information in a factual visual question answering task. We use a constraint-based formulation which views a visual question as having a set of visual or textual constraints that the model's generated answer must satisfy to be correct (e.g. What movie directed by \emph{the director in this photo} has won a \emph{Golden Globe}?). Under this setting, we contribute i) a method that extends causal information tracing from pure language to the multi-modal setting, and ii) \emph{VQA-Constraints}, a test-bed of 9.7K visual questions annotated with constraints. We use these tools to study two open-source MLLMs, LLaVa and multi-modal Phi-2. Our key findings show that these MLLMs rely on MLP and self-attention blocks in much earlier layers for information storage, compared to LLMs whose mid-layer MLPs are more important. We also show that a consistent small subset of visual tokens output by the vision encoder are responsible for transferring information from the image to these causal blocks. We validate these mechanisms by introducing MultEdit a model-editing algorithm that can correct errors and insert new long-tailed information into MLLMs by targeting these causal blocks. We will publicly release our dataset and code.

---

## 论文详细总结（自动生成）

# 理解多模态大语言模型中的信息存储与传输

## 1. 论文的核心问题与整体含义（研究动机和背景）

论文聚焦于多模态大语言模型（MLLMs）中信息存储与传输机制的理解。虽然已有大量工作研究了纯文本大语言模型（LLMs）中事实知识在参数中的存储位置和流动路径，但这些研究尚未扩展到多模态场景。MLLMs（如LLaVa、多模态Phi-2）在视觉问答等任务中广泛应用，其架构（视觉编码器+投影层+语言模型）与LLMs存在显著差异，因此原有的理解可能无法直接迁移。论文旨在通过事实性视觉问答（factual VQA）任务，首次系统性地探究MLLMs如何处理多模态信息，从而推动模型可解释性研究。

## 2. 论文提出的方法论：核心思想、关键技术细节

论文提出了一个基于约束的框架，将视觉问题视为包含视觉约束（如“这张照片中的导演”）和/或文本约束（如“获得金球奖”）的组合。模型需要从参数记忆中检索满足这些约束的信息才能正确回答。

主要方法论包括：

- **多模态因果追踪（Multimodal Causal Trace）**：扩展了LLM中的因果追踪方法。标准方法通过向约束词嵌入添加高斯噪声来破坏模型，但MLLM中视觉令牌数量巨大（如576个），噪声难以逆转。论文采用**替换约束词ID**的方式（例如将“这座建筑”替换为“泰姬陵”）来破坏模型，同时保持语法合理。然后迭代地从干净模型复制层激活到破坏模型（窗口大小为1或3），计算间接估计效应（restored probability - corrupted probability），从而定位因果层（即信息存储的关键层）。

- **注意力贡献（Attention Contributions）**：用于分析信息传输。计算在自注意力层中，一组令牌（如视觉令牌）对另一组令牌（如约束令牌）的贡献值，追踪信息从视觉令牌到因果层、以及从因果层到最终令牌的流动。

- **模型编辑算法 MultEdit**：基于定位到的早期因果MLP层，对其中的投影矩阵 \(W_{\text{proj}}\) 进行闭式更新。首先通过前向传播获取关键（key，MLP输入）和值（value，MLP输出），然后优化值使正确答案概率上升，最后求解带L2正则的最小二乘问题得到新的投影矩阵。公式：\(W_{\text{proj}}^{*} = (\lambda W_{\text{proj}}' + z^* k^T)(\lambda I + k k^T)^{-1}\)。

- **新数据集 VQA-Constraints**：包含9.7K个视觉问题，标注了视觉约束和文本约束。数据来源于OK-VQA、Movies（从文本改造）和Known（从文本改造），使用GPT-4辅助标注并人工校验。

## 3. 实验设计

- **数据集/场景**：
  - 因果分析：使用VQA-Constraints中的三个子集（Multimodal Known、Movies、OK-VQA），包含单约束（仅视觉约束）和多约束（视觉+文本约束）问题。
  - 模型编辑：使用Multimodal Known中LLaVa答错的约450个问题（修正错误场景），以及Encyclopedic VQA中的长尾知识问题（插入新知识场景）。

- **基准模型**：LLaVa-7B和多模态Phi-2（均属于投影层族）。

- **对比方法**：
  - 因果分析对比：LLaMA (Vicuna)-7B（纯文本LLM）。
  - 模型编辑对比：全部微调（fine-tuning all layers）和带约束微调（fine-tuning with constraints from [38]）。

- **评估指标**：
  - 编辑效果：Editing Efficacy（正确答案概率）、Generalization（问题改写后概率）、Specificity（无关VQA准确率）。

## 4. 资源与算力

论文在“Compute”部分说明：所有实验在 **Nvidia-A6000 和 A5000 GPUs** 上执行。未提供具体数量或训练时长。实验主要为推理和少量优化（编辑阶段），因此算力需求相对较低。

## 5. 实验数量与充分性

- **因果分析**：在三个数据集上对LLaVa和多模态Phi-2分别进行了单约束和多约束的因果追踪，并对比了不同窗口大小（1、3、6）。提供了定性图（如Fig.3、Fig.8-13）和平均结果。
- **注意力贡献分析**：展示了视觉令牌到因果层的贡献热图（Fig.5），以及约束令牌到最终令牌的贡献对比（Fig.15-16）。
- **模型编辑**：两个场景（修正错误、插入长尾知识），每个场景报告了平均指标，并消融了编辑不同层（早期、中期、后期）的效果（Fig.14）。
- **早期失败检测**：使用注意力贡献和置信度计算AUROC（0.63 vs 0.76），结果来自Multimodal Known数据集。

总体而言，实验覆盖了多个数据集、两种架构、多种窗口大小，并进行了消融。但在统计显著性（误差棒）方面未明确报告（虽然论文声称“已报告误差信息”，但正文中主要展示定性图或平均柱状图，无置信区间）。对比基线仅有两个微调方法，鲁棒性分析（如不同随机种子）未提及。

## 6. 论文的主要结论与发现

1. **存储位置不同**：MLLMs的信息存储于 **早期MLP和自注意力层**（1-4层），而LLMs存储在中间层（4-7层）。MLLMs仅需窗口大小为1即可恢复因果状态，LLMs需要更大窗口（5以上）。
2. **多约束需更多记忆**：对于同时包含视觉和文本约束的问题，因果层扩展到早期和中间层（窗口大小至少6）。
3. **视觉信息传输**：视觉编码器输出的**后部视觉令牌**（索引540-576）通过第一自注意力层将信息传递到早期因果MLP层。
4. **中间层负责路由**：自注意力层的中间层（16-17层）负责将信息从存储位置传递到最终令牌。
5. **正确/错误回答差异**：正确回答时中间层注意力贡献更高，可辅助早期失败检测（AUROC 0.63），但模型置信度更可靠（AUROC 0.76）。
6. **模型编辑有效**：MultEdit通过在早期因果MLP层进行闭式更新，能有效修正错误（编辑正确率0.82）和插入长尾知识（0.83），且对无关任务影响小（精度下降约1.5%）。

## 7. 优点

- **新颖性**：首次将信息存储/传输研究扩展到多模态大语言模型，揭示了与纯文本模型的关键差异。
- **方法论严谨**：提出了适用于MLLM的因果追踪方法（通过替换而非加噪），解决了视觉令牌数量大的问题。
- **数据集贡献**：VQA-Constraints为未来研究提供了带约束标注的多模态测试床。
- **实用价值**：基于发现的因果层设计模型编辑算法MultEdit，实现了高效且精准的知识修正与注入。
- **解释性**：结合因果追踪和注意力贡献，形成了完整的“存储-传输”分析链。

## 8. 不足与局限

- **实验覆盖有限**：仅测试了投影层族MLLMs（LLaVa、Phi-2），未探索交叉注意力族（如Flamingo、BLIP-2）。结果可能不普适。
- **问题类型局限**：仅针对事实性VQA，且答案形式为短词/短语，未涉及主观问题、图表或长文本生成。
- **视觉令牌语义未映射**：未分析视觉令牌对应图像中的哪些具体概念。
- **编辑方法潜在风险**：MultEdit可能被恶意用于注入虚假信息，论文虽提到但未提供防御机制。
- **统计报告不足**：未提供误差棒或多次运行结果，实验公平性（如超参数选择细节）描述不够充分。
- **注意力贡献作为早期检测的AUROC仅0.63**，实际应用价值有限。

（完）
