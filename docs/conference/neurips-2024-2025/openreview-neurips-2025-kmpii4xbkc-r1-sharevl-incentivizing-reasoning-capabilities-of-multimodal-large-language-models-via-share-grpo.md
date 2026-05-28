---
title: "R1-ShareVL: Incentivizing Reasoning Capabilities of Multimodal Large Language Models via Share-GRPO"
title_zh: "R1-ShareVL: 通过Share-GRPO激励多模态大语言模型的推理能力"
authors: "Huanjin Yao, Qixiang Yin, Jingyi Zhang, Min Yang, Yibo Wang, Wenhao Wu, Fei Su, Li Shen, Minghui Qiu, Dacheng Tao, Jiaxing Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kMPII4XbKC"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态大语言模型推理的强化学习方法
tldr: 多模态大语言模型（MLLM）的推理能力可通过强化学习提升，但面临稀疏奖励和优势消失问题。本文提出Share-GRPO，通过数据变换扩展问题空间，鼓励MLLM探索不同推理路径，并在扩展问题间共享发现。该方法有效缓解了RL训练中的困难，显著提升了MLLM的推理性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 215, \"height\": 197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 217, \"height\": 196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 218, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 217, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 219, \"height\": 184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kmpii4xbkc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 224, \"height\": 269, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 797, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 778, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 950, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 570, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 527, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1416, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1143, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kmpii4xbkc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 760, \"height\": 125, \"label\": \"Table\"}]"
motivation: 现有RL方法在提升MLLM推理时遭遇稀疏奖励和优势消失，效果受限。
method: 提出Share-GRPO，扩展问题空间并共享推理轨迹，缓解稀疏奖励问题。
result: 在多个推理基准上，R1-ShareVL显著优于基线方法，推理能力提升明显。
conclusion: Share-GRPO为MLLM的RL推理优化提供了有效范式。
---

## Abstract
In this work, we aim to incentivize the reasoning ability of Multimodal Large Language Models (MLLMs) via reinforcement learning (RL) and develop an effective approach that mitigates the sparse reward and advantage vanishing issues during RL.  To this end, we propose Share-GRPO, a novel RL approach that tackle these issues by exploring and sharing diverse reasoning trajectories over expanded question space. Specifically, Share-GRPO first expands the question space for a given question via data transformation techniques, and then encourages MLLM to effectively explore diverse reasoning trajectories over the expanded question space and shares the discovered reasoning trajectories across the expanded questions during RL. In addition, Share-GRPO also shares reward information during advantage computation, which estimates solution advantages hierarchically across and within question variants, allowing more accurate estimation of relative advantages and improving the stability of policy training. Extensive evaluations over 6 widely-used reasoning benchmarks showcase the superior performance of our method. Code is available at https://github.com/HJYao00/R1-ShareVL.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，对《R1-ShareVL: Incentivizing Reasoning Capabilities of Multimodal Large Language Models via Share-GRPO》进行结构化、深入、客观的总结。

### **论文核心总结：R1-ShareVL**

---

#### **1. 核心问题与整体含义 (研究动机与背景)**

*   **研究动机**：近年来，基于强化学习（RL）的方法（如DeepSeek-R1中的GRPO）在提升大语言模型（LLM）的长链推理能力上取得了巨大成功。本研究旨在将类似理念应用于多模态大语言模型（MLLM），以激励其视觉推理能力。
*   **核心问题**：直接将适用于LLM的RL方法（如GRPO）应用于MLLM时，会遭遇两个关键挑战：
    *   **稀疏奖励 (Sparse Reward)**：尤其在训练早期，对于复杂问题，MLLM生成的推理路径中只有极少数能获得正向奖励，导致模型探索效率低下，训练不稳定。
    *   **优势消失 (Advantage Vanishing)**：当模型对一个问题生成一组同质化响应（例如，全部正确或全部错误），所有响应获得相同奖励时，相对优势会趋近于零，从而导致RL训练失效。
*   **整体含义**：本文提出了一种名为**Share-GRPO**的新颖RL框架，通过引入“信息共享”机制来有效缓解上述两个问题，从而更有效地激励MLLM的推理能力。

---

#### **2. 提出的方法论：Share-GRPO**

*   **核心思想**：通过扩展问题空间，让模型探索更多样化的推理轨迹，并在不同的问题变体间共享这些轨迹及其奖励信息，从而丰富奖励信号，稳定训练过程。
*   **关键技术细节**:
    1.  **推理空间扩展**：
        *   **问题空间扩展**：对每个原始问题 `Q = (Image, Text)`，应用“语义一致性变换 (SCT)”生成一组 `m` 个问题变体。
            *   **离线文本变换**：在RL训练前，使用GPT-4o对文本提示进行改写，生成语义等价的变体。
            *   **在线多模态变换**：在RL训练中，动态地对图像进行变换（如旋转、加噪声），并同步修改文本描述以保持一致，生成新的多模态变体。
        *   **解空间扩展**：将问题变体集合 `Q = {Q1, ..., Qm}` 输入到策略模型中，每个变体生成 `n` 个推理响应，从而得到一个更大、更多样化的解空间 `O = {{o1^Q1, ..., on^Q1}, ..., {o1^Qm, ..., on^Qm}}`。
    2.  **共享优势估计 (Shared Advantage Estimation)**：提出分层次的优势估计方法，在计算一个响应的优势时，同时考虑全局和局部信息：
        *   **全局层次**：将所有问题变体的所有响应的奖励聚合在一起，计算该响应的全局相对优势 `Â_{global}`。
        *   **局部层次**：仅基于当前问题变体自身生成的响应的奖励，计算该响应的局部相对优势 `Â_{local}`。
        *   **最终优势**：当响应由其自身所在的问题变体生成时，最终优势为全局与局部优势之和；当响应由其他问题变体生成（跨变体共享）时，最终优势仅使用全局优势。
    3.  **共享策略优化 (Shared Policy Optimization)**：在策略优化阶段，模型不仅使用自身生成的响应进行更新，还使用来自**其他问题变体**的响应进行更新，真正实现了“信息共享”。其优化目标函数如下（公式8）：
        `L(θ) = E_{Q~pD, o~π_θold(·|Q)} [ 1/n * Σ_i 1/m^2 * Σ_j Σ_k min( (π_θ(o_i^{Qj} | Qk) / π_θold(o_i^{Qj} | Qk)) * Â, clip(..., 1-ε, 1+ε) * Â ) ]`
        *   **关键解读**：此公式允许由问题变体 `Qj` 生成的响应 `o_i^{Qj}` 在另一个变体 `Qk` 上更新策略，从而最大化信息共享。

---

#### **3. 实验设计**

*   **使用的数据集/基准 (Benchmarks)**：论文在6个广泛使用的推理基准上进行了评估，涵盖数学和通用推理领域：
    *   **数学推理**：MathVista, MathVerse, MathVision
    *   **多学科/通用推理**：MMMU, MMStar, AI2D
*   **对比方法**：
    *   **基线模型**：Qwen2.5-VL-7B 和 Qwen2.5-VL-32B (论文的基础模型)
    *   **其他SOTA RL方法训练的MLLM**：OpenVLThinker-7B, MM-Eureka-7B/32B, ThinkLite-7B, R1-Onevision-7B, Vision-R1-7B 等。
    *   **闭源模型**：GPT-4o, Claude3.7-Sonnet, Kimi1.5。

---

#### **4. 资源与算力**

*   **算力详情**：
    *   **7B模型**：在 **8块 NVIDIA H100 GPU** 上进行训练。
    *   **32B模型**：在 **32块 NVIDIA H100 GPU** 上进行训练。
*   **其他细节**：训练使用EasyR1代码库，全局batch size为128，rollout batch size为512，学习率为1e-6。论文未明确说明具体训练时长，但提到共采样了52K多模态数据进行训练。

---

#### **5. 实验数量与充分性**

*   **实验数量**：实验非常充分。
    *   **主实验**：在6个基准上对比了10余种方法，涵盖了7B和32B两种模型尺寸。
    *   **消融实验**：系统地拆分了Share-GRPO的各个组件（离线/在线共享策略、全局/局部优势估计），共4组实验，验证了每个设计的贡献。
    *   **补充分析/讨论**：探讨了与动态采样方法的互补性 (4组对比)、问题变体数量 `m` 的敏感性 (3组)、采样数量 `N` 的影响 (5组对比)、与数据增强的对比 (5组)、以及与GRPO在所有基准上的扩展对比 (6组)。
*   **公平性与客观性**：
    *   **控制变量**：大部分对比使用了相同的基础模型(Qwen2.5-VL-7B/32B)，确保了对比的公平性。
    *   **SOTA对比**：提供了与多个公开报告结果的全面对比，结果定位清晰。
    *   **分析深入**：“与动态采样的互补性”和“与数据增强的对比”等实验，有力地证明了方法的核心贡献在于“信息共享”，而不仅仅是简单的输入增强。
*   **结论**：实验设计全面，覆盖了主效果验证、消融分析和深入讨论，充分且客观地证明了方法的有效性。

---

#### **6. 主要结论与发现**

1.  **有效性显著**：Share-GRPO能有效解决MLLM在RL训练中的稀疏奖励和优势消失问题，在6个推理基准上均取得了优于基线GRPO的结果。
2.  **性能全面领先**：所训练的R1-ShareVL-7B模型在大多数数学和多学科推理基准上超越了OpenVLThinker、MM-Eureka、ThinkLite等当前最佳的7B级RL训练MLLM。
3.  **泛化能力强**：在提升数学推理能力的同时，R1-ShareVL在通用的多学科基准（如MMMU, MMStar）上也能保持或提升性能，没有出现常见的退化现象。
4.  **可扩展性**：方法成功地从7B模型扩展到32B模型，性能进一步提升，证明了其可扩展性。
5.  **信息共享是核心**：消融实验证明，策略共享（增加轨迹多样性）和优势共享（更精确的梯度信号）是性能提升的关键，且二者互补。

---

#### **7. 优点**

1.  **问题定义精准**：敏锐地识别并指向了MLLM+RL领域的关键挑战——稀疏奖励和优势消失。
2.  **方法论创新优雅**：首次将“信息共享”概念系统性地引入MLLM推理RL框架，其核心思想清晰，技术方案（问题空间扩展+分层优势估计）直击痛点。
3.  **理论洞察与实验验证相结合**：不仅在引言和问题分析中清晰地阐述了问题，还通过丰富的实验（如Fig.1(b)的奖励和优势比曲线）和对比分析（如与动态采样的互补性）验证了其解决方案的有效性。
4.  **结果亮眼且泛化性好**：不仅在数学专项任务上达到SOTA，在保持甚至提升通用推理能力方面也表现突出，证明了方法本身的鲁棒性和价值。

---

#### **8. 不足与局限**

1.  **依赖外部模型**：离线文本变换依赖于GPT-4o，这可能引入额外的成本和潜在的生成质量问题（论文附录中也提及需过滤低质量样本）。这限制了方法的完全自主性。
2.  **变换策略的自动搜索**：当前的多模态变换策略（如旋转、噪声）是手动选择的。如何自动学习或搜索出对于推理最有效、最不会丢失关键信息的变换策略，是一个值得探索的方向。
3.  **计算成本增加**：扩展问题空间（生成 `m` 个变体）和增加采样数量（每个变体生成 `n` 个响应）不可避免地会增加RL训练的计算开销。虽然论文论证了该方法比单纯增加采样的效率更高，但其总成本仍高于基础GRPO。
4.  **潜在偏差**：经过变换后的问题可能引入一些未预料到的偏差或改变了原始问题的难度分布，尽管论文通过实验验证了其有效性，但理论上这种风险是存在的。
5.  **应用限制**：论文的实验主要聚焦于标准化的、有明确正确答案的推理基准上。对于需要开放性、创造性或主观判断的视觉任务（如艺术评价、创意文案生成），该方法的效果和适用性尚待验证。

（完）
