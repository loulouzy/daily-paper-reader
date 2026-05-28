---
title: Language Model as Visual Explainer
title_zh: 语言模型作为视觉解释器
authors: "Xingyi Yang, Xinchao Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Dsi8Ibxg9H"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 基于LLM的视觉模型解释
tldr: 理解视觉模型内部机制是重要但困难的任务。本文提出LVX，利用LLM与视觉模型协作，无需额外训练。LLM生成层次化视觉属性，文本-图像API检索匹配图像，构建视觉嵌入树。通过语言模板动态修剪和生长树结构，以自然语言解释模型行为。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 710, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1355, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1308, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 679, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1320, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 425, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dsi8ibxg9h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 333, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 692, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 761, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 729, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 757, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1427, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 515, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 875, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 604, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 878, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1288, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1289, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dsi8ibxg9h/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1255, \"height\": 421, \"label\": \"Table\"}]"
motivation: 现有视觉模型解释方法需要额外训练或仅提供单一解释。
method: 利用LLM生成层次化属性，结合文本-图像API构建动态嵌入树，通过语言模板调整解释结构。
result: 在多个视觉模型上生成结构化和可理解的语言解释，无需训练。
conclusion: 语言模型可充当灵活的解释器，帮助理解视觉模型的决策过程。
---

## Abstract
In this paper, we present Language Model as Visual Explainer (\texttt{LVX}), a systematic approach for interpreting the internal workings of vision models using a tree-structured linguistic explanation, without the need for model training. Central to our strategy is the collaboration between vision models and LLM to craft explanations. On one hand,  the LLM is harnessed to delineate hierarchical visual attributes, while concurrently,  a text-to-image API retrieves  images that are most aligned with these textual concepts. By mapping the collected texts and images  to the vision model's embedding space,  we construct a hierarchy-structured visual embedding tree. This tree is dynamically pruned and grown by querying the LLM using language templates, tailoring the explanation to the model.  Such a scheme allows us 
to seamlessly incorporate new attributes while eliminating undesired concepts based on the model's representations. When applied to testing samples, our method provides human-understandable explanations in the form of attribute-laden trees. Beyond explanation, we retrained the vision model by calibrating it on the generated concept hierarchy, allowing the model to incorporate the refined knowledge of visual attributes. To access the effectiveness of our approach, we introduce new benchmarks and conduct rigorous evaluations, demonstrating its plausibility, faithfulness, and stability.

---

## 论文详细总结（自动生成）

# 论文总结：《Language Model as Visual Explainer (LVX)》

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：深度视觉模型（如CNN、ViT）的决策过程难以被人类直接理解。现有可解释性方法（如归因、原型分析）只能提供像素级或特征级高亮，缺乏人类可读的自然语言解释；而自然语言解释方法往往需要大量人工标注或额外训练，且解释形式单一（如单句描述）。
- **整体含义**：本文提出一种无需模型训练、利用大语言模型（LLM）与视觉模型协作，生成**树结构语言解释**的系统——LVX，旨在以层次化、属性化的树形结构揭示视觉模型内部决策逻辑，同时可反哺模型校准，提升性能与可靠性。

## 2. 方法论：核心思想、关键技术细节、公式与算法流程

- **核心思想**：将LLM作为“常识知识提供者”和“动态树构造器”，通过LLM生成类别属性层次树，利用文本-图像API（如Bing搜索、Stable Diffusion）为每个节点检索对应图像，提取视觉嵌入构建嵌入树；再通过训练集样本遍历树，根据模型对属性的识别程度进行**剪枝与生长**，最终得到与模型特征空间对齐的解释树。测试时，样本特征沿树路由，从根到叶的路径即为个性化解释。

- **关键步骤**：
  1. **初始树构建**：对每个类别 `c_i`，利用LLM（如ChatGPT）使用in-context prompting生成嵌套JSON格式的属性树（包含Concepts、Substances、Attributes、Environments等），解析为初始树 `T_i^{(0)}`。
  2. **文本-图像映射**：对每个节点 `v`，调用文本-图像API获取K张支持图像，用视觉模型提取嵌入 `P_v = {g(e x)}`，形成嵌入树。
  3. **树精炼**：
     - 对训练集样本，提取特征 `q_j`，通过**点到集距离** `D(q_j, P_v) = inf{ d(q_j, p) | p ∈ P_v }`（具体实现 `d(q,p) = -log(||q-p||^2+1 / ||q-p||^2+ε)`）找到最近邻节点。
     - 统计各节点被分配的次数 `C_{v*}`，对低频节点剪枝，对高频节点通过LLM提示“Add visual attributes for ...”生成更细粒度属性进行生长。
     - 对跨类别共享节点（如“ear”），通过对比问题“The <NodeName> of <ClassName1> is different from <ClassName2> because...”进行差异化生长。
     - 迭代5轮，更新树结构。
  4. **测试路由**：对新样本预测类别 `ŷ`，提取特征 `q'`，在对应树中寻找top-k最近邻节点，合并根到这些节点的路径作为解释树。

- **模型校准（Calibration）**：利用生成的解释树作为伪标签，引入层次多标签对比损失（HiMulCon）`L_HMC`，结合交叉熵损失联合微调模型。`L_HMC` 每10个epoch更新一次解释树以对齐模型变化。

- **公式说明**：训练目标为 `min Σ [L_CE(f(x_j), y_j) + λ L_HMC(g(x_j), T̂_j)]`。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **原有数据集**：CIFAR-10、CIFAR-100、ImageNet，但缺乏层次化解释标注。
  - **新标注数据集**：H-CIFAR-10、H-CIFAR-100、H-ImageNet，由LLM+人工验证构建属性树作为ground-truth。
  - **支持集**：为每个属性从Bing或Stable Diffusion检索/生成图像，经CLIP过滤（阈值0.5），统计见Table 1（如H-ImageNet含1000类、26928个属性、50000张图像）。

- **对比方法**：
  - **Constant**：使用固定类别模板树。
  - **Random**：随机从模板树中选择子树。
  - **Subtree**：选择测试集最常见的子树。
  - **TrDec**：基于树拓扑RNN解码器，用CLIP生成伪标签训练，可学习式解释。
  - **消融**：w/o Refine（无精炼）、ActMag（用激活幅度替代特征相似度作精炼标准）。

- **评估指标**：
  - **Plausibility**：与人工标注树的相似度，使用MCS（最大公共子图）和Tree Kernel（TK）。
  - **Faithfulness**：通过模型诱导的样本-概念距离（MSCD）衡量（越小越好）。
  - **Stability**：输入微小扰动（高斯噪声、Cutout）下解释的MCS/TK变化。

- **被解释模型**：跨12种架构（VGG、ResNet、DenseNet、MobileNet、GoogLeNet、Inception、ViT等），覆盖CNN和Transformer。

## 4. 资源与算力

- **论文未明确说明具体GPU型号、数量及训练时长**。仅提及训练时使用SGD优化器，50个epoch，学习率在{0.001,0.01,0.03}中选择。精炼阶段迭代5轮。支持集图像检索和嵌入提取涉及外部API和预训练模型（CLIP、Stable Diffusion），但无具体算力统计。

## 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 在3个核心数据集（CIFAR-10/100、ImageNet）上评估Plausibility、Faithfulness、Stability，覆盖12种网络架构。
  - 消融实验：无精炼（w/o Refine）、不同精炼标准（ActMag vs. 特征相似度）、不同阈值。
  - 附加实验：CNN vs. Transformer分析（26,928个概念上比较）、用户研究（37人，15题）、自监督模型（SimCLR、BYOL、DINO等）、胸部X光诊断（Chestx-ray14，多标签）、OOD泛化测试（ImageNet-A/Sketch）。
  - 提供完整数值表格（附录）和可视化案例（含错误预测分析、噪声标签识别）。

- **充分性与公平性**：实验设计系统，从多个维度（合理性、忠实性、稳定性）评估，对比了多种基线（随机、固定、学习式），并在不同架构上验证。用户研究进一步支持了LVX的实用性。消融实验证实了精炼阶段的必要性。

## 6. 主要结论与发现

- LVX能够生成与模型内部表示高度一致、人类可读的树结构解释，**无需模型训练**，在Plausibility、Faithfulness、Stability指标上全面超越现有基线（Subtree、TrDec等）。
- 树精炼过程有效提升了解释与模型的对齐度，仅用特征相似度比激活幅度（ActMag）更优。
- LVX可诊断错误预测：即使分类错误，仍能识别正确属性（如“鳍”在鲸鱼和鲨鱼间共享），并能发现数据中的噪声标签。
- 通过解释校准模型，不仅提升了分类准确率（在CIFAR-10/100、ImageNet上均优于NBDT等神经树方法），还增强了OOD泛化能力（ImageNet-A +4.36%，ImageNet-S +7.32%）。
- 自监督模型（如DINO ViT）在属性解缠上优于监督模型，尽管整体准确率略低。
- CNN偏向纹理和局部模式，Transformer更擅长全局语义（如环境），与已有研究一致。

## 7. 优点（方法或实验设计亮点）

- **创新性**：首个无需训练、利用LLM生成树结构解释视觉模型的方法，融合了语言、视觉和检索API，解决了纯视觉模型缺乏文本概念的问题。
- **动态精炼机制**：通过LLM查询自动剪枝和生长树，使解释适应模型的具体识别能力，具有自适应性。
- **实用性强**：支持开放词汇（open-vocabulary），适用于任意类别和架构；路由过程仅需少量特征相似度计算，推理高效。
- **模型校准副产物**：利用解释树作为伪标签，引入层次对比学习，同时提升模型性能和可解释性，形成正反馈。
- **评估完整性**：构建了新的层次化标注数据集（H-CIFAR等），提出MCS、MSCD等定量指标，并进行了用户研究、多领域（医学、OOD）验证，实验体量大、结论可靠。

## 8. 不足与局限

- **依赖外部API和LLM**：解释质量受LLM生成准确性、文本-图像API检索质量影响（可能产生错误图像或无法覆盖罕见属性）。论文指出存在假阳性图像、分布外样本、数据偏差等问题，已通过CLIP过滤和手动消歧缓解，但未完全消除。
- **忽略深层特征层次**：仅基于最后一层嵌入，未利用多层级特征，可能丢失中间层细节。
- **支持集构建成本**：每个类别需检索/生成大量图像，对于大规模数据集（ImageNet 1000类）需预处理21万张图像，有一定计算开销。
- **未公开详细算力信息**：模型训练和精炼过程的GPU需求未明确，不利于复现和资源评估。
- **仅适用于分类任务**：方法设计基于分类模型（特征提取器+线性分类头），对目标检测、分割等任务的扩展性未讨论。
- **树结构深度有限**：实验中最大深度约4-5层，过于复杂的属性层次可能导致路由不稳定或LLM生成失效。

（完）
