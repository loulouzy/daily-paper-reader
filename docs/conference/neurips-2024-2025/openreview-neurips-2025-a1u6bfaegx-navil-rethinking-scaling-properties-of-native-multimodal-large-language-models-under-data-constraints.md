---
title: "NaViL: Rethinking Scaling Properties of Native Multimodal Large Language Models under Data Constraints"
title_zh: "NaViL: 数据约束下原生多模态大语言模型的缩放特性再思考"
authors: "Changyao Tian, Hao Li, Gen Luo, Xizhou Zhu, Weijie Su, Hanming Deng, Jinguo Zhu, Jie Shao, Ziran Zhu, Yunpeng Liu, Lewei Lu, Wenhai Wang, Hongsheng Li, Jifeng Dai"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=A1u6BFAEGx"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型论文
tldr: 针对现有MLLM组合训练范式难以探索多模态缩放特性的问题，NaViL采用端到端原生训练方式，在数据约束下系统研究设计空间和缩放规律，找到了性能与成本最优的元架构。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 529, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1378, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 584, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 558, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1356, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1303, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1374, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 815, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 573, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 566, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 573, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 809, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 591, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a1u6bfaegx/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 511, \"height\": 248, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 948, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 882, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 952, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1216, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 1087, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1006, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1434, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 567, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 566, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a1u6bfaegx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 565, \"height\": 444, \"label\": \"Table\"}]"
motivation: 当前多模态大语言模型采用组合训练，其多模态缩放特性难以研究。
method: 采用端到端原生训练，系统研究不同架构选择的性能与成本平衡。
result: 确定了数据约束下的最优元架构，揭示了多模态缩放规律。
conclusion: 原生训练为高效多模态大模型设计提供了新视角和实用指南。
---

## Abstract
Compositional training has been the de-facto paradigm in existing Multimodal Large Language Models (MLLMs), where pre-trained vision encoders are connected with pre-trained  LLMs through continuous multimodal pre-training. However,  the multimodal scaling property of this paradigm remains difficult to explore due to the separated training. In this paper, we focus on the native training of MLLMs in an end-to-end manner  and systematically study its design space and scaling property under a practical setting, i.e., data constraint. Through careful study of various choices in MLLM, we obtain the optimal meta-architecture that best balances performance and training cost. After that, we further explore the scaling properties of the native MLLM and indicate the positively correlated scaling relationship between visual encoders and LLMs.  Based on these findings, we propose a native MLLM called NaViL, combined with a simple and cost-effective recipe.  Experimental results on 14 multimodal benchmarks confirm the competitive performance of NaViL against existing  MLLMs. Besides that, our findings and results provide in-depth insights for the future study of native MLLMs.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

当前多模态大语言模型（MLLMs）普遍采用**组合训练范式**：分别预训练视觉编码器和语言模型，再通过连续的多模态预训练将它们连接。然而，这种分离式训练使得**多模态缩放特性难以探索**，并且当面临**数据约束（有限训练数据）** 时，原生MLLMs（端到端联合训练）是否能在可接受成本下达到或超越顶尖组合MLLMs的性能，仍是一个关键实际问题。为此，论文系统研究了数据约束下原生MLLMs的设计空间和缩放规律，并提出了高效的原生MLLM——**NaViL**。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 采用**端到端原生训练**方式，视觉编码器与语言模型（含MoE扩展）同时优化，同一目标（Next-Token Prediction）。
- 通过系统实验找到**性能与训练成本最优平衡的元架构**，并揭示视觉编码器与LLM之间的正相关缩放关系。

### 关键技术细节
1. **元架构定义**
   - 视觉编码器 \( V_{d,w} \)：d层Transformer，宽度w，双向注意力，下采样+MLP连接器。
   - LLM：基于预训练LLM（如InternLM2-1.8B）初始化。
   - MoE扩展：在LLM的每层引入**模态特异性专家**——注意力层和FFN层分别使用不同投影矩阵处理视觉和语言token，保持激活参数数不变。

2. **最优设计发现**
   - **LLM初始化**：从预训练LLM初始化相比从头训练，收敛速度提高10倍以上，零样本caption性能显著领先。
   - **MoE有效性**：MoE架构使模型在相同激活参数下损失下降更快，达到相同验证损失仅需1/10的数据。
   - **视觉编码器深度与宽度**：在固定参数量下，深度过浅或过宽均导致性能下降，存在一个较宽的合理区间；浅层编码器在早期数据少时收敛快，深层编码器在更多数据下略微更优。

3. **缩放规律**
   - 单独缩放LLM：损失随LLM大小指数下降，符合语言模型缩放律。
   - 单独缩放视觉编码器：在固定LLM下，视觉编码器增大收益递减，受限于LLM容量。
   - 联合缩放：最优视觉编码器大小随LLM大小**对数线性增长**，表明两者应协同缩放。这挑战了组合MLLM中固定视觉编码器尺寸的做法。

4. **NaViL架构**
   - 支持任意分辨率输入，使用 **Visual Multi-scale Packing**（多尺度图像拼接）。
   - 特殊标记 `<begin_of_image>`、`<end_of_image>`、`<end_of_line>`、`<end_of_scale>` 保持空间信息。

## 3. 实验设计

- **数据集**：
  - 预训练：约5亿图像-文本对（Laion-2B、Coyo-700M、Wukong、SA-1B），其中2亿用InternVL-8B合成描述；随后1.85亿高质量多模态数据（来自InternVL-2.5）。
  - 微调：680万高质量指令数据。
  - 消融验证：使用web-scale噪声数据子集及COCO Caption、Flickr Caption、NoCaps的CIDEr指标。
- **Benchmark（共14个）**：
  - 多模态综合：MMVet、MMMU、MMBench、MME、MathVista、OCRBench、CCBench。
  - VQA：TextVQA、ScienceQA-IMG、GQA、DocVQA、AI2D、ChartQA、InfographicVQA。
- **对比方法**：
  - 组合MLLM：InternVL-2.5-2B（直接对标，相同LLM和数据）、Qwen2VL、MiniCPM-V-2、PaliGemma等。
  - 原生MLLM：EVE、Emu3、Mono-InternVL、Chameleon、VoRA、SAIL等。
  - 特别控制：InternVL-2.5-2B使用从6B蒸馏的300M视觉编码器，NaViL的视觉编码器为原生训练。

## 4. 资源与算力

论文**未明确说明具体GPU型号、数量和训练总时长**（因公司政策限制），仅给出训练步数和批次大小：
- NaViL-2B：预训练阶段S1.1（70k步，batch size 7000）、S1.2（40k步，batch size 4614）、SFT（30k步，batch size 2234）。
- NaViL-9B：预训练S1.1（50k步，batch size 10300）、S1.2（33k步，batch size 1792）、SFT（6k步，batch size 3520）。
- 总训练token量：NaViL-2B约800B，NaViL-9B约450B，远少于组合MLLM（如InternVL-2.5-8B需>3.5T）。

文中承认“因计算资源有限，仅探索到9B参数规模”。

## 5. 实验数量与充分性

- **消融实验**：包括LLM初始化（有/无）、MoE（有/无）、视觉编码器深度/宽度（5种组合 × 4种数据量）、视觉编码器与LLM大小独立缩放（3个LLM大小 × 5~6个视觉编码器大小 × 4种数据量）、联合缩放（找到最优编码器大小）——共计**数十组对比实验**。
- **最终性能对比**：在14个基准上与10+个基线方法对比，涵盖各种模态能力（OCR、图表、文档、推理、caption等）。
- **公平性**：控制相同LLM和高质量数据（与InternVL-2.5-2B一致）；比较时使用相同评测工具（OpenCompass）。
- **充分性**：多维度消融设计覆盖了架构、缩放、数据量，结论被多个指标（loss、CIDEr、准确率）交叉验证。但**未报告误差棒（统计显著性）**，部分实验（如零样本caption）只展示单次结果。

## 6. 论文的主要结论与发现

1. **LLM初始化**是原生MLLM高效训练的关键，从头训练需要>10倍数据才能追上。
2. **MoE扩展**在不增加激活参数下显著加速收敛并提升性能。
3. **视觉编码器**存在较宽的深度-宽度最优区间，浅层编码器早期收敛快，深层编码器在大数据下略优。
4. **缩放特性**：
   - LLM缩放遵循传统语言缩放律（损失随指数下降）。
   - 视觉编码器缩放收益递减，受LLM容量约束。
   - **最优视觉编码器大小与LLM大小呈对数线性关系**，应联合缩放。
5. **NaViL性能**：在2.4B激活参数下，平均性能优于所有现有原生MLLM（7B级），且与组合MLLM InternVL-2.5-2B持平（后者使用蒸馏视觉编码器）。9B版本进一步超越原生MLLM。
6. **训练效率**：NaViL仅需800B/450B token即达到与组合MLLM（>3T token）相当的性能。

## 7. 优点

- **系统性与完整性**：首次在数据约束下对原生MLLM的设计空间和缩放特性进行系统研究，从架构组件到联合缩放，逻辑清晰。
- **结论可操作性强**：5条明确观察可直接指导后续MLLM设计（如“最优编码器与LLM大小正相关”）。
- **数据高效**：仅用约6亿预训练数据达到顶尖水平，远超组合MLLM的数据需求。
- **公平比较**：控制LLM和高质量数据与最强组合基线一致，消除数据不平衡因素。
- **可视化解释**：注意力图可视化直观展示大视觉编码器如何促进跨模态交互。

## 8. 不足与局限

- **规模限制**：仅验证到9B参数（约8B激活），更大规模（30B/70B）的缩放规律未验证，结论泛化性待确认。
- **模态局限**：仅涵盖视觉和语言，未涉及音频、视频等多模态。
- **统计数据缺失**：未报告误差棒或多次运行结果，实验结果可能存在随机波动。
- **资源信息不透明**：GPU型号、数量、总耗时不公开，可复现性降低。
- **数据不可全部开放**：训练数据含商业元素，部分无法开源。
- **对比覆盖不足**：未与Gemini、GPT-4V等闭源模型比较（规模差异大）。
- **消融实验设计**：视觉编码器深度-宽度消融仅在固定总参数量（600M）下进行，未验证更大参数量时是否保持最优比例。

（完）
