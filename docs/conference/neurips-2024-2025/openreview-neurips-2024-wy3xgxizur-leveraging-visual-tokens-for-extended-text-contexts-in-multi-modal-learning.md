---
title: Leveraging Visual Tokens for Extended Text Contexts in Multi-Modal Learning
title_zh: 利用视觉令牌扩展多模态学习中的文本上下文
authors: "Alex Jinpeng Wang, Linjie Li, Yiqi Lin, Min Li, Lijuan Wang, Mike Zheng Shou"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=WY3xgXIZUR"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 多模态大语言模型利用视觉令牌扩展上下文长度
tldr: 本文针对多模态大语言模型长上下文训练中GPU内存和计算成本高的问题，提出利用视觉令牌处理长上下文文本的方法。该方法将文本信息编码为视觉令牌，显著降低了内存占用和浮点运算量。以56B参数的MoE模型为例，将预训练上下文长度从256扩展到2048令牌，同时FLOPs更少，为MLLM高效处理长文本提供了新方向。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 579, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 520, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wy3xgxizur/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 639, \"height\": 857, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1054, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 930, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 645, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1133, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 646, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1308, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 808, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1197, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1425, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wy3xgxizur/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1057, \"height\": 225, \"label\": \"Table\"}]"
motivation: 多模态模型中长上下文训练导致巨大的GPU内存和计算开销。
method: 使用视觉令牌表示长文本，压缩信息以降低计算成本。
result: 将MLLM预训练上下文长度从256扩展到2048令牌，且FLOPs减少。
conclusion: 视觉令牌作为文本压缩表示，可经济地扩展MLLM的上下文容量。
---

## Abstract
Training models with longer in-context lengths is a significant challenge for multimodal machine learning due to substantial GPU memory and computational costs. This exploratory study does not present state-of-the-art models; rather, it introduces an innovative method designed to increase in-context text length in multi-modality large language models (MLLMs) efficiently. We present \ModelFullName (\ModelName), which processes long in-context text using visual tokens. This technique significantly reduces GPU memory usage and floating point operations (FLOPs). For instance, our method expands the pre-training in-context length from 256 to 2048 tokens with fewer FLOPs for a 56 billion parameter MOE model. Experimental results demonstrate that \ModelName enhances OCR capabilities and delivers superior performance on common downstream benchmarks for in-context few-shot evaluation. Additionally, \ModelName proves effective for long context inference, achieving results comparable to full text input while maintaining computational efficiency.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态大语言模型（MLLMs）在训练过程中需要处理长上下文文本，但GPU内存和计算开销巨大。例如，OpenFlamingo-9B仅处理256个token的文本，仍需32块80GB A100 GPU训练超过3天。现有方法（如记忆库、新型自注意力机制）虽可扩展上下文，但计算成本仍然很高。
- **研究动机**：作者观察到MLLMs的视觉编码器（如ViT-L）参数量远小于文本解码器（如56B MoE），且视觉编码器在图像-文本配对训练后已具备一定的OCR能力。因此，**将长文本转化为图像，利用轻量视觉编码器处理，可以显著降低计算成本，同时保留文本语义**。
- **整体含义**：提出一种名为**VisInContext**（Visualized In-Context Text Processing）的方法，通过将文本渲染为图像并用视觉token表示，使模型能够高效处理更长的上下文文本（从256 token扩展到2048 token），且FLOPs几乎不变。

## 2. 论文提出的方法论

- **核心思想**：将长文本中“被截断”的部分（因GPU内存限制只能采样256 token而丢失的上下文）渲染为图像，然后用视觉编码器提取视觉token，再通过可学习的重采样器（resampler）压缩成固定数量的token，送入语言模型。这样，模型实际看到的文本长度（In-context Text Length）远大于直接输入LLM的文本token长度（Text Token Length）。

- **关键技术细节**：
  1. **文本渲染（Text Rendering）**：将文本以HERSHEY字体（10px）渲染为RGB图像，每个16×16 patch平均容纳约1.5个OPT token。224×224的图像可包含约294个token，所需视觉token仅为原文本的1/3。
  2. **Token Masking**：为避免模型忽略文本图像，在训练时以一定概率屏蔽原始图像token，迫使模型从文本图像中学习文本语义。
  3. **文本中心对比学习（TCCL, Text-Centric Contrastive Loss）**：将文本图像经过视觉编码器+重采样器后的特征与文本分词器提取的文本特征进行对比对齐，公式为：
     \[
     L_{ij} = -\log \frac{\exp(\text{sim}(f_v^i, f_t^j)/\tau)}{\sum_{k=1}^N \exp(\text{sim}(f_v^i, f_t^k)/\tau)}
     \]
     其中 \(f_v^i\) 为第i个文本图像的特征，\(f_t^j\) 为第j个文本的特征，通过平均池化后计算余弦相似度，\(\tau\) 为温度参数。
  4. **整体流程**：原始图像和文本渲染图像共享一个冻结的视觉编码器（如ViT-L/16），分别通过两个可学习的重采样器提取固定数量的token，然后与文本token拼接输入LLM。训练时冻结语言模型和视觉编码器，仅训练门控交叉注意力层和重采样器。

## 3. 实验设计

- **数据集与场景**：
  - 预训练：180M数据子集，包括DataComp1B（108M）、MMC4（30M）、OBELICS（30M）、Rendered Text（12M）。
  - 下游评估：广泛的多模态少样本任务（OK-VQA, TextVQA, VizWiz, VQAv2, COCO Caption, Flickr30K, Hateful Memes）。
  - 文档理解：DocVQA、OCR VQA。
  - 新任务：序贯多模态检索（Sequential Multimodal Retrieval, SMR）——基于OBELICS文档，预测下一图像或文本。

- **基准方法**：
  - 主要基线：OpenFlamingo-9B（Mistral-7B为语言模型）、OpenFlamingo MoE（56B模型）、CosMo。
  - 扩展验证：FuYu-8B（仅用线性嵌入的MLLM）、不同LLM backbone（OPT-1.3B、MPT-7B、MoE-56B）。

- **评估指标**：VQA准确率、Caption指标（CIDEr/SPICE）、平均归一化Levenshtein相似度（ANLS）、OCR next-word准确率、检索Recall（Recall@1）。

## 4. 资源与算力

- 文中明确说明了算力配置：
  - 56B MoE模型使用4-bit量化、DeepSpeed ZeRO-2、CPU offloading、Flash Attention，训练于NVIDIA H100 GPU（80GB），每GPU batch size为32，FP16。
  - 较小模型（3B、9B）使用相同策略但无需CPU offloading。
  - 具体GPU数量未明确给出，但提到OpenFlamingo-9B基线需32×80GB A100 GPU超过3天；本文方法在相同算力下可扩展7倍上下文长度。
  - 预训练步骤：3B/9B模型200K steps，56B模型500K steps。

## 5. 实验数量与充分性

- **实验数量充足**：
  - 主实验：对比基线（表1、表2、表3），涵盖7个VQA/Caption数据集和文档理解任务。
  - 消融实验（表6）：分别验证文本图像、Token Masking、TCCL三个组件的贡献。
  - 超参数消融（表7、表8）：字体大小和间隔阈值。
  - 不同LLM backbone的扩展实验（附录表12）：OPT-1.3B、MPT-7B、MoE。
  - 不同模型架构的扩展（表5）：FuYu-8B。
  - 推理成本比较（图4）：展示上下文长度从1K扩展到9K。
  - 视觉编码器是否可学习的实验（附录表13）。
- **公平性**：所有对比均在相同的预训练数据子集（180M）、相同steps下进行，基线为作者自己实现的OpenFlamingo，避免不公平比较。

## 6. 论文的主要结论与发现

1. VisInContext可将预训练上下文文本长度从256扩展到2048 token，而FLOPs几乎不变，GPU内存显著降低。
2. 在56B MoE模型上，32-shot平均性能从55.8%提升至57.8%，尤其TextVQA从23.2%提升至31.2%。
3. 文本渲染为图像后，模型OCR能力大幅提升（next-word预测top-1 accuracy从67.37%提升至85.25%）。
4. 在文档理解（DocVQA、OCR VQA）上，VisInContext优于基线（DocVQA提升3.2%，OCR VQA提升6.9%）。
5. 序贯多模态检索任务中，使用渲染文本图像作为周围文本输入，检索下一图像的性能显著优于直接使用原始文本。
6. 推理阶段可处理长达9192 token的上下文（56B MoE, 80GB H100），远超基线。
7. TCCL和Token Masking是关键组件，缺一不可。

## 7. 优点

- **创新性**：首次利用视觉token压缩文本上下文，思路新颖，不同于传统的注意力优化或记忆库方法。
- **效率高**：将计算从LLM侧转移到轻量视觉编码器，大幅降低GPU内存和FLOPs，且与现有方法互补（可结合Ring Attention等）。
- **实验充分**：覆盖多种模型规模（3B、9B、56B）、多种LLM backbone、多种下游任务，消融实验完整。
- **可复现**：代码已开源，预训练数据使用公开数据集，超参数详细附录。
- **实用性**：对文档理解、OCR任务有显著提升，且可扩展至仅用线性嵌入的MLLM（如FuYu）。

## 8. 不足与局限

- **文本渲染固定大小**：即使短文本也需渲染为固定大小图像（16×8192），造成一定冗余。作者计划未来动态调整图像大小，仅保留非空patch。
- **实验覆盖率**：未在更大规模（如LLaVA类指令微调模型）和更多样化任务（如图表理解、多页文档）上进行验证。新任务SMR仅基于1K样本，规模较小。
- **偏差风险**：渲染字体为HERSHEY，可能与真实文档字体分布不一致；视觉编码器对旋转、扭曲等复杂文本场景的鲁棒性未讨论。
- **训练稳定性**：若将视觉编码器设可学习，性能虽进一步提升（DocVQA +1.9%），但训练不稳定且需更多迭代，分类任务反而下降。
- **与SOTA对比缺失**：本文明确表示不追求SOTA，是一种探索性工作，但未与现有长上下文方法（如Ring Attention、Unlimiformer）进行直接对比。

（完）
