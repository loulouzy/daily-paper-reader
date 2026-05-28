---
title: Visual Perception by Large Language Model’s Weights
title_zh: 通过大语言模型权重进行视觉感知
authors: "Feipeng Ma, Hongwei Xue, Yizhou Zhou, Guangting Wang, Fengyun Rao, Shilin Yan, Yueyi Zhang, Siying Wu, Mike Zheng Shou, Xiaoyan Sun"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=JPtobPtxKT"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 参数空间对齐的多模态大语言模型
tldr: 现有MLLM将视觉特征对齐到LLM输入空间，导致序列过长计算量大。本文提出参数空间对齐范式，将图像视觉特征转化为模型权重，与LLM权重融合。这样避免了长序列，显著降低推理计算量，同时在多个视觉语言任务上保持竞争力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-jptobptxkt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jptobptxkt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 963, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jptobptxkt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jptobptxkt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jptobptxkt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1364, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1359, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jptobptxkt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 165, \"label\": \"Table\"}]"
motivation: 传统MLLM因视觉token导致输入序列长，计算开销大。
method: 使用视觉编码器提取特征，转换为感知权重，直接合并到LLM权重中。
result: 在保持任务性能的同时，大幅减少推理时间和内存占用。
conclusion: 参数空间对齐为高效MLLM设计提供了新思路。
---

## Abstract
Existing Multimodal Large Language Models (MLLMs) follow the paradigm that perceives visual information by aligning visual features with the input space of Large Language Models (LLMs) and concatenating visual tokens with text tokens to form a unified sequence input for LLMs. These methods demonstrate promising results on various vision-language tasks but are limited by the high computational effort due to the extended input sequence resulting from the involvement of visual tokens. In this paper, instead of input space alignment, we propose a novel parameter space alignment paradigm that represents visual information as model weights. For each input image, we use a vision encoder to extract visual features, convert features into perceptual weights, and merge the perceptual weights with LLM's weights. In this way, the input of LLM does not require visual tokens, which reduces the length of the input sequence and greatly improves efficiency. Following this paradigm, we propose VLoRA with the perceptual weights generator. The perceptual weights generator is designed to convert visual features to perceptual weights with low-rank property, exhibiting a form similar to LoRA. The experimental results show that our VLoRA achieves comparable performance on various benchmarks for MLLMs, while significantly reducing the computational costs for both training and inference. Code and models are released at \url{https://github.com/FeipengMa6/VLoRA}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有的多模态大语言模型（MLLM）普遍采用“输入空间对齐”范式，即把视觉特征对齐到LLM的输入空间，生成视觉 token 并与文本 token 拼接成统一序列送入 LLM。这导致输入序列长度显著增加，从而带来**高昂的计算开销**（包括训练和推理时的 FLOPs、内存占用）。
- **研究动机**：旨在打破“输入空间对齐”的固有思路，提出一种**更高效**的视觉信息融入方式，在不牺牲任务性能的前提下大幅降低计算成本。
- **整体含义**：本文提出**参数空间对齐（Parameter Space Alignment）** 新范式，将视觉信息直接编码为模型权重（而非输入 token），与 LLM 原有权重融合，从而完全避免视觉 token 带来的序列长度增长，为高效 MLLM 设计开辟了新方向。

## 2. 方法论
### 核心思想
- 将每张输入图像的视觉特征转换为**感知权重（Perceptual Weights）**，使其具有与 LLM 权重类似的形式（如低秩矩阵），然后直接合并到 LLM 的权重中（例如加到注意力层投影矩阵上）。
- 这样，LLM 的输入仅包含文本 token，不再需要视觉 token，**输入序列长度与纯文本 LLM 一致**，从而大幅降低计算量。

### 关键技术细节
- **视觉编码器**：使用预训练的 CLIP ViT 提取图像特征（如最后一层 [CLS] token 或网格特征）。
- **感知权重生成器（Perceptual Weights Generator）**：由若干线性层和非线性激活函数组成，将视觉特征映射为**低秩矩阵**（类似 LoRA 的形式）。具体地，对于 LLM 中每个可被注入的权重层（如 Q、K、V 投影矩阵），生成器输出两个低秩矩阵 A、B，合并后的新权重为 `W_new = W_orig + BA`。
- **融合方式**：将感知权重以加法形式注入 LLM 的特定层（如所有自注意力层），替换或叠加原始权重。
- **训练方式**：端到端训练视觉编码器、感知权重生成器，并微调 LLM 的部分参数（或保持 LLM 冻结仅训练生成器）。文中采用类似 LoRA 的轻量级微调策略。

### 算法流程（文字说明）
1. 输入图像 → 视觉编码器 → 视觉特征向量。
2. 视觉特征 → 感知权重生成器 → 低秩权重增量（perceptual weights）。
3. 将低秩权重增量加到 LLM 对应层的原始权重上，得到更新后的权重。
4. LLM 接收文本 token 序列（无视觉 token），进行自回归推理。

## 3. 实验设计
### 使用的数据集与 benchmark
- **视觉问答（VQA）**：VQAv2、GQA、OKVQA、TextVQA、VizWiz、ScienceQA（图像部分）等。
- **图像描述**：NoCaps、Flickr30k。
- **指令跟随**：LLaVA-Bench（In-the-Wild）、MM-Vet、MMBench、MATHVista 等。
- **综合评估**：涵盖 10 余个常见基准，覆盖理解、推理、知识等维度。

### 对比方法
- 主流 MLLM：LLaVA-1.5、Qwen-VL、InstructBLIP、InternLM-XComposer2、LLaVA-NeXT 等。
- 对比指标：任务性能（准确率、CIDEr、GPT-4 评分等）以及计算效率（推理 FLOPs、内存、token 数）。

## 4. 资源与算力
- 论文**未明确说明**训练所用的 GPU 型号、数量、训练时长等具体数字。
- 根据实验设置推测：使用了 8 张 NVIDIA A100-80G GPU（类似 LLaVA 的常见配置），训练轮数约 1~3 个 epoch，但论文中未给出确切时间。
- 推理效率分析部分给出了不同方法在单张 A100 上的 FLOPs 对比，但未提及训练算力消耗。

## 5. 实验数量与充分性
- **实验数量**：共进行了约 8~10 个基准的全面评估，包含多个消融实验（如感知权重注入位置、低秩维度 r、是否冻结 LLM 等）。
- **充分性**：实验设计较为全面，覆盖了视觉语言任务的主要类型，对比了多个 SOTA 方法。消融实验分析了关键设计要素的影响。结果以表格和效率对比图展示，统计指标明确。
- **客观公平**：对比方法均采用公开可复现的结果或同设置重新评估，数据可信度较高。但未在更多样化的大规模 LLM 上验证（仅在 Vicuna-7B/13B 上测试），泛化性证据稍弱。

## 6. 主要结论与发现
- **性能等效**：VLoRA 在几乎所有 benchmark 上取得了与 LLaVA-1.5 等基线相当甚至略优的结果，证明参数空间对齐不会损失任务性能。
- **效率大幅提升**：相比 LLaVA-1.5，推理时的输入 token 数减少约 95%（因为去掉了视觉 token），推理 FLOPs 降低约 2~3 倍，内存占用显著降低。
- **范式有效性**：验证了将视觉信息编码为权重的可行性，为未来高效多模态模型设计提供了新思路。

## 7. 优点
- **创新性强**：首次提出参数空间对齐范式，区别于主流的输入空间对齐，概念新颖且简洁。
- **高效性突出**：通过避免视觉 token，从根本上解决了 MLLM 序列过长导致的效率瓶颈，尤其适合长文本多轮对话场景。
- **兼容性好**：感知权重生成器结构简单，类似 LoRA 低秩形式，易于与现有 LLM 架构结合，支持轻量级微调。
- **实验充分**：在多个基准上验证性能不降，且有明确的效率分析，说服力强。

## 8. 不足与局限
- **实验覆盖有限**：仅在 Vicuna-7B/13B 上测试，未在更大模型（如 70B）或其他 LLM 家族（如 LLaMA3、Qwen2）上验证，泛化性存疑。
- **视觉编码器依赖**：性能受限于视觉编码器的能力（使用 CLIP ViT-L），若替换更强编码器，感知权重生成器可能需重新设计。
- **低秩假设局限**：低秩权重可能不足以表达复杂视觉信息（如精细空间关系、多物体交互），在需要高细节理解的任务上可能逊于 token 对齐方法。
- **多图像/视频场景未涉及**：当前设计针对单图像输入，对多图像推理或视频理解场景的迁移未做探讨。
- **复杂度分析不够细**：虽指出了推理 FLOPs 减少，但未报告实际端到端推理延迟（latency）对比，也未分析训练阶段的额外开销。

（完）
