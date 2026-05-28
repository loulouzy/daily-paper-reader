---
title: Unlocking Multimodal Mathematical Reasoning via Process Reward Model
title_zh: 通过过程奖励模型解锁多模态数学推理
authors: "Ruilin Luo, Zhuofan Zheng, Lei Wang, Yifan Wang, Xinzhe Ni, Zicheng Lin, Songtao Jiang, Yiyao Yu, Chufan Shi, Ruihang Chu, Jin zeng, Yujiu Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=96I8PGPALv"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 过程奖励模型用于多模态数学推理和强化学习
tldr: 过程奖励模型在单模态数学推理中效果显著，但在多模态推理中未充分探索。本文首次将PRM引入多模态数学推理，识别了数据稀缺、过程标注自动化等挑战，并在基础MLLM上结合测试时扩展和强化学习显著提升了推理能力，为多模态推理与强化学习的结合开辟了新方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1374, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1219, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1421, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 630, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1340, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 258, \"height\": 192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 501, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 247, \"height\": 184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 238, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 66, \"height\": 62, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 371, \"height\": 251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-96i8pgpalv/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 421, \"height\": 322, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 985, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1369, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1231, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1082, \"height\": 1173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 812, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1167, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1390, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1389, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1019, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1176, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1308, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 542, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-96i8pgpalv/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 475, \"height\": 429, \"label\": \"Table\"}]"
motivation: PRM在多模态数学推理中的应用尚未被探索，面临数据稀缺等挑战。
method: 将PRM与MLLM结合，在测试时扩展和强化学习框架下进行多模态数学推理。
result: 在多项多模态数学推理任务上取得显著提升，验证了PRM在多模态领域的有效性。
conclusion: 为多模态推理与强化学习的融合提供了重要基础和方法论。
---

## Abstract
Process Reward Models (PRMs) have shown promise in enhancing the mathematical reasoning capabilities of Large Language Models (LLMs) through Test-Time Scaling (TTS). However, their integration into multimodal reasoning remains largely unexplored. In this work, we take the first step toward unlocking the potential of PRMs in multimodal mathematical reasoning. We identify three key challenges: (i) the scarcity of high-quality reasoning data constrains the capabilities of foundation Multimodal Large Language Models (MLLMs), which imposes further limitations on the upper bounds of TTS and reinforcement learning (RL); (ii) a lack of automated methods for process labeling within multimodal contexts persists; (iii) the employment of process rewards in unimodal RL faces issues like reward hacking, which may extend to multimodal scenarios. To address these issues, we introduce URSA, a three-stage Unfolding multimodal pRocess-Supervision Aided training framework. We first construct MMathCoT-1M, a high-quality large-scale multimodal Chain-of-Thought (CoT) reasoning dataset, to build a stronger math reasoning foundation MLLM, URSA-8B. Subsequently, we go through an automatic process to synthesize process supervision data, which emphasizes both logical correctness and perceptual consistency. We introduce DualMath-1.1M to facilitate the training of URSA-8B-RM. Finally, we propose Process-Supervised Group-Relative-Policy-Optimization (PS-GRPO), pioneering a multimodal PRM-aided online RL method that outperforms vanilla GRPO. With PS-GRPO application, URSA-8B-PS-GRPO outperforms Gemma3-12B and GPT-4o by 8.4% and 2.7% on average across 6 benchmarks.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

过程奖励模型（PRM）在单模态大语言模型（LLM）的数学推理中已展现出显著效果（如测试时扩展TTS和强化学习ReFT），但PRM在多模态大型语言模型（MLLM）数学推理中的应用尚未被探索。论文识别出三个关键挑战：
- **数据稀缺**：高质量多模态推理数据不足，限制了基础MLLM的能力，进而制约TTS和RL的上限；
- **过程标注自动化缺失**：多模态场景下缺乏自动化的过程监督标注方法，需要同时保证逻辑正确性和感知一致性；
- **奖励黑客与长度偏差**：在单模态RL中，过程奖励作为标量优化目标容易导致奖励黑客和长度偏差，该问题可能延伸到多模态。

为解决上述问题，论文提出**URSA**（Unfolding multimodal pRocess-Supervision Aided training framework）三阶段训练框架，首次将PRM系统地整合到多模态数学推理中，并验证其在测试时扩展和在线强化学习中的有效性。

## 2. 论文提出的方法论

### 核心思想
通过三个阶段构建多模态PRM并用于RL训练：先构建大规模高质量CoT推理数据集提升基础模型；再自动合成双视角过程监督数据训练PRM；最后设计一种利用PRM相对质量而非标量奖励的在线RL方法（PS-GRPO），缓解奖励黑客和长度偏差。

### 关键技术细节

**阶段I：数学密集型对齐与指令微调**
- 从Multimath、MAVIS、Geo170K等来源收集URSA-Alignment-860K进行视觉-语言对齐（仅训练MLP投影器）。
- 收集1.43M样本，按解答类型分为三类：仅答案式、分析格式式、CoT格式式。分别采用三种合成策略生成高质量CoT轨迹：
  - **CoT扩展**：对仅答案数据，利用Gemini-1.5-Flash-002根据问题和正确答案生成合理推理步骤；
  - **重写**：对分析格式数据，增强逐步推理和语言多样性；
  - **格式统一**：对数学符号式CoT数据，转化为自然语言风格。
- 经过正确性和一致性过滤后得到**MMathCoT-1M**（约1M样本），用于全参数指令微调得到基础模型**URSA-8B**（基于Qwen2.5-Math-Instruct + SAM-B+SigLIP-L混合视觉编码器）。

**阶段II：双视角过程监督数据合成与PRM训练**
- **二进制错误定位引擎（BEL）**：从URSA-8B零样本推理收集约553K错误解答，利用蒙特卡洛树搜索（MCTS）标记第一步错误位置。通过二分查找优化：若中间步的mc值>0（正确潜力），则错误在后半部分，否则在前半部分。加入约180K正确解答（所有步标记为True），共得773K数据。
- **误解插入引擎（MIE）**：针对多模态中特有的感知不一致问题，自动插入幻觉信息。三步：提取图像数学信息→在正确解答中替换易混淆条件→继续推理并自动为后续步骤标注负标签。生成约302K样本。
- 合并为**DualMath-1.1M**，训练PRM（URSA-8B-RM）为二分类任务，每个步骤预测正确性。

**阶段III：多模态PRM辅助的在线RL（PS-GRPO）**
- 先分析两种标量过程奖励变体（平均过程奖励+结果奖励、逐步过程奖励）在GRPO中的失败模式：易受奖励黑客（测试准确率低于普通GRPO）、PRM存在长度偏差（导致模型被动推理、步数变少）。
- 提出**PS-GRPO**：利用PRM奖励序列中的“drop-moment”（连续步间奖励显著下降）作为可信信号。定义相对下降比例δᵢₚ，当超过阈值ρ时视为“丢弃时刻”。对结果正确的rollout施加惩罚γ，最终奖励：
  - \( R_i = 1 \)（若结果正确且δᵢₚ < ρ），\( 1-\gamma \)（若结果正确且δᵢₚ ≥ ρ），否则0。
- 该方法通过比较rollout的相对质量而非依赖标量值，避免奖励黑客和长度偏差，同时区分学习价值。

## 3. 实验设计

### 数据集与基准
使用6个广泛使用的多模态数学推理基准：
- **MathVerse** (testmini)、**MathVision** (full set)、**MathVista** (GPS)、**WE-MATH** (testmini)、**DYNAMATH** (testmini)、**GeoQA** (full set)
- 指标：准确率（MathVerse、MathVision、MathVista、GeoQA）、Score（WE-MATH松散模式）、平均准确率（DYNAMATH）。

### 对比方法
- **闭源MLLMs**：GPT-4o、GPT-4o-mini、Gemini-1.5-pro。
- **开源通用MLLMs**：InternVL系列、LLaVA-OneVision、Gemma3-12B、Qwen2-VL等。
- **开源数学推理MLLMs**：AtomThink-EMOVA、InfiMM-Math、MAVIS、MathGLM-Vision、LlamaV-o1等（选择未使用MathVision作为训练集的模型）。
- 过程奖励模型BoN评估对比：Self-Consistency、InternVL2.5-8B作为ORM。

## 4. 资源与算力

论文在附录G.2明确说明：
- **硬件**：默认使用32× NVIDIA H100-HBM3 GPU。
- **训练时长**：
  - 阶段I（VL对齐）：约3.5小时（860K数据）。
  - 指令微调：约11小时（1.0M数据）。
  - PRM训练：约12小时（1.1M数据）。
  - PS-GRPO：约18小时（15K RL数据，2轮训练）。
- **数据生成算力**：MMathCoT-1M和DualMath-1.1M的生成使用16× H100 GPU（关于28小时用于配对生成，20小时用于BEL）。
- 此外，数据合成使用了Gemini-1.5-Flash-002作为低成本工具（约2.7M API调用），避免大规模人工标注。

## 5. 实验数量与充分性

实验设计较为全面，主要包括：
- **主表**（Table 1）：在6个基准上对比URSA-8B、URSA-8B-PS-GRPO与各类闭源/开源模型。
- **BoN评估**（Table 2）：在3个基准上比较Self-Consistency、ORM和URSA-8B-RM的验证性能。
- **消融实验**：
  - 各阶段贡献（Figure 6b）：显示VL-Alignment、SFT、PS-GRPO均有效。
  - DualMath-1.1M组件消融（Table 3）：分别移除MIE和BEL数据，显示两者均贡献。
  - 超参数灵敏度分析（Table 4）：γ和ρ对性能的影响。
  - PS-GRPO vs. 过程奖励集成基线（Table 5）：比较Variant1、Variant2、DS-GRPO。
- **缩放律验证**（Table 10）：不同比例MMathCoT-1M的数据量对性能影响。
- **泛化验证**（Figure 8 & 附录C.4）：在InternVL2.5-8B和MultiMath上验证MMathCoT-1M和PS-GRPO的通用性。
- **详细分项结果**（Table 6-9）：MathVision按学科、DYNAMATH按科目和知识水平、MathVerse按模态、WE-MATH按步骤数和策略的细粒度对比。

实验数量充足，对比公平（选择未使用MathVision作为训练集的模型，所有评估采用零样本推理），且包含充分的消融和泛化验证。

## 6. 论文的主要结论与发现

- **URSA-8B-PS-GRPO**在6个基准上平均准确率58.2%，超越Gemma3-12B（49.8%）8.4%，超越GPT-4o（55.5%）2.7%，首次在MathVision上超越GPT-4o（31.5 vs 30.4）。
- **更优的基础模型**：URSA-8B比AtomThink-EMOVA高5.2分，证明高质量SFT数据（MMathCoT-1M）的重要性。
- **有效的过程验证**：URSA-8B-RM在BoN评估中显著优于Self-Consistency和ORM，且只需4次采样即可大幅提升。
- **PS-GRPO优于普通GRPO**：相同设置下，PS-GRPO提升6.8%，普通GRPO仅3.1%。
- **自动过程标注的双视角均有效**：BEL（逻辑正确性）和MIE（感知一致性）共同贡献。
- **PS-GRPO超参数敏感但合理**：γ在0.3-0.7、ρ在0.2-0.4范围内性能稳定，过大过小均不利。
- **泛化性好**：MMathCoT-1M和PS-GRPO在InternVL2.5-8B和MultiMath上同样带来显著提升。

## 7. 优点

1. **首次系统性引入PRM到多模态数学推理**：填补了该领域空白，为后续工作奠定基础。
2. **自动化过程标注方法兼具效率和质量**：BEL采用二分搜索优化，MIE针对多模态幻觉问题，两者互补，无需人工标注。
3. **PS-GRPO创新性解决RL中的过程奖励问题**：通过“drop-moment”识别和相对优势计算，有效缓解奖励黑客和长度偏差，且比标量过程奖励变体有明显优势。
4. **开源数据与模型**：释放MMathCoT-1M、DualMath-1.1M等大规模数据集及URSA系列模型，促进社区研究。
5. **实验充分且公平**：覆盖6个基准、多种对比方法，包含细粒度分析和泛化验证。

## 8. 不足与局限

1. **计算成本较高**：训练需要32×H100 GPU，数据合成使用16×H100和大量API调用，可能阻碍资源有限的团队复现。
2. **主要聚焦STEM数学推理**：未在更通用的视觉-语言任务（如VQA、Captioning）上验证PRM的有效性，领域泛化性待考。
3. **数据合成依赖外部MLLM（Gemini-1.5-Flash-002）**：虽然成本低，但可能引入模型偏见或噪声，且未与更强模型（如GPT-4o）进行充分对比（仅在小规模实验上）。
4. **RL训练规模较小**：仅使用15K数据、每提示8个rollout、2轮训练，可能未充分释放PRM的潜力。
5. **未讨论公平性与社会影响**：虽然论文在附录K提及潜在依赖风险，但未深入分析偏见、安全等伦理问题。
6. **超参数ρ和γ需手动调整**：虽然灵敏度分析表明在合理范围内稳定，但最优值可能依赖具体PRM和数据集。

（完）
