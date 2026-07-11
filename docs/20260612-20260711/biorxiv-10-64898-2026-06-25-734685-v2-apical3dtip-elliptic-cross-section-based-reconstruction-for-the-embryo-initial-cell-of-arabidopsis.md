---
title: "Apical3DTip: Elliptic Cross-section-based Reconstruction for the Embryo Initial Cell of Arabidopsis"
title_zh: "Apical3DTip: 基于椭圆截面的拟南芥胚胎初始细胞重建"
authors: "Nonoyama, T., Kang, Z., Hanaki, Y., Itagaki, Y., Matsumoto, H., Kimata, Y., Tsugawa, S., Ueda, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734685v2.full.pdf"
tags: ["query:d-mesh"]
score: 9.0
evidence: 基于椭圆横截面的3D重建，解决网格方法的方向保持问题
tldr: 拟南芥胚胎早期发育中细胞几何形状决定分裂方向，但动态3D定量分析受限于2D投影和复杂网格重建。本文提出Apical3DTip框架，通过标准化坐标系统和椭圆截面近似，从堆栈成像数据重建顶细胞3D形态。该方法无需手动校正网格，即可准确量化细胞形状各向异性和体积特征。为活体植物胚胎3D形态动力学提供简便、抗噪的定量平台，有助于探究几何与发育模式的关系。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1261, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1471, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1459, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1469, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 1186, \"label\": \"Figure\"}]"
motivation: 现有2D投影和网格重建方法难以定量分析拟南芥胚胎初始细胞的动态3D形态，需要一种简单抗噪的几何表征方法。
method: 基于底部平面和光轴标准化细胞方向，通过椭圆拟合序列截面重建顶细胞3D形态，避免复杂表面网格。
result: 成功量化顶细胞3D形状各向异性及后续分裂的容积特征，实现跨时间点的形态比较。
conclusion: Apical3DTip提供了无需手动校正的活细胞3D形态定量分析框架，支持胚胎发育模式研究。
---

## 摘要
背景：细胞几何形状在拟南芥早期胚胎发生过程中决定分裂方向和体轴形成中起核心作用。然而，动态三维(3D)形态的定量分析仍然具有挑战性，因为活体成像研究通常依赖于二维(2D)投影，而现有的3D重建方法（包括基于网格的方法）往往会丢失相对于胚珠的原始方向信息，并需要耗费大量人工进行网格校正。此外，由于胚胎在液体培养基中漂浮和持续生长引起的位置波动，使得在共同坐标系中分析时间形态变化变得困难。

结果：我们开发了一个稳健的框架，用于胚胎初始细胞（顶端细胞）形态的定量三维和四维(4D; 3D + 时间)分析。该方法首先通过基于底面和观察光轴归一化细胞方向，建立一个标准化的3D坐标系。然后通过基于椭圆的近似方法重建从堆叠成像数据中提取的连续截面上的细胞形态，从而无需复杂的表面网格重建即可实现准确的几何表征。为了评估形状各向异性，我们量化了顶端细胞在3D中的形状。该框架还支持后续分裂的体积特征表征，为量化3D胚胎发生提供了基础。

结论：我们的框架为活细胞形态的3D定量分析提供了一种简单且降噪的方法。我们将坐标归一化与基于椭圆截面的重建相结合的方法命名为Apical3DTip。该方法无需大量手动校正即可实现细胞形状的一致比较。该方法克服了基于2D投影和依赖网格的分析的关键限制，并为定量细胞形状和子细胞形状的3D提供了实用平台。更广泛地说，它为探索活体植物胚胎中细胞几何形状、形态动力学和发育模式之间的关系提供了定量基础。

## Abstract
BackgroundCell geometry plays a central role in determining division orientation and body axis formation during early embryogenesis in Arabidopsis thaliana. However, quantitative analysis of dynamic three-dimensional (3D) morphology remains challenging because live-imaging studies often rely on two-dimensional (2D) projections, while existing 3D reconstruction approaches, including mesh-based methods, often lose the original orientation information relative to the ovule and require labor-intensive mesh correction. In addition, embryo positional fluctuation caused by floating in liquid medium and continuous growth makes it difficult to analyze temporal morphological changes within a common coordinate system.

ResultsWe developed a robust framework for quantitative 3D and four-dimensional (4D; 3D + time) analysis of embryo initial cell (apical cell) morphology. The method first establishes a standardized 3D coordinate system by normalizing cell orientation based on the bottom plane and the optical axis of the observation. Cell morphology is then reconstructed through ellipse-based approximation of serial cross-sections extracted from stacked imaging data, enabling accurate geometric characterization without the need for complex surface mesh reconstruction. To evaluate shape anisotropy, we quantified the apical cell shape in 3D. The framework further supports the characterization of volumetric features of subsequent division, providing a basis for quantifying 3D embryogenesis.

ConclusionOur framework provides a simple and noise-reduced approach for quantitative analysis of living cell morphology in 3D. We named the integrated method of combining coordinate normalization with elliptical cross-section-based reconstruction Apical3DTip. This method enables consistent comparison of cell shapes without extensive manual corrections. The method overcomes key limitations of 2D projection-based and mesh-dependent analyses and offers a practical platform for quantifying cell shape and daughter cell shapes in 3D. More broadly, it provides a quantitative foundation for exploring the relationship between cell geometry, morphodynamics, and developmental patterning in living plant embryos.