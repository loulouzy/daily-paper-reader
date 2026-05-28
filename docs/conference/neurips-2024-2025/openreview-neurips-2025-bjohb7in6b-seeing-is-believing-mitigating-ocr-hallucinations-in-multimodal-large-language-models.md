---
title: Seeing is Believing? Mitigating OCR Hallucinations in Multimodal Large Language Models
title_zh: 眼见为实？减轻多模态大语言模型中的OCR幻觉
authors: "Zhentao he, Can Zhang, Ziheng Wu, Zhenghao Chen, Yufei Zhan, Yifan Li, Zhao Zhang, Xian Wang, Minghui Qiu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=bjoHB7IN6b"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 减轻多模态大语言模型OCR幻觉
tldr: 本文指出多模态大语言模型在视觉质量退化（如模糊、遮挡）时会产生内容幻觉。通过分析发现模型过度依赖语言先验和图文推理错位是主因，并提出一种检测和减轻幻觉的方法，增强了MLLM在真实场景下的可靠性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bjohb7in6b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1306, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bjohb7in6b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1370, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bjohb7in6b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bjohb7in6b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 606, \"height\": 312, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bjohb7in6b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bjohb7in6b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 668, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bjohb7in6b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 207, \"label\": \"Table\"}]"
motivation: MLLM在视觉退化条件下产生幻觉，影响文档理解可靠性。
method: 分析了模糊、遮挡等退化条件下模型的幻觉机制，并提出了针对性缓解策略。
result: 揭示了模型在退化条件下过度依赖语言先验和视觉-文字推理错位的问题。
conclusion: 改善MLLM在真实复杂场景下的可靠性和鲁棒性。
---

## Abstract
Recent advancements in multimodal large language models (MLLMs) have enhanced document understanding by integrating textual and visual information. However, existing models exhibit incompleteness within their paradigm in real-world scenarios, particularly under visual degradation (e.g., blur, occlusion, low contrast). In such conditions, the current response paradigm often fails to adequately perceive visual degradation and ambiguity, leading to overreliance on linguistic priors or misaligned visual-textual reasoning. This difficulty in recognizing uncertainty frequently results in the generation of hallucinatory content, especially when a precise answer is not feasible. To better demonstrate and analyze this phenomenon and problem, we propose KIE-HVQA, the first benchmark dedicated to evaluating OCR hallucination in degraded document understanding. This dataset includes test samples spanning identity cards, invoices, and prescriptions, with simulated real-world degradations and pixel-level annotations for OCR reliability. This setup allows for evaluating models' capacity, under degraded input, to distinguish reliable visual information and answer accordingly, thereby highlighting the challenge of avoiding hallucination on uncertain data. To achieve vision-faithful reasoning and thereby avoid the aforementioned issues, we further introduce a Group Relative Policy Optimization (GRPO)-based framework featuring a novel reward mechanism. By incorporating a self-awareness of visual uncertainty and an analysis method that initiates refusal to answer to increase task difficulty within our supervised fine-tuning and reinforcement learning framework, we successfully mitigated hallucinations in ambiguous regions. Experiments on Qwen2.5-VL demonstrate that our 7B-parameter model achieves a ~28% absolute improvement in hallucination-free accuracy over GPT-4o on KIE-HVQA and there is no significant performance drop in standard tasks, highlighting both effectiveness and robustness. This work advances the development of reliable MLLMs for real-world document analysis by addressing critical challenges in visual-linguistic alignment under degradation.

---

## 论文详细总结（自动生成）

# 论文总结：Seeing is Believing? Mitigating OCR Hallucinations in Multimodal Large Language Models

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在真实场景下的文档理解中，当遭遇视觉退化（如模糊、遮挡、低对比度）时，会生成与图像内容不符的幻觉性OCR输出。模型往往过度依赖语言先验，而不是忠实于视觉证据，导致跨模态幻觉。
- **研究动机**：现有MLLMs在预训练阶段缺乏退化场景的关键信息提取（KIE）数据；指令微调阶段忽略了退化场景的处理范式；评估阶段缺少量化OCR幻觉的专用基准。这些不足阻碍了MLLMs在关键应用（如身份证识别、医疗处方解析）中的可靠性。
- **整体含义**：本文旨在通过构建首个专门评估退化文档OCR幻觉的基准（KIE-HVQA）并提出一种结合强化学习的框架，来提升MLLMs在视觉退化条件下的视觉-语言对齐能力，减少幻觉。

## 2. 方法论

### 核心思想
- 提出 **KIE-HVQA benchmark**，包含2000个训练样本和400个测试样本，覆盖身份证、收据、发票等文档类型，模拟真实退化（运动模糊、低对比度、部分遮挡），并带有像素级OCR可靠性标注。
- 基于 **Group Relative Policy Optimization (GRPO)** 算法，设计了一套新颖的奖励机制，引导模型对清晰字符准确识别、对部分模糊但可识别的字符保留、对完全模糊的字符拒绝输出（用空格代替），从而强制模型忠实于视觉证据。

### 关键技术细节
1. **冷启动初始化（Cold-start Initialization）**：利用GPT-4o将多模态信息（图像、问题、答案）转化为伪思维链（CoT）文本，再输入DeepSeek-R1生成高质量CoT推理数据；最终与图像配对形成多模态CoT数据集，用于监督微调（SFT）。
2. **GRPO训练**：
   - 对于一个输入`q`，GRPO采样G个输出`{o1,...,oG}`，计算每个输出的奖励`r_i`，然后归一化得到优势`A_i`。
   - 优化目标：  
     `J_GRPO(θ) = (1/N) Σ [ (π_θ(o_i|q)/π_θold(o_i|q)) * A_i - β * KL(π_θ || π_ref) ]`
   - 奖励函数设计：根据字符清晰程度分为三类——清晰字符准确识别得正奖励；部分遮挡但人类可识别的字符保留（标记为异常）也给予奖励；完全不可识别的字符必须用空格替换以防幻觉，否则惩罚。
   - 奖励计算公式：  
     `F = Σ_i f_i(A_i, G_i) * (1 - Σ_j g_j(A_j, G_j))`  
     其中`f`为编辑距离评估，`g`为数值计数评估，`A`为模型输出，`G`为 ground truth。

### 算法流程（文字说明）
- 步骤1：输入退化文档图像和问题。
- 步骤2：模型进行多模态定位，识别与问题相关的文本区域。
- 步骤3：在字符级别评估识别置信度（边缘锐度、对比度等）。
- 步骤4：基于奖励函数，模型生成答案：清晰字符直接输出；部分模糊字符保留并标记；完全模糊字符输出空格/拒绝回答。
- 步骤5：GRPO通过组间比较最大化优势，迭代优化模型策略。

## 3. 实验设计

### 数据集与场景
- **KIE-HVQA benchmark**：包含三类来源：
  - **OCRBench**：100个KIE查询，经文本检测和字符定位后，随机退化，双模型（GPT-4o和Qwen2.5-VL-72B）验证可见性，人工仲裁。
  - **WildReceipt**：提取实体类型答案，生成问题，应用退化。
  - **GPT-4o生成图像**：200个合成身份/文档模板，虚构信息，添加退化。
- 评估指标：**Legible Character Accuracy**（清晰字符准确率）、**Degraded Character Accuracy**（退化字符准确率）、**Global OCR Performance**（最终答案编辑距离）。

### 对比方法
- 闭源模型：GPT-4o (1120)、Claude3.5-Sonnet、Claude3.7-Sonnet、Gemini2.5-pro。
- 开源模型：InternVL3系列（8B/38B/78B）、Qwen2.5-VL系列（8B/32B）、MiniCPM-o-2.6等。
- 本文模型：基于Qwen2.5-VL-7B，经过冷启动SFT + GRPO训练。

## 4. 资源与算力

- **冷启动SFT**：使用LLaMA-Factory框架，基于Qwen2.5-VL-7B-Instruct，训练5个epoch，学习率1e-6，数据rollout batch size为512，耗时约4小时。未明确GPU型号和数量。
- **GRPO训练**：使用Easy-R1框架，训练数小时。同样未报告具体GPU资源。
- 文中提到，使用GPT-4o和DeepSeek-R1生成数据约耗时12小时，但这是数据准备阶段，并非模型训练算力。
- 总体而言，论文未详细披露GPU型号、数量、内存等算力细节。

## 5. 实验数量与充分性

- **主实验结果**（表1）：在KIE-HVQA的三个子集（OCRBench-KIE、WildReceipt、Card）上，对比了8个基线模型（含闭源和开源），报告了清晰字符、模糊字符、最终OCR及平均分数。本文模型（SFT+RL）在平均分上达到58.05%，比GPT-4o（30.21%）提升显著。
- **通用OCR能力保持实验**（表2）：在OCRBench的三个标准领域（Scene Text VQA、Doc-oriented VQA、KIE）上对比了GPT-4o、Claude3.7、Qwen2.5-VL-7B等，本文模型得分与原始模型相近，表明未牺牲通用能力。
- **奖励设置消融**（表3）：对比仅使用清晰字符奖励、仅使用最终字符奖励、使用全部奖励三种设置，证明多目标奖励合成的必要性。
- **训练策略消融**：文中提到比较SFT单独使用与SFT+RL的差异，但并未以表格形式详细给出（表1中已隐含SFT和SFT+RL两行结果，但未单独列出SFT基线）。不过表1中“Our Model + SFT”和“Our Model + SFT+RL”两条结果已经体现了策略效果。
- 实验数量充足，覆盖了多种退化类型、多种模型、多种评价维度，消融实验较为充分。但缺少对比其他RL算法（如PPO）的消融，也未报告统计误差棒（文中提到因资源限制未报告）。

## 6. 主要结论与发现

- 所提出的KIE-HVQA基准能够有效评估MLLMs在视觉退化下的OCR幻觉。
- 基于GRPO的框架结合冷启动SFT和新型奖励函数，显著降低了幻觉：7B模型在KIE-HVQA上达到58.05%平均分数，比GPT-4o（30.21%）绝对提升约28%。
- 该框架在提升退化场景性能的同时，未对标准OCR任务造成明显下降（表2中场景、文档、信息提取分数与原始Qwen2.5-VL-7B接近）。
- 多目标奖励合成优于单目标奖励，清晰/模糊/最终三者的联合监督效果最佳。
- 验证了强化学习（GRPO）在OCR幻觉抑制任务中的有效性，为MLLMs在真实复杂场景下的可靠应用提供了可行方案。

## 7. 优点

- **首创性**：首次提出专门针对退化文档OCR幻觉的基准（KIE-HVQA），填补了评估空白。
- **方法论创新**：将GRPO算法引入OCR幻觉抑制，设计了基于字符清晰度分级的精细奖励函数，并融入视觉不确定性感知的拒绝回答机制。
- **数据可靠性**：使用双模型（GPT-4o和Qwen2.5-VL-72B）验证退化标注，人工仲裁边界情况，提高了标注质量。
- **实用性**：模型仅7B参数，性能超越GPT-4o，且不牺牲通用能力，具备实际部署潜力。
- **实验全面**：涵盖多种退化类型、多种文档类别、多种基线模型，并有消融实验验证各组件贡献。
- **开源承诺**：数据集已在HuggingFace发布，代码即将开源（待机构审批），有利于后续研究。

## 8. 不足与局限

- **算力资源未透明**：未明确报告GPU型号、数量、训练总耗时（仅给出SFT约4小时、GRPO数小时的粗略描述），不利于复现和成本评估。
- **代码暂未开源**：因机构内审流程，代码目前尚未公开，影响可复现性。
- **退化模拟的局限性**：退化效果是通过算法模拟的（如随机模糊、遮挡），可能无法完全覆盖真实世界中的复杂退化（如扫描噪声、墨水渗漏、光影变化）。真实退化数据的收集仍显不足。
- **基准规模有限**：KIE-HVQA仅包含2400个样本（2000训练+400测试），且集中在英文文档（身份证、收据、发票、处方），缺乏多语言和更多文档类型（如表格、学术论文）。
- **模型泛化性**：实验仅使用了Qwen2.5-VL-7B作为基础模型，未验证在其他架构（如LLaVA、InternVL）上的迁移效果。
- **未探讨统计显著性**：实验未提供误差棒或置信区间，结果波动性未知。
- **未与其他RL方法对比**：消融中未与PPO、DPO等常见强化学习算法进行比较，GRPO的优势缺乏更全面的基准对照。
- **潜在偏差风险**：冷启动数据依赖GPT-4o和DeepSeek-R1生成，可能引入这些模型的固有偏见。此外，训练数据中退化程度和类型可能分布不均，导致模型在极端退化下仍可能失败。
- **应用限制**：在关键任务（如医疗、金融）中，即使模型声称“拒绝回答”，也可能因不确定性判断不准确而导致误判。安全性尚未充分论证。

（完）
