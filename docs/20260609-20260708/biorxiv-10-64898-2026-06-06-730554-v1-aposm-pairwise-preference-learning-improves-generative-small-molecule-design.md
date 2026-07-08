---
title: "APOSM: Pairwise preference learning improves generative small-molecule design"
title_zh: APOSM：成对偏好学习改进生成式小分子设计
authors: "Dreisler, M. W., Michael, R., Hatzakis, N. S., Boomsma, W."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.06.730554v1.full.pdf"
tags: ["query:pref-learn"]
score: 9.0
evidence: 成对偏好学习用于分子设计
tldr: 小分子设计受限于筛选数据的噪声和稀疏性，传统绝对评分代理模型可靠性不足。APOSM采用成对偏好学习替代绝对回归，结合片段生成器与图神经网络代理，在主动学习循环中利用概率排名进行批量候选选择。在标准分子优化基准和GPCR配体重发现任务中，APOSM显著提升目标达成率和采样效率。该方法在绝对评分难以校准的任务上优势尤为明显，为高成本小分子设计提供了更可靠的方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 筛选数据的噪声和稀疏性限制了传统绝对评分代理模型的可靠性，亟需更鲁棒的候选排序方法。
method: 提出APOSM主动学习算法，集成片段生成器与成对消息传递图神经网络，通过概率排名进行批量选择。
result: 在PMO基准和GPCR重发现任务上，APOSM在目标达成率和采样效率上全面超越片段优化、Graph-GA及逐点回归变体。
conclusion: 成对偏好学习能有效提升小分子设计代理模型的信号可靠性，尤其适用于绝对评分校准困难的场景。
---

## 摘要
小分子先导化合物的优化受限于合成与测定候选分子的成本，这使得优先排序化合物用于实验测试的替代模型成为设计过程的核心。此类替代模型的可靠性受到筛选测量噪声和稀疏性的限制。我们证明，在候选分子间进行成对比较（而非基于绝对预测分数）来训练替代模型，能在该场景下为活性候选物筛选提供更可靠的信号。我们开发了APOSM，一种主动学习算法，结合了基于片段的生成器、成对消息传递图神经网络替代模型以及批量获取循环中的概率排序。在Practical Molecular Optimization基准测试和GPCR配体重新发现任务中，APOSM在目标达成率和采样效率上优于无指导的基于片段优化、Graph-GA遗传算法以及逐点回归消融方法，且在绝对分数最难校准的任务上提升最大。

## Abstract
Small-molecule lead refinement is constrained by the cost of synthesizing and assaying candidates, making the surrogate models that prioritize compounds for experimental testing central to the design process. The reliability of such surrogates is limited by the noise and sparsity of screening measurements. We show that training the surrogate on pairwise comparisons between candidate molecules, rather than on absolute predicted scores, yields a substantially more reliable signal for active candidate selection in this regime. We develop APOSM, an active-learning algorithm that combines a fragment-based generator, a pairwise message-passing graph neural network surrogate, and probabilistic ranking inside a batched acquisition loop. On the Practical Molecular Optimization benchmark and a GPCR ligand rediscovery task, APOSM improves target attainment and sampling efficiency over unguided fragment-based optimization, the Graph-GA genetic algorithm, and a pointwise-regression ablation, with the largest gains on tasks where absolute scores are hardest to calibrate.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
小分子先导化合物的优化受制于合成与生物测试的高昂成本，因此依赖代理模型（surrogate model）来对候选化合物进行优先级排序，以指导实验测试。然而，实际筛选数据通常噪声大且稀疏，导致基于绝对分数（如IC50预测）训练的代理模型可靠性不足。作者提出，在低数据环境下，学习分子间的成对比较（哪一个更优）比学习绝对数值更鲁棒，因为即使数据量不足以校准绝对分数，仍能有效区分候选物的相对优劣。这一思路借鉴了蛋白质工程中定向进化（iterative comparative selection）的成功经验。

### 2. 论文提出的方法论：核心思想、关键技术细节
**核心思想**：将小分子先导优化视为偏好引导的主动学习问题，使用成对偏好监督替代传统的绝对回归监督，并与片段生成器结合形成迭代优化循环。

**关键技术细节**：
- **生成器**：采用CReM（Chemically Reasonable Mutations），基于ChEMBL片段库对当前种群进行局部结构扰动（替换一个连接子片段），参数为上下文半径r=1（最宽松设置）。
- **代理模型**：基于消息传递图神经网络（MPGNN），共享编码器对输入分子对 `(s_i, s_j)` 分别编码，得到嵌入后通过偏好头（MLP）输出单一标量logit `z_{ij}`。训练使用二进制交叉熵损失，标签 `t_{ij} = 1[Δy_{ij} > 0]`（Δy为真实分数差）。训练样本均匀采样自已标注分子对，排除太接近的平局（|Δy| < ε_Δ）。
- **全局排序**：将代理模型输出的成对偏好logit转化为全局排名，采用Bradley-Terry模型，通过Iterative Luce Spectral Ranking（ILSR）算法快速求解最大似然估计，得到每个候选物的参数π。为控制计算成本，先对每个父代候选保留top-K子代，再在短列表上运行全局排序，并设置多样性上限（单父代贡献不超过25%）。
- **主动学习循环**：每一轮：1) 用CReM生成子代；2) 用代理模型计算成对偏好；3) 全局排序选取top子集；4) 查询oracle（真实评估）；5) 将新标注数据加入训练集，重新训练代理模型。

**算法流程（文字描述）**：
初始化：初始数据集D0，预算b0。
循环直至预算用尽：
- 从当前种群生成子代（CReM）。
- 若标注数据不足，直接查询oracle；否则：
  - 对每个父代，用代理模型选出top-K子代比较对。
  - 对比较对进行重要性采样至固定数量c_max。
  - 过滤低置信度比较（|Δˆy| < ε_Δ）。
  - 用ILSR从偏好中估算全局参数π。
  - 选取π最高的k个候选，查询oracle。
- 更新数据集，重新训练代理模型。

### 3. 实验设计
**数据集/场景**：
- **PMO基准（Practical Molecular Optimization）**：包含25个任务，覆盖相似度（Similarity）、多参数优化（MPO）、重发现（Rediscovery）、骨架跳跃（Hop）、对接（Dock）、单个性质优化（Optimize）等。每个任务从单个未评分分子开始，总Oracle预算1000次评估。
- **GPCR配体重发现任务**：使用GPCRdb中多巴胺受体配体数据，随机选取一个高亲和力配体作为目标，给予300个已知配体作为初始训练集，目标为最大化与目标分子的Tanimoto相似度（ECFP4）。

**对比方法**：
- Unguided fragment-based optimization（无引导的CReM）
- Graph-GA（图遗传算法，强基线）
- Pointwise ablation（点状Chemprop回归模型，其余组件与APOSM相同）

**评估指标**：每个generation的平均分数、累计best-so-far、分布对齐（KL散度、MMD）。GPCR中还使用了二维投影轨迹和多样性度量。

### 4. 资源与算力
论文未明确说明使用的GPU型号、数量、训练时长。仅致谢中提到资助机构，未提及计算资源信息。

### 5. 实验数量与充分性
- **GPCR场景**：使用5个不同随机种子，报告了均值与标准差。
- **PMO场景**：25个任务，每个任务多种子（表1中给出±std），结果按任务组聚合。
- **预验证实验**（Preflight surrogate validation）：对每个PMO任务先生成一个多样化的化合物池，按OOD-1协议（每个测试对中有一个分子不在训练对中）评估代理模型的成对符号准确率和Spearman秩相关系数。
- 消融实验：对比成对偏好代理与点状回归代理。
- 实验覆盖了多种优化目标类型，使用了多个基线，比较公平（共享生成器、相同循环结构等）。实验数量较充分，统计上报告了变异。

### 6. 论文的主要结论与发现
- 成对偏好学习在低数据场景下比绝对回归更可靠，且这种可靠性能转化为主动学习循环中的优化效率提升。
- 在PMO基准上，APOSM在大多数任务组（相似度、MPO、重发现、骨架跳跃、对接）优于Graph-GA和无引导CReM，在性质优化上持平。点状消融在整体上略逊于APOSM，但差异较小。
- 在GPCR任务中，APOSM更紧密地沿着高适应度脊线探索，达到更高的mean分数和累计best-so-far，多样性低于Graph-GA（反映聚焦搜索）。
- 分布对齐分析显示，APOSM的分数分布更接近ENAMINE合成候选高分分布（MPO组除外）。
- 代理级验证表明，成对偏好符号准确率在大部分任务上高于点状回归，且在绝对回归难校准的任务上优势最明显。

### 7. 优点
- **方法论创新**：将成对偏好学习与主动学习、全局概率排名结合，适应湿实验批量筛选节奏。
- **生成器无关**：框架可替换任何分子生成器，通用性强。
- **鲁棒性强**：偏好目标对噪声不敏感，尤其适合低数据、高噪声的真实筛选场景。
- **实验设计严谨**：进行了预验证、多任务、多种子、消融实验，并报告分布对齐指标，全面评估性能。
- **效率优先级**：使用两阶段排名（per-parent top-K + 全局BT）和ILSR算法，在约10^5量级比较下保持可行。
- **可解释性**：通过化学空间投影和多样性分析直观展示搜索行为。

### 8. 不足与局限
- **未在真实湿实验数据上验证**：所有评估均基于模拟oracle（如Tanimoto、计算对接），实际噪声分布可能与模拟不同。
- **MPO任务上分布对齐效果差**：作者认为复合目标压缩了分数分布，偏好信号不如单目标直接，可能需要显式Pareto处理。
- **点状消融对比不完全公平**：点状代理使用Chemprop（不同架构），虽然同为图神经网络，但超参数未对齐。
- **计算资源未报告**：无法评估方法的实际部署成本。
- **仅测试了CReM生成器**：虽然声称生成器无关，但实验中仅用CReM，未验证其他生成器（如REINVENT、扩散模型）的表现。
- **GPCR目标单一**：仅使用Tanimoto相似度作为代理，未探索其他活性度量。
- **未讨论合成可行性**：虽然CReM保证一定合成合理性，但未使用合成可及性分数进行筛选。

（完）
