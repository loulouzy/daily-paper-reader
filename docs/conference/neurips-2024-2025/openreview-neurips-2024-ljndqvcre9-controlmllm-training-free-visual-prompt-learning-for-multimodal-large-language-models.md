---
title: "ControlMLLM: Training-Free Visual Prompt Learning for Multimodal Large Language Models"
title_zh: ControlMLLM：多模态大语言模型的无训练视觉提示学习
authors: "Mingrui Wu, Xinyue Cai, Jiayi Ji, Jiale Li, Oucheng Huang, Gen Luo, Hao Fei, GUANNAN JIANG, Xiaoshuai Sun, Rongrong Ji"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=LjnDqVcrE9"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 多模态大语言模型的无训练视觉提示注入
tldr: 本文提出一种无需训练的方法，通过优化可学习的潜在变量，在推理时调整多模态大语言模型的视觉令牌，控制注意力聚焦于指定区域。该方法基于能量函数增强参考区域在注意力图中的响应，实现了精细的区域描述与推理，避免了高昂的训练成本，并在多个视觉定位和区域描述任务上取得优异效果。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1349, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1401, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 1073, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 1027, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 447, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 443, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 446, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1419, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 441, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 448, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1414, \"height\": 1282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1417, \"height\": 1162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1428, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1421, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ljndqvcre9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1260, \"height\": 731, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 787, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 553, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 735, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 503, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1382, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 525, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 510, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 875, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1406, \"height\": 1064, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1406, \"height\": 1061, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ljndqvcre9/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1421, \"height\": 343, \"label\": \"Table\"}]"
motivation: 现有视觉提示注入需要额外训练，代价高且灵活性受限。
method: 在推理时通过能量函数优化潜在变量，调整视觉令牌以控制注意力聚焦。
result: 在区域描述和推理任务上，该方法无需训练即可达到与有监督方法可比的性能。
conclusion: 无训练视觉提示注入为MLLM的灵活交互提供了低成本解决方案。
---

## Abstract
In this work, we propose a training-free method to inject visual prompts into Multimodal Large Language Models (MLLMs) through learnable latent variable optimization. We observe that attention, as the core module of MLLMs, connects text prompt tokens and visual tokens, ultimately determining the final results. Our approach involves adjusting visual tokens from the MLP output during inference, controlling the attention response to ensure text prompt tokens attend to visual tokens in referring regions. We optimize a learnable latent variable based on an energy function, enhancing the strength of referring regions in the attention map. This enables detailed region description and reasoning without the need for substantial training costs or model retraining. Our method offers a promising direction for integrating referring abilities into MLLMs, and supports referring with box, mask, scribble and point. The results demonstrate that our method exhibits out-of-domain generalization and interpretability.

---

## 论文详细总结（自动生成）

# 论文《ControlMLLM: Training-Free Visual Prompt Learning for Multimodal Large Language Models》详细总结

## 1. 核心问题与整体含义（动机与背景）

- **问题**：现有多模态大语言模型（MLLMs）通常只进行粗粒度的图像级对齐，用户只能通过文本提示指导模型，难以指定图像中的特定区域进行细粒度描述或推理。已有的注入视觉提示（如框、掩码等）的方法（如Ferret、Shikra）需要大量训练数据和昂贵的重新训练，且在新领域或新基座模型上泛化性差。
- **目标**：提出一种**无需训练**的方法，在推理阶段向MLLMs注入视觉提示，使模型能够关注用户指定的区域，实现细粒度区域理解与生成，同时保持模型原有的语言能力和跨领域泛化性。
- **整体含义**：该方法不需要修改模型参数，通过优化可学习的潜在变量来调整视觉令牌，控制注意力聚焦于参考区域，为MLLMs提供了一种灵活、低成本的视觉提示注入方案，并展现出良好的可解释性和领域外迁移能力。

## 2. 方法论：核心思想与技术细节

- **核心思想**：基于观察——MLLMs中的注意力机制连接文本令牌和视觉令牌，决定了最终输出。通过编辑视觉令牌（MLP输出）来间接影响注意力图，使文本令牌更关注参考区域。具体做法是向视觉令牌添加一个可学习的潜在变量，基于能量函数优化该变量，增强参考区域在注意力图中的响应。
- **关键技术细节**：
  - **视觉令牌编辑**：在推理的第0步，初始化一个与视觉令牌形状相同的零向量 `p_v`，添加到视觉令牌 `e_v` 上，形成新的视觉令牌 `e_v + p_v`。
  - **能量函数**：使用上下文令牌（所有文本令牌注意力图的平均池化）与参考区域掩码或距离图计算损失。分为两种：
    - **硬掩码能量函数**（用于框和掩码）：最大化参考区域内注意力响应占比的平方。
    - **软掩码能量函数**（用于涂鸦和点）：基于距离变换，让注意力响应集中在给定点/划线附近。
  - **优化过程**：通过反向传播迭代更新 `p_v`，迭代次数 T=5，学习率 α=400，使用指数移动平均（EMA, β=0.5）和早停（ES）防止过拟合。
  - **流程**：在推理第0步，输入图像和文本提示，经过视觉编码器和MLP得到视觉令牌，加入 `p_v`，然后送入LLM并计算所有注意力层中上下文令牌与视觉令牌的注意力图，利用能量函数计算损失，反向传播更新 `p_v`，重复 T 次后，用优化后的 `p_v` 进行正常自回归生成。
- **公式说明**：
  - 硬掩码能量函数：\( E = 1 - (\sum_{i \in r} A_i / \sum_{i} A_i)^2 \)
  - 软掩码能量函数：基于高斯距离权重，类似地惩罚注意力响应偏离参考区域。
  - 更新：\( p_v \leftarrow p_v - \alpha \nabla_{p_v} E \)

## 3. 实验设计

- **数据集与任务**：
  - **Referring Object Classification (ROC)**：基于LVIS验证集构建1748个问题（其中1548测试，200验证），提示格式：“Is the object [location] a [class A] or a [class B]?”。支持框、掩码、涂鸦、点四种提示。
  - **Referring Text Classification (RTC)**：基于COCO-Text数据集构建1372个问题，二分类任务，仅测试框和掩码（因文本不连续性）。
  - **Referring Description**：基于RefCOCOg测试集，使用区域-文本对，评估指标为BLEU@4、METEOR、CIDEr-D、SPICE。
  - **其他**：OCR、Screenshot等展示性应用。
- **对比方法**：
  - **训练方法**：Kosmos-2, GPT4-ROI, Shikra-7B, Ferret-7B。
  - **训练自由方法**：基线LLaVA（无提示）、LLaVA+Blur（模糊区域外）、LLaVA+Color（区域高亮）、LLaVA+Edit Att（直接编辑注意力加常数η）。
- **基座模型**：主要为LLaVA-v1.5-7B，同时验证了InstructBLIP-7B/13B、LLaVA-HR-7B等。

## 4. 资源与算力

- **硬件**：2块RTX 3090 GPU，每块24GB显存。
- **推理时间**：未报告训练时间（方法无需训练）。推理阶段，短输出（约7令牌）比基线慢约2.3秒（3.56s vs 1.22s）；长输出（约400令牌）差距缩小至约1.7秒（7.45s vs 5.78s）。最大显存占用从7G升至14G（表8）。
- **说明**：文中明确提到“所有实验在两块RTX 3090上进行”，但未详细给出每个任务的运行总时长。

## 5. 实验数量与充分性

- **实验数量**：约10组以上主要实验（表1-8，以及附录中多个补充实验）。包括：
  - ROC任务（表1）：比较5种训练自由方法和4种训练方法，涵盖4种提示类型。
  - RTC任务（表2）：类似比较，训练自由方法表现突出。
  - 描述任务（表3）：在RefCOCOg上验证。
  - 不同MLLMs对比（表4）：LLaVA, InstructBLIP, LLaVA-HR。
  - 消融实验（表5、6、7）：T、α、EMA、早停、LLM规模。
  - 额外实验：不同文本提示、视觉提示大小、高亮令牌对比、更多可视化（附录）。
- **充分性与客观性**：
  - 实验设计较为全面：涵盖了分类、描述、跨领域文本识别等任务，对比了多个有代表性方法，包括训练方法和训练自由方法。
  - 评估指标合理（准确率、描述生成指标）。
  - 消融实验考虑了关键超参数，并提供了“相关性分数”控制过拟合。
  - 局限性：部分训练方法（如Ferret）在域内性能更高，但本文方法在域外泛化上优势明显，对比公平；但ROC任务上训练自由方法整体低于最先进的Ferret，作者指出受限于基座LLaVA的能力。
  - 描述任务指标（BLEU等）受模型输出风格影响，仅用于内部对比，未与其他模型直接对比，合理。

## 6. 主要结论与发现

- **有效性**：无需训练即可成功向MLLMs注入视觉提示，支持框、掩码、涂鸦、点四种形式，显著提升区域描述和推理能力。
- **跨领域泛化**：在文本分类（RTC）等域外任务上，性能显著优于需要训练的方法（如Ferret仅55.47%，本文61.22%），表明方法具有良好的泛化性。
- **可解释性**：优化后的注意力图与参考区域高度一致，能可视化模型关注的区域。
- **缓解幻觉**：引导模型关注指定区域，减少了输出中的幻觉内容（如错误对象描述）。
- **关键消融**：迭代次数T=5、α=400、EMA（β=0.5）及早停策略可平衡收敛与过拟合；相关性分数在0.18左右时性能最佳。

## 7. 优点

- **无需训练**：避免数据收集和昂贵微调，即插即用于现有白盒MLLMs。
- **支持多种视觉提示**：涵盖框、掩码、涂鸦、点，灵活性高。
- **优秀的域外泛化能力**：在文本识别等跨领域任务上超过需训练的方法。
- **可解释性**：通过注意力图可视化揭示模型决策依据。
- **简单高效**：仅需少量迭代优化，易于实现和集成。

## 8. 不足与局限

- **推理开销**：相比基线增加额外时间（尤其短输出时明显），尽管可用工程优化缓解。
- **仅支持单区域**：当前仅能处理一个视觉提示，多区域控制未实现。
- **依赖白盒模型**：需要获取梯度进行优化，不适用于黑盒API。
- **受文本提示影响**：模糊或歧义的文本提示可能导致优化效果不佳（需清晰具体的文本）。
- **对基础模型能力敏感**：若基座MLLMs本身对区域理解能力弱（如InstructBLIP文本识别差），提升有限。
- **可能过拟合**：需精细调节超参数（T、α、EMA、ES）以避免注意力过度集中于参考区域而破坏语言能力。

（完）
