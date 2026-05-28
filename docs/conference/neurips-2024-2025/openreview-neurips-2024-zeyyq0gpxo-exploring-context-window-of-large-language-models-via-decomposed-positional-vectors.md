---
title: Exploring Context Window of Large Language Models via Decomposed Positional Vectors
title_zh: 通过分解位置向量探索大语言模型的上下文窗口
authors: "zican Dong, Junyi Li, Xin Men, Xin Zhao, Bingning Wang, Zhen Tian, weipeng chen, Ji-Rong Wen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=zeYyq0GpXO"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 大型语言模型实验室研究论文
tldr: 针对Transformer大语言模型上下文窗口有限的问题，本文通过均值分解法从隐藏状态中解耦位置向量，分析了位置信息的形成及其对注意力的影响，并研究了超长文本下位置向量的变化规律，为理解长度外推方法提供了新视角。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-zeyyq0gpxo/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 3108, \"height\": 2046}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-zeyyq0gpxo/fig-002.webp\", \"caption\": \"\", \"page\": 5, \"index\": 2, \"width\": 7859, \"height\": 3664}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-zeyyq0gpxo/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 364, \"height\": 355}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-zeyyq0gpxo/fig-004.webp\", \"caption\": \"\", \"page\": 7, \"index\": 4, \"width\": 364, \"height\": 355}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-zeyyq0gpxo/fig-005.webp\", \"caption\": \"\", \"page\": 18, \"index\": 5, \"width\": 9000, \"height\": 3600}]"
motivation: 现有大语言模型上下文窗口有限，超长文本下性能显著下降，且对长度外推方法的机制解释不足。
method: 提出均值分解法从隐藏状态中解耦位置向量，分析其形成过程及对注意力的影响。
result: 揭示了位置向量在上下文窗口内外的行为模式，为理解长度外推提供了理论依据。
conclusion: 该方法有助于解释大语言模型的位置编码机制，可指导更优的长度外推技术。
---

## Abstract
Transformer-based large language models (LLMs) typically have a limited context window, resulting in significant performance degradation when processing text beyond the length of the context window. Extensive studies have been proposed to extend the context window and achieve length extrapolation of LLMs, but there is still a lack of in-depth interpretation of these approaches. In this study, we explore the positional information within and beyond the context window for deciphering the underlying mechanism of LLMs. By using a mean-based decomposition method, we disentangle positional vectors from hidden states of LLMs and analyze their formation and effect on attention. Furthermore, when texts exceed the context window, we analyze the change of positional vectors in two settings, i.e., direct extrapolation and context window extension. Based on our findings, we design two training-free context window extension methods, positional vector replacement and attention window extension. Experimental results show that our methods can effectively extend the context window length.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：基于Transformer的大语言模型（LLMs）通常具有有限的上下文窗口（context window），当输入文本超出该长度时，模型性能会显著下降（表现为困惑度飙升）。虽然已有多种长度外推和上下文窗口扩展方法，但这些方法背后的机制缺乏深入解释。
- **背景**：位置编码（如RoPE、ALiBi）或无位置编码（NoPE）的Transformer中，隐式位置信息存在于隐藏状态中。先前工作已发现位置向量可分解为语义向量和位置向量，但尚未系统分析其在上下文窗口内外的形成与影响。
- **核心目标**：通过分解位置向量揭示LLMs上下文窗口的工作机制，并基于发现提出无需训练的上下文窗口扩展方法。

## 2. 方法论
### 核心思想
- 采用**均值分解法**将隐藏状态 \(\mathbf{h}_{l,t}\) 分解为位置向量 \(\mathbf{p}_{l,t}\) 和语义向量 \(\mathbf{c}_{l,t}\)：
  \[
  \mathbf{h}_{l,t} = \mathbf{p}_{l,t} + \mathbf{c}_{l,t}
  \]
  其中位置向量进一步分解为均值向量 \(\mathbf{u}_l\) 和位置基向量 \(\mathbf{m}_{l,t}\)：
  \[
  \mathbf{p}_{l,t} = \mathbf{u}_l + \mathbf{m}_{l,t}
  \]
- 通过在大规模语料上采样，利用统计平均估计 \(\mathbf{p}_{l,t}\)，从而解耦出纯净的位置信息。

### 关键技术细节
1. **位置向量形成机制分析**：
   - 在第一层注意力后，初始几个token（如1-4个）形成显著不同的位置向量，作为“锚点”（anchor）。
   - 后续token的位置向量通过注意力机制从初始token逐步传播形成：初始token的位置向量通过注意力权重影响后续token的隐藏状态，使得不同位置逐渐获得区分性。
   - 对于窗口注意力，位置向量随层数增加而逐步扩展，每个新窗口大小（W）的token会新增不同的位置向量。

2. **位置向量对注意力的影响**：
   - 移除位置向量或位置基会导致**注意力汇聚（attention sinks）** 消失（初始token的高注意力分数下降）。
   - 移除位置向量会导致**长距离衰减（long-term decay）** 特性丢失（注意力分数不再随相对距离增加而下降）。

3. **超长文本下的变化**：
   - 直接外推时，超出上下文窗口的位置向量变为**分布外（OOD）**，导致注意力和输出分布崩溃。
   - 上下文窗口扩展方法（如Dynamic-NTK、Attention Scaling）通过**插值**方式使位置向量保持一致性，有效插值比率接近扩展因子。

4. **提出的无需训练方法**：
   - **位置向量替换**：对NoPE模型，在早期层（如第4层）将超出窗口的位置向量替换为窗口内位置向量的线性插值结果，并乘以缩放因子α。初始4个token保持不变。
   - **注意力窗口扩展**：对窗口注意力的NoPE模型，同步扩展窗口大小（按比率r），并对注意力logits乘以缩放因子λ，实现位置向量的插值。

### 伪代码（文字说明）
- **位置向量替换**：从选定层的输出隐藏状态中减去原始位置向量，然后加上插值后的新位置向量（线性插值）。
- **注意力窗口扩展**：在FlashAttention-2中，将窗口大小设为rW，并将key乘以λ。

## 3. 实验设计
- **数据集**：
  - 训练/分析：RedPajama（用于持续预训练和位置向量提取，32K样本）。
  - 评估：PG-19测试集（语言建模，滑动窗口法计算不同长度下的PPL）。
- **基准模型**：
  - 基于TinyLlama-1.1B持续预训练50B tokens，构建多组对比模型：TL-NoPE、TL-RoPE、TL-ALiBi、TL-Window（窗口512）、TL-Window-80、TL-Window-RoPE。
  - 额外评估：Llama-3-8B、Yi-9B、Qwen1.5-7B、TL-NoPE-new（从头训练）。
- **对比方法**：
  - 长度外推：Dynamic-NTK（对RoPE）、Attention Scaling（对NoPE）。
  - 自己提出的：位置向量替换、注意力窗口扩展。
- **评估指标**：PPL、位置向量相似度（cosine similarity）、有效插值比率。

## 4. 资源与算力
- 模型持续预训练：**16块A800 GPU**，训练**2天**。
- 后续实验（推理、分析）：**8块A800 GPU**。
- 未明确说明单次推理或消融实验的具体GPU时长，但总体算力需求中等。

## 5. 实验数量与充分性
- **主要实验组**：
  - 位置向量形成分析：PCA可视化（多模型、多层）、消融实验（移除不同组件对后续位置向量和PPL的影响，如表2、表6）。
  - 注意力影响分析：注意力热图对比（4种设置：原版、移除语义向量、移除位置向量、移除位置基）。
  - 直接外推实验：PPL随位置变化曲线、最大cosine相似度曲线（图4）。
  - 上下文扩展实验：PPL表（表4，2K-8K长度，多种配置）、有效插值比率分析（表3）。
  - 额外主流LLM验证（附录F）：Llama-3-8B、Yi-9B、Qwen1.5-7B上重复类似分析。
  - 位置向量替换参数调优：不同替换层、不同r和α（附录D图8、图9）。
- **充分性评价**：实验覆盖多种位置编码（RoPE、ALiBi、NoPE）和注意力模式（全注意力、窗口注意力），消融实验设计合理，验证了核心发现（初始token锚点作用、位置向量对注意力的影响、OOD导致崩溃、插值机制）。对主流模型也做了验证，增强了结论普适性。但所有自训练模型规模较小（1.3B参数），可能限制泛化性。

## 6. 主要结论与发现
1. **位置向量形成**：第一层后初始token形成独特位置向量，作为锚点通过注意力机制逐步传播，使后续token获得位置区分性。窗口注意力下，位置向量随层数按窗口大小逐步扩展。
2. **位置向量作用**：位置向量是**注意力汇聚**和**长距离衰减**的关键驱动因素（而非语义信息）。
3. **超长文本崩溃原因**：超出上下文窗口时，位置向量变为OOD，破坏注意力分布和输出概率分布，导致性能剧降。
4. **扩展方法机制**：长度外推方法保持位置向量一致性；上下文扩展方法通过**插值**实现位置向量平滑过渡，有效插值比率接近扩展因子。
5. **提出的方法有效**：位置向量替换和注意力窗口扩展均能在无需微调下显著降低超长文本PPL，其中注意力窗口扩展在8K长度上优于Attention Scaling。

## 7. 优点
- **新颖的视角**：首次从**位置向量分解**角度统一解释长度外推和上下文窗口扩展的机制，揭示了OOD位置向量是性能下降的本质原因。
- **方法论清晰**：均值分解法简单有效，分析流程（形成→影响→超长文本变化→提出方法）逻辑严密。
- **实验设计细致**：多组对比模型、多层次消融（移除不同组件、不同位置）、结合主流模型验证，增强了结论可靠性。
- **无训练方法实用**：提出的两种方法无需微调，计算开销低，可即插即用。
- **理论贡献**：不仅提供了解释，还直接指导了算法设计，具有实践价值。

## 8. 不足与局限
- **模型规模局限**：自训练模型只有1.1B参数（TinyLlama），较小规模模型的结论能否完全推广至数十亿/百亿级参数模型尚需验证（尽管附录补充了部分8B模型的初步分析）。
- **方法适用性有限**：位置向量替换仅对NoPE模型有效（需要显式位置向量）；注意力窗口扩展仅限窗口注意力+NoPE模型。对主流RoPE模型只能借鉴分析思路，而非直接应用。
- **实验覆盖度不足**：仅使用了PG-19语言建模任务，未在长文理解、问答等下游任务上评估有效性；未与其他先进的微调扩展方法（如YaRN、位置插值PI）进行对比。
- **消融实验细节缺失**：位置向量替换时为何选第4层、为何保留前4个token，虽有实验支持但缺乏理论解释；α和r的调参仍依赖经验。
- **性能天花板**：位置向量替换在8K长度下PPL较高（73.79），表明插值仍不完美；有效插值比率随层数衰减，限制了进一步扩展。
- **可重复性风险**：未提供完整代码和数据，仅提供了伪代码和训练细节，复现需大量算力和数据处理。

（完）
