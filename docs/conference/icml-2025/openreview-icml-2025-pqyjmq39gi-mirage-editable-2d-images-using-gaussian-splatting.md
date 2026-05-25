---
title: "MiraGe: Editable 2D Images using Gaussian Splatting"
title_zh: MiraGe：利用高斯溅射的可编辑二维图像
authors: "Joanna Waczynska, Tomasz Szczepanik, Piotr Borycki, Slawomir Tadeja, Thomas Bohné, Przemysław Spurek"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PQYJMq39gI"
tags: ["query:real-ir"]
score: 9.0
evidence: 使用镜面反射和平面控制高斯实现精确二维图像编辑
tldr: 该论文提出MiraGe方法，利用镜面反射将二维图像感知为三维空间，并运用平面控制高斯实现精确编辑，克服了传统隐式神经表示不可编辑的问题，在保持图像质量和压缩比的同时提供了灵活的编辑能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 676, \"height\": 928, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 826, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 827, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1685, \"height\": 1320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 757, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 833, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 808, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 735, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 852, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 815, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 820, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 861, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 810, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 758, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 785, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 824, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 836, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1782, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1512, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pqyjmq39gi/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1667, \"height\": 579, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pqyjmq39gi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1327, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pqyjmq39gi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1601, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pqyjmq39gi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1505, \"height\": 785, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pqyjmq39gi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1520, \"height\": 1350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pqyjmq39gi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1470, \"height\": 591, \"label\": \"Table\"}]"
motivation: 现有高斯表示方法（如GaussianImage）不支持图像编辑。
method: 使用镜面反射将二维图像引入三维空间，采用平面控制高斯进行编辑。
result: 在保持质量与压缩比的同时实现了精确的二维图像编辑。
conclusion: MiraGe为二维图像提供了一种可编辑的高斯表示新方式。
---

## Abstract
Implicit Neural Representations (INRs) approximate discrete data through continuous functions and are commonly used for encoding 2D images. Traditional image-based INRs employ neural networks to map pixel coordinates to RGB values, capturing shapes, colors, and textures within the network’s weights. Recently, GaussianImage has been proposed as an alternative, using Gaussian functions instead of neural networks to achieve comparable quality and compression. Such a solution obtains a quality and compression ratio similar to classical INR models but does not allow image modification. In contrast, our work introduces a novel method, MiraGe, which uses mirror reflections to perceive 2D images in 3D space and employs flat-controlled Gaussians for precise 2D image editing. Our approach improves the rendering quality and allows realistic image modifications, including human-inspired perception of photos in the 3D world. Thanks to modeling images in 3D space, we obtain the illusion of 3D-based modification in 2D images. We also show that our Gaussian representation can be easily combined with a physics engine to produce physics-based modification of 2D images. Consequently, MiraGe allows for better quality than the standard approach and natural modification of 2D images.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：传统的隐式神经表示（INR）和基于高斯函数的图像表示（如GaussianImage）能高效编码二维图像，但缺乏对图像内容的编辑能力，尤其是无法模拟人类将照片视为三维空间中平面对象并进行直观变换的感知方式。
- **整体含义**：研究者提出MiraGe，将二维图像视为三维空间中的平面，并使用参数化的平坦三维高斯（flat 3D Gaussians）来表示图像。通过镜面反射感知和由网格（triangle soup）驱动的高斯参数化，实现了高质量图像重建的同时，支持对图像的直观三维编辑和物理模拟，填补了高斯图像表示在可编辑性上的空白。

### 2. 论文提出的方法论
- **核心思想**：
  - 将二维图像置于三维空间的XZ平面，用一组平坦的三维高斯分布（一个缩放维度接近零）建模图像颜色和透明度。
  - 引入GaMeS参数化，将每个平坦高斯表示为一个三角面片（三个顶点定义），形成“三角形汤”（triangle soup），从而通过操作三角形顶点来直接编辑高斯的位置、旋转和缩放。
  - 训练时使用两个对向的“镜像相机”：一个相机渲染原图，另一个渲染水平翻转的镜像，迫使高斯分布在两个相机间保持合理空间约束，提升编辑后的质量。
  - 提出三种高斯运动控制模式：Amorphous（自由在三维空间移动）、2D（强制高斯中心位于XZ平面并旋转使其法向与Y轴对齐）、Graphite（允许沿Y轴少量漂移以维持正确遮挡顺序）。
- **关键技术细节与公式**：
  - 平坦高斯参数化：$\Sigma = R S S R^T$，其中$S = \text{diag}(\epsilon, s_2, s_3)$，$\epsilon$接近零。三角面片顶点$V = [v_1, v_2, v_3]$，其中$v_1 = m$，$v_2 = m + s_2 r_2$，$v_3 = m + s_3 r_3$，$m$为均值，$R=[r_1,r_2,r_3]$为旋转矩阵。
  - 训练损失：$L = (1-\lambda)L_1(I, GS(I)) + \lambda L_{\text{D-SSIM}}(I, GS(I))$，同时添加镜像损失$L(I)+L(M(I))$。
  - 三种高斯控制方案通过约束均值坐标和旋转实现不同空间自由度。
- **算法流程**：初始化高斯在XZ平面 → 通过镜像相机和图像重建损失优化高斯参数（均值、旋转、缩放、透明度、球谐颜色）→ 优化过程中可应用3DGS的自适应高斯增删策略 → 编辑时通过移动三角形顶点驱动高斯形变。

### 3. 实验设计
- **数据集**：
  - Kodak数据集（24张768×512图像）
  - DIV2K验证集（100张图像，经2×降采样，分辨率408×1020至1020×1020）
- **基准方法与对比对象**：
  - INR类：SIREN、WIRE、I-NGP、NeuRBF
  - 高斯类：GaussianImage、3DGS（作为图像重建的参考）
- **评价指标**：PSNR、MS-SSIM、LPSIS、训练时间、FPS、内存占用
- **编辑能力验证**：通过手动编辑、与DragGAN对比局部编辑保真度，以及集成物理引擎（Taichi\_elements、Blender）展示基于物理的动画效果。

### 4. 资源与算力
- 文中明确提到采用NVIDIA GeForce RTX 4070 Laptop版和NVIDIA GeForce RTX 2080进行实验，附录中的训练时间比较使用V100 GPU。
- 训练时间因初始高斯数量和迭代次数而异，如表1所示：MiraGe-70k(5k迭代)在Kodak上训练57秒，30k迭代需约547秒；MiraGe-100k(30k迭代)约560秒。对比的GaussianImage-70k训练约116秒。

### 5. 实验数量与充分性
- **实验组数**：至少包含6个大类对比实验。
  - 图像重建质量比较（表1）
  - 三种高斯控制模式（Amorphous、2D、Graphite）与镜像相机组合的消融（表3、表5）
  - 不同初始高斯数量（10k至150k）的重建性能评估（表4）
  - 不同图像分辨率缩放下的训练时长和PSNR分析（表2）
  - 与DragGAN、PhysGen的编辑/物理合理性视觉对比（图8、10、12）
  - 多种编辑场景演示（姿态变化、表情调整、物理模拟、2.5D视角变化）
- **充分性与公平性**：实验设计覆盖了重建质量和编辑应用两大维度，消融实验详细分析了高斯约束方式和相机设置的影响，指标选用合理。与基线方法的对比数据源自原论文或直接复现，确保了公平性。但部分编辑效果评估仍依赖主观视觉判断，缺乏定量编辑质量指标。

### 6. 论文的主要结论与发现
- MiraGe通过平坦三维高斯和镜像相机训练，在Kodak和DIV2K数据集上取得了比GaussianImage、SIREN等高出数分贝的PSNR（如Kodak上59.52 dB），重建质量显著提升。
- 采用Amorphous高斯控制结合镜像相机在编辑任务中质量最佳，能有效减少编辑时的人为瑕疵。
- 参数化的三角形网格表示使得高斯分布可被直接操纵，实现局部细节编辑、全局三维变换以及物理驱动的变形，且不会像生成模型（如DragGAN）那样产生非意图的全局改变。
- 与物理引擎的结合允许在二维图像上模拟材料点法（MPM）等真实物理效果，增强了应用的沉浸感。

### 7. 优点
- **兼顾重建与编辑**：首次实现基于高斯表示的高保真二维图像重建与自由编辑的统一框架。
- **直观的编辑范式**：通过三角形网格的顶点操作，提供类似三维建模软件的编辑方式，降低了图像三维变换的门槛。
- **物理交互能力**：能够与标准物理引擎对接，使静态图像中的对象拥有物理属性，拓宽了在游戏、VR等领域的应用前景。
- **严谨的消融分析**：对比了高斯运动约束和相机设置的影响，为后续研究提供了明确的设计参考。

### 8. 不足与局限
- **非生成式带来的空洞问题**：当编辑大幅移动前景对象时，暴露的背景区域缺乏信息，会出现空洞，需依赖外部修复（inpainting）。
- **编辑伪影**：在带有单色背景的图像中，训练残留的背景高斯在动画时可能浮现，产生视觉瑕疵。
- **参数量与实时性**：为获得高重建质量，所需高斯数量较多（如100k），导致存储和渲染速度较GaussianImage有所下降，实时性能受限（大约数百FPS）。
- **光照与风格扩展有限**：当前模型不具备物理光照重新打光或风格迁移能力，论文虽提及未来可结合相关技术，但当前版本未实现。
- **编辑质量评估**：编辑结果的评价主要依赖可视化对比，缺乏结构化的定量度量标准。

（完）
