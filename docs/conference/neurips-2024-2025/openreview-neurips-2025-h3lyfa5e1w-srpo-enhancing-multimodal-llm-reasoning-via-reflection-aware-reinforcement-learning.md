---
title: "SRPO: Enhancing Multimodal LLM Reasoning via Reflection-Aware Reinforcement Learning"
title_zh: SRPO：通过反思感知强化学习增强多模态大语言模型推理
authors: "Zhongwei Wan, Zhihao Dou, Che Liu, Yu Zhang, Dongfei Cui, Qinjian Zhao, Hui Shen, Jing Xiong, Yi Xin, Yifan Jiang, Chaofan Tao, Yangfan He, Mi Zhang, Shen Yan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=h3lyFa5e1W"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 利用强化学习增强多模态大语言模型的自我反思推理能力
tldr: 该论文针对多模态大语言模型在复杂推理任务中自我反思和自我纠正能力不足的问题，提出SRPO框架。现有反射方法生成的反馈缺乏指导性。SRPO采用两阶段强化学习策略，结合群体相对策略优化，显式训练模型进行自我反思与纠错。实验结果表明，SRPO显著提升了MLLM在需要多步推理和视觉理解的任务上的表现，为多模态模型高级推理提供了一种有效训练范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 多模态大语言模型在复杂推理中缺乏有效的自我反思和自我纠正能力。
method: 提出两阶段反思感知强化学习框架，采用组相对策略优化来自我反思训练。
result: 在多种视觉推理基准上大幅超越基线，展示了自我反思的有效性。
conclusion: 强化学习是提升多模态模型推理能力的有效工具。
---

## Abstract
Multimodal large language models (MLLMs) have shown promising capabilities in reasoning tasks, yet still struggle significantly with complex problems requiring explicit self-reflection and self-correction, especially compared to their unimodal text-based counterparts. Existing reflection methods are simplistic and struggle to generate meaningful, instructive feedback, as the reasoning ability and knowledge limits of pre-trained models are largely fixed during initial training. To overcome these challenges, we propose \textit{multimodal \textbf{S}elf-\textbf{R}eflection enhanced reasoning with Group Relative \textbf{P}olicy \textbf{O}ptimization} \textbf{SRPO}, a two-stage reflection-aware reinforcement learning (RL) framework explicitly designed to enhance multimodal LLM reasoning. In the first stage, we construct a high-quality, reflection-focused dataset under the guidance of an advanced MLLM, which generates reflections based on initial responses to help the policy model to learn both reasoning and self-reflection. In the second stage, we introduce a novel reward mechanism within the GRPO framework that encourages concise and cognitively meaningful reflection while avoiding redundancy. Extensive experiments across multiple multimodal reasoning benchmarks—including MathVista, MathVision, Mathverse, and MMMU-Pro—using Qwen-2.5-VL-7B and Qwen-2.5-VL-32B demonstrate that SRPO significantly outperforms state-of-the-art models, achieving notable improvements in both reasoning accuracy and reflection quality.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在复杂推理任务中缺乏有效的**自我反思（self-reflection）**和**自我纠正（self-correction）**能力，导致推理步骤冗余、错误累积，最终性能甚至不如不进行显式推理的快速模型（如GPT-o1在MathVista上低于Qwen2.5-VL-72B）。
- **背景**：现有方法（如直接提示或简单强化学习）受限于预训练模型内在的认知边界，无法真正引入全新的反思能力；需要外部干预（如高质量反思示例）来突破这一限制。
- **整体意义**：提出SRPO框架，通过**两阶段反思感知强化学习**，显式训练MLLM进行自我反思与纠错，从而在保持推理链的同时提升准确率和反思质量，使模型能够超越预训练阶段固有的推理上限。

## 2. 论文提出的方法论

### 2.1 核心思想
- 结合**监督微调（SFT）冷启动**与**强化学习（RL）优化**，系统性地向MLLM注入自我反思能力。
- 利用外部高级MLLM生成高质量反思样本，再通过专门设计的奖励函数激励模型产出简洁、有意义的反思。

### 2.2 第一阶段：反思导向的冷启动初始化
- **数据构造**：
  - 从Mulberry、MathV360K、LLaVA-CoT三个数据集中筛选10,000个高质量样本（涵盖物理、数学、通用知识）。
  - 使用策略模型（Qwen-2.5-VL-7B/32B）生成初始应答（CoT）。
  - 借助高级MLLM（GPT-o4-mini）基于初始应答与标准答案生成自我反思内容，形成如下结构：`<think>初始推理</think><answer>初始答案</answer><reflection>反思</reflection><think>修正推理</think><answer>最终答案</answer>`。
  - 数据分布：约30%初始应答正确（用于精简冗余），约70%错误（用于修正）。
- **冷启动训练**：使用上述数据对策略模型进行SFT，损失函数为：

  `L_cold-start = -E[∑log π_initial(answer_with_reflection | question)]`

  目标：使模型学会从初始应答出发，借助反思向正确答案靠拢。

### 2.3 第二阶段：反思感知强化学习（SRPO）
- **基础算法**：沿用组相对策略优化（GRPO），其目标函数包含组内优势估计和KL散度惩罚。
- **增强奖励函数**：

  `R_total = R_task + R_reflection`

  - **任务奖励 R_task**：包括格式奖励（0.5分，要求使用`<think>`标签）和准确率奖励（0.5分，初始答案正确）。
  - **反思奖励 R_reflection**：
    - 格式指示 `I_ref`：0.25分（反思段使用`<reflection>`标签）。
    - 长度奖励 `f_len`：基于指数衰减函数，鼓励输出长度接近目标长度 `T_target`，惩罚过短或过长。
    - 有效性指示 `I_eff`：根据反思对最终答案的影响给出分数（+0.25保持正确，+0.5纠正错误，0未纠正，-0.25误导正确答案）。
- **优势**：相比标准GRPO，SRPO通过结构化反思格式、平滑长度约束、有效性激励，有效防止奖励黑客行为（如空反思或冗长反思），促进真正的推理改进。

## 3. 实验设计

### 3.1 数据集与场景
| 阶段 | 数据集 | 规模 | 用途 |
|------|--------|------|------|
| SFT冷启动 | Mulberry, MathV360K, LLaVA-CoT 中精选 | 10K | 训练自我反思能力 |
| RL训练 | ScienceQA, GeoQA, ChartQA, DVQA, AI2D, MATH, Virgo, R1-OneVision, MMK12, PhyX | 37K | 强化推理与反思 |

### 3.2 评估基准
- **数学推理**：MathVista、MathVerse、MathVision、OlympiadBench、WeMath。
- **通用推理**：MMMU-Pro、MMMU、EMMA。
- **跨学科推理**：MMK12（物理、化学、生物）。

### 3.3 对比方法
- **闭源模型**：Claude3.7-Sonnet、GPT-4o、GPT-o1、Gemini2-flash、Seed1.5-VL-T。
- **开源通用MLLM**：InternVL2.5、Qwen-2.5-VL等（7B~38B）。
- **开源推理MLLM**：MM-Eureka、VL-Rethinker、R1-VL、Vision-R1、OpenVLThinker等。

### 3.4 实验设置
- 基础模型：Qwen-2.5-VL-7B-Instruct、Qwen-2.5-VL-32B-Instruct。
- SFT：1 epoch，10K样本。
- RL：3 epochs，37K样本，rollout batch size 128（每样本8次采样），温度1.0，优化器Adam，学习率1e-6。

## 4. 资源与算力

- **训练环境**：
  - 7B模型：8×NVIDIA H100 GPU。
  - 32B模型：32×NVIDIA H100 GPU（4节点×8卡）。
- **训练时长（附录B.3表9）**：
  - 7B SFT：约3.5小时；7B RL（SRPO）：约31.2小时；7B GRPO RL：约25.8小时。
  - 32B SFT：约4.7小时；32B RL（SRPO）：约45.1小时。
- **推理效率（附录B.3表10）**：MathVista test-mini（1000样本）单H100，SRPO平均响应502.3 tokens，耗时60.5分钟；GRPO平均355.4 tokens，45.6分钟。
- 文中明确说明了资源用量，实验可复现。

## 5. 实验数量与充分性

论文开展了**大量且多维度的实验**，主要包括：

| 实验类型 | 具体内容 | 结果 |
|----------|----------|------|
| 主实验对比 | 7B/32B在6个数学基准+3个通用基准+MMK12跨学科对比 | SRPO全面领先开源模型，接近/超越闭源推理模型 |
| 消融实验 | 训练数据规模（5K/15K/37K） | 数据越多越好，5K仍显著优于GRPO |
| 效果分析 | 移除自我反思SFT、自我反思RL、长度奖励、有效性奖励 | 每项去除均导致性能下降，证明各组件有效 |
| 反思格式vs教师蒸馏 | 相同数据下，带反思SFT比纯CoT SFT平均+1.3分；再经反思RL再+2.1分 | 结构化反思本身带来增益，非仅蒸馏 |
| 与2-step thinking对比 | SRPO vs GRPO+两轮思考 | 纯两轮思考无增益，SRPO的显式反思有效 |
| 整合到其他RL方法 | 将反思奖励融入PPO、DAPO | 所有方法反射变体均优于原版，SRPO略优于PPO+反思，与DAPO+反思持平 |
| 长度系数灵敏度 | α=0.05/0.1/0.3 | α=0.1最优，表明适度约束最佳 |
| 定性分析 | 展示训练中/测试中的反思生成案例 | 验证反思确实纠正错误、精简正确推理 |

**充分性与公平性评价**：实验覆盖了多个维度，对比了最主流的开源/闭源模型，消融设计合理，控制变量明确。训练设置与评估协议均遵循公开标准，结果可信。

## 6. 论文的主要结论与发现

1. **SRPO显著提升多模态推理性能**：在MathVista（7B:75.8%、32B:78.5%）、MathVerse、MathVision、MMMU-Pro等基准上全面超越现有开源推理模型，部分指标接近GPT-o1。
2. **自我反思是核心增益来源**：仅通过反思SFT获得有限提升，结合反思感知RL才能释放全部潜力；奖励函数中长度约束和有效性监督缺一不可。
3. **反思泛化到未知领域**：在未见的物理、化学、生物推理任务（MMK12）上也取得领先，说明反思训练增强了模型对跨学科问题的泛化能力。
4. **反思训练是通用的**：将反思奖励机制整合到PPO、DAPO等不同RL算法中均能带来一致提升，验证了方法的可迁移性。
5. **训练动态更稳定**：SRPO的clip ratio曲线更低且平滑，说明反思感知奖励有助于保持策略更新的一致性，避免梯度爆炸。

## 7. 优点

- **方法创新性**：首次在MLLM中系统性地将自我反思融入SFT和RL两阶段，提出专门的反思奖励函数（格式+长度+有效性），设计精巧。
- **奖励设计细致**：区分了保持正确、纠正错误、未纠正、误导四种情况，并结合指数长度约束，有效抵御奖励投机。
- **消融实验充分**：逐步拆解每个组件的作用，清晰验证了反思SFT、反思RL、奖励子项的贡献。
- **跨领域验证**：在数学、通用推理、物理化生等多学科基准上全面评测，增强结论的普适性。
- **与多种RL算法兼容**：展示了反思奖励的通用性，不仅局限于GRPO。
- **定性分析丰富**：给出训练和测试阶段的反思示例，直观展示模型行为变化。

## 8. 不足与局限

- **模型架构局限**：实验仅在密集（dense）MLLM（7B/32B）上进行，未扩展到MoE或扩散LM等架构，泛化性未知。
- **数据规模限制**：RL训练数据仅37K，且全部来自公开数据集，未使用更大规模商业级数据集（如OpenAI内部数据），可能限制性能上限。
- **计算开销**：SRPO因生成反思和二次思考，导致响应长度增加约40%，推理延迟相应增大（7B: 60.5min vs 45.6min），对实时应用不友好。
- **反思质量评估**：虽然有人工和LLM评判，但仅基于100样本，统计严谨性有限；且反思内容的可解释性、可迁移性未深入分析。
- **潜在偏差风险**：高级MLLM（GPT-o4-mini）生成反思数据可能引入分布外偏差，若基础模型依赖特定反思模式，在面对分布偏移时可能失效。
- **缺乏长链推理压力测试**：未评估在极长推理链下反思的累积错误控制能力。

---
（完）
