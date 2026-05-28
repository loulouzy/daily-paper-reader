---
title: "Lua-LLM: Learning Unstructured-Sparsity Allocation for Large Language Models"
title_zh: Lua-LLM：学习大型语言模型的非结构化稀疏分配
authors: "Mingge Lu, Jingwei Sun, Junqing Lin, Zechun Zhou, Guangzhong Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CA1xVSvn72"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 实验室的大语言模型研究：非结构化剪枝分配
tldr: 大规模语言模型（LLM）虽然能力强大，但参数量巨大带来部署挑战。现有逐层剪枝方法需要合适的稀疏度分配且易次优。本文提出Lua-LLM，一种基于学习的全局非结构化剪枝分配方法，通过自动学习每个层的稀疏度分配来优化整体模型。实验表明该方法在保持性能的同时显著减少模型大小。这项工作为LLM高效部署提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 588, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 457, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 455, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 454, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1421, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 696, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1389, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ca1xvsvn72/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 694, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 625, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 773, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 718, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 675, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 685, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1009, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1152, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 573, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1437, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1436, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1155, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 870, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1014, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ca1xvsvn72/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 581, \"height\": 349, \"label\": \"Table\"}]"
motivation: 现有LLM剪枝方法采用逐层策略，需要手动分配稀疏度，容易导致整体次优解。
method: 提出Lua-LLM，基于学习的全局剪枝框架，自动学习每层非结构化稀疏分配。
result: 在多个LLM上验证，剪枝后模型性能损失小且压缩率高。
conclusion: Lua-LLM实现了全局最优的稀疏分配，提升了LLM部署效率。
---

## Abstract
Large Language Models (LLMs) have demonstrated remarkable capabilities, yet their extensive parameter scales pose significant challenges for practical deployment. Unstructured pruning has emerged as an effective model compression strategy with minimal performance loss, which introduces fine-grained sparsity for weight parameters. While existing methods employ a layer-wise pruning strategy to avoid the complexity of global pruning for billion-scale LLMs, they require appropriate sparsity allocation for the layer-wise pruning objectives and often lead to suboptimal solutions for the overall model. In this paper, we propose Lua-LLM ($\textbf{L}$earning $\textbf{u}$nstructured-sparsity $\textbf{a}$llocation in LLMs), a learning-based global pruning framework that explores the optimal unstructured sparsity allocation. Unlike existing pruning methods, which primarily focus on allocating per-layer sparsity, Lua-LLM achieves flexible allocation for both layer-wise and intra-layer sparsity. Furthermore, Lua-LLM leverages a soft Top-K operator to approximate the importance-based mask selection mechanism, enabling efficient binary mask learning. Experimental results on LLaMA and OPT families demonstrate significant performance improvements over existing methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：大型语言模型（LLM）参数量巨大，部署时面临显存和计算瓶颈。非结构化剪枝通过移除不重要的单个权重，可在最小性能损失下实现模型压缩。
- **现有方法不足**：现有方法（如 SparseGPT、Wanda）采用逐层剪枝策略，需要在各层手动分配稀疏度（sparsity ratio）。这种逐层分配往往忽略层内（intra-layer）重要性差异，且依赖启发式指标，导致整体性能次优。尤其在高稀疏度下（如 70%–80%），均匀分配或简单启发式方法引发严重性能退化。
- **核心问题**：如何自动地为 LLM 的每个权重行（row）学习最优的稀疏度分配，从而在全局上最小化模型损失。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程（用文字说明即可）

- **核心思想**：将全局剪枝问题分解为逐行（row-wise）的子问题，每行通过一个可学习的阈值参数控制剪枝比例，并使用 soft Top‑K 算子使掩码选择可微，从而实现端到端的梯度优化。
- **关键技术细节**：
  1. **重要性度量**：沿用 Wanda 的度量：`S_ij = |W_ij| * ||X_:,j||_2`（权重绝对值 × 输入激活列范数）。
  2. **逐行掩码生成**：对每一行权重，根据重要性分数 `s` 和阈值 `t` 进行 Top‑K 选择（K = (1-p)*C_in）。原始选择函数（阶跃函数）不可微，用 Sigmoid 近似：`m̃_i = σ(λ(s_i - t))`，λ 设为通道数以保证近似精确。
  3. **阈值学习**：每行一个可学习参数 `t`，初始化为目标稀疏度。整体训练时冻结原始权重，仅更新阈值参数，损失函数为语言建模交叉熵 + 稀疏正则化项（控制全局稀疏度）。
  4. **算法流程**：（见 Algorithm 1）先统一初始化阈值，然后迭代前向计算、反向传播更新阈值，最后根据学习到的阈值生成二进制硬掩码进行剪枝。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - 训练数据：C4 数据集（2048 token 片段）。
  - 评估：WikiText-2 验证集（语言建模困惑度），以及 7 个零样本下游任务（BoolQ、PIQA、HellaSwag、WinoGrande、ARC‑easy、ARC‑challenge、OpenbookQA）。
- **Benchmark**：
  - 模型：LLaMA‑7B/13B、LLaMA‑2‑7B/13B、LLaMA‑3‑8B、OPT‑6.7B/13B。
  - 稀疏度：50%、60%、70%、80%。
- **对比方法**：
  - 均匀剪枝：Wanda。
  - 自适应层稀疏分配：OWL、DSA、AlphaPruning、ATP。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **训练资源**：
  - LLaMA‑7B 模型：约 1 小时，使用 2 × NVIDIA A100 80GB GPU。
  - LLaMA‑13B 模型：约 2 小时，使用 4 × NVIDIA A100。
  - OPT‑6.7B/7B/8B 等类似规模：42–60 分钟，2 × A100。
- **推断加速测试**：在单张 NVIDIA A100 80GB GPU 上使用 SpInfer 框架测量吞吐量。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **主要实验**：
  - 语言建模困惑度（Table 1）：覆盖 7 个模型 × 4 个稀疏度 × 3 个基线（Wanda/OWL/DSA），共 84 组结果。
  - 零样本下游任务（Table 2, 11, 12）：在 LLaMA‑7B/2‑7B/3‑8B 上测试 60%、70%、80% 三个稀疏度，对比 Wanda、OWL、DSA、ATP，每组 7 个任务。
  - 与 AlphaPruning、ATP 的对比（Table 3）：在 LLaMA‑7B 和 LLaMA‑2‑7B 上 70% 和 80% 稀疏度。
  - MMLU 5-shot 评估（Table 13）：覆盖 LLaMA‑7/13B 和 LLaMA‑2‑7/13B，50%–70% 稀疏度。
  - 推断加速测试（Table 4, 9）：OPT‑6.7B/13B 在 50%–70% 稀疏度下与 dense 模型对比。
- **消融实验**：
  - 剪枝粒度（Table 7）：对比行、列、层级别，验证行级最优。
  - 训练数据规模与域（Table 8）：使用不同样本数和 WikiText103 对比，显示鲁棒性。
  - 初始化策略对收敛的影响（Figure 5）。
  - 正则化系数 λ_reg 的影响（Table 6）。
  - 重要性度量比较（Figure 6）：Magnitude、Wanda、Pruner‑Zero。
  - 与 SparseGPT 结合（Table 14）：将 Lua‑LLM 的稀疏分配用于 SparseGPT。
  - 与 LoRA 微调结合（Table 15, 16）。
- **充分性与公平性**：实验覆盖了多种模型族（LLaMA、OPT）、多个稀疏度、多种下游任务，并进行了充分的消融。对比基线均为公开的最先进方法，且结果均在同一设置下重新运行（如使用 EleutherAI LM‑Eval‑Harness 评估），保证了公平性。

### 6. 论文的主要结论与发现

- Lua‑LLM 在所有模型和稀疏度下均显著优于均匀剪枝（Wanda）及其他自适应方法（OWL、DSA、AlphaPruning、ATP）。例如，在 LLaMA‑3‑8B 上 70% 稀疏度时，困惑度降低 99.5（vs. Wanda）、67.29（vs. OWL）、79.14（vs. DSA）。
- 高稀疏度下优势更明显：在 80% 稀疏度时，Lua‑LLM 在 LLaMA‑2‑7B 上困惑度仅 30.27，远低于 AlphaPruning（698.56）和 ATP（176.80）。
- 学习到的稀疏分配呈现层间递增趋势（但首层和末层有特殊模式），且层内不同通道稀疏度差异显著，说明自适应分配的必要性。
- Lua‑LLM 可结合 LoRA 微调或 SparseGPT 进一步提升性能，具有良好兼容性。

### 7. 优点：方法或实验设计上有哪些亮点。

- **方法论亮点**：
  - 将全局非结构化剪枝转化为逐行可学习的阈值参数，参数量极少（每行一个标量），效率高。
  - 使用 soft Top‑K 近似实现二值掩码的可微学习，避免离散优化困难。
  - 初始化策略（统一初始化为目标稀疏度）有效加速收敛并继承 Wanda 的优良先验。
- **实验设计亮点**：
  - 覆盖多种模型族（LLaMA‑1/2/3、OPT）、多种稀疏度、多种任务，结果全面且有说服力。
  - 包含与加速框架 SpInfer 的结合测试，验证了实际推理加速（1.18×–1.73×）。
  - 消融实验完整，验证了剪枝粒度、训练数据、正则化、重要性度量等设计选择的有效性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等。

- **计算资源**：虽然已比 DSA 等进化算法高效，但仍需 GPU 训练（数百次迭代），相比一次性剪枝（如 Wanda）更耗时。
- **推理加速**：非结构化稀疏模式需要特定 GPU 推理框架（如 SpInfer）才能取得实际加速，且 SpInfer 在预填充阶段 batch 和序列长度较大时仍有较高内存开销。
- **实验覆盖**：
  - 未在更大规模模型（如 30B+ 或 70B）上验证，训练成本可能显著增加。
  - 未在编码器模型（如 BERT）或非自回归模型上测试，通用性有限。
  - 仅使用单一训练数据集（C4），尽管做了跨域消融，但未探索多轮对话或代码等任务。
- **理论支撑**：重要性度量沿用 Wanda 的启发式指标，未提供理论保证；soft Top‑K 的参数 λ 设为通道数，缺乏自适应调节机制。

（完）
