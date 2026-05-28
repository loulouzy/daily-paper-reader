---
title: Efficient Multi-modal Large Language Models via Progressive Consistency Distillation
title_zh: 通过渐进式一致性蒸馏实现高效多模态大语言模型
authors: "Zichen Wen, Shaobo Wang, Yufa Zhou, Junyuan Zhang, Qintong Zhang, Yifeng Gao, Zhaorun Chen, Bin Wang, Weijia Li, Conghui He, Linfeng Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gZjPllL9jM"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型论文：渐进式一致性蒸馏提升效率
tldr: 多模态大语言模型（MLLM）处理大量视觉标记导致高计算开销。现有压缩方法忽略学习难度增加。本文提出EPIC渐进式一致性蒸馏框架，通过分解特征空间扰动逐步压缩视觉标记，降低学习难度。实验证明EPIC在保持性能的同时显著提升MLLM效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 620, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gzjplll9jm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 382, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 1068, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1176, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 941, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 945, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gzjplll9jm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 529, \"height\": 414, \"label\": \"Table\"}]"
motivation: MLLM视觉标记压缩增加了模型适应难度，现有方法忽视此问题。
method: 提出渐进式一致性蒸馏框架，逐步压缩视觉标记并分解扰动。
result: 在多个MLLM上效率提升明显，性能几乎无损。
conclusion: EPIC有效解决了MLLM效率与学习难度的平衡。
---

## Abstract
Visual tokens consume substantial computational resources in multi-modal large models (MLLMs), significantly compromising their efficiency. Recent works have attempted to improve efficiency by compressing visual tokens during training, either through modifications to model components or by introducing additional parameters. However, they often overlook the increased learning difficulty caused by such compression, as the model’s parameter space struggles to quickly adapt to the substantial perturbations in the feature space induced by token compression. In this work, we propose to develop Efficient MLLMs via Progressive Consistency Distillation (EPIC), a progressive learning framework. Specifically, by decomposing the feature space perturbations introduced by token compression along the token-wise and layer-wise dimensions, we introduce token consistency distillation and layer consistency distillation, respectively, aiming to reduce the training difficulty by leveraging guidance from a teacher model and following a progressive learning trajectory. Extensive experiments demonstrate the superior effectiveness, robustness, and generalization capabilities of our proposed framework.

---

## 论文详细总结（自动生成）

# 论文《Efficient Multi-modal Large Language Models via Progressive Consistency Distillation》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- 多模态大语言模型（MLLMs）在图像描述、视觉问答等任务中表现优异，但需要处理大量视觉token（例如单张图像576个token），导致计算开销极大（FLOPs高达9.3T，KV缓存达到367MB）。
- 现有方法通过token压缩提升效率，但训练阶段直接施加高压缩比会引入特征空间扰动，导致模型参数空间难以快速适应，优化过程容易陷入不良局部最优。
- 本文提出**EPIC（Efficient MLLMs via Progressive Consistency Distillation）**，通过渐进式一致性蒸馏框架，将特征空间扰动沿token维度和层维度分解，逐步引导模型从低压缩比向高压缩比过渡，降低学习难度。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 利用权重共享的单模型同时充当教师和学生，教师使用略低的压缩比（压缩比gap逐步增大），通过KL散度损失约束学生输出分布与教师一致。
- 从**token-wise**和**layer-wise**两个维度设计渐进式学习轨迹，使每个中间最优解与前一最优解距离较近，避免直接高压缩导致的优化困难。

### 技术细节
#### (a) Token Consistency Distillation (TCD)
- 学生模型压缩比 $r^{stu}_t$ 从均匀分布 $\mathcal{U}(R^{stu}_{min,t}, R^{stu}_{max,t})$ 采样，$R^{stu}_{max,t}$ 从5%线性增至90%，$R^{stu}_{min,t}$ 从0%缓慢增至50%。
- 教师模型压缩比 $r^{tea}_t = \max(0, r^{stu}_t - \Delta_t)$，其中 $\Delta_t$ 从 $\delta_{min}$ 逐渐增至 $\delta_{max}$（最大30%）。
- 损失函数：$L_{total} = (1-\lambda) L_{SFT} + \lambda L_{TCD}$，$L_{TCD} = KL(p^{tea} \| p^{stu})$，$\lambda=0.7$。

#### (b) Layer Consistency Distillation (LCD)
- 压缩层从深层向浅层渐进移动：$l_t = \text{Round}(L - \beta_t (L - l_{min}))$，$\beta_t = t/T$。
- 每个训练步，学生压缩比从固定范围 $[0.2, 0.9]$ 均匀采样，教师减去 $\Delta_t$。
- 损失函数类似 KL散度。

#### (c) 理论直觉：1D原型
- 假设压缩中心 $c_r$ 满足单调、Lipschitz、凸性，证明渐进路径的总变差严格小于直接路径，反映EPIC的平滑优化轨迹。

### 算法流程
1. 初始化模型参数（共享权重）。
2. 对于每个训练步 $t$：
   - 根据当前阶段策略采样学生压缩比 $r^{stu}_t$，计算教师压缩比 $r^{tea}_t$。
   - 在固定层（TCD）或渐进层（LCD）分别对教师和学生执行token压缩及前向传播。
   - 计算SFT交叉熵损失和KL蒸馏损失，更新参数。
3. 两阶段训练可选集成（ICD），即层维度渐进中每一层内部再执行token-wise渐进。

## 3. 实验设计

### 数据集与Benchmark
- 训练数据：LLaVA-665K指令微调数据集（第二阶段）。
- 评估：10个视觉理解基准：VQA V2、GQA、VizWiz、ScienceQA (SQA)、TextVQA、POPE、MME、MMBench、MMBench-CN、OCRBench。

### 对比方法
- 通用MLLMs：BLIP-2、InstructBLIP、IDEFICS、Qwen-VL、SPHINX、mPLUG-Owl2、Video-LLaVA、LLaVA-v1.5。
- 训练感知token压缩方法：Average-Pooling、MQT-LLaVA、QT-LLaVA、LLaMA-VID、VoCo-LLaMA、TokenPacker、LLaVA-Mini。
- 自己方法的消融变体：w/o蒸馏损失、w/o渐进压缩比/层。

### 实验设置
- 视觉编码器：CLIP ViT-L/14；语言模型：Vicuna-v1.5-7B；分辨率336。
- 三种token压缩策略：DART（冗余修剪）、FastV（重要性修剪）、Random。

## 4. 资源与算力

- 训练：8×A100 GPU，约12.2小时（仅需第二阶段微调）。
- 对比方法：MQT-LLaVA需约34小时（8×A6000），LLaMA-VID约48小时（8×A100），LLaVA-Mini约26小时（8×A100）。
- 推理：保留64 token时，FLOPs从9.3T降至1.5T（降83.9%），KV缓存从367.2MB降至40.9MB（降88.9%），CUDA时间从1103.5s降至约700-750s（降约32-37%）。

## 5. 实验数量与充分性

- **主要结果表（Table 1）**：TCD和LCD分别在5个token数量（256,192,128,64,36）下报告10个基准分数，共100个数值。
- **消融实验（Tables 3,4）**：对TCD和LCD分别做两组消融（w/o蒸馏损失、w/o渐进策略），在2个token数量（128,64）下报告10个基准，共80个数值。
- **泛化性实验（Figures 4,6,7）**：DART、FastV、Random三种压缩策略交叉测试，共12组对比。
- **效率分析（Table 2）**：三种压缩方法下KV、CUDA时间、FLOPs。
- **极端压缩分析（Figure 5）**：FLOPs、延迟与token数的关系曲线。
- **集成实验（Table 5）**：ICD在5个token数量下10个基准。
- **总体评价**：实验数量充足，覆盖多种压缩比、多种压缩方法、多种基准，消融设计合理，对比方法包含主流基线，且设置公平（相同架构、数据、超参）。实验具有较高的客观性和充分性。

## 6. 主要结论与发现

- EPIC（TCD和LCD）在保留128 token时，平均性能与原始LLaVA-v1.5-7B相当（甚至略高）；保留192+ token时，在4/10基准上超越原始模型。
- 相比于需修改架构的MQT-LLaVA、TokenPacker等方法，EPIC在同等token数下取得更好或相当的平均性能，证明训练策略与架构改进同等重要。
- 渐进式策略（渐进压缩比/层）和教师蒸馏损失均显著提升性能，缺失任一组件都会导致平均分下降1-2%。
- EPIC在不同压缩策略间具有良好的泛化能力：训练时用DART，推理时切换到FastV或Random仍能保持增益。
- 极端token压缩（<36）带来的加速收益递减，且性能大幅下降；而保留64-128 token处于“高ROI区域”。
- 集成ICD（同时渐进token和层）性能与单独TCD/LCD相当，进一步验证框架的灵活性。

## 7. 优点

- **无需修改模型架构**：仅需在训练时应用渐进蒸馏，可与任何即插即用token压缩方法结合，兼容性强。
- **训练高效**：仅需12小时（8×A100），比其他训练感知方法（30-48小时）快2-4倍。
- **理论与直觉结合**：提供1D原型理论证明渐进路径总变差更小，解释优化优势。
- **实验全面**：覆盖10个基准、多种压缩比和压缩策略，消融实验设计清晰，泛化性验证充分。
- **效率分析深入**：指出极端压缩并非最优，给出“高ROI区域”指导，有实际工程价值。

## 8. 不足与局限

- **仅应用于微调阶段**：本文只在第二阶段指令微调时应用蒸馏；作者在附录提出可扩展至预训练阶段，但未实验验证，可能限制性能上限。
- **未进行人类偏好对齐**：训练后模型参数偏移，未进一步RLHF/DPO对齐，可能存在对抗鲁棒性或输出有害内容风险（作者在Broader Impacts中提及）。
- **依赖固定分辨率（336）**：未测试动态分辨率或高分辨率场景下的泛化性。
- **压缩策略选择依赖**：虽然泛化性较好，但最佳性能仍需与具体压缩方法匹配（如DART略优于FastV）。
- **集成ICD未超越单独TCD/LCD**：作者未深入分析原因，可能说明token-wise和layer-wise渐进存在冗余或冲突。

（完）
