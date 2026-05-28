---
title: "SpatialRGPT: Grounded Spatial Reasoning in Vision-Language Models"
title_zh: SpatialRGPT：视觉语言模型中的接地空间推理
authors: "An-Chieh Cheng, Hongxu Yin, Yang Fu, Qiushan Guo, Ruihan Yang, Jan Kautz, Xiaolong Wang, Sifei Liu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=JKEIYQUSUc"
tags: ["query:llm-vlm"]
score: 8.0
evidence: 视觉语言模型中的空间推理
tldr: 视觉语言模型在2D任务上表现优秀，但空间推理能力有限。本文提出SpatialRGPT，通过3D场景图数据标注流程和深度信息插件模块，增强VLM的空间感知。在用户指定区域后，模型能准确判断相对方向和距离，在空间推理基准上显著提升。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 516, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 752, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1368, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1377, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1288, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 297, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 501, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 419, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 306, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 478, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1423, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1457, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1435, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1444, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1391, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1390, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jkeiyqusuc/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1405, \"height\": 679, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 1175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 698, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 625, \"height\": 810, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1457, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 653, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1411, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 785, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jkeiyqusuc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1247, \"height\": 312, \"label\": \"Table\"}]"
motivation: 当前VLM缺乏对空间关系的深入理解和推理能力。
method: 构建3D场景图数据标注流程，并设计可插拔深度模块集成到VLM视觉编码器中。
result: 在空间关系推理任务上达到最先进性能，并能泛化到未见场景。
conclusion: 融合3D场景图和深度信息能有效弥补VLM的空间感知短板。
---

## Abstract
Vision Language Models (VLMs) have demonstrated remarkable performance in 2D vision and language tasks. However, their ability to reason about spatial arrangements remains limited. In this work, we introduce Spatial Region GPT (SpatialRGPT) to enhance VLMs’ spatial perception and reasoning capabilities. SpatialRGPT advances VLMs’ spatial understanding through two key innovations: (i) a data curation pipeline that enables effective learning of regional representation from 3D scene graphs, and (ii) a flexible ``plugin'' module for integrating depth information into the visual encoder of existing VLMs. During inference, when provided with user-specified region proposals, SpatialRGPT can accurately perceive their relative directions and distances. Additionally, we propose SpatialRGBT-Bench, a benchmark with ground-truth 3D annotations encompassing indoor, outdoor, and simulated environments, for evaluating 3D spatial cognition in Vision-Language Models (VLMs). Our results demonstrate that SpatialRGPT significantly enhances performance in spatial reasoning tasks, both with and without local region prompts. The model also exhibits strong generalization capabilities, effectively reasoning about complex spatial relations and functioning as a region-aware dense reward annotator for robotic tasks. Code, dataset, and benchmark are released at https://www.anjiecheng.me/SpatialRGPT.

---

## 论文详细总结（自动生成）

# SpatialRGPT 论文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有视觉语言模型（VLM）在2D视觉与语言任务上表现出色，但在空间推理（如区分左右、前后、远近，以及理解度量距离和方向）方面存在严重不足。主要瓶颈包括：(i) 大多数VLM仅处理全局图像，无法精确指定和推理局部区域间的空间关系；(ii) 仅依赖RGB像素难以准确感知三维空间信息（如方向、距离）。
- **整体含义**：本文旨在通过引入区域级表示和深度信息，增强VLM对3D空间的感知与推理能力，从而为机器人导航、操作、AR等需要精细空间意识的应用提供基础。

## 2. 论文提出的方法论

### 核心思想
- 构建自动化的数据标注管道，从单张2D图像生成3D场景图（节点为物体实例，边为空间关系），并转换为空间问答数据。
- 设计可插拔的深度信息模块，在现有VLM视觉编码器中灵活集成相对深度，提升3D感知能力。
- 基于RegionGPT的区域特征提取方式，支持用户通过边界框或掩码指定区域，模型输出空间关系答案。

### 关键技术细节
1. **数据管道（3D场景图构建）**：
   - 过滤：使用CLIP过滤不适合图片（如截图、绘画等）。
   - 开放词汇检测与分割：先用图像标签模型识别物体类别，再用GroundingDino检测边界框，最后用分割模型（SAM-HQ）生成精确掩码。
   - 度量深度估计：采用Metric3Dv2估计每像素度量深度。
   - 相机标定：WildCamera估计内参，PerspectiveFields估计外参（俯仰、滚转），将点云规范到地理坐标系。
   - 点云处理：去除统计离群点、体素降采样、DBSCAN去噪，为每物体构建轴对齐3D边界框（AABB）。
   - 生成场景图：节点存储类别、宽度、高度；边存储相对关系（左/右、前/后等）和度量关系（方向、直接距离、水平/垂直距离）。
   - QA生成：模板方法生成基础问答；将场景图转为文本描述后输入LLaMA-3-70B，生成复杂推理问答。
   - 最终产出：Open Spatial Dataset (OSD) 包含100万图像、500万物体实例、870万模板QA、70万LLM QA。

2. **模型架构**：
   - 基础：视觉编码器（CLIP或SigLIP）→ 区域特征提取器（MaskPooling）→ 线性连接器 → LLM（LLaMA2-7B）。
   - 深度插件模块：同一视觉编码器处理归一化相对深度图生成深度特征图，通过独立的深度-语言连接器投影到语言空间。该连接器仅对空间相关QA训练，可灵活启用或禁用。
   - 分词：特殊标记`<image>`、`<region>`、`<depth>`分别代表图像级、区域RGB、区域深度嵌入，与文本令牌交错输入LLM。

3. **训练范式（三阶段）**：
   - 阶段一：使用CC3M预训练RGB连接器（冻结其他）。
   - 阶段二：使用MMC4、COYO、区域理解数据、OSD预训练LLM和连接器。
   - 阶段三：使用LLaVA指令数据、区域级指令数据、OSD指令微调全部参数。
   - 深度连接器在阶段二后期单独用OSD空间数据训练。

## 3. 实验设计

- **基准数据集**：
  - **SpatialRGPT-Bench**：基于Omni3D真实3D标注，包含nuScenes、KITTI（室外）、SUNRGBD、ARKitScenes（室内）、Hypersim（仿真），共657定性+749定量QA，覆盖88类物体。
  - **标准VLM基准**：VQA v2、GQA、SQA、POPE、MME、MMB、MMB-CN、SEED、MMMU等。
  - **区域基准**：COCO-2017 val（物体分类）、BLINK相对深度基准。
  - **应用演示**：机器人奖励标注（真实机器人抓取任务）、复杂多跳推理。

- **对比方法**：
  - 盲LLM：GPT-4（仅文本）。
  - 语言指称VLM：GPT-4V、LLaVA-v1.6-34B。
  - 区域VLM：GPT-4V + SoM、LLaVA + SoM、KOSMOS-2、RegionVILA（即RegionGPT+VILA预训练，无OSD数据）。
  - 本文变体：SpatialRGPT-7B（RGB版）、SpatialRGPT-7B（RGB+D）、3B/8B版。

- **评估方式**：使用GPT-4自动化评估。定性题判断回答是否与正确答案一致（0/1）；定量题提取数值并转换到统一单位，计算成功率（±25%内）和绝对相对误差。

## 4. 资源与算力

- **数据管道**：8 GPU（型号未明确），过滤4h + 深度估计4h + 检测分割8h + LLM QA合成12h，总计约一天半。
- **模型训练**：
  - 前两阶段继承VILA，使用16节点A100（每节点8GPU，共128GPU），训练时长数天（具体未给出，但VILA论文详述）。
  - 深度连接器预训练：2节点A100（共16GPU），4小时。
  - 指令微调：2节点A100（共16GPU），12小时。
- **SpatialRGPT-Bench构建**：掩码生成4h，QA合成后人工验证一天。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。
  - 主表（表1）：在SpatialRGPT-Bench上对比6类方法，定性10个子类别定量6个子类别。
  - 表2：通用VLM基准上对比基础模型VILA-1.5-3B，显示持平或略优。
  - 表3：COCO区域分类对比多种方法（CLIP、LLaVA、Shikra、GPT4RoI、RegionGPT等）。
  - 表4：BLINK相对深度对比SOTA（GPT-4V、Gemini、Claude等），SpatialRGPT-7B达82.3%，8B达87.9%。
  - 附录消融实验4组（A-D）：增强基准、宽度高度数据影响、边界框类型、输入模态。
  - 应用演示：包含真实机器人实验和多轮推理示例。

- **充分性与公平性**：
  - 基线选择全面，覆盖盲模型、顶级VLM、区域VLM。
  - 使用同一自动化评估标准（GPT-4），减少人工偏差。
  - 在标准基准上验证了空间训练对通用能力无损害。
  - 消融实验验证了各组件贡献。
  - 但未与其他同类工作（如SpatialVLM）直接比较（SpatialVLM未公开Bench）；评估依赖GPT-4可能存在对结构化回答的偏好；未提供统计显著性检验（除机器人实验外）。

## 6. 论文的主要结论与发现

- SpatialRGPT在空间推理（定性+定量）上显著超越所有基线，包括GPT-4V，尤其在需要精确距离、方向、相对大小判断的任务上。
- 深度插件模块有效提升对前/后、宽/窄、距离等依赖深度信息的任务性能。
- 模型在标准VLM基准上表现基本持平或略优，证明空间训练不损害通用能力。
- 模型展现出强大的泛化能力：能回答未见过的多跳推理问题，能作为机器人密集奖励标注器（距离估计单调递减）。
- 开源的数据管道、数据集和基准可促进社区研究。

## 7. 优点

- **方法论亮点**：
  - 自动化大规模数据管道：无需人工标注，从2D图像自动构建3D场景图并生成高质量空间QA。
  - 可插拔深度模块：不改变原始VLM结构，可灵活开关，降低训练成本。
  - 区域级表示：支持任意形状的掩码输入，避免文本描述歧义。
- **实验设计亮点**：
  - 提出了包含真实3D标注的综合空间推理基准，覆盖室内外及仿真环境。
  - 多维度评估（定性/定量、标准/空间/区域/深度）。
  - 展示了实际应用价值（机器人奖励、多跳推理）。
- **其他**：代码、数据、模型全开源，易于复现。

## 8. 不足与局限

- **技术局限**：
  - 使用轴对齐边界框（AABB）而非有向边界框（OBB），在物体倾斜或非正对时可导致尺寸误差。
  - 单步深度估计误差（尤其是遮挡区域或反光表面）会影响点云精度。
  - 数据管道依赖多个预训练模型（检测、分割、深度、标定），错误会累积。
  - 未处理多视角或完整3D信息，仅依赖单张2D图像。
- **实验局限**：
  - 未公开与其他同任务工作（如SpatialVLM）的直接比较（因其基准未公开）。
  - 评估依赖GPT-4，可能引入新的偏差（如对事实一致性或单位转换的判断错误）。
  - 仅测试7B/8B模型，未探索更大模型（如13B/34B）或不同LLM架构的通用性。
  - 机器人应用仅为初步演示，未进行系统比较或消融。
- **数据与偏见**：
  - 训练数据来自OpenImages，其类别和场景分布可能存在偏见（如欧美场景为主）。
  - 未讨论模型在隐私、安全、公平性方面的潜在风险。

（完）
