---
title: Fine-Tuning Large Vision-Language Models as Decision-Making Agents via Reinforcement Learning
title_zh: 通过强化学习将大型视觉语言模型微调为决策智能体
authors: "Yuexiang Zhai, Hao Bai, Zipeng Lin, Jiayi Pan, Shengbang Tong, Yifei Zhou, Alane Suhr, Saining Xie, Yann LeCun, Yi Ma, Sergey Levine"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=nBjmMF2IZU"
tags: ["query:llm-vlm"]
score: 9.0
evidence: 使用强化学习微调视觉语言模型用于决策
tldr: 本文提出一个算法框架，利用强化学习微调大型视觉语言模型（VLM）作为决策智能体，解决传统监督微调在多步目标导向任务中效率低下的问题。该框架通过任务描述引导VLM生成链式思维推理，探索中间步骤并输出文本动作。实验证明，RL微调显著提升了VLM在交互环境中的决策性能，为多模态强化学习开辟了新途径。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1348, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 511, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1152, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1346, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1149, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1345, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1148, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1346, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1177, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1353, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1282, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1344, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1409, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1416, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1351, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1351, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1480, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1481, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1480, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1484, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1472, \"height\": 991, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1475, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1474, \"height\": 1053, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1476, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 318, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nbjmmf2izu/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 319, \"height\": 320, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nbjmmf2izu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 619, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nbjmmf2izu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nbjmmf2izu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nbjmmf2izu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1061, \"height\": 329, \"label\": \"Table\"}]"
motivation: 传统监督微调无法使VLM在交互式多步任务中高效学习最优决策。
method: 提出RL微调框架，利用任务描述和链式思维推理，结合强化学习优化VLM的动作输出。
result: 在多个决策任务上，RL微调的VLM显著优于监督微调的基线模型。
conclusion: RL微调是赋予VLM决策能力的有效范式，可推广至复杂多模态环境。
---

## Abstract
Large vision-language models (VLMs) fine-tuned on specialized visual instruction-following data have exhibited impressive language reasoning capabilities across various scenarios. However, this fine-tuning paradigm may not be able to efficiently learn optimal decision-making agents in multi-step goal-directed tasks from interactive environments. To address this challenge, we propose an algorithmic framework that fine-tunes VLMs with reinforcement learning (RL). Specifically, our framework provides a task description and then prompts the VLM to generate chain-of-thought (CoT) reasoning, enabling the VLM to efficiently explore intermediate reasoning steps that lead to the final text-based action. Next, the open-ended text output is parsed into an executable action to interact with the environment to obtain goal-directed task rewards. Finally, our framework uses these task rewards to fine-tune the entire VLM with RL. Empirically, we demonstrate that our proposed framework enhances the decision-making capabilities of VLM agents across various tasks, enabling 7b models to outperform commercial models such as GPT4-V or Gemini. Furthermore, we find that CoT reasoning is a crucial component for performance improvement, as removing the CoT reasoning results in a significant decrease in the overall performance of our method.

---

## 论文详细总结（自动生成）

# 论文《Fine-Tuning Large Vision-Language Models as Decision-Making Agents via Reinforcement Learning》详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：大型视觉语言模型（VLM）通过视觉指令微调（supervised fine-tuning on visual instruction data）在多种场景中展现出强大的语言推理能力。
- **问题**：传统的视觉指令微调是一种监督学习范式，依赖预先收集的静态数据集，无法与交互式环境进行多步、目标导向的决策任务交互。因此，这种范式难以学习最优的决策智能体。
- **动机**：强化学习（RL）已被证明在训练多步交互式智能体（如游戏、机器人控制）中非常有效，但现有工作多聚焦于纯文本任务，尚未有研究将RL直接用于端到端微调VLM的多步视觉决策任务。

## 2. 方法论：核心思想、关键技术细节、算法流程
### 核心思想
- 提出一个算法框架，利用RL直接微调整个VLM，使其成为决策智能体。
- 该框架通过任务描述提示（prompt）引导VLM先生成链式思维（Chain-of-Thought, CoT）推理，再输出文本动作，随后将文本动作解析为环境可执行的合法动作，并获取任务奖励，最后使用PPO算法利用这些奖励微调VLM的所有参数。

### 关键技术细节
1. **输入输出设计**：  
   - 输入：当前视觉观察（RGB图像） + 输入提示（包含任务描述、合法动作空间、期望输出格式）。  
   - 输出：格式化的JSON文本，包含 `"thoughts": "CoT推理"` 和 `"action": "选定的文本动作"`。

2. **后处理函数 \(f\)**：  
   - 从输出文本中提取关键字 `"action": "a"`，若未找到则以均匀随机方式选择一个合法动作，保证RL训练继续。

3. **动作概率估计**：  
   - 由于输出包含CoT（较长）和动作（较短），直接使用整个输出的对数概率会导致大部分梯度来自CoT，不利于学习动作决策。  
   - 提出缩放系数 \(\lambda \in [0,1]\)，将动作概率估计修正为：  
     \[
     \log \pi_\theta(a_t|o_t, v^t_{in}) = \lambda \log \pi_\theta(v^t_{tht}|o_t, v^t_{in}) + \log \pi_\theta(v^t_{act}|o_t, v^t_{in}, v^t_{tht})
     \]  
   - 实验表明，\(\lambda\) 在 0.2–0.5 之间效果最佳，过大或过小均导致性能下降。

4. **算法流程（Algorithm 1）**：
   - 初始化VLM参数 \(\theta_0\)，环境，后处理函数 \(f\)，缩放系数 \(\lambda\)，重放缓冲区大小 \(B\)，最大步长 \(T\)。  
   - 对每个RL轮次 \(k\)：
     - 重置环境，生成初始观察 \(o_t\) 和提示 \(v^t_{in}\)。  
     - 循环收集 \(B\) 条轨迹：VLM输出 \(v^t_{out}\) → 解析动作 \(a_t\) → 计算修正后的 \(\log \pi_\theta(a_t|\cdot)\) → 执行动作获得奖励 \(r_t\) 和下一观察 \(o_{t+1}\) → 存储到缓冲区。  
     - 使用PPO对缓冲区中的数据进行更新，得到新的参数 \(\theta_{k+1}\)。

## 3. 实验设计：数据集/场景、Benchmark、对比方法
### 实验场景
- **Gym Cards（原创环境）**：包含四个任务，测试细粒度视觉识别与语言推理能力。  
  - NumberLine：将当前数字移动到目标数字（确定性）。  
  - EZPoints：用两张牌的数字计算12（确定性）。  
  - Points24：用四张牌的数字计算24（确定性，更难）。  
  - Blackjack：黑杰克游戏（随机性）。
- **ALFWorld**：基于文本的具身AI环境，包含六类目标条件任务（Pick & Place、Examine in Light、Clean & Place、Heat & Place、Cool & Place、Pick Two & Place），测试视觉语义理解能力。

### Benchmark
- 评价指标：**平均成功率**（episode success rate）。  
- Gym Cards：每个任务分别计算，最后取四个任务的平均。  
- ALFWorld：由于子任务出现概率不等，取加权平均。

### 对比方法
1. **GPT-4V** 和 **Gemini**：商用闭源模型，使用相同提示。
2. **LLaVA-sft**：使用相同数据（包含CoT）进行监督微调的 LLava-v1.6-mistral-7b。
3. **CNN+RL**：使用相同CLIP视觉编码器的CNN策略网络 + PPO（用于对比传统RL方法）。
4. **BUTLER（灰条标记）**：需要专家数据，采用不同解码策略，仅作参考。
5. **Ours**：提出的RL微调框架（基于LLaVA-sft初始化）。

## 4. 资源与算力
- **硬件**：8 × NVIDIA A100（80GB）DGX 机器，最大VRAM使用 < 40GB。
- **训练时长**：每条训练曲线（15k env steps for gym_cards，5k for ALFWorld）≤ 36小时。
- **微调方式**：使用LoRA（\(r=128, \alpha=256, dropout=0.05\)）微调所有可训练组件（视觉编码器、LLM、MLP投影器）。
- **分布式训练**：采用DeepSpeed ZeRO2进行多GPU训练；部分实验（如ALFWorld）因采样时间方差大，每轮只用单GPU。

## 5. 实验数量与充分性
- **实验数量**：  
  - 每个任务至少使用4个随机种子（4 GPU），训练曲线报告平均值和标准差。  
  - Gym Cards：200–1000个测试episode；ALFWorld：200个测试episode。
- **消融实验**：  
  - 有CoT vs 无CoT（两个领域、多个任务）。  
  - 不同 \(\lambda\) 值（0.1, 0.3, 0.5, 0.7, 0.9）在NumberLine上的表现。
- **充分性与公平性**：  
  - 所有对比方法在相同条件下测试（相同提示、环境、随机种子）。  
  - BUTLER方法因使用专家数据被单独列出，对比组（Ours vs 无专家数据的方法）公平。  
  - 实验覆盖了确定性、随机性任务，以及多任务场景，结论具有普适性。

## 6. 主要结论与发现
1. **RL微调显著提升VLM的决策能力**：  
   - 在Gym Cards上，平均成功率从LLaVA-sft的18.4%提升至45.5%；在ALFWorld上从17.7%提升至21.7%。
   - 7B参数的模型在多数任务上超过GPT-4V和Gemini。

2. **CoT推理是关键组件**：  
   - 去除CoT后，在NumberLine和EZPoints上几乎无提升，在ALFWorld上也有明显下降（平均成功率降低5.4%）。

3. **缩放系数 \(\lambda\) 的重要性**：  
   - 选择适中的\(\lambda\)（0.2–0.5）才能有效利用CoT信息，过大或过小均导致训练失败。

4. **局限性**：  
   - Points24任务性能极差（<3%），主要原因是VLM无法准确识别四张卡片的数字或推理出错。  
   - ALFWorld的增益有限（仅+4%），归因于其多任务性质和大动作空间。

## 7. 优点
- **方法创新**：首次提出端到端RL微调VLM作为决策智能体，打通了从视觉输入、语言推理到动作执行的完整闭环。
- **利用CoT探索**：通过提示CoT推理，让VLM在决策前进行中间推理，有效加速探索，这是传统CNN+RL无法做到的。
- **实用性强**：7B小模型在多个任务上超越商用大模型，表明轻量级模型通过RL可接近甚至超越学究式大模型。
- **开源可复现**：提供详细代码、数据、超参数，实验设置透明。

## 8. 不足与局限
- **实验覆盖有限**：未涉及标准图像Atari任务（因计算资源限制），且Points24几乎无法解决，表明方法在复杂多步推理任务上仍有挑战。
- **偏差风险**：SFT数据由人工或GPT-4V生成，可能存在分布偏差；RL训练仅在单任务上进行，未测试多任务泛化能力。
- **资源依赖**：训练仍需8×A100、数十小时，对于更大模型（如13B+）可能难以承受。
- **超参数敏感**：\(\lambda\) 需要针对不同任务调参（论文给出范围但未提供自动选择策略）。
- **CoT提示工程未深入**：仅使用了简单的CoT模板，未探索更复杂的推理结构（如Tree-of-Thought）。

（完）
