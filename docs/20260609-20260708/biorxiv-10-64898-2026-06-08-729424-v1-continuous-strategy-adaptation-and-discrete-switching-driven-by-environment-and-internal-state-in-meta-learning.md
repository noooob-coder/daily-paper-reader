---
title: Continuous Strategy Adaptation and Discrete Switching Driven by Environment and Internal State in Meta-Learning
title_zh: 元学习中由环境和内部状态驱动的连续策略适应与离散切换
authors: "Chen, J., Taira, M., Doya, K."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.729424v1.full.pdf"
tags: ["query:decision"]
score: 6.0
evidence: 使用RL模型分析两步决策任务中的策略适应
tldr: 环境和内部状态共同驱动行为策略的连续调整与离散切换。本研究结合stay-switch概率分析、广义线性混合模型、带时变元参数的强化学习模型（多步粒子滤波）以及有限内态模型，分析小鼠在两步决策任务中的行为。结果发现，学习进程促使策略转向基于模型、基于价值的模式，并伴随选择坚持性增强；不确定奖励环境则引发随机探索行为。元参数动态揭示了策略的连续变化，而状态转换捕获了试次间的离散模式切换。研究揭示了策略适应的多层次机制，为元学习中的灵活行为调控提供了新见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究环境和内状态如何驱动策略的连续与离散切换，从而理解元学习中的灵活适应机制。
method: 结合四种方法分析小鼠两步决策行为：stay-switch概率分析、GLMM、时变元参数RL模型（粒子滤波）以及有限内态模型。
result: 学习进程促进基于模型的策略；不确定奖励引发探索；元参数反映连续变化，状态转换捕获离散切换。
conclusion: 策略适应包含连续和离散过程，在奖励变化时小鼠在自重复状态与模型化策略间切换，表现出不完全适应。
---

## 摘要
行为策略可以根据环境和内部状态逐渐或突然地改变，从而实现灵活适应。这种策略调节是元学习（即学习如何学习的能力）的核心。以往的研究使用假设连续或离散变化的模型和理论分析了时间或条件依赖的策略变化。本文通过四种不同方法分析小鼠在两步决策任务中的行为：停留-切换选择概率分析；基于先前任务事件的选择和反应时间的广义线性混合模型（GLMM）；通过一种新颖的多步粒子滤波方法拟合具有时变元参数的强化学习（RL）模型；以及拟合一个有限内部状态（FIS）模型，该模型根据离散状态转换产生选择和反应时间。综合来看，停留概率和GLMM分析表明，学习进展促使向基于模型、基于价值的学习策略转变，同时伴随着选择坚持的增加。更不确定的奖励设置或其变化导致随机、探索性的行为。元参数动态显示，随着学习的进行，学习速度加快，基于模型的策略参与度增加，选择随机性增强，选择坚持更快发展，但对最终决策的贡献减少。面对不确定的奖励设置或其变化时的探索行为，其基础是更慢的遗忘和更大的基于模型的贡献。FIS模型发现了一个试次级别的切换，即在最优的基于价值的学习状态和次优的自我重复状态之间切换。元参数动态反映了连续策略变化，而状态转换则捕捉了突然的离散策略切换。在中等时间尺度上，当奖励设置发生变化时，两个过程相互作用：小鼠坚持自我重复状态，导致尝试适应不完整的基于模型的策略。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWBehavioral strategies can change in response to environmental and internal states, either gradually or abruptly, enabling flexible adaptation. Such strategy regulation is central to meta-learning, the ability to learn to learn. Previous studies analyzed temporal or condition-dependent strategy change using models and theories that assume continuous or discrete changes. Here, we analyze the mices behavior in a two-step decision task using four different approaches: stay-switch choice probability analysis; generalized linear mixed model (GLMM) of choice and reaction time (RT) given preceding task events; fitting a reinforcement learning (RL) model with time-varying meta-parameter by a novel multiple-step particle filtering method; and fitting a finite internal state (FIS) model that produces choice and RT depending on discrete state transition. Together, the stay probability and GLMM analyses reveal that learning progress encourages a shift toward a model-based, value-based learning strategy, accompanied by elevated choice perseveration. More uncertain reward settings or changes in them lead to random, exploratory behavior. Meta-parameter dynamics show faster learning, greater involvement of a model-based strategy, higher choice stochasticity, and more rapid development of choice perseveration with less contribution to the final decision as learning progresses. Exploratory behavior in the face of uncertain reward settings or changes in those settings is underpinned by slower forgetting and greater model-based contribution. FIS modeling discovered a trial-level switch between an optimal value-based learning state and a suboptimal self-repeating state. Meta-parameter dynamics reflect continuous strategy changes, while state transitions capture abrupt, discrete strategy switches. At an intermediate timescale, when reward settings change, two processes interact: mice persist in a self-repeating state, leading to attempts at model-based strategy with incomplete adaptation.