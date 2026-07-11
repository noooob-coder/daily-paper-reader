---
title: "Apical3DTip: Elliptic Cross-section-based Reconstruction for the Embryo Initial Cell of Arabidopsis"
title_zh: Apical3DTip：基于椭圆截面的拟南芥胚胎初始细胞三维重建
authors: "Nonoyama, T., Kang, Z., Hanaki, Y., Itagaki, Y., Matsumoto, H., Kimata, Y., Tsugawa, S., Ueda, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734685v2.full.pdf"
tags: ["query:d-mesh"]
score: 8.0
evidence: 基于椭圆截面的拟南芥胚胎初始细胞3D重建（使用网格方法）
tldr: 拟南芥早期胚胎发生中细胞几何形状决定分裂方向和体轴形成，但现有3D重建依赖2D投影或复杂网格，丢失方向信息且需手动校正。本文提出Apical3DTip框架：先标准化坐标系，再基于椭圆截面近似重建细胞形态，免去网格重建。该方法实现对顶端细胞形状各向异性的3D量化，并支持后续分裂体积分析，为活体胚胎形态动态研究提供简便降噪的定量平台。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1261, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1471, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1459, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1469, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 1186, \"label\": \"Figure\"}]"
motivation: 现有2D投影和网格重建方法难以准确分析胚胎初始细胞的动态3D形态，且缺乏统一坐标系，亟需鲁棒的4D定量框架。
method: 建立标准化坐标系（底平面+光轴），从堆栈图像提取椭圆截面近似重构细胞形态，无需表面网格。
result: 成功量化顶端细胞3D形状各向异性，并表征分裂后子细胞体积特征，克服了2D与网格依赖的局限性。
conclusion: Apical3DTip提供简便降噪的活细胞3D形态定量方法，为探究细胞几何与发育模式关系建立基础。
---

## 摘要
背景细胞几何结构在拟南芥早期胚胎发生中决定分裂方向和体轴形成中起着核心作用。然而，由于活体成像研究通常依赖二维（2D）投影，而现有的三维重建方法（包括基于网格的方法）往往丢失相对于胚珠的原始方向信息且需要大量人工网格校正，因此动态三维（3D）形态的定量分析仍具挑战。此外，胚胎在液体培养基中浮动和持续生长引起的位置波动，使得难以在共同坐标系中分析时间形态变化。

结果我们开发了一个用于胚胎初始细胞（顶端细胞）形态定量三维和四维（4D；3D+时间）分析的稳健框架。该方法首先通过基于底面和观察光轴归一化细胞方向，建立标准化的3D坐标系。然后通过基于椭圆的近似，对从堆叠成像数据中提取的连续截面进行细胞形态重建，从而无需复杂的表面网格重建即可实现精确的几何表征。为了评估形状各向异性，我们对顶端细胞形状进行了3D量化。该框架进一步支持后续分裂的体积特征表征，为量化3D胚胎发生提供了基础。

结论我们的框架为活细胞形态的3D定量分析提供了一种简单且降噪的方法。我们将坐标归一化与基于椭圆截面的重建相结合的方法命名为Apical3DTip。该方法无需大量人工校正即可实现细胞形状的一致比较。该方法克服了基于2D投影和依赖网格的分析的关键局限性，并为量化3D中的细胞形状和子细胞形状提供了一个实用平台。更广泛地说，它为探索活体植物胚胎中细胞几何结构、形态动力学和发育模式之间的关系提供了定量基础。

## Abstract
BackgroundCell geometry plays a central role in determining division orientation and body axis formation during early embryogenesis in Arabidopsis thaliana. However, quantitative analysis of dynamic three-dimensional (3D) morphology remains challenging because live-imaging studies often rely on two-dimensional (2D) projections, while existing 3D reconstruction approaches, including mesh-based methods, often lose the original orientation information relative to the ovule and require labor-intensive mesh correction. In addition, embryo positional fluctuation caused by floating in liquid medium and continuous growth makes it difficult to analyze temporal morphological changes within a common coordinate system.

ResultsWe developed a robust framework for quantitative 3D and four-dimensional (4D; 3D + time) analysis of embryo initial cell (apical cell) morphology. The method first establishes a standardized 3D coordinate system by normalizing cell orientation based on the bottom plane and the optical axis of the observation. Cell morphology is then reconstructed through ellipse-based approximation of serial cross-sections extracted from stacked imaging data, enabling accurate geometric characterization without the need for complex surface mesh reconstruction. To evaluate shape anisotropy, we quantified the apical cell shape in 3D. The framework further supports the characterization of volumetric features of subsequent division, providing a basis for quantifying 3D embryogenesis.

ConclusionOur framework provides a simple and noise-reduced approach for quantitative analysis of living cell morphology in 3D. We named the integrated method of combining coordinate normalization with elliptical cross-section-based reconstruction Apical3DTip. This method enables consistent comparison of cell shapes without extensive manual corrections. The method overcomes key limitations of 2D projection-based and mesh-dependent analyses and offers a practical platform for quantifying cell shape and daughter cell shapes in 3D. More broadly, it provides a quantitative foundation for exploring the relationship between cell geometry, morphodynamics, and developmental patterning in living plant embryos.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：在拟南芥早期胚胎发生中，细胞几何结构（尤其是顶端细胞）决定了分裂方向和体轴形成。然而，现有的活体成像研究主要依赖二维（2D）投影，无法准确捕捉三维（3D）动态形态；已有的3D重建方法（如基于网格的方法）存在两大局限：
  - 丢失相对于胚珠的原始方向信息；
  - 需要大量人工网格校正，且难以处理胚胎在液体培养基中的浮动和生长引起的位置波动。
- **核心问题**：缺乏一个鲁棒的、标准化的3D/4D定量分析框架，用于统一坐标系下量化胚胎初始细胞的形态变化。
- **整体含义**：开发一种简便、降噪且无需复杂网格重建的方法（Apical3DTip），为理解细胞几何与发育模式之间的关系提供定量基础。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过标准化坐标系 + 基于椭圆截面的近似重建，替代传统的2D投影和网格重建。
- **关键技术细节**：
  1. **坐标标准化**：基于胚胎的底面（bottom plane）和观察光轴（optical axis）建立标准化3D坐标系，消除因胚胎浮动和生长导致的位置漂移。
  2. **椭圆截面近似**：从堆栈成像数据中提取连续截面，用椭圆拟合每个截面的轮廓，从而重建细胞3D形态，无需构建表面网格。
  3. **形状各向异性量化**：在3D空间中对顶端细胞形状的各向异性进行量化。
  4. **分裂后体积特征**：该框架支持对后续分裂后的子细胞体积特征进行表征。
- **算法流程（文字说明）**：
  - 输入：活体显微镜获取的3D堆栈图像序列（4D数据）。
  - 步骤1：检测细胞底面（接触点），计算光轴方向，旋转平移使所有时间点的细胞对齐到共同坐标系。
  - 步骤2：沿光轴方向等间距切片，对每层切片提取细胞轮廓，用最小二乘法拟合椭圆。
  - 步骤3：组合所有椭圆截面形成重建的细胞形态（体积、表面积、各向异性指数等）。
  - 输出：标准化后的3D细胞形态及其随时间变化的量化参数。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：论文未明确说明数据来源细节，推测使用了拟南芥胚胎活体成像的共聚焦显微镜4D堆栈图像（时间序列）。可能为实验室自有数据集或公开数据。
- **基准（Benchmark）**：未明确提及标准基准。方法定性比较可能以传统2D投影分析或手动网格重建作为参考。
- **对比方法**：
  - 传统2D投影方法（丢失深度信息）。
  - 现有基于网格的3D重建方法（需人工校正，易丢失方向）。
  - 文中虽未列出具体对比方法名称，但通过分析精度、人工工作量、方向保持性等维度进行讨论。
- **实验设置**：主要针对顶端细胞的形状各向异性量化，以及分裂后子细胞体积分析。

## 4. 资源与算力

- **文中未明确说明使用的GPU型号、数量、训练时长等算力信息**。由于该方法不涉及深度学习或大规模计算，可能仅需普通CPU即可完成。但论文未提及任何硬件资源，因此只能指出这一缺失。

## 5. 实验数量与充分性

- **实验数量**：从文本描述看，可能使用了多个时间点的活体胚胎图像（如连续时间序列），但未给出具体样本量（如多少胚胎、多少时间点）。
- **消融实验**：未提及消融实验。方法本身为两步流程（坐标标准化 + 椭圆截面重建），但没有分别验证每一步的必要性。
- **充分性评估**：
  - **优点**：方法原理清晰，定性展示了重建效果和量化结果。
  - **不足**：缺乏定量对比指标（如重建误差、与传统方法的耗时比较、不同胚胎重复性统计等）；未报告与真实几何的误差衡量。实验覆盖面有限，仅针对顶端细胞，未验证其他细胞类型或物种。

## 6. 论文的主要结论与发现

- 成功开发了Apical3DTip框架，能够**在标准化坐标系下对拟南芥顶端细胞进行3D形态重建**。
- 该方法**免除了表面网格重建和大量手动校正**，显著简化了活体胚胎4D形态分析。
- 能够**量化细胞形状各向异性**，并**表征分裂后子细胞的体积特征**。
- 为探索细胞几何与发育模式之间的关系提供了**简单、降噪且可重复的定量平台**，克服了2D投影和网格依赖方法的局限性。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：将坐标标准化与椭圆截面近似结合，避免传统网格重建的复杂性和主观性。
- **实用性**：大幅减少人工干预，提高分析通量，适合长时序活体成像数据。
- **降噪能力**：椭圆拟合本身对轮廓噪声有一定的平滑作用。
- **可推广性**：原理可迁移至其他植物或动物胚胎的初始细胞分析。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制

- **实验覆盖有限**：仅针对拟南芥顶端细胞，未测试其他细胞类型或发育阶段，普适性未验证。
- **缺乏定量验证**：未与真实3D几何（如高分辨率电镜重建）或手动标注进行比较，重建精度未知。
- **椭圆拟合假设**：假设细胞截面近似为椭圆，对于非对称或形状畸变的细胞可能产生偏差。
- **坐标系依赖**：底面和光轴的检测准确性直接影响后续结果，若胚胎形态不规则，标准化可能引入误差。
- **算力与资源缺失**：未提供任何计算资源信息，不利于可复现性。
- **无公开代码/数据**：论文未提及代码或数据集是否开源，影响他人复现。

（完）
