---
title: "VaxjoGNN: A Graph Neural Network for Ontology-Grounded Vaccine Adjuvant Recommendation"
title_zh: VaxjoGNN：一种基于本体论的疫苗佐剂推荐图神经网络
authors: "He, Y., Zheng, Y."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.27.690985v3.full.pdf"
tags: ["query:recsys"]
score: 8.0
evidence: 使用基于知识图谱的图神经网络进行疫苗佐剂top-k推荐
tldr: "疫苗佐剂筛选是开发瓶颈，现有计算多关注抗原。本文将疾病-佐剂匹配转化为异构知识图谱上的推荐任务，引入VaxjoGNN模型，采用列表级排序目标训练。在公开基准上，对已知疾病NDCG@10达0.59，对未知疾病达0.27，比随机基线提升5.4倍。该框架基于本体，为佐剂优先排序提供了新途径，可与抗原工具互补。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-27-690985-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1610, \"height\": 1108, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-27-690985-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1590, \"height\": 1147, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-11-27-690985-v3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 997, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-11-27-690985-v3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1078, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-11-27-690985-v3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1107, \"height\": 240, \"label\": \"Table\"}]"
motivation: 佐剂选择依赖经验，缺乏计算工具，而现有研究多聚焦抗原发现。
method: 构建基于本体的异构知识图谱，使用VaxjoGNN进行列表级排序推荐。
result: "公开基准上，已知疾病NDCG@10为0.59，未知疾病为0.27。"
conclusion: 提供本体驱动的佐剂推荐框架，有效补充抗原发现工具。
---

## 摘要
选择有效的佐剂仍是疫苗开发的瓶颈，但大多数计算工作集中于抗原发现而非佐剂优先级排序。我们将疾病-佐剂匹配视为基于生物医学本体论的异构知识图上的top-k推荐任务，整合了整理的事实、机制通路和文本证据。我们引入了VaxjoGNN，一种使用列表式排序目标训练的图神经网络。在一个公开基准上，VaxjoGNN在已知疾病上实现了0.59的NDCG@10，在先前未见过的疾病上实现了0.27（比随机基线提高了5.4倍）。该框架提供了一种基于本体的佐剂优先级排序方法，补充了现有的以抗原为中心的工具。

## Abstract
Selecting an effective adjuvant remains a bottleneck in vaccine development, but most computational efforts have targeted antigen discovery rather than adjuvant prioritization. We frame disease-adjuvant matching as a top-k recommendation task on a heterogeneous knowledge graph grounded in biomedical ontologies, integrating curated facts, mechanistic pathways, and textual evidence. We introduce VaxjoGNN, a graph neural network trained with a listwise ranking objective. On a public benchmark, VaxjoGNN achieves NDCG@10 of 0.59 on seen diseases and 0.27 on previously unseen diseases (a 5.4x improvement over a random baseline). The framework provides an ontology-anchored approach to adjuvant prioritization that complements existing antigen-focused tools.