---
title: Embedding-Aligned Language Models
title_zh: 嵌入对齐的语言模型
authors: "Guy Tennenholtz, Yinlam Chow, ChihWei Hsu, Lior Shani, Yi Liang, Craig Boutilier"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=WSu1PPi2UP"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 使用RL训练LLM对齐潜在嵌入目标
tldr: 本文提出嵌入对齐的引导语言模型（EAGLE），利用强化学习将预训练大语言模型视为环境，训练智能体逐步引导生成朝向潜在嵌入空间中的最优区域。在MovieLens和Amazon数据集上展示了填补内容空白的能力。该方法为受控且符合特定目标的文本生成提供了新途径。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wsu1ppi2up/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wsu1ppi2up/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 335, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1170, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1227, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1118, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1111, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 492, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 763, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wsu1ppi2up/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 794, \"height\": 250, \"label\": \"Table\"}]"
motivation: 需要让LLM生成符合潜在嵌入空间定义的目标。
method: 将LLM作为环境，使用RL训练EAGLE智能体迭代引导生成。
result: 在推荐任务中有效发现并生成满足潜在需求的内容。
conclusion: RL方法可有效使LLM生成与嵌入目标对齐的文本。
---

## Abstract
We propose a novel approach for training large language models (LLMs) to adhere to objectives defined within a latent embedding space. Our method leverages reinforcement learning (RL), treating a pre-trained LLM as an environment. Our embedding-aligned guided language (EAGLE) agent is trained to iteratively steer the LLM's generation towards optimal regions of the latent embedding space, w.r.t. some predefined criterion. We demonstrate the effectiveness of the EAGLE agent using the MovieLens 25M and Amazon Review datasets to surface content gaps that satisfy latent user demand. We also demonstrate the benefit of using an optimal design of a state-dependent action set to improve EAGLE's efficiency. Our work paves the way for controlled and grounded text generation using LLMs, ensuring consistency with domain-specific knowledge and data representations.

---

## 论文详细总结（自动生成）

好的，基于您提供的论文内容，以下是对该论文的结构化、深入、客观的中文总结。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：如何让大型语言模型（LLM）的文本生成过程能够严格遵从特定领域内由**潜在嵌入空间**（latent embedding space）定义的目标或准则。例如，在推荐系统中，如何引导LLM生成一个能填补“内容空白”（content gap）、满足用户潜在需求但现实中不存在的电影情节描述。
- **研究背景**：
  - LLM（如Gemini、GPT）在通用文本生成上表现出色，但应用于专业领域时通常需要大量领域知识和人工标注数据。
  - 在许多领域（如推荐系统、图像分类、科学文献），领域知识已经以**潜在嵌入向量**（latent embeddings）的形态存在，且通常已预计算完毕，是一种现成的丰富知识源。
  - 然而，如何将这种向量化的目标（如“一个高用户效用的内容空白点”）有效地传递给LLM，并生成对应的自然语言（如电影情节），仍是一个挑战。
- **论文目标**：提出一个名为 **EAGLE（Embedding-Aligned Guided LanguagE）** 的通用框架，利用强化学习（RL）将预训练LLM作为环境，训练一个智能体（agent）来**迭代地引导LLM的生成，使其逐步逼近嵌入空间中的最优区域**，从而生成符合领域知识和数据表示的文本内容。

---

### 2. 论文提出的方法论

- **核心思想**：将LLM视为一个**环境（environment）**，EAGLE智能体通过选择“动作”（action，即修改文本的提示词）来改变当前实体描述（如电影情节）。每次修改后的新描述被编码为嵌入向量，然后根据预定义的效用函数（utility function）计算奖励，智能体通过RL优化策略，使得生成的描述最终落入嵌入空间中的高效用区域。
- **关键技术细节**：
  1.  **问题建模为马尔可夫决策过程（MDP）**：
      - **状态空间（S）**：所有可能的实体描述（如电影情节文本）。
      - **动作空间（A）**：用于修改实体描述的语言提示（action）。
      - **转移函数（P）**：由预训练LLM（环境）根据当前状态和动作生成下一个状态。
      - **奖励函数（r）**：定义为最终状态的效用函数值（\(r_{H-1} = U(E_D(x); D)\)），中间步奖励为0。
      - **初始状态**：从现有数据集D中选取一个实体（如一部已有电影）。
  2.  **动作空间设计**：
      - **利用LLM生成候选动作**：对每个初始实体，使用另一个LLM（如Gemini Ultra）生成K个候选动作（如修改情节、增强角色等），动作分为通用和个性化两种。
      - **G-最优设计（G-optimal design）**：为了在嵌入空间中高效探索并减少动作偏置，论文使用一个**参考策略**（reference policy）来引导训练。其中，G-最优设计是一种选择动作子集的方法，使所选动作的嵌入向量在子空间的协方差矩阵上具有最小的最坏情况方差，从而增强探索的覆盖面和效率。
  3.  **参考策略与RL训练**：
      - **参考策略参考策略**：使用监督学习在选定动作集上训练一个策略（基于Gemini Nano-2），作为RL训练的初始化和正则化项。
      - **RL训练**：使用策略梯度算法（如REINFORCE + GAE），损失函数包含原始PG损失和与参考策略的KL散度正则项，避免策略偏离太远。环境LLM（如Gemini Ultra）负责执行动作并生成新描述。
  4.  **编码器（Encoder）**：训练一个小型LLM（Gemini Nano-2）将实体描述映射到潜在嵌入空间（使用L2回归损失），用于计算效用函数。
- **算法流程**（Algorithm 1）：
  1.  为数据集D中每个实体生成K个候选动作。
  2.  对每个实体的动作集，计算近似的G-最优设计分布q(x)。
  3.  利用候选动作数据和G-最优设计训练参考策略πref。
  4.  使用参考策略、环境LLM、编码器和奖励函数，训练策略梯度算法（EAGLE agent）。

---

### 3. 实验设计

- **数据集与场景**：
  - **主要数据集**：**MovieLens 25M**（包含2500万条评分，62423部电影，162541个用户）。任务：为特定用户生成填补“内容空白”的电影描述。
  - **辅助数据集**：**Amazon Review**数据集中的“服装、鞋子和珠宝”子集（附录I）。任务：生成符合用户偏好的产品描述。
- **Benchmark与对比方法**：
  - **ELM（Embedding Language Model）**[Tennenholtz et al., 2024]：直接训练解码器从嵌入空间映射回文本，优化效用找到最优嵌入点，再解码。
  - **纯监督训练（参考策略）**：三种参考策略变体：均匀随机（Uniform）、乐观（Optimistic，选择单步效用最高的动作）、G-最优设计。
  - **EAGLE（本文方法）**：在上述三种参考策略基础上进行RL训练。
- **评估方法**：
  - **效用分数（Utility Score）**：基于电影嵌入与用户嵌入的点积，以及距离现有内容的L2距离，计算综合效用\(U(z; D) = \langle z_u, z_m \rangle + \lambda \sum \|z_m - z_{m'}\|\)。
  - **人类评分员评估**：124名评分员在不知道原始/生成版本的情况下，比较原始电影和EAGLE生成的电影。评估指标包括：用户效用（与给定用户画像的匹配度）、评分员自身效用（个人喜好）、距离分数（与原始电影的不同程度）。

---

### 4. 资源与算力

- **模型规模**：
  - EAGLE智能体（agent）和参考策略基于**Gemini Nano-2**（3.25B参数）。
  - 环境LLM使用**Gemini Ultra**或**Gemini Pro**（API调用）。
  - 编码器（encoder）同样基于Gemini Nano-2。
- **训练硬件**：EAGLE智能体训练在等效于**16块A100 GPU**的集群上并行进行。
- **训练时间**：每次EAGLE训练大约需要**5-7天**。
- **备注**：论文指出环境LLM可通过API调用，无需本地部署大型模型，但训练过程中的环境交互需要大量计算资源（使用了16个环境LLM实例同时交互）。

---

### 5. 实验数量与充分性

- **实验组数**：核心实验共8组表格结果（Table 2-4、Table 8），外加消融实验和条件分析。
  - **表2**：对比ELM、三种参考策略、以及在这些参考策略上训练的EAGLE变体（共7种方法）。
  - **表3**：环境迁移实验（训练/测试使用不同LLM组合，共4种配置）。
  - **表4**：动作空间消融实验（默认、无个性化、宏动作、组合动作，共4种配置）。
  - **附录I表8**：Amazon数据集上的AI评估结果（参考策略 vs EAGLE）。
  - **条件性能分析**：分别在低评分和高评分电影上评估EAGLE。
- **充分性与客观性**：
  - 实验覆盖了**核心方法的对比**（ELM vs EAGLE）、**动作空间设计的影响**（个性化、宏动作）、**环境泛化能力**（不同LLM环境）、**不同数据集**（MovieLens + Amazon）。
  - 评估采用**人类评分员**和**自动效用分数**相结合，且设计为**盲测**（评分员不知原始/生成版本），**公平性较好**。
  - 对比方法**ELM是现有方法**，参考策略变体作为消融基线，**对比合理**。
- **不足之处**：Amazon数据集实验仅在附录中给出，且使用AI模拟评分员（Gemini），缺乏真实人类评估。此外，实验主要针对推荐系统中的“内容空白”任务，对于其他应用场景（如图像描述、控制对话）的泛化能力未做验证。

---

### 6. 论文的主要结论与发现

1.  **EAGLE显著优于ELM**：在用户效用和评分员效用上，EAGLE（尤其是基于G-最优设计参考策略的版本）大幅超过ELM（例如表2：EAGLE G-最优设计U=0.74，ELM U=0.57）。这表明直接在嵌入空间中优化再解码的方法存在“离流形”（off-manifold）和泛化问题。
2.  **G-最优设计参考策略至关重要**：在三种参考策略中，G-最优设计在EAGLE框架下表现最佳，并产生更高的距离分数（生成的电影与原始电影差异更大），表明它有助于更高效地探索状态空间。
3.  **EAGLE具有环境迁移能力**：在Gemini Pro上训练的EAGLE可以成功应用于Gemini Ultra甚至GPT-4环境，性能保持甚至提升，表明其鲁棒性。
4.  **个性化动作起关键作用**：去除个性化动作后，EAGLE性能显著下降（表4：用户效用从0.76降至0.54）。
5.  **细粒度动作优于宏动作**：相比之下，使用单步动作（每次改一项）比使用宏动作（一次改五项）效果更好，结合两者（组合动作空间）效果更佳。
6.  **对低评分电影提升明显**：EAGLE在初始评分低的电影上平均效用提升约30%，而在已高评分电影上略有下降（平均降低5%），说明其有助于发现并改进不满意的内容。

---

### 7. 优点

- **方法创新性**：将RL与潜在嵌入空间对齐LLM生成，形成了一个无需解码器、仅需编码器的生成框架，规避了ELM的“离流形”泛化问题。
- **利用现成预训练LLM**：将强大LLM作为环境，无需训练大型模型，使EAGLE智能体可以用较小模型实现，降低了训练成本。
- **有效的动作空间设计**：利用LLM生成候选动作，并结合G-最优设计进行探索性选择，从理论上减少了动作偏置，提高了搜索效率。
- **全面的实验评估**：使用真实人类评分员进行盲测，评估指标多维（效用、用户匹配、差异度），结果可信度高。
- **环境泛化性好**：验证了EAGLE在不同环境LLM（Gemini Ultra、GPT-4）上的迁移能力，实用性较强。

---

### 8. 不足与局限

- **动作空间覆盖可能不完整**：EAGLE的性能受限于预定义动作集的质量和多样性。如果环境LLM无法通过当前动作集覆盖嵌入空间中的某些方向，EAGLE可能无法找到全局最优解（Sec. 7讨论了动作空间覆盖问题）。
- **计算成本依然较高**：RL训练需要与环境LLM进行大量交互（16个环境实例并行），训练周期长（5-7天），尽管智能体模型较小，但整体资源消耗依然可观。
- **人类评估有限**：Amazon数据集实验使用AI模拟人类反馈，缺乏真实人类判断。此外，评分员数量（124人）虽不算少，但任务单一（仅电影描述生成），可能存在主观偏差。
- **泛化测试不足**：实验仅限于文本领域的两个数据集（电影、商品描述），论文未验证在图像、视频、多模态等更广泛模态下的适用性。
- **潜在偏置与伦理风险**：论文在附录A中讨论了可能的偏置放大、操纵用户行为等社会风险，但未提出具体的缓解措施（如公平性约束、事实核查机制），仅进行了理论性讨论。
- **假设依赖于高质量动作生成**：本文假设可以通过LLM生成足够多样且有效的动作，但在某些专业领域（如医疗、法律）可能无法实现，需要专家介入，这限制了方法的自动化程度。

---

（完）
