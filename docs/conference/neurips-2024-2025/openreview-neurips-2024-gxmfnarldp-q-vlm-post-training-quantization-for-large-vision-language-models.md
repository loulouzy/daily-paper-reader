---
title: "Q-VLM: Post-training Quantization for Large Vision-Language Models"
title_zh: "Q-VLM: 大型视觉语言模型的训练后量化"
authors: "Changyuan Wang, Ziwei Wang, Xiuwei Xu, Yansong Tang, Jie Zhou, Jiwen Lu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=gxMfNArldP"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型量化方法
tldr: 大型视觉语言模型（LVLM）的多模态推理需要高效量化。传统量化方法逐层搜索舍入函数，忽略了跨层依赖性。本文提出Q-VLM，挖掘跨层依赖对离散化误差的影响，并嵌入到最优量化策略搜索中，以低搜索成本获得高质量量化方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 560, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 73, \"height\": 69, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 473, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 469, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 70, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gxmfnarldp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1411, \"height\": 500, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 982, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1412, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1463, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gxmfnarldp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1466, \"height\": 460, \"label\": \"Table\"}]"
motivation: LVLM部署需要高效量化，但逐层量化无法考虑跨层依赖，导致次优解。
method: 提出挖掘跨层依赖的量化框架，利用激活熵与输出误差的相关性引导搜索。
result: 实验表明Q-VLM在低比特率下保持模型精度，优于传统量化方法。
conclusion: Q-VLM实现了LVLM的高效量化，有助于边缘部署。
---

## Abstract
In this paper, we propose a post-training quantization framework of large vision-language models (LVLMs) for efficient multi-modal inference. Conventional quantization methods sequentially search the layer-wise rounding functions by minimizing activation discretization errors, which fails to acquire optimal quantization strategy without considering cross-layer dependency. On the contrary, we mine the cross-layer dependency that significantly influences discretization errors of the entire vision-language model, and embed this dependency into optimal quantization strategy searching with low search cost. Specifically, we observe the strong correlation between the activation entropy and the cross-layer dependency concerning output discretization errors. Therefore, we employ the entropy as the proxy to partition blocks optimally, which aims to achieve satisfying trade-offs between discretization errors and the search cost. Moreover, we optimize the visual encoder to disentangle the cross-layer dependency for fine-grained decomposition of search space, so that the search cost is further reduced without harming the quantization accuracy. Experimental results demonstrate that our method compresses the memory by 2.78x and increase generate speed by 1.44x about 13B LLaVA model without performance degradation on diverse multi-modal reasoning tasks.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
大型视觉语言模型（LVLMs）在多模态推理任务中表现出色，但庞大的参数量和存储开销严重阻碍了其在资源受限设备（如手机、机器人）上的部署。模型量化是有效的压缩加速手段，其中训练后量化（PTQ）因无需完整训练数据更实用。然而，现有PTQ方法（如AWQ、QLoRA）通常采用逐层贪心搜索舍入函数，忽略了层间离散化误差的**跨层依赖**，导致量化策略次优、模型性能严重下降。本文提出**Q-VLM**框架，通过挖掘并利用跨层依赖，以极低的搜索成本实现高精度量化，首次在W4A4位宽下保持LVLMs的竞争力。

## 2. 论文提出的方法论
### 核心思想
- **利用激活熵作为跨层依赖的代理**：观察到**离散化误差差异（DED）** 与激活熵之间存在强相关性（相关系数0.97），而DED与量化误差的相关性较弱（0.81）。因此，用熵衡量两层之间的依赖程度，熵越高表明依赖越强。
- **基于跨层依赖的块划分**：将整个模型划分为多个块，每个块内层间依赖强，从而联合搜索块内所有层的舍入函数，最小化块输出离散化误差。块划分公式：  
  \( B_i = \bigcup_{k=k_r}^{k_s} Q_k \) 当平均依赖 \( D(k_r,k_s) > (k_s-k_r)h_0 \)。
- **视觉编码器优化**：通过优化视觉编码器参数，降低激活熵并解耦跨层依赖，实现更细粒度的搜索空间分解，进一步减少搜索成本。优化目标：  
  \( L = L_{reg} + \lambda_1 L_{ent} + \lambda_2 L_{err} \)  
  其中 \( L_{ent} \) 为加权熵最小化，\( L_{err} \) 为视觉编码器和LVLM输出离散化误差。

### 关键技术细节
- 使用均匀量化，舍入函数通过选择最佳百分位（percentile）截断值来搜索。
- 校准集：随机64个视觉-语言对，batchsize=8，更新10个epoch。
- 块内最大层深度设为3（超参数调优确定）。

### 算法流程
1. 加载预训练LVLM，冻结参数。
2. 用校准集前向传播，计算各层激活熵及跨层依赖。
3. 根据熵阈值划分块（确保块内依赖强）。
4. 对每个块，联合搜索各层舍入函数（最小化块输出误差）。
5. 同时优化视觉编码器（最小化联合损失），重复步骤2-4直至收敛。
6. 使用得到的量化舍入函数进行推理。

## 3. 实验设计
### 数据集与场景
- **ScienceQA（SQA）**：多模态问答（主数据集）。
- **VizWiz**：盲人视觉问答。
- **VQA v2**：通用视觉问答。
- **Hateful Memes**：多模态仇恨言论检测（附录C）。

### Benchmark方法
- **AWQ**：激活感知权重量化（权重仅量化）。
- **QLoRA** + 激活PTQ（逐层搜索）。
- **ZeroQuant-V2**：动态逐Token量化。
- **RPTQ**：重排式激活量化。

### 实验设置
- 模型：LLaVA-7B/13B、MoE-LLaVA-1.6B、OpenFlamingo-3B。
- 位宽：W8A8、W6A6、W4A4。
- 评价指标：Top-1准确率、搜索时间、推理内存。

## 4. 资源与算力
- 文中未明确列出GPU型号与数量，但在附录提及使用**RTX 3090**。
- 搜索成本：LLaVA-7B W4A4下搜索时间约24.6（单位未明确，推测为分钟或小时），低于AWQ和QLoRA。
- 推理内存：LLaVA-13B W4A4下从24.0G降至9.6G，推理时间从12.9h降至8.9h（表4）。
- 总体资源需求较低，适合单卡实验。

## 5. 实验数量与充分性
- **多模型对比**：LLaVA-7B/13B、MoE-LLaVA、OpenFlamingo，共4种架构。
- **多数据集**：SQA、VizWiz、VQA v2、Hateful Memes，共4个数据集。
- **多量化位宽**：W8A8、W6A6、W4A4。
- **消融实验**：最大层深度、不同代理（熵 vs 量化误差）、超参数p和η、各模块贡献（CDM、VEO）。
- **定性分析**：可视化推理示例（图4）。
- **充分性评价**：实验设计全面，覆盖主流LVLM架构和常见VQA任务，对比了多个SOTA方法。公平性：采用官方代码和默认设置。但未在更大模型（如LLaVA-34B）或不同模态（如视频）上验证，跨领域泛化性有限。

## 6. 论文的主要结论与发现
- Q-VLM在W4A4下显著优于现有方法：LLaVA-7B SQA准确率79.79%（比QLoRA提升2.26%），LLaVA-13B达80.78%。
- 压缩效果：13B模型内存降低**2.78倍**，推理速度提升**1.44倍**。
- 激活熵作为跨层依赖代理高效且准确，搜索成本仅为量化误差代理的一半且性能更好。
- 视觉编码器优化进一步降低搜索开销，无需牺牲精度。

## 7. 优点
- **创新性**：首次将跨层依赖引入LVLM量化，利用激活熵代理实现高效块划分，思路新颖且理论依据充分。
- **效率**：搜索成本低（仅需少量校准样本和短时间），实际部署友好。
- **性能**：在极低比特（W4A4）下保持与全精度模型接近的性能，超越多个SOTA。
- **通用性**：在多种LVLM架构（LLaVA、MoE-LLaVA、OpenFlamingo）和数据集上均有效。
- **可复现性**：代码开源（GitHub链接），实验设置详细。

## 8. 不足与局限
- **极端低比特限制**：W4A4下仍有性能下降，尤其是对容量更小的模型（如MoE-LLaVA-1.6B），无法做到无损。
- **模型架构依赖**：核心设计针对LLaVA-like架构（视觉编码器+LLM），未验证是否适用于编码器-解码器结构（如Flamingo）或其他视觉骨干（如ViT-G）。
- **校准集敏感性**：依赖随机选择的64个样本，可能受数据分布影响，文中未进行多次实验统计误差。
- **超参数调优**：涉及多个超参数（p、η、λ1、λ2、块深度、最大层数），不同模型需手动调整，缺乏自适应策略。
- **硬件部署验证**：仅给出了内存和速度的理论减少，未在真实移动设备（如手机、嵌入式系统）上进行实际部署测试。
- **未考虑权值-激活联合优化**：视觉编码器优化仅在视觉部分，语言模型部分仍沿用逐块搜索，可能未完全挖掘联合优化潜力。

（完）
