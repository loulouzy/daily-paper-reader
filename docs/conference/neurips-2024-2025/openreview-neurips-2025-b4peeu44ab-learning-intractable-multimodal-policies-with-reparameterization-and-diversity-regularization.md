---
title: Learning Intractable Multimodal Policies with Reparameterization and Diversity Regularization
title_zh: 通过重参数化和多样性正则化学习难处理的多模态策略
authors: "Ziqi Wang, Jiashun Liu, Ling Pan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=b4pEeU44AB"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 多模态强化学习策略学习
tldr: 传统深度强化学习使用单一峰值或高斯策略，无法表达多模态决策分布，限制了在多样性关键任务中的表现。现有基于扩散或摊销的策略虽能表达多模态但难以优化。本文提出将现有难处理的多模态策略统一框架，并通过重参数化进行策略梯度优化，同时引入多样性正则化。实验表明该方法在性能和多样性之间取得良好平衡。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 448, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 487, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1460, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 874, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1416, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1436, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1413, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1412, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1413, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1412, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1412, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1413, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1442, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1441, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1284, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1283, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1436, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b4peeu44ab/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1442, \"height\": 894, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-b4peeu44ab/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-b4peeu44ab/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-b4peeu44ab/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1148, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-b4peeu44ab/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1401, \"height\": 178, \"label\": \"Table\"}]"
motivation: 现有RL算法无法表达复杂多模态决策分布，且现有方法在性能、多样性和效率间难以平衡。
method: 将难处理的多模态策略统一框架，用重参数化实现策略梯度优化，并加入多样性正则化。
result: 在连续控制任务上，该方法优于现有多模态RL方法，兼具高性能和策略多样性。
conclusion: 该方法为多模态RL策略学习提供了有效且高效的解决方案。
---

## Abstract
Traditional continuous deep reinforcement learning (RL) algorithms employ deterministic or unimodal Gaussian actors, which cannot express complex multimodal decision distributions. This limitation can hinder their performance in diversity-critical scenarios. There have been some attempts to design online multimodal RL algorithms based on diffusion or amortized actors. However, these actors are intractable, making existing methods struggle with balancing performance, decision diversity, and efficiency simultaneously. To overcome this challenge, we first reformulate existing intractable multimodal actors within a unified framework, and prove that they can be directly optimized by policy gradient via reparameterization. Then, we propose a distance-based diversity regularization that does not explicitly require decision probabilities. We identify two diversity-critical domains, namely multi-goal achieving and generative RL, to demonstrate the advantages of multimodal policies and our method, particularly in terms of few-shot robustness. In conventional MuJoCo benchmarks, our algorithm also shows competitive performance. Moreover, our experiments highlight that the amortized actor is a promising policy model class with strong multimodal expressivity and high performance.  Our code is available at https://github.com/PneuC/DrAC

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统连续深度强化学习（RL）算法采用确定性或单峰高斯策略，无法表达复杂的多模态决策分布。这在需要决策多样性的场景（如多目标导航、生成式RL）中严重限制了性能。
- **现有方法的困境**：已有一些基于扩散或摊销（amortized）策略的多模态在线RL算法，但这些策略是**难处理的**（intractable，即决策概率无闭式表达），导致现有方法难以同时兼顾性能、决策多样性和效率。
- **本文目标**：提出**多样性正则化的Actor-Critic（DrAC）**框架，通过重参数化技巧直接优化难处理的多模态策略，并引入不需要显式概率的距离多样性正则化，实现在多模态策略学习中的性能-多样性平衡。

## 2. 方法论

### 核心思想
- 将多模态策略统一为**随机映射actor**（stochastic-mapping actor）：\(\pi_\theta = \{f_\theta, p_z\}\)，其中 \(f_\theta\) 是参数化映射函数，\(p_z\) 是固定的潜变量分布。动作通过采样 \(z \sim p_z\) 并计算 \(a = f_\theta(s, z)\) 得到。
- 包含两类重要实例：**摊销actor**（直接连接s和z）和**扩散actor**（通过扩散过程生成动作）。

### 关键技术细节
- **重参数化策略梯度（PGRT）**：不需要策略概率密度，直接通过 \(\nabla_\theta J(\pi_\theta) = \mathbb{E}_{s,z}[\nabla_a Q(s, f_\theta(s,z)) \nabla_\theta f_\theta(s,z)]\) 计算梯度，可泛化到所有随机映射actor。
- **距离多样性正则化**：使用**几何平均对数距离** \(\tilde{\mathcal{D}}_\theta(s) = \frac{1}{n} \sum_{i=1}^n \log \delta(f_\theta(s, z^x_i), f_\theta(s, z^y_i))\)，避免平均距离对离群簇的过度估计，且无需概率表达式。
- **自动系数调整**：可学习的系数 \(\alpha\) 通过梯度下降匹配目标多样性 \(\hat{\mathcal{D}} = \log(\beta \sqrt{|\mathcal{A}|})\)，减少超参数调优成本。

### 算法流程（DrAC）
1. 从重放缓冲区采样状态转移 \((s,a,r,s')\)。
2. 从 \(p_z\) 采样多个潜变量，计算目标值 \(y = r + \gamma(\hat{Q}(s', f_\theta(s',z); \hat{\phi}) + \alpha \tilde{\mathcal{D}}_\theta(s'))\)。
3. 更新双Q网络（MSE损失）。
4. 更新actor：最小化 \(-\mathbb{E}[Q(s, f_\theta(s,z); \phi) + \alpha \tilde{\mathcal{D}}_\theta(s)]\)。
5. 更新系数 \(\alpha\) 以最小化 \(\alpha(\tilde{\mathcal{D}}_\theta(s) - \hat{\mathcal{D}})\)。
6. 软更新目标网络。

## 3. 实验设计

- **测试场景**：
  - **多目标PointMaze**（D4RL改进版）：三个难度迷宫，稀疏奖励（到达目标得+100），同时评估成功率、可达目标数及**少样本鲁棒性**（目标移除/障碍）。
  - **生成式RL**：游戏关卡生成（MarioPuzzle和MultiFacet两种风格），奖励基于专家知识和可解性检查，评价指标为回合回报和多样性（平均Hamming距离）。
  - **标准MuJoCo-v4**：六个连续控制任务（Ant, HalfCheetah, Hopper, Humanoid, Walker2d, HumanoidStandup）。

- **对比方法**：
  - 多模态基线：SQL（摊销actor+SVGD）、DACER（扩散actor+噪声缩放）、S2AC（能量基SVGD采样）。
  - 单峰基线：SAC（高斯actor）。
  - DrAC两个版本：DrAmort（摊销actor）和DrDiffus（扩散actor）。

- **公平性措施**：所有算法使用相同的神经网络架构（两层256隐藏层）和公共超参数（学习率、批大小等），进行网格搜索确定温度，每种配置运行**5个随机种子**。

## 4. 资源与算力

- **硬件**：一台Linux服务器，配备**8块NVIDIA RTX 3090 GPU**和**Intel Xeon Platinum 8375C CPU**。每次训练使用单块GPU。
- **计算成本（附录B.1）**：以Ant-v4为基准，DrAmort每1000步训练约21.0秒（甚至快于SAC的22.7秒），扩散版本（DrDiffus约84.8秒，DACER约76.9秒），S2AC最慢（220.5秒）。GPU峰值内存：DrAmort 392M，DrDiffus 608M，S2AC高达3462M。
- 论文未明确报告总训练时长，但提供了相对效率对比。

## 5. 实验数量与充分性

- **实验组数**：
  - 多目标PointMaze：3种地图 × 每种算法5种子 = 大量个体实验；另包含两种鲁棒性测试。
  - 生成式RL：2种风格 × 每个算法至少3个温度 × 5种子，以及t-SNE可视化。
  - MuJoCo：6个任务 × 每种算法5种子。
  - 消融/敏感性：温度敏感性实验（DrAmort和DrDiffus各5个温度，基线各3个温度）。
- **充分性与客观性**：
  - 覆盖了多样性关键领域和标准基准，实验设计全面。
  - 使用相同网络架构、优化器、种子等，公平性较好。
  - 报告均值和标准差，曲线平滑处理。
  - 不足：未进行超参数敏感性分析中对基线方法的完整网格搜索（仅三个温度），但论文说明了选择依据。

## 6. 主要结论与发现

- **DrAC能有效训练多模态策略**，尤其在两个多样性关键领域（多目标导航和生成式RL）表现出色，同时标准MuJoCo任务上具有竞争力。
- **摊销actor（DrAmort）性能最优**：在多目标PointMaze中实现最佳多样性和鲁棒性；在生成式RL中取得最高回报和良好多样性；在MuJoCo中超过SQL并接近SAC。计算效率接近甚至优于SAC。
- **扩散actor（DrDiffus）优势不显著**：虽然有一定多模态能力，但训练慢、调参敏感，未明显超越SAC或DACER。可能需更复杂的网络和超参数。
- **多样性带来少样本鲁棒性**：在多目标PointMaze的离分布测试中，DrAmort因轨迹多样性而显著优于其他算法，验证了多样性对鲁棒性的关键作用。
- **距离多样性正则化优于熵正则化**：熵正则化不偏好多模态，且无法用于难处理策略；所提基于几何平均的距离度量避免了过度估计。

## 7. 优点

- **方法论创新**：统一了难处理多模态策略的框架，并提出重参数化策略梯度和距离多样性正则化，解决了概率不可计算问题。
- **算法通用性**：适用于任何可表达为随机映射actor的模型（摊销、扩散、甚至高斯）。
- **实验设计亮点**：识别并系统研究了两个多样性关键领域（多目标、生成式RL），并引入少样本鲁棒性测试，具有实际意义。
- **计算效率**：DrAmort在保持多模态表达能力的同时，速度与SAC相当，显著优于扩散方法。
- **自动超参数调整**：目标多样性匹配机制简化了温度调优。
- **代码开源**：提供完整代码和复现脚本。

## 8. 不足与局限

- **实验局限**：
  - 多目标PointMaze仅为二维简单迷宫，未在更复杂的3D环境（如DM Control）中验证。
  - 生成式RL仅基于GAN潜空间的游戏关卡生成，多样性度量采用简单Hamming距离，可能不够精细。
  - MuJoCo上DrAmort虽好，但未超越SAC的最佳表现，部分任务差异不显著。
- **方法局限**：
  - 多样性正则化仅使用L2距离，可能不适用于所有动作空间（如离散或高维动作）。
  - 多样性估计需要额外采样（每状态n=8对），引入少量计算开销，且可能受样本量影响稳定性。
  - 未研究调度温度或更复杂多样性度量（如核函数、对抗多样性）的效果。
- **扩散actor未充分挖掘潜力**：论文指出扩散actor可能需更深的网络和更精细调参，但未系统探索，结论尚不完整。
- **实际应用限制**：仅模拟环境，未在真实机器人或复杂现实任务中测试。理论分析（如收敛性）较弱。
- **消融实验不足**：未做消融以区分重参数化与多样性正则化的单独贡献，也未与基于熵的难处理正则化方法对比（如通过近似概率）。

（完）
