---
title: "Glance2Gaze: Efficient Vision-Language Models from Glance Fusion to Gaze Compression"
title_zh: Glance2Gaze：从扫视融合到凝视压缩的高效视觉语言模型
authors: "Juan Chen, Honglin liu, Yingying Ao, Ting Zhang, Yan Huang, Xudong Liu, Biao Li, Jintao Fang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gm65gK3uOJ"
tags: ["query:llm-vlm"]
score: 7.0
evidence: 高效的视觉语言模型，受认知启发设计注意力
tldr: 本文受人类视觉认知的粗略扫视与聚焦注视两阶段机制启发，提出Glance2Gaze框架：Glance Fusion模块融合多层视觉Transformer特征生成全局表示，Gaze Compression模块压缩重要区域令牌。该方法在保持精度的前提下大幅减少视觉令牌数量，提升VLM推理速度，在多个视觉理解基准上达到效率与性能的平衡。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1340, \"height\": 449, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1327, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1078, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 905, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1074, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1078, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1031, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 522, \"label\": \"Table\"}]"
motivation: 现有VLM效率受限于大量视觉令牌导致的冗余计算。
method: 提出认知启发的两阶段框架：全局融合与聚焦压缩，减少视觉令牌。
result: 在多个VLM基准上，以更少令牌实现同等或更好性能，推理加速明显。
conclusion: 模拟人类视觉注意力的两阶段处理是提升VLM效率的有效方法。
---

## Abstract
Vision-language models heavily rely on visual representations, yet ensuring its efficiency remains a critical challenge. Most existing approaches focus on reducing visual tokens either at the visual encoder phase or during the LLM decoder stage. Inspired by human visual cognition, where an initial global glance precedes focused attention on semantically salient regions, we introduce Glance2Gaze, a cognitively inspired framework that mimics the human two-stage attention process. The framework consists of two key components: the Glance Fusion module, which integrates multi-layer vision transformer features with text-aware attention to generate a semantically enriched global representation, and the Gaze Compression module, which utilizes a novel query-guided mechanism to selectively compress visual tokens based on their semantic relevance. Experimental results on widely adopted benchmarks demonstrate that Glance2Gaze outperforms existing methods, achieving superior performance with equal or lower computational cost. Furthermore, it generalizes well to high-resolution and video scenarios, showcasing robust and scalable efficiency improvements in VLMs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：视觉语言模型（VLM）严重依赖视觉表示，但大量视觉令牌导致注意力机制的二次计算复杂度，造成推理延迟高、内存消耗大、可扩展性差。
- **现有方法局限**：当前减少视觉令牌的方法要么在视觉编码器阶段修剪，要么在LLM解码器阶段基于注意力得分修剪，但忽略了人类视觉注意力的层次性——先快速全局扫视，再聚焦注视。
- **动机**：受人类视觉认知的“粗略扫视→聚焦注视”两阶段机制启发，旨在设计一个更符合认知原理的视觉令牌压缩框架，在保持性能的同时大幅提升效率。

## 2. 方法论
### 核心思想
- 模拟人类视觉的两阶段处理：**Glance（扫视）** 阶段快速获取全局场景理解；**Gaze（注视）** 阶段逐步聚焦到语义相关的局部区域。
- 框架由两个互补模块组成：**Glance Fusion** 和 **Gaze Compression**。

### 关键技术细节
- **Glance Fusion（扫视融合）**：
  - 从ViT中采样多个中间层（如第7、13、19、23层）的特征。
  - 利用**文本感知注意力**计算每个视觉令牌与指令令牌的跨模态相关性得分。
  - 将得分作为动态权重，加权融合多层特征，生成任务增强的全局视觉表示，且**不增加视觉令牌数量**。
  - 关键公式：先计算每层视觉令牌与指令的相关性矩阵 \( A_{v2t} \)，平均得到 \( g_{v2t} \)，堆叠后Softmax得到权重，加权求和得最终 \( V_Q \)。
- **Gaze Compression（凝视压缩）**：
  - 在LLM解码器的**特定起始层（如第9层）之后**，对视觉令牌进行渐进式压缩。浅层保留全部令牌以充分理解，深层逐步减少令牌数。
  - 采用**共享可学习查询池** \( Q_s \)，所有参与压缩的解码层共享同一组查询嵌入，不同层取前 \( p_l \) 个查询。
  - 压缩操作：通过交叉注意力（查询为 \( Q_s \) 的子集，键值为上一层的视觉令牌）得到压缩后的视觉令牌，替换原有令牌输入下一层。
  - 压缩比例随层数单调递减（如从256递减到2），模拟从全局到局部的聚焦过程。
- **效率分析**：Glance Fusion 的额外FLOPs占总FLOPs不到2.72%，可忽略；Gaze Compression通过渐进压缩显著降低LLM中视觉令牌的计算量（如33% FLOPs时保持99.9%性能）。

## 3. 实验设计
### 使用的数据集/场景
- **图像理解**：TextVQA, POPE, GQA, VQAv2, SEEDBench, MMBench, MME, ScienceQA-IMG, MMVet, LLaVA-Bench-in-the-wild（共10个数据集）。
- **视频理解**：TGIF, MSVD, MSRVTT, ActivityNet（4个数据集）。

### 基准模型
- 图像：LLaVA-1.5-7B, LLaVA-NeXT-7B（高分辨率场景）。
- 视频：Video-LLaVA。

### 对比方法
- FastV, SparseVLM, PDrop, VisionZip（均为当前主流的视觉令牌压缩方法）。
- 另外在消融中对比了 Dense Connector, MMFuser 等融合策略。

### 实验设置
- 不同压缩比例：FLOPs保留33%、22%、11%（图像）；22%、11%、5%（LLaVA-NeXT）；6%（视频）。
- 对比指标：各数据集准确率、平均相对性能保持率、推理延迟、CUDA时间、吞吐量。

## 4. 资源与算力
- **硬件**：8块 NVIDIA A100-80G GPU。
- **训练时长**（补充材料表10）：
  - LLaVA-1.5-7B 基准：104 GPU小时；Glance2Gaze 不同配置：43~72 GPU小时。
  - LLaVA-NeXT-7B 基准：366 GPU小时；Glance2Gaze：87~242 GPU小时。
  - Video-LLaVA 基准：297 GPU小时；Glance2Gaze：151 GPU小时。
- 推理时，Glance2Gaze（5% FLOPs）在LLaVA-NeXT上预填充时间加速6.39倍，总体延迟加速3.15倍，吞吐量提升3.14倍。

## 5. 实验数量与充分性
- **数量**：非常充分。涵盖10个图像数据集、4个视频数据集；对比4种主流方法；3~4种压缩比例；多种消融实验（共享查询池 vs 层特定查询、有无Glance Fusion、不同起始层r和压缩尺寸pr、不同层数融合、指令必要性等）。
- **充分性**：实验设计全面，覆盖了不同任务类型、不同分辨率、不同模态（图像+视频），并且报告了FLOPs、延迟、吞吐量等效率指标，对比了多种基线。
- **客观与公平**：实验设置遵循原模型配置，对比方法采用官方实现或相同设置。但缺少统计显著性检验（如误差条），可能因计算成本高而省略。综合来看，实验充分且结论可信。

## 6. 主要结论与发现
- Glance2Gaze 在**所有压缩比例下均优于或持平现有方法**，尤其在极低FLOPs（11%、5%）下保持高相对性能（95.6%、94.8%）。
- **视频任务**：6% FLOPs 保持96.2%性能，远超FastV（52.1%），优于VisionZip（93.2%）。
- **推理效率**：相比原始模型，预填充时间加速最高6.39倍，吞吐量提升3.14倍。
- **消融实验证实**：（1）共享查询池比层特定查询效果更好；（2）Glance Fusion 能显著提升细粒度OCR任务（如TextVQA提升1.0~1.6点）；（3）过早压缩（r过小）或压缩过大（pr过小）会降低性能；（4）文本感知融合优于简单平均或查询无关的聚合。

## 7. 优点
- **认知启发性**：框架自然模拟人类视觉的两阶段注意力过程，具有生物学合理性。
- **模块化设计**：Glance Fusion 增强全局语义而不增加令牌数；Gaze Compression 渐进压缩，浅层保持全令牌、深层压缩，符合观察现象。
- **共享查询池**：减少参数，隐式约束优化域，提升压缩效果。
- **兼容高效注意力**：不依赖完整注意力矩阵，可与 FlashAttn 等加速库兼容（区别于某些基于注意力得分的修剪方法）。
- **广泛适用性**：在标准分辨率、高分辨率图像和视频场景均表现优异，泛化能力强。
- **实验全面**：覆盖多数据集、多模型、多压缩比，对比多个强基线，消融深入。

## 8. 不足与局限
- **认知建模浅层**：虽然框架受认知启发，但内部融合和压缩策略仍是启发式设计，缺乏对认知过程（如眼动、空间频率处理）的显式建模，论文承认这一点。
- **缺乏统计显著性检验**：未报告误差条或置信区间，无法判断结果是否具有统计显著性。
- **架构依赖性**：仅在 LLaVA 系列和 Video-LLaVA 上验证，在其他VLM架构（如Qwen2-VL、InternVL）上的表现未知，泛化性待验证。
- **极端压缩下性能下降**：在FLOPs保留11%以下（如5%），高分辨率场景性能下降相对明显（从99.2%降到94.8%），仍有改进空间。
- **训练资源需求**：尽管推理效率高，但训练仍需多块A100 GPU和数十至上百小时，小团队复现门槛较高。
- **未讨论模型幻觉**：视觉令牌压缩可能增加模型幻觉风险，论文未分析此副作用。

（完）
