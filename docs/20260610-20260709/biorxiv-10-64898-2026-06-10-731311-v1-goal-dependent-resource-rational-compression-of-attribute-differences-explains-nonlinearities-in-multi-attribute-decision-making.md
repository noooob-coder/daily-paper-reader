---
title: Goal-dependent resource-rational compression of attribute differences explains nonlinearities in multi-attribute decision making
title_zh: 目标依赖的资源理性压缩属性差异解释多属性决策中的非线性
authors: "Bao, S. D., Bedi, S., Li, D., Ruff, C. C., Hare, T. A."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731311v1.full.pdf"
tags: ["query:decision"]
score: 9.0
evidence: 多属性决策的资源理性模型
tldr: 多属性选择常违背加权加性规则，传统归因于偏差或启发式。本文提出资源理性压缩理论：价值差异通过容量有限的信息通道编码，导致表示扭曲，产生幂律关系。压缩程度由处理容量、长尾先验分布及目标权重决定。通过差异估计任务和食物/社会选择数据验证，为多属性决策非线性提供规范性信息论解释。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有解释多属性选择偏离加权加性规则时，多归因于偏差或启发式，缺乏理性基础。本文旨在从资源理性压缩角度提供规范性解释。
method: 提出资源理性压缩模型，预测价值差异的幂律扭曲；通过属性差异估计实验及重新分析食物、社会选择数据集进行检验。
result: 实验和再分析支持幂律压缩预测，证实容量限制、先验分布和目标权重共同决定压缩程度及选择行为非线性。
conclusion: 多属性决策非线性可被信息论视角下的资源理性压缩统一解释，表明目标与认知容量交互塑造表征精度，影响决策质量。
---

## 摘要
为什么多属性选择如此频繁地偏离经典的加权相加决策规则？我们不是将这些偏差仅仅归因于偏见或启发式，而是提出一种资源理性解释，其中价值差异通过容量有限的信息通道进行编码。在资源理性压缩下，这些差异表征被系统性地扭曲，导致行为偏离加权相加预测，因为价值差异并未被真实表征。这一理论解释对真实差异与内部表征差异之间的幂律关系做出了可检验的预测。幂律压缩的程度由信息处理容量、属性差异上涌现的长尾先验分布以及在选择情境中决定有限容量在属性通道间分配的目标依赖主观权重所决定。我们在一个属性差异估计任务中，并通过重新分析现有的食物和社会选择数据集，检验并发现了对这些预测的支持。这些结果为多属性决策中系统性非线性的规范性、信息论解释提供了汇聚性证据。它们共同展示了目标如何与认知容量和先验相互作用，以可能促进或损害决策的方式塑造表征精度。

## Abstract
Why do multi-attribute choices so often depart from classical weighted-additive decision rules? Rather than attributing such deviations solely to biases or heuristics, we propose a resource-rational account in which value differences are encoded via capacity-limited information channels. Under resource-rational compression, these difference representations are systematically distorted, such that behavior deviates from weighted-additive predictions because value differences are not represented veridically. This theoretical account makes testable predictions about power-law relationships between true and internally represented differences. The amount of power-law-like compression is determined by information-processing capacity, emergent long-tailed prior distributions over attribute differences, and, in choice contexts, goal-dependent subjective weights that govern the allocation of limited capacity across attribute channels. We test and find support for these predictions in an attribute difference-estimation task and by reanalyzing existing food- and social-choice datasets. These results provide converging evidence for a normative, information-theoretic account of systematic nonlinearities in multi-attribute decision making. Together they show how goals can interact with cognitive capacity and priors to shape representational precision in ways that may facilitate or impair decision making.

---

## 论文详细总结（自动生成）

### 论文详细总结

#### 1. 论文的核心问题与整体含义（研究动机与背景）
- **核心问题**：为什么多属性选择会频繁偏离经典的加权相加（WADD）决策规则？传统解释多归因于认知偏差或启发式，但这些解释缺乏规范性基础。
- **整体含义**：本文提出一种**资源理性压缩（resource-rational compression）**框架，从信息论角度将偏差视为理性适应认知容量限制的结果。价值差异通过容量有限的信息通道编码，导致表示系统性地扭曲（产生幂律关系），从而解释了WADD预测偏离的非线性行为。该理论统一了目标、容量与先验对决策的影响，为多属性决策中的系统性非线性提供了规范性解释。

#### 2. 论文提出的方法论
- **核心思想**：决策时，多属性间的价值差异并非真实表征，而是在容量有限的感知/认知通道中被压缩编码，遵循信息论中的**率失真理论**。压缩程度取决于处理容量、属性差异的**长尾先验分布**以及目标依赖的主观权重（决定容量在不同属性间的分配）。压缩后的内部表征与真实差异之间呈现**幂律关系**（幂指数小于1）。
- **关键技术细节**：
  - 模型预测：真实差异 \(d\) 与内部表征差异 \(\hat{d}\) 满足 \(\hat{d} \propto d^\alpha\)，其中 \(\alpha\) 反映压缩程度（\(\alpha<1\)）。
  - 压缩程度由容量、先验分布形状（长尾）、目标权重共同决定：容量越小、先验越分散、目标权重越低，\(\alpha\) 越小（压缩越强）。
- **公式或算法流程（文字说明）**：未提供具体公式，但抽象描述为资源理性压缩模型（resource-rational compression model），通过率失真理论推导幂律扭曲预测。

#### 3. 实验设计
- **数据集/场景**：
  1. **属性差异估计任务**：被试直接估计属性差异，以检验内部表征是否呈幂律压缩。
  2. **现有食物选择数据集**：重分析前人研究中食物选择的决策数据。
  3. **现有社会选择数据集**：重分析社会偏好决策数据（如信任游戏或社会价值判断）。
- **Benchmark**：未明确指定基准模型。理论预测对比的应是经典的加权加性（WADD）模型，但文中未报告定量比较结果（如准确率提升）。实验主要检验幂律关系预测是否成立。
- **对比方法**：未提及具体对比方法（如启发式模型、线性模型等）。论文核心是验证理论预测，而非在性能上超越现有模型。

#### 4. 资源与算力
- **未提及**：文中没有说明使用了多少GPU、训练时长或算力资源。鉴于实验为行为实验和已有数据集的再分析，可能无需大规模计算资源。

#### 5. 实验数量与充分性
- **实验数量**：共三类数据来源：一个自设计的差异估计任务 + 两个现有数据集（食物与社会选择）的再分析。未报告具体子实验数量或消融实验。
- **充分性**：从摘要来看，实验覆盖了感知估计（差异任务）和实际选择（食物、社会）两类场景，提供了一定汇聚证据。但缺乏：
  - 与替代模型（如启发式、非线性效用模型）的系统比较。
  - 对容量、先验、权重等关键参数的操纵验证。
  - 统计检验细节（效应量、置信区间）。
- **客观性与公平性**：论文声称结果支持预测，但限于摘要信息，无法评估数据选择、分析流程是否无偏。需谨慎。

#### 6. 论文的主要结论与发现
- **主要结论**：
  - 多属性决策中的非线性行为（偏离WADD）可以被资源理性压缩的信息论框架统一解释。
  - 行为数据支持属性差异的内部表征存在幂律压缩，压缩程度受认知容量、先验分布和目标权重调节。
  - 目标（动机）通过与认知容量和先验的交互，塑造了表征精度，可能促进也可能损害决策质量。

#### 7. 优点
- **理论创新**：从信息论（资源理性）角度为决策偏差提供规范性解释，超越传统的“偏差/启发式”观点，具有更强的理论基础。
- **跨场景验证**：结合自建任务与两个不同领域的现有数据集（食物选择、社会选择），增加了结论的泛化性。
- **可检验性**：理论给出了明确的可检验预测（幂律关系），便于后续实验证伪。

#### 8. 不足与局限
- **信息不完整**：由于仅基于摘要，无法评估全文的实验细节、统计方法、鲁棒性测试等。
- **缺乏竞争性比较**：未与已有解释模型（如概率抽样模型、非线性效用理论）进行定量对比，说服力不足。
- **未操纵关键变量**：摘要未提及对容量、先验、权重的直接实验操纵，主要依赖已有数据集的再分析，因果证据较弱。
- **可能偏差风险**：幂律关系在行为数据中很容易被其他因素（如回归效应、测量噪声）所模仿，需更严格的控制。
- **应用限制**：结论基于实验室或自选数据集，是否适用于高 stakes 现实决策（如医疗、金融）尚需验证。

（完）
