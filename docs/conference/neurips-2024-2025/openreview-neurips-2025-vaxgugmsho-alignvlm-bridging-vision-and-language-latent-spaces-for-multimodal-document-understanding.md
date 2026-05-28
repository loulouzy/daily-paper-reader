---
title: "AlignVLM: Bridging Vision and Language Latent Spaces for Multimodal Document Understanding"
title_zh: "AlignVLM: 弥合视觉与语言潜在空间的多模态文档理解"
authors: "Ahmed Masry, Juan A. Rodriguez, Tianyu Zhang, Suyuchen Wang, Chao Wang, Aarash Feizi, Akshay Kalkunte Suresh, Abhay Puri, Xiangru Jian, Pierre-Andre Noel, Sathwik Tejaswi Madhusudhan, Marco Pedersoli, Bang Liu, Nicolas Chapados, Yoshua Bengio, Enamul Hoque, Christopher Pal, Issam H. Laradji, David Vazquez, Perouz Taslakian, Spandana Gella, Sai Rajeswar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vAxGuGmshO"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型论文
tldr: 针对视觉语言模型中视觉与语言特征对齐难的问题，AlignVLM提出将视觉特征映射到LLM文本嵌入的加权平均，利用语言先验约束视觉特征，实现了更优的跨模态对齐，在多模态文档理解任务上表现更佳。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 738, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 685, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 696, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1323, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1461, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 426, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 432, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 428, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 439, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 498, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 497, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 497, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 499, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 567, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 563, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 567, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 568, \"height\": 558, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 1082, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1325, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1026, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1331, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1387, \"height\": 258, \"label\": \"Table\"}]"
motivation: 现有视觉-语言连接器缺乏归纳偏置，导致跨模态对齐数据需求大且易错位。
method: 将视觉特征映射为LLM文本嵌入的加权平均，利用语言先验约束视觉特征。
result: 在多模态文档理解任务上优于传统MLP连接器，对齐更高效。
conclusion: 该方法有效利用语言结构先验，提升了视觉-语言模型的性能和数据效率。
---

## Abstract
Aligning visual features with language embeddings is a key challenge in vision-language models (VLMs). The performance of such models hinges on having a good connector that maps visual features generated by a vision encoder to a shared embedding space with the LLM while preserving semantic similarity. Existing connectors, such as multilayer perceptrons (MLPs), lack inductive bias to constrain visual features within the linguistic structure of the LLM’s embedding space, making them data-hungry and prone to cross-modal misalignment. In this work, we propose a novel vision-text alignment method, AlignVLM, that maps visual features to a weighted average of LLM text embeddings. Our approach leverages the linguistic priors encoded by the LLM to ensure that visual features are mapped to regions of the space that the LLM can effectively interpret. AlignVLM is particularly effective for document understanding tasks, where visual and textual modalities are highly correlated. Our extensive experiments show that AlignVLM achieves state-of-the-art performance compared to prior alignment methods, with larger gains on document understanding and under low-resource setups. We provide further analysis demonstrating its efficiency and robustness to noise.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉语言模型（VLM）中，如何将视觉编码器产生的连续特征有效映射到大语言模型（LLM）的文本嵌入空间是一个关键挑战。现有连接器（如MLP、Perceiver Resampler、Ovis等）缺乏归纳偏置，导致投影后的视觉特征可能偏离LLM预训练文本嵌入的分布区域，产生噪声或错位表示，且数据效率低，尤其在低资源场景下表现不佳。
- **整体含义**：AlignVLM提出一种新的连接器，通过将视觉特征强制约束在LLM文本嵌入的凸包内，利用语言先验提升跨模态对齐质量，从而在文档理解等模态高度相关的任务上取得更优性能，同时数据效率更高、鲁棒性更强。

## 2. 方法论

- **核心思想**：将视觉特征映射为LLM现有预训练词汇嵌入的**加权平均（凸组合）**，而不是直接做线性或非线性投影。这样每个视觉特征都位于LLM文本嵌入的凸包内，确保LLM能有效解释。
- **关键技术细节**：
  - **模型架构**：视觉编码器（SigLip-400M）提取图像块特征 → Align模块 → LLM（Llama 3.2-1B/3B、Llama 3.1-8B）。
  - **Align模块流程**：
    1. 线性层W1将视觉特征投影到LLM嵌入维度D。
    2. 线性层W2（初始化为LLM的语言模型头权重）加LayerNorm和softmax，得到词汇表上的概率分布 \( P_{\text{vocab}} \in \mathbb{R}^V \)。
    3. 用LLM文本嵌入矩阵 \( E_{\text{text}} \) 计算加权和：\( F'_{\text{align}} = P_{\text{vocab}}^\top E_{\text{text}} \)。
    4. 将 \( F'_{\text{align}} \) 与文本嵌入拼接后输入LLM。
  - **训练三阶段**：
    - Stage 1：在CC-12M（8.1M图像-文本对）上训练Align模块（全模型训练）。
    - Stage 2：在BigDocs-7.5M（文档理解数据集）上增强文档理解能力（全模型训练）。
    - Stage 3：在DocDownstream指令微调数据集上微调，冻结视觉编码器，仅训练LLM和Align模块。

## 3. 实验设计

- **数据集/场景**：
  - **文档理解基准**：DocVQA、InfoVQA、DeepForm、KLC、WTQ、TabFact、ChartQA、TextVQA、TableVQA。
  - **低资源场景**：LLaVA-NeXT数据集（779K样本），额外使用MMMU、SeedBench、MMVet、POPE、GQA评估通用视觉任务。
  - **特殊任务**：VCR（视觉字幕恢复，像素级OCR任务）。
- **对比方法**：
  - **浅层融合连接器**：MLP、Perceiver Resampler、Ovis、H-Reducer、HoneyBee。
  - **Base VLM（相同训练数据）**：Qwen2-VL-2B、DocOwl1.5-8B、Llama3.2-11B。
  - **Instruct VLM（开源/闭源）**：Claude-3.5、GeminiPro-1.5、GPT-4o、Qwen2/2.5-VL系列、InternVL系列、Phi3.5-Vision、LLaVA-NeXT、Pixtral-12B等。
- **公平性**：所有Baseline（MLP、Perceiver等）在相同数据集、相同训练配置下训练；Base VLM对比确保训练数据一致。

## 4. 资源与算力

- 论文明确说明：使用 **8 节点 H100 GPU（共64张H100）** 进行全部实验。
- 训练使用MS-Swift框架和DeepSpeed ZeRO-3优化。
- 具体训练时长未报告（但Stage 1、2、3各1 epoch，可推算总时间）。
- 附录给出了各阶段的batch size、学习率、文本最大长度等超参数。

## 5. 实验数量与充分性

- **主要实验**：在9个文档理解基准上评估AlignVLM与多个SOTA模型对比（表1），包含1B/3B/8B三种尺寸。
- **连接器对比实验**：在**高资源**（BigDocs-7.5M，表2）和**低资源**（LLaVA-NeXT，表3）两个设置下，对比MLP、Perceiver、Ovis、H-Reducer、HoneyBee五种连接器。
- **消融与分析**：
  - 概率分布分析（图3、图4）：发现仅需约3.4K高概率嵌入，性能几乎不变（表4）。
  - 鲁棒性测试（表5）：加入高斯噪声后，Align仅下降1.67%，而MLP下降25.54%。
  - 像素级任务VCR实验（图5、图6）：对比MLP，硬任务提升10.18%，软任务提升14.41%。
  - 运行时效率对比（附录A.2，表7）：Align推理速度和内存占用与MLP/Ovis相当。
- **充分性**：实验覆盖了不同尺寸LLM、不同数据量、多种连接器、噪声鲁棒性、像素级任务，对比了多种SOTA模型，设计较为全面和客观。但未报告多次运行的标准差（受计算资源限制）。

## 6. 主要结论与发现

- **性能领先**：AlignVLM在所有文档理解基准上超越相同训练数据的Base VLM（如Qwen2-VL-2B、DocOwl1.5-8B、Llama3.2-11B），平均得分最高。
- **低资源更强**：在LLaVA-NeXT（779K样本）下，Align相比其他连接器的性能差距更大（如DocVQA：71.43 vs MLP 42.11），验证了其数据效率。
- **鲁棒性优异**：加入噪声后性能几乎不变，而MLP严重退化，表明凸包约束起到了正则化作用。
- **紧凑子集**：只需约3.4K高概率词汇嵌入即可保持性能，可优化计算效率。
- **跨模态对齐的本质**：Align通过语言先验强制视觉特征落在文本嵌入凸包内，避免了OOD投影，这是其成功的关键。

## 7. 优点

1. **方法创新性**：首次将视觉特征映射为LLM词汇嵌入的加权平均，利用语言先验约束，简单而有效。
2. **数据效率高**：在低资源场景下优势显著，适合学术实验室或有限数据场景。
3. **鲁棒性强**：对噪声具有天然抗性，适用于实际脏数据场景。
4. **架构轻量**：仅增加一个LM head层，参数量和计算开销极小（与MLP相当）。
5. **公平实验**：所有Baseline在相同数据、相同训练配置下对比，结论可靠。
6. **全面分析**：提供了概率分布可视化、嵌入空间PCA、噪声测试、像素级任务等深入分析。

## 8. 不足与局限

1. **未见标准差/误差线**：实验未报告多次运行的标准差，由于计算资源昂贵，但其统计显著性可能存疑。
2. **适用范围有限**：论文主要聚焦于多模态文档理解（OCR、表格、图表等），未在更通用的视觉问答（如COCO、A-OKVQA）或图像描述任务上验证；附录低资源实验虽有通用基准，但主要结果仍以文档为主。
3. **对比SOTA的公平性**：与Qwen2.5-VL-7B等Instruct VLM相比，AlignVLM训练数据更少且未使用大规模专有数据集，但实际部署中这类模型可能更优。
4. **潜在偏差风险**：Align倾向于将视觉特征映射到更常见的词汇（如VCR实验中误将“Llanengan”猜为“Llanongan”），可能在处理稀有或特殊词汇时表现不佳。
5. **计算资源仍较高**：虽然比深融合方法轻量，但Stage 1/2仍需要64张H100训练全模型，对小型研究团队仍有门槛。
6. **未讨论失败模式**：论文未系统分析模型在何种情况下失效，仅给出少量案例（如VCR负例）。
7. **无理论证明**：方法虽直觉合理，但未给出凸包约束为何能保证对齐的理论分析或收敛性证明。

（完）
