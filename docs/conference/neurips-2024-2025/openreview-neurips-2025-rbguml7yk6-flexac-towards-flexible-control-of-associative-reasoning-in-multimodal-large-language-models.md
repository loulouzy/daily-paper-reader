---
title: "FlexAC: Towards Flexible Control of Associative Reasoning in Multimodal Large Language Models"
title_zh: "FlexAC: 迈向多模态大语言模型关联推理的灵活控制"
authors: "Shengming Yuan, Xinyu Lyu, Shuailong Wang, Beitao Chen, Jingkuan Song, Lianli Gao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RbGUML7YK6"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型论文，关注推理灵活控制
tldr: 多模态大语言模型（MLLM）在忠实性和创造性之间存在权衡，不同任务对关联推理强度有不同需求。现有方法缺乏灵活调节推理强度的能力。本文提出FlexAC，通过研究MLLM内部机制发现中间层决定了关联倾向，通过修改这些层的表征可以有效控制推理强度。该方法使MLLM能够在事实性和创造性场景间自适应，弥补了现有工作的不足。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1414, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 684, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 571, \"height\": 246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1293, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1302, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 697, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 877, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1154, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1021, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1361, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1344, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1363, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 661, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1421, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1427, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1427, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1420, \"height\": 1547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1444, \"height\": 1444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1442, \"height\": 1444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1397, \"height\": 1889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 221, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 104, \"height\": 102, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 204, \"height\": 182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 199, \"height\": 212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 106, \"height\": 100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1345, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 100, \"height\": 89, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 206, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 104, \"height\": 103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 325, \"height\": 221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 101, \"height\": 92, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 315, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1278, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbguml7yk6/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1409, \"height\": 983, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1306, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1304, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1173, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbguml7yk6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1355, \"height\": 2114, \"label\": \"Table\"}]"
motivation: 现有MLLM无法根据任务需求灵活调节关联推理强度，限制了其在事实性和创造性场景中的适应性。
method: 通过分析MLLM内部机制发现中间层决定推理倾向，并提出基于表征修改的关联推理强度控制方法。
result: 实验表明该方法能有效调节推理强度，提升模型在不同任务上的表现。
conclusion: FlexAC实现了对MLLM关联推理的灵活控制，为模型适应性提供了新思路。
---

## Abstract
Multimodal large language models (MLLMs) face an inherent trade-off between faithfulness and creativity, as different tasks require varying degrees of associative reasoning. However, existing methods lack the flexibility to modulate this reasoning strength, limiting MLLMs' adaptability across factual and creative scenarios. To bridge this gap, we propose equipping MLLMs with mechanisms that enable flexible control over associative reasoning. We begin by investigating the internal mechanisms underlying associative behavior in MLLMs and  find that: (1) middle layers play a pivotal role in shaping model’s associative tendencies,  (2) modifying representations in these layers effectively regulates associative reasoning strength, and  (3) hallucinations can be exploited to derive steering vectors that guide this modulation. Building on these findings, we introduce Flexible Association Control (FlexAC), a lightweight and training-free framework for modulating associative behavior in MLLMs. FlexAC first induces hallucination-guided intermediate representations to encode associative directions. Then, it selects high-association instances to construct effective associative steering vectors, whose strengths are adaptively calibrated to balance creative guidance with output stability. Finally, recognizing the multi-dimensional nature of associative reasoning, FlexAC incorporates task-specific associative vectors derived from a forward pass on a few target-domain samples, enabling models to follow diverse associative directions and better adapt to creative tasks. Notably, our method achieves up to a 5.8× improvement in creativity on Creation-MMBench and a 29\% reduction in hallucination rate on CHAIR, surpassing existing baselines and demonstrating its effectiveness in enabling flexible control over associative reasoning in MLLMs. Our code is available at https://github.com/ylhz/FlexAC.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在忠实性（faithfulness）与创造性（creativity）之间存在固有权衡。不同任务（如图像描述与事件规划）需要不同程度的关联推理（associative reasoning）强度，但现有方法无法灵活调节这一强度，限制了MLLM在不同场景下的适应性。
- **研究动机**：受认知科学中发散与收敛思维的启发，作者认为MLLM具备类似人类的联想过程，应能像人脑一样灵活调节联想强度，以同时支持事实推理和创造性生成。现有幻觉缓解技术（如对比解码、偏好优化）虽提高了忠实性，但抑制了创造性；而创造性增强方法又缺乏可控性。
- **整体含义**：本文首次将幻觉与创造性统一视为关联推理的不同表现，并提出了一个轻量级、免训练的框架FlexAC，使MLLM能够根据任务需求在事实性与创造性之间灵活切换。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过分析MLLM内部表征，发现中间层（middle layers）对联想的形成起关键作用，且幻觉响应可以编码可靠的联想方向。基于此，FlexAC在推理时向中间层注入可控的联想向量，从而调节关联强度。
- **关键技术细节**：
  - **Phase I: 离线控制向量构建**
    1. **幻觉引导中间状态**：对同一输入生成忠实（低联想）和幻觉（高联想）响应对，提取中间层隐藏状态，计算差值作为联想方向。
    2. **实例选择（Instance Selection）**：选取Top-K个余弦距离最大的响应对，平均其差值得出通用联想向量（general associative vector），以减少噪声。
    3. **方向集成（Directional Integration）**：针对需要多维联想（如隐喻、语境关联）的任务，利用GPT-4o生成少量目标域高联想样本，通过前向传播提取任务特定联想向量（task-specific vector）。
  - **Phase II: 推理时控制**
    1. **向量注入**：在中间层隐藏状态上叠加通用向量和任务特定向量（带可调系数α）。
    2. **自适应强度校准（Steering Intensity Calibration, SIC）**：为防止过度引导，根据当前表征与联想方向的对齐程度动态调节α：当表征已接近联想方向时减弱强度，反之增强。公式为 α = sigmoid(max(-fl·vl/(∥fl∥∥vl∥), 0))，并对调制后的特征进行归一化以保持尺度。
- **公式/流程说明**（非数学推导，文字描述）：
  - 控制向量 v_l = 平均（幻觉特征 - 忠实特征）
  - 推理时：f_control = f_l + α_gen * v_gen + α_task * v_task
  - α 由 SIC 模块基于余弦相似度计算，经 sigmoid 归一化
  - 最后对 f_control 进行长度归一化，保持原始尺度

### 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集/场景**：
  - 幻觉（低联想任务）：CHAIR（基于COCO2014图像标注）、POPE（500张COCO验证集图像）
  - 创造力（高联想任务）：VDAT（本文新提出的视觉发散联想测试，基于CLIP相似度评估联想强度）、Creation-MMBench（包含765个测试用例，涵盖文学写作、功能性写作、专业写作和创意理解等子类）
  - 通用能力：MME、MMMU、MMStar（涵盖感知、推理等多种能力）
- **对比方法**：Regular（基线）、Ha-DPO（幻觉感知偏好优化）、VCD（视觉对比解码）、VAF（视觉信号增强）。注意：Ha-DPO仅用于LLaVA-1.5。
- **模型**：LLaVA-1.5-7b、Qwen-VL-Chat、DeepSeek-VL2-tiny

### 4. 资源与算力

- 论文明确说明：所有实验在 **8×RTX 4090 GPU** 上运行。
- 训练量：FlexAC是**训练无关（training-free）** 框架，仅需在少量样本（50张COCO图像）上进行前向传播以构建控制向量，无需模型训练。
- 推理开销：与原始模型相比，FlexAC仅增加极少的计算开销（图16显示其推理时间略高于Regular，但远低于VCD的双次前向传播）。

### 5. 实验数量与充分性

- 实验数量充足：涵盖了**三大类共6+个benchmark**（CHAIR、POPE、VDAT、Creation-MMBench、MME、MMMU、MMStar），并在附录中额外测试了MM-Vet、MMBench、SEED-Bench等11个基准（表5）。
- 消融实验：包括**层控制位置分析**（浅层/中层/深层对比）、**组件消融**（Instance Selection、SIC、Directional Integration）、**Top-K敏感性**（从1到2000变化）。
- 用户研究（附录D.1）：15名评估者对30个样本进行盲评，验证VDAT与人类判断的一致性。
- 充分性判断：实验覆盖了多个模型、多个任务类型、多个baseline，并进行了充分的消融和敏感性分析，结果客观、公平。但主要局限在开源模型，未在封闭模型（如GPT-4V）上验证。

### 6. 论文的主要结论与发现

- **关键发现**：
  - MLLM的联想行为主要编码在**中间层**（而非浅层或深层），修改中间层表征可有效调控联想强度。
  - 幻觉响应可作为有效的**引导方向**（steering direction）来刺激或抑制联想能力。
- **方法有效性**：
  - 在低联想任务（CHAIR）：FlexAC-P（抑制联想）将Qwen-VL的CHAIR_S从40.6降至19.2，在LLaVA-1.5上从50.8降至36.6，显著优于对比方法。
  - 在高联想任务（VDAT、Creation-MMBench）：FlexAC-C（增强联想）在VDAT上达到88.49（LLaVA-1.5），在Creation-MMBench上Reward提升10.92（Qwen-VL），远超其他方法。
  - 通用能力：在MME、MMMU、MMStar上，FlexAC-C和FlexAC-P均保持与基线相当的性能，表明不会损害核心能力。
- **可控性**：通过调节α系数，模型可在事实性与创造性之间连续切换，且自适应校准避免了过度引导。

### 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - 统一了幻觉与创造性为关联推理的两种表现，提供新视角。
  - 训练无关、轻量级，仅需少量样本构建控制向量，易于部署。
  - 引入自适应校准机制和方向集成，实现精细可控的联想强度调节。
  - 提出VDAT基准，直接衡量视觉驱动的发散联想能力，填补了创造力评估的空白。
- **实验亮点**：
  - 在多个开源MLLM上验证，具有泛化性。
  - 消融实验系统全面，证明了各组件（实例选择、强度校准、方向集成）的必要性。
  - 用户研究验证了VDAT与人类感知的一致性，增强了评估的可信度。

### 8. 不足与局限

- **应用限制**：
  - 需要**白盒访问**模型中间层隐藏状态，因此不适用于黑盒模型（如ChatGPT、GPT-4V）。
  - 需构建少量任务特定样本（依赖GPT-4o），有一定额外成本。
- **实验局限性**：
  - 仅在7B左右的开源模型上测试，未在更大模型（如LLaVA-13B、Qwen-VL-72B）或商业模型上验证。
  - 对幻觉的评估主要基于CHAIR和POPE，未覆盖更复杂的开放领域幻觉检测。
  - 创造性评估（VDAT、Creation-MMBench）可能受限于自动指标和标注质量，用户研究样本量较小（30个）。
- **潜在偏差风险**：控制向量来源于特定COCO数据集（2000张），可能引入数据分布偏差。任务特定向量由GPT-4o生成，存在模型偏见。
- **理论分析**：对中间层机制的探讨基于相关性分析，缺乏严格因果证明，但层替换实验一定程度支持了因果性。

（完）
