---
title: Inverse reinforcement learning reveals action-oriented value signals in naturalistic decision making
title_zh: 逆强化学习揭示自然决策中的行动导向价值信号
authors: "Lee, S. H., Chung, C., Oh, M.-h., Ahn, W.-Y."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.733779v1.full.pdf"
tags: ["query:pref-learn"]
score: 9.0
evidence: 使用逆强化学习从自然决策中推断奖励轨迹
tldr: 自然主义决策中价值计算是认知神经科学的挑战。标准计算模型难以适应实时行为。该研究使用逆强化学习(IRL)从fMRI扫描下的实时驾驶行为推断潜在奖励轨迹，发现其与背侧纹状体等脑区活动相关，表明IRL奖励可作为行为驱动的动作导向价值信号代理。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1611, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1609, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1608, \"height\": 1344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1598, \"height\": 1559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1617, \"height\": 1174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1616, \"height\": 1181, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1694, \"height\": 1492, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-24-733779-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 228, \"label\": \"Table\"}]"
motivation: 探索自然主义决策中大脑如何实时计算动作导向价值，克服传统模型在复杂环境中的局限。
method: 在fMRI扫描下的实时驾驶任务中，应用逆强化学习从观测行为推断每一时刻的奖励轨迹。
result: IRL奖励轨迹与背侧纹状体活动最强相关，并涉及认知控制和感觉运动处理等广泛脑区。
conclusion: IRL奖励提供了自然主义决策中动作导向价值的、行为驱动的、时间分辨的神经表征。
---

## 摘要
认知神经科学的一个主要挑战是解释在复杂和自然环境中的目标导向行为的价值是如何计算的。标准的决策计算模型在受控的、基于试验的范式中非常成功，但它们通常不适用于自然范式中实时展开的行为。逆强化学习（IRL）提供了一种从自然环境中观察到的行为推断潜在评估状态的方法，但其神经可解释性在很大程度上尚不清楚。本研究探讨了在fMRI扫描过程中进行实时驾驶任务时，从IRL导出的瞬时奖励轨迹是否映射到大脑中的价值信号。IRL导出的奖励轨迹与背侧纹状体（一个常与价值引导的行动选择相关的区域）的活动关联最为显著。它们还与支持其他过程（包括认知控制和感觉运动处理）的分布式区域显示出关联。这种模式表明，IRL奖励捕捉了以奖赏回路为中心的分布式神经活动，可能反映了估值如何与其他过程相互作用。总之，这些发现表明，IRL奖励为自然决策中的行动导向估值提供了一个行为学上可验证的、时间上可解析的代理。

## Abstract
A major challenge for cognitive neuroscience is to explain how value of a goal-directed behavior is computed in complex and naturalistic environments. Standard computational models of decision making have been highly successful in controlled, trial-based paradigms, but they are often ill-suited to real-time behavior unfolding in naturalistic paradigms. Inverse reinforcement learning (IRL) offers a way to infer latent evaluative state from observed behavior in naturalistic environments, but its neural interpretability remains largely unknown. Here, we investigated whether moment-to-moment reward trajectories derived from IRL map onto value signals in the brain during a real-time driving task performed during fMRI scanning. IRL-derived reward trajectories were most robustly associated with activity in the dorsal striatum, a region often linked to value-guided action selection. They also showed associations with distributed regions supporting additional processes, including cognitive control and sensorimotor processing. This pattern suggests that IRL reward captures distributed neural activity centered on the reward circuitry, potentially reflecting how valuation interacts with other processes. Together, these findings suggest that IRL reward provides a behaviorally grounded, temporally resolved proxy for action-oriented valuation during naturalistic decision making.