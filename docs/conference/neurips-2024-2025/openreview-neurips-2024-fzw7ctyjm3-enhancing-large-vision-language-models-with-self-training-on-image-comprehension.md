---
title: Enhancing Large Vision Language Models with Self-Training on Image Comprehension
title_zh: 通过图像理解自训练增强大视觉语言模型
authors: "Yihe Deng, Pan Lu, Fan Yin, Ziniu Hu, Sheng Shen, Quanquan Gu, James Zou, Kai-Wei Chang, Wei Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=FZW7Ctyjm3"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 大视觉语言模型自训练
tldr: 大视觉语言模型在理解图像时缺乏高质量视觉语言数据。本文提出STIC自训练方法，利用模型自身生成数据来增强图像理解能力，为在有限标注下提升LVLM感知和推理性能提供了有效途径。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 417, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 421, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 573, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 408, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 413, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 387, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 575, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1191, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 434, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1436, \"height\": 986, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 803, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 708, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 708, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1203, \"height\": 257, \"label\": \"Table\"}]"
motivation: LVLM的图像理解能力提升需要高质量视觉语言数据，但获取成本高。
method: 提出STIC自训练框架，利用模型自身生成数据来改善图像理解能力。
result: 在无需额外标注数据的情况下提升了LVLM的视觉感知和推理性能。
conclusion: 自训练可以有效缓解LVLM对标注数据的依赖，提升模型实用性。
---

## Abstract
Large vision language models (LVLMs) integrate large language models (LLMs) with pre-trained vision encoders, thereby activating the perception capability of the model to understand image inputs for different queries and conduct subsequent reasoning. Improving this capability requires high-quality vision-language data, which is costly and labor-intensive to acquire. Self-training approaches have been effective in single-modal settings to alleviate the need for labeled data by leveraging model's own generation. However, effective self-training remains a challenge regarding the unique visual perception and reasoning capability of LVLMs. To address this, we introduce **S**elf-**T**raining on **I**mage **C**omprehension (**STIC**), which emphasizes a self-training approach specifically for image comprehension. First, the model self-constructs a preference dataset for image descriptions using unlabeled images. Preferred responses are generated through a step-by-step prompt, while dis-preferred responses are generated from either corrupted images or misleading prompts. To further self-improve reasoning on the extracted visual information, we let the model reuse a small portion of existing instruction-tuning data and append its self-generated image descriptions to the prompts. We validate the effectiveness of STIC across seven different benchmarks, demonstrating substantial performance gains of 4.0% on average while using 70% less supervised fine-tuning data than the current method. Further studies dive into various components of STIC and highlight its potential to leverage vast quantities of unlabeled images for self-training.

---

## 论文详细总结（自动生成）

# 论文总结：Enhancing Large Vision Language Models with Self-Training on Image Comprehension (STIC)

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大视觉语言模型（LVLMs）在理解图像内容并基于查询进行推理时，需要大量高质量的视觉-语言数据来进行微调。然而，获取这类数据（如人工标注或GPT-4V生成）成本高昂且劳动密集。
- **背景**：自训练方法在纯文本的单模态大语言模型中已成功缓解了对标注数据的依赖，但直接应用到多模态的LVLMs面临独特挑战——模型必须同时提升图像感知能力和图文联合推理能力。
- **研究动机**：提出一种无需额外标注（包括人类标注或教师模型），仅利用模型自身生成的数据来增强LVLM图像理解能力的自训练方法，从而降低数据获取成本。

## 2. 方法论

### 2.1 核心思想
STIC 是一种**两阶段的自训练算法**，专注于提升LVLMs的图像理解能力：
- **第一阶段（图像理解自训练）**：模型利用未标注图像自行构建描述偏好数据集（偏好/非偏好响应对），通过DPO（直接偏好优化）损失微调。
- **第二阶段（描述注入微调）**：模型复用少量已有的指令微调数据，将自生成的图像描述注入到提示中，进一步微调以增强基于图像描述的推理能力。

### 2.2 关键技术细节

#### 第一阶段：图像理解自训练
- **构建偏好数据**：
  - **偏好响应**：使用精心设计的“逐步描述提示”（如“请详细描述图像，聚焦于主角、环境、情绪等”）引导模型生成高质量、准确的描述。
  - **非偏好响应**：
    - 通过“坏提示”诱导模型产生幻觉（例如“描述图像中可能存在的想象物体”）。
    - 通过图像损坏（颜色抖动、低分辨率）生成不准确的描述。
  - 数据来源：6k张来自MSCOCO数据集的未标注图像。
- **损失函数**：带正则化的DPO损失：
  \[
  \mathcal{L}(\theta,\theta_{\text{ref}}) = \mathbb{E}_{(x,y_w,y_l)\sim\mathcal{S}} \left[ \ell\left( \lambda \log\frac{p_\theta(y_w|x)}{p_{\theta_{\text{ref}}}(y_w|x)} - \lambda \log\frac{p_\theta(y_l|x)}{p_{\theta_{\text{ref}}}(y_l|x)} \right) - \alpha \log p_\theta(y_w|x) \right]
  \]
  其中 \(\ell(t)=\log(1+\exp(-t))\)，\(\alpha\) 控制对偏好响应的额外强调。

#### 第二阶段：描述注入微调
- 从模型已有指令微调数据中随机抽取5k条。
- 将模型自生成的图像描述与原指令拼接（如：“图像描述：...\n原始指令”），保持原始真实回答不变。
- 对模型进行1个epoch的LoRA微调。

#### 推理时的可选策略：描述后回答（DaR）
- 先让模型生成图像描述，然后将描述与原始问题拼接后再回答，可进一步提升推理质量。

## 3. 实验设计

### 3.1 基准与数据集
- **基础模型**：LLaVA-v1.6 (Mistral-7B) 为主要实验模型；LLaVA-v1.5 (Vicuna-7B) 用于与POVID对比。
- **评估基准**（7个广泛使用的LVLM基准）：
  - 科学推理：ScienceQA
  - 数学推理：MathVista
  - 文字识别：TextVQA
  - 图表理解：ChartQA
  - 综合问答：LLaVA-Bench、MMBench、MM-Vet
- **偏好数据构建数据源**：MSCOCO train2014（6k张未标注图像）。
- **消融研究**还使用了Vision Flan数据集（VFLAN，191任务，6k张）验证图像分布多样性影响。

### 3.2 对比方法
- 原始LVLM（LLaVA-v1.5、LLaVA-v1.6）
- POVID（一种基于人工修改图像或注入幻觉的并发偏好微调方法）

### 3.3 实验充分性与公平性
- 所有评估使用LLaVA官方评估脚本，确保与原模型结果公平比较。
- 消融实验覆盖多个方面：
  - 描述后回答（DaR）效果
  - 两阶段逐步贡献
  - 负样本（非偏好响应）的必要性
  - 缩放规律（6k vs 12k vs 30k图像）
  - 图像分布对性能增益的影响（t-SNE可视化）
  - 不同图像源（COCO vs VFLAN）的效果
  - 更大模型（LLaVA-v1.6 13B）的可扩展性
- 实验数量超10组，涵盖不同数据集和设置，较为充分、客观。

## 4. 资源与算力

- **GPU型号**：NVIDIA RTX A6000
- **数量与时长**：
  - 自训练（6k图像+5k指令数据）在4个GPU上耗时约6小时。
  - 每个基准评估耗时2-8小时（主要取决于测试集大小）。
- **微调方式**：采用LoRA（lora_r=128, lora_alpha=256, 目标为所有层）以提高效率。

## 5. 主要结论与发现

1. **显著性能提升**：在7个基准上平均准确率提高**4.0%**（LLaVA-v1.6从54.7%升至58.7%），同时减少70%的监督微调数据使用。
2. **偏好数据构建有效**：自生成的非偏好响应（来自坏提示/图像损坏）对提升至关重要。去掉负样本后，性能平均下降2.5%（在ScienceQA、TextVQA、LLaVA-Bench上）。
3. **描述后回答（DaR）带来额外增益**：结合STIC的DaR比单独使用效果更好，平均再提升1.1%。
4. **缩放性**：偏好数据从6k增至12k，在LLaVA-Bench上的增益从1.9%升至3.1%；使用30k图像可进一步提升至3.9%，说明STIC可有效利用大量无标签图像。
5. **图像分布相关性**：t-SNE分析表明，MSCOCO图像与下游任务图像分布重叠越大，STIC提升越显著（例如ScienceQA提升6.4%）；但ChartQA分布重叠少却仍获得5.1%提升，表明基础图像理解能力本身对图表推理有根本性帮助。
6. **更大模型也受益**：在LLaVA-v1.6 13B上，STIC在MM-Vet上提升+4.3%，在LLaVA-Bench上提升+1.1%，证明可扩展性。

## 6. 优点

- **无需标注数据**：完全利用模型自身生成构建偏好数据，避免昂贵的人工或GPT-4V标注。
- **两阶段设计合理**：先提升感知，再增强推理，符合认知规律；Das（第二阶段的描述注入）与推理时的DaR协同作用。
- **消融实验全面深入**：系统验证了负样本、DaR、数据量、图像分布等关键因素，提供了可靠的洞察。
- **成本效益突出**：仅用70%之前的监督数据就能达到更好效果，且可利用海量无标注图像。
- **通用性**：不仅在自然图像（COCO）上有效，在多样化图像源（VFLAN）上也有持续提升。

## 7. 不足与局限

- **对特定任务提升有限**：在MathVista上仅提升2.4%，可能因为该基准包含多种数学推理任务和图像类型（从基础到大学水平），超出了单纯图像理解范畴。
- **偏好数据构建策略简单**：基于“好/坏提示”和图像损坏的方式可能不足以处理需要细微理解的场景；更复杂的策略可能带来更好的对齐。
- **两阶段非端到端**：当前为顺序训练，未来可探索合并为统一训练框架以增强协同。
- **缩放上限未探索**：虽展示了缩放性，但未研究当数据量极大时是否会出现收益递减；需进一步表征缩放行为。
- **统计显著性未报告**：除LLaVA-Bench外，未提供误差条或置信区间，主要因采用贪心解码（确定性输出）且计算资源限制。
- **公平性评估缺失**：未讨论模型可能存在的偏差（如对特定人群或场景的偏见），虽在Broader Impacts中提及但未实验验证。

---
（完）
