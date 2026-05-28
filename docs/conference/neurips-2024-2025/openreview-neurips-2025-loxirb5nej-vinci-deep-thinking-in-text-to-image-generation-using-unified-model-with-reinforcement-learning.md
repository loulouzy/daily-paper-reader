---
title: "Vinci: Deep Thinking in Text-to-Image Generation using Unified Model with Reinforcement Learning"
title_zh: Vinci：基于强化学习的统一模型文本到图像深度推理
authors: "Wang Lin, Wentao Hu, Liyu Jia, Kaihang Pan, Zhang Majun, Zhou Zhao, Fei Wu, Jingyuan Chen, Hanwang Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=lOXirB5NeJ"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 强化学习用于多模态文本到图像生成
tldr: 现有统一模型未能实现图像生成与理解的端到端集成，缺乏跨模态推理能力。本文提出Vinci框架，利用少量多模态思维链数据进行冷启动，并通过强化学习引导模型深度推理，实现文本到图像的交互式生成与理解。实验证明该方法在图像生成质量和推理准确性上取得了显著提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-loxirb5nej/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-loxirb5nej/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1378, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-loxirb5nej/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 2304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-loxirb5nej/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1327, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-loxirb5nej/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1393, \"height\": 695, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-loxirb5nej/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-loxirb5nej/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-loxirb5nej/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 1444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-loxirb5nej/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 1692, \"label\": \"Table\"}]"
motivation: 现有统一模型无法端到端集成图像生成和理解，限制了自我反思和跨模态推理。
method: 利用多模态思维链数据冷启动，采用强化学习训练模型进行深度推理，实现图像生成与理解的交替过程。
result: 在文本到图像生成和多模态推理任务上，Vinci超越了现有方法，生成质量更高且推理链更一致。
conclusion: 强化学习结合思维链可以显著增强统一模型的多模态深度推理能力。
---

## Abstract
With the continuous development of large language models and reasoning chain technologies, the potential of deep reasoning based on reinforcement learning has shown remarkable promise in multi-task scenarios.  However, existing unified models have yet to achieve end-to-end integration in image generation and understanding tasks, limiting the model’s self-reflection ability and the realization of cross-modal reasoning chains.  To address this, we propose Vinic, a novel framework designed to enable interleaved image generation and understanding through deep reasoning capabilities.  We leverage a small amount of multimodal chain-of-thought (MCoT) data for cold-start and employ reinforcement learning to guide the integration of image generation and understanding tasks.  Additionally, we introduce a momentum-based reward function, which dynamically adjusts the reward distribution by considering historical improvements, ensuring the stability of the model across multiple generations.  Experimental results demonstrate that integrating MCoT can achieve a +22% improvement over the base model on Geneval, effectively enhancing both image generation quality and instruction alignment capabilities.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：现有统一模型（例如 Janus-Pro、Show-o）虽然能够同时执行图像生成与理解，但**缺乏端到端集成**：生成图像与理解图像采用不同的表示方式，导致模型无法对自身生成的图像进行实时反思与跨模态推理。简而言之，模型只看懂别人生成的图，却看不懂自己生成的图。
- **核心问题**：如何让文本到图像生成模型具备“深度思考”能力——即像人类一样，在生成过程中不断观察、评估、反思和迭代优化图像，而不是一次性输出。
- **整体含义**：本文提出 **Vinci**，这是**首个具备深度推理能力的图像生成模型**，利用多模态思维链（MCoT）和强化学习（RL）实现生成与理解的交替融合，显著提升指令遵循质量和图像生成稳定性。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：
  - 让模型在生成最终图像之前，先通过文本推理与中间图像的交替序列进行“思考”：生成一张图像 → 理解并评价该图像 → 指出问题 → 提出改进 → 生成下一张图像 → 重复直至满意。
  - 采用**冷启动 + 强化学习**的两阶段训练策略，确保模型学会生成并利用这种多模态推理链。

- **关键技术细节**：
  1. **冷启动阶段（Cold Start with MCoT）**：
     - 构建多模态思维链数据（MCoT）：针对每个文本提示，先用 FLUX 生成 n 张候选图；用 Mask2Former 检测物体；用 Qwen-VL 为每张图生成描述和质量评分；按分排序后随机选取 k 个三元组（含至少一个高分图）拼接成推理链文本。
     - 使用 GPT-4o 过滤幻觉或终点失败的数据，最终得到 20,000 条 MCoT 样本（1步/2步/3步推理）。
     - 用这些数据微调基础模型，使其学会输出推理链格式。

  2. **强化学习阶段（Reinforcement Learning for Deep Thinking）**：
     - **奖励函数设计**（三类奖励组合）：
       - **程序化奖励（Program-based Reward，Ri）**：利用视觉检测器（如物体计数）评估图像与提示的一致性，返回 0/1 分数。
       - **问答奖励（QA-based Reward，Rt）**：利用多模态大模型评估生成文本是否完整描述图像、是否指出问题、是否包含改进策略，每项 0-2 分，取平均。
       - **动量过程奖励（Momentum Process Reward，Rm）**：基于历史改进动态分配奖励，鼓励持续稳定的进步而非偶发高质。公式类似 Adam 优化器：考虑当前改进 Δk、历史波动 Vk（指数滑动平均）、时间衰减 λ，平衡即时的质量与长期稳定性。
     - 总奖励：R = Ri + Rt + Rm。
     - 训练方法：基于 GRPO（Group Relative Policy Optimization），生成 G 个候选序列并比较组内奖励，无需批评模型。

- **模型架构**：基于 Emu3-Gen（自回归统一模型），扩展上下文长度至 15,360 tokens，支持约三轮迭代。

## 3. 实验设计

- **数据集与基准**：
  - 主要 Benchmark：**GenEval**（评估文本到图像对齐能力，包含单物体、两物体、计数、颜色、位置、颜色属性等维度和总体分数）。
  - 训练数据：冷启动阶段 20,000 条 MCoT（图像来自 FLUX，文本来自 Qwen-VL）；RL 阶段 30,000 条提示（无对应图像，与测试集不重叠）。

- **对比方法**：
  - **仅生成模型**：PixArt-α、SDXL、FLUX.1-dev、DALL-E 3、CogView4-6B、SD3-Medium。
  - **统一模型**：SEED-X、Emu3-Gen（基线）、TokenFlow-XL、Transfusion、D-DiT、Show-o、ILLUME+、Infinity、Janus-Pro-7B、GPT-4o。

- **实验结果**（表1）：
  - Vinci 在 GenEval 上总体得分为 **0.76**，超过基线 Emu3-Gen（0.54），提升 **+22%**。
  - 在 **Position** 维度提升最显著（0.17 → 0.86，+0.69），其次为 **Color Attr**（0.21 → 0.54，+0.33）。
  - 仅落后于 Janus-Pro-7B（0.80）和 GPT-4o（0.85），在统一模型中表现位居前列。

- **消融实验**（表2）：
  - 单独使用 Rt（文本奖励）可提升 Position 和 Color Attr；
  - 加入 Ri（图像奖励）进一步大幅提升（Overall 0.54→0.66）；
  - 同时使用 Ri&Rt 达到 0.71；
  - 加入动量奖励 Rm 达到最优 0.76，验证各组件必要性。

- **可视化与定性分析**：展示了不同复杂度的推理链长度自适应（1-3步）以及多轮迭代修正效果。

## 4. 资源与算力

- **文中明确说明**：
  - GPU：**16 张 A800 GPU**。
  - 冷启动阶段：批次大小 64，训练约 **20 小时**。
  - 强化学习阶段：分组大小 8，训练约 **60 小时**。
  - 未说明具体显存消耗或推理开销。

## 5. 实验数量与充分性

- **实验数量**：
  - 在 GenEval 上与 **12 种**基线模型对比（含仅生成和统一模型）。
  - 消融实验：**4 组**（仅 Rt、仅 Ri、Ri+Rt、全奖励）。
  - 额外提供了推理链长度分布统计、多轮生成案例。
  - 附录还包含数据集构建细节和奖励评估提示示例。

- **充分性评估**：
  - 实验较为充分，覆盖了主流方法，消融设计合理，能清晰揭示各奖励贡献。
  - 然而，仅采用 GenEval 一个 benchmark，缺乏在 T2I-CompBench、DrawBench 等更全面基准上的评估，泛化性验证不足。
  - 未报告置信区间或多次重复实验的标准差，统计显著性存疑。
  - 定性可视化仅展示少数示例，未能系统分析失败案例。

## 6. 主要结论与发现

- 多模态思维链（MCoT）**显著提升**了文本到图像生成与指令对齐质量，尤其在**空间位置**和**颜色属性**等需多物体推理的场景中效果突出。
- 图像理解能力可以正向反馈图像生成：即使只使用文本评估奖励，也能改善生成质量；加入直接图像评估奖励效果更佳。
- 动量过程奖励有效促进了**稳定迭代**，防止模型在多次生成中性能震荡，提升了训练的鲁棒性和最终表现。
- 模型能够根据问题复杂度**自适应决定推理步数**（1-3步），在简单任务上快速输出，复杂任务上深入迭代。

## 7. 优点

- **方法创新性**：首次将多模态思维链（MCoT）与强化学习结合应用于图像生成，实现了生成与理解的**闭环反思**。
- **奖励函数设计**：动量过程奖励借鉴 Adam 优化器思想，鼓励持续改进而非单次跳跃，有效防止训练不稳定。
- **冷启动策略**：利用外部模型（FLUX、Qwen-VL、GPT-4o）自动构建高质量 MCoT 数据，无需人工标注，可扩展性强。
- **消融实验清晰**：逐步揭示不同奖励组件的增益，逻辑链条完整。
- **结果显著**：在关键指标（Position）上提升超过 0.69，相比基线提升 22%，效果直观。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅使用 GenEval 单个 benchmark，缺少更多样化的评估（如复杂场景、艺术风格、忠实度、安全偏见等）。
  - 未与近期同样使用 RL 的方法（如 T2I-R1）在相同条件下对比，仅列出部分文献引用。
- **依赖外部模型**：MCoT 数据构建依赖 FLUX 和 Qwen-VL，奖励函数中的 QA 评估也依赖多模态大模型，引入额外偏差和计算成本。
- **上下文窗口限制**：每张图像需数百个 token，当前扩展至 15,360 token 仅支持三轮迭代，限制了更长推理链的可能性。
- **未进行统计检验**：缺乏置信区间或重复运行的标准差，结论稳健性无法充分保证。
- **社会风险**：作者在附录中承认，深度推理模型可能被滥用于生成误导性或虚假图像（如深度伪造），但未提出具体防护机制。
- **可复现性**：未提供正式开源代码或数据，仅提及项目页面，第三方复现有一定门槛。

（完）
