---
title: Search for Efficient Large Language Models
title_zh: 搜索高效大语言模型
authors: "Xuan Shen, Pu Zhao, Yifan Gong, Zhenglun Kong, Zheng Zhan, Yushu Wu, Ming Lin, Chao Wu, Xue Lin, Yanzhi Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=lxSmLxlVks"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 提出训练无关的架构搜索以获取高效大语言模型
tldr: 该论文关注大语言模型的效率问题，指出现有压缩技术主要优化权重而非架构。作者提出一种无需训练的架构搜索框架，能够从原始LLM中找到保留核心优势的最优子网络，同时降低内存和加速推理。该方法避免了传统架构搜索的高计算消耗，为设计高效LLM提供了新思路。实验证明，搜索得到的子网络在多项任务上保持与原模型相当的性能。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 732, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 680, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 707, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 716, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 719, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lxsmlxlvks/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 723, \"height\": 557, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 1051, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 646, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 786, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 812, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1158, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lxsmlxlvks/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 809, \"height\": 276, \"label\": \"Table\"}]"
motivation: 现有LLM压缩技术侧重权重优化，忽略了架构搜索的潜力。
method: 提出无需训练的架构搜索框架，通过识别最优子网络保持模型性能。
result: 搜索得到的子网络在保持性能的同时显著降低计算开销。
conclusion: 架构搜索是提升LLM效率的有效且低成本的途径。
---

## Abstract
Large Language Models (LLMs) have long held sway in the realms of artificial intelligence research.
Numerous efficient techniques, including weight pruning, quantization, and distillation, have been embraced to compress LLMs, targeting memory reduction and inference acceleration, which underscore the redundancy  in LLMs.
However, most model compression techniques concentrate on weight optimization, overlooking the exploration of optimal architectures.
Besides, traditional architecture search methods, limited by the elevated complexity with extensive parameters, struggle to demonstrate their effectiveness on LLMs.
In this paper, we propose a training-free architecture search framework to identify optimal subnets that preserve the fundamental strengths of the original LLMs while achieving inference acceleration.
Furthermore, after generating subnets that inherit specific weights from the original LLMs, we introduce a reformation algorithm that utilizes the omitted weights to rectify the inherited weights  with a small amount of calibration data.
Compared with SOTA training-free structured pruning works that can generate smaller networks, our method demonstrates superior performance across standard benchmarks.
Furthermore, our generated subnets can directly reduce the usage of GPU memory and achieve inference acceleration.

---

## 论文详细总结（自动生成）

# 论文深度分析与总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究背景**：大语言模型（LLMs）在AI领域表现卓越，但其巨大的计算和存储成本限制了在资源受限设备上的部署。例如GPT-3（175B参数）在FP16格式下需要超过326GB内存，远超现有GPU。
- **现有方法的不足**：现有压缩技术（剪枝、量化、蒸馏）主要集中在权重优化，而忽略了模型架构的探索。传统神经网络架构搜索（NAS）方法因LLM参数规模巨大、训练成本过高而难以有效应用于LLM。
- **研究动机**：本文试图在预训练的LLM内部，通过无需训练的架构搜索找到最优子网络（subnet），在保持原模型核心能力的同时实现推理加速和内存减少。

## 2. 方法论（核心思想、关键技术细节）

### 核心思想
- 提出一个**无需训练的搜索框架**，在原始LLM中搜索高效子网络，并引入**重新形成算法（Reformation）**利用被省略的权重对继承的权重进行校准，进一步提升性能。

### 关键技术细节
1. **搜索初始化（Search Initialization）**
   - 首先基于权重重要性得分（WoodFisher方法，类似于SparseGPT）计算每个行/列的得分，公式如下：
     \[
     [\Phi^r_W]_i = \sum_j [\Phi]_{i,j},\quad [\Phi^c_W]_j = \sum_i [\Phi]_{i,j},\quad [\Phi]_{i,j} = \frac{[W]^2_{i,j}}{[(2XX^\top)^{-1}]_{j,j}}
     \]
   - 对自注意力模块和MLP模块分别构造选择掩码 \(S_{attn}\) 和 \(S_{mlp}\)，通过最小化重要性得分和选择要保留的行/列，获得初始子网络（所有层使用统一的继承比率）。

2. **架构搜索（Architecture Search）**
   - 采用**进化算法**，从初始子网络出发进行全局搜索。
   - **变异（Mutation）**：使用特殊的掩码变异算法（Algorithm 1），改变继承的行/列索引集合，同时保持继承比率和相似度约束。
   - **搜索空间**：包括模型深度 \(d\)、自注意力头继承比率 \(\Gamma_{attn}\) 和MLP继承比率 \(\gamma_{mlp}\)。注意MLP的搜索空间更大，因为MLP比自注意力冗余更多（图4证明了MLP对参数减少不敏感）。
   - **候选评估（Candidate Evaluation）**：使用少量WikiText2训练样本计算困惑度（perplexity）来快速筛选候选。
   - **初始化必要性**：实验证明，没有重要性初始化时，自注意力模块很难搜索到有效子网络（图5）。

3. **重新形成算法（Reformation）**
   - 在搜索得到子网络后，针对每一线性层，利用被剪掉的权重来校正继承的权重，最小化层输出差异（ℓ2范数）：
     \[
     \min_{\hat{W}} \|\hat{W}X - WX\|_2^2,\quad \text{s.t. } \hat{W} \odot M = 0
     \]
   - 采用**ADMM（交替方向乘子法）**迭代求解（Theorem 3.1），公式如下：
     \[
     \begin{aligned}
     \hat{W}^{k+1} &= (XX^\top + \rho I)^{-1}(XX^\top W^\top + \rho(Z^k - U^k)^\top)\\
     Z^{k+1} &= (\hat{W}^{k+1} + U^k) \odot M\\
     U^{k+1} &= U^k + \hat{W}^{k+1} - Z^{k+1}
     \end{aligned}
     \]
   - 只需约30次迭代即可收敛，仅需128个校准样本（WikiText2训练集），无需重新训练。

4. **高效推理**：将搜索得到的子网络转换为紧凑的稠密模型，实际减少参数量和内存占用。

## 3. 实验设计

### 数据集与Benchmark
- **语言建模**：WikiText2 和 PTB 数据集，序列长度2048（部分实验使用128）。
- **零样本分类**：BoolQ、PIQA、HellaSwag、WinoGrande、ARC-easy、ARC-challenge、OpenbookQA，共7个数据集，以平均准确率作为指标。

### 基线方法
- LLM-Pruner (v/e2/e1, c/b)
- SliceGPT
- FLAP
- 均遵循LLM-Pruner提供的统一评估pipeline以保证公平。

### 模型系列
- LLaMA (7B, 13B, 30B, 65B)
- Vicuna (7B)
- OPT (125M, 1.3B, 2.7B)

### 实验设置
- 进化搜索参数：种群大小N=100，变异数Nm=50，交叉数Nc=30，每代保留top 10。
- 变异概率：初始P_m=0.6, P_s=0.3；后续P_m=0.3, P_s=0.1；深度变异概率P_d=0.1。
- 相似度阈值α=0.8，最大迭代η=1000，总进化代数=50。
- 重新形成：ρ=1.0，迭代次数30，校准样本128（从WikiText2训练集随机抽取）。

## 4. 资源与算力

- 文中仅在LLaMA-7B的搜索中提到：在**单个NVIDIA A100 40GB GPU**上完成搜索，耗时约**5小时**。
- 对于其他模型（如LLaMA-13B、OPT等），未明确给出搜索时间，但推测类似或更长。
- 重新形成过程仅需前向传播和少量计算，不涉及重训练，GPU内存开销低。

## 5. 实验数量与充分性

- **主要实验**：在LLaMA-7B、13B上测试了90%、80%两种继承比率（以及70%、60%、50%等低比率），在Vicuna-7B、OPT-125M/1.3B/2.7B上测试了不同比率。
- **消融实验**：
  - 自注意力 vs MLP 的冗余性分析（图4）
  - 初始化必要性分析（图5）
  - 重新形成样本数量影响（图6：128, 512, 1024）
  - ADMM迭代步数（图A1）和ρ（图A2）的影响
  - 不同序列长度（128 vs 2048）的对比（表7、表A3）
  - 不同校准数据集（WikiText2 vs PTB）的搜索和评估（表A2）
  - 与SliceGPT使用不同校准数据的对比（表A1）
- **总体判断**：实验覆盖了多个模型（3个系列，7种规模）、多种继承比率、多种基准（困惑度和零样本分类），消融全面，对比公平。结论充分，实验设计严谨。

## 6. 主要结论与发现

- 提出的训练无关搜索框架能有效发现优于当前SOTA结构化剪枝方法的子网络。
- 在LLaMA-7B上，80%继承比率时，WikiText2困惑度6.89，显著优于LLM-Pruner（10.73）、SliceGPT（8.71）、FLAP（7.40）。
- 在更低的继承比率（50%）和更大的模型（30B、65B）上，本文方法依然保持最优或接近最优性能。
- 重新形成算法仅需128个样本即可有效提升子网络性能，且对样本数量不敏感。
- 搜索得到的子网络可实现实际的内存减少和推理加速（图7）。
- 该方法无需重训练，仅依赖前向传播，计算开销低。

## 7. 优点（方法或实验设计亮点）

- **无需训练**：整个搜索和重新形成过程仅需少量前向传播，避免了传统NAS的高昂训练成本。
- **架构搜索与权重优化结合**：不仅搜索最优架构，还利用被剪掉的权重通过ADMM校准，提升性能。
- **鲁棒且泛化**：在多个模型家族（LLaMA、Vicuna、OPT）、不同规模上均表现优异，且对校准数据集变化不敏感。
- **实用性强**：能直接转换为紧凑稠密模型，实现GPU内存减少和推理加速。
- **搜索空间设计合理**：基于冗余性分析（MLP比自注意力更冗余），设定不同大小的搜索空间，提高效率。
- **初始化策略有效**：重要性感知初始化显著加速搜索收敛（图5）。

## 8. 不足与局限

- **搜索成本随模型规模增加**：文中承认LLaMA-7B搜索需要约5小时，对于更大模型（如30B、65B）可能需要更多时间（未给出具体数据），限制了即时部署。
- **校准数据依赖**：虽然对样本数量不敏感，但仍需依赖少量校准数据（128个样本），且校准数据来源于WikiText2，可能存在领域偏差。
- **缺乏对多模态或非Transformer架构的验证**：实验仅覆盖了纯文本LLM（LLaMA、OPT、Vicuna），未扩展到多模态模型或不同架构（如Mamba）。
- **重新形成仅对列进行校正**：文中指出仅对继承的列（而非行）进行重构，因为被省略的行输出始终为零，可能限制了校正能力。
- **未讨论公平性、偏见或安全性影响**：没有评估子网络在敏感任务上的偏差或安全风险。
- **与某些基线（如SliceGPT）的比较中，校准数据集不同可能导致不公平**：但作者已通过附录C、D补充了不同设置下的对比，较为充分。

（完）
