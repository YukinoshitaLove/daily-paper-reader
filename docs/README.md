<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-07-07
- 运行时间：2026-07-07 21:17:32 UTC
- 运行状态：成功
- 本次总论文数：26
- 精读区：15
- 速读区：11

### 今日简报（AI）
今日精读15篇前沿论文，聚焦图像恢复与扩散模型的可控性，其中两篇满分研究最受关注。  
CURE实现复杂退化图像的真正统一恢复，另一满分工作则揭示了高CFG扩散反演失败的深层机制。  
建议尝试将CURE思路融入你的图像处理管线，并在扩散模型生成中谨慎设置CFG值以提升稳定性。
- 详情：[/202607/07/README](/202607/07/README)

### 精读区论文标签
1. [CURE: Controllable Unified Image Restoration for Complex Degradations](/202607/07/2607.03044v1-cure-controllable-unified-image-restoration-for-complex-degradations)  
   标签：评分：10.0/10、query:real-ir
   evidence：提出针对复杂复合退化的可控制统一图像复原框架
2. [When Does High-CFG Diffusion Inversion Fail? A Controlled Study of Prompt--Latent Interactions](/202607/07/2607.04731v1-when-does-high-cfg-diffusion-inversion-fail-a-controlled-study-of-prompt--latent-interactions)  
   标签：评分：10.0/10、query:real-ir
   evidence：分析高无分类器引导扩散逆映射在图像编辑中的失败模式
3. [Geometry-aware Depth-guided Representation Learning for Structure-preserving Low-light Image Enhancement](/202607/07/2607.05005v1-geometry-aware-depth-guided-representation-learning-for-structure-preserving-low-light-image-enhancement)  
   标签：评分：10.0/10、query:real-ir
   evidence：通过深度引导的多尺度注意力网络进行结构保持的低光增强
4. [What Does a Discrete Diffusion Model Learn?](/202607/07/2607.05381v1-what-does-a-discrete-diffusion-model-learn)  
   标签：评分：10.0/10、query:real-ir
   evidence：理论分析离散扩散模型的学习目标，证明Oracle距离定理
5. [SE-UNet: Singular Equivariant Imaging for Real-World Constrained Generation](/202607/07/2607.02628v1-se-unet-singular-equivariant-imaging-for-real-world-constrained-generation)  
   标签：评分：9.0/10、query:real-ir
   evidence：利用几何等变性和奇异值门控的扩散模型零样本图像修复
6. [Pooling-Based Context Modeling for Convolution-Free Deep Image Prior](/202607/07/2607.02952v1-pooling-based-context-modeling-for-convolution-free-deep-image-prior)  
   标签：评分：9.0/10、query:real-ir
   evidence：Pool-DIP以无卷积架构提升去噪性能，属于图像恢复方法
7. [ReLo-IRR: Reflection-Guided LoRA Framework for Image Reflection Removal](/202607/07/2607.02957v1-relo-irr-reflection-guided-lora-framework-for-image-reflection-removal)  
   标签：评分：9.0/10、query:real-ir
   evidence：使用扩散模型和LoRA的图像反射去除
8. [MambaLIE: Scene Light Intensity-Boosted Low-Light Image Enhancement with State Space Model](/202607/07/2607.03013v1-mambalie-scene-light-intensity-boosted-low-light-image-enhancement-with-state-space-model)  
   标签：评分：9.0/10、query:real-ir
   evidence：使用状态空间模型的低光图像增强，属于图像恢复类任务
9. [Mixture-of-Gaussians-Guided Schedule Design for Brownian Bridge Diffusion Models](/202607/07/2607.03517v1-mixture-of-gaussians-guided-schedule-design-for-brownian-bridge-diffusion-models)  
   标签：评分：9.0/10、query:real-ir
   evidence：为图像恢复设计布朗桥扩散的分析性调度方案
10. [Perceptual Flow Matching for Few-Step Generative Modeling](/202607/07/2607.03524v1-perceptual-flow-matching-for-few-step-generative-modeling)  
   标签：评分：9.0/10、query:real-ir
   evidence：感知流匹配加速生成模型，与扩散采样加速方法目标一致
11. [EMPURPLE: A Free Lunch for Diffusion Distillation based on the Information Bottleneck](/202607/07/2607.04276v1-empurple-a-free-lunch-for-diffusion-distillation-based-on-the-information-bottleneck)  
   标签：评分：9.0/10、query:real-ir
   evidence：提出扩散蒸馏方法以改善FID指标
12. [From Open Loop to Closed Loop: A Test-Time Iterative Optimization Framework for Reference-Consistent Image Generation](/202607/07/2607.04691v1-from-open-loop-to-closed-loop-a-test-time-iterative-optimization-framework-for-reference-consistent-image-generation)  
   标签：评分：9.0/10、query:real-ir
   evidence：参考一致性图像生成的测试时迭代优化，图像编辑
13. [Non-asymptotic Convergence of Stochastic Gradient Descent in Score-based Generative Models](/202607/07/2607.04775v1-non-asymptotic-convergence-of-stochastic-gradient-descent-in-score-based-generative-models)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于分数的生成模型属于扩散模型，本文研究了SGD训练的策略收敛性
14. [RADIANCE: Relative Adaptive Denoising with IP-Adapter for Novel Concept Enhancement](/202607/07/2607.05088v1-radiance-relative-adaptive-denoising-with-ip-adapter-for-novel-concept-enhancement)  
   标签：评分：9.0/10、query:real-ir
   evidence：免训练反馈框架用于扩散文本到图像生成
15. [Erasing Without Collateral Damage: Precise Concept Removal in Diffusion Models](/202607/07/2607.05274v1-erasing-without-collateral-damage-precise-concept-removal-in-diffusion-models)  
   标签：评分：9.0/10、query:real-ir
   evidence：扩散模型中精确无附带损伤的概念擦除，使用保持子空间感知的闭式方向

### 速读区论文标签
1. [DICT: Data Injection and Contrastive Trajectory Refinement for Conditional Image Generation with Diffusion Models](/202607/07/2607.03899v1-dict-data-injection-and-contrastive-trajectory-refinement-for-conditional-image-generation-with-diffusion-models)  
   标签：评分：8.0/10、query:real-ir
   evidence：提出无训练方法DICT，通过数据注入和对比轨迹优化改进扩散模型条件图像生成
2. [Tightening the Score Matching Gap for Diffusion Models](/202607/07/2607.04442v1-tightening-the-score-matching-gap-for-diffusion-models)  
   标签：评分：8.0/10、query:real-ir
   evidence：扩散模型得分匹配间隙的理论分析
3. [LILAC: Layer-Wise Independent LoRAs and Cascaded Conditioning for Multi-Concept Customization of Diffusion Models](/202607/07/2607.04801v1-lilac-layer-wise-independent-loras-and-cascaded-conditioning-for-multi-concept-customization-of-diffusion-models)  
   标签：评分：8.0/10、query:real-ir
   evidence：提出将概念组合为独立图像层，使用独立LoRA避免扩散模型多概念定制中的干扰。
4. [Steering Optimisation Trajectories in Diffusion Representation Learning](/202607/07/2607.05319v1-steering-optimisation-trajectories-in-diffusion-representation-learning)  
   标签：评分：8.0/10、query:real-ir
   evidence：引导扩散自编码器的优化轨迹以改善表征学习
5. [PointDiT: Pixel-Space Diffusion for Monocular Geometry Estimation](/202607/07/2607.02515v1-pointdit-pixel-space-diffusion-for-monocular-geometry-estimation)  
   标签：评分：7.0/10、query:real-ir
   evidence：提出像素空间扩散变换器用于单目三维重建
6. [Global Pose Control for Generative View Synthesis in Normalized Object Coordinate Space](/202607/07/2607.02712v1-global-pose-control-for-generative-view-synthesis-in-normalized-object-coordinate-space)  
   标签：评分：7.0/10、query:real-ir
   evidence：标准化物体坐标空间下的全局位姿可控生成式视图合成
7. [Flex-Forcing: Towards a Unified Autoregressive and Bidirectional Video Diffusion Model](/202607/07/2607.03509v1-flex-forcing-towards-a-unified-autoregressive-and-bidirectional-video-diffusion-model)  
   标签：评分：7.0/10、query:real-ir
   evidence：统一自回归与双向生成的视频扩散模型
8. [Reflected Schrödinger Bridge Matching](/202607/07/2607.03626v1-reflected-schrdinger-bridge-matching)  
   标签：评分：7.0/10、query:real-ir
   evidence：为反射薛定谔桥（一种生成建模技术）提出部分免仿真训练框架
9. [ProxyUp: Training-Free Proxy-Conditioned Video Generation for Controllable Dynamics](/202607/07/2607.03732v1-proxyup-training-free-proxy-conditioned-video-generation-for-controllable-dynamics)  
   标签：评分：7.0/10、query:real-ir
   evidence：提出免训练的代理条件视频生成，实现可控动态
10. [PGE-SAM: Prompt-Guided Feature Enhancement for Interactive Segmentation under Degradation](/202607/07/2606.30477v1-pge-sam-prompt-guided-feature-enhancement-for-interactive-segmentation-under-degradation)  
   标签：评分：6.0/10、query:real-ir
   evidence：退化条件下通过提示引导特征增强恢复SAM分割精度
11. [Signal or Noise? Understanding Generative Models for Real-World Sensor Time Series](/202607/07/2607.04245v1-signal-or-noise-understanding-generative-models-for-real-world-sensor-time-series)  
   标签：评分：6.0/10、query:real-ir
   evidence：大规模研究生成模型在传感器时间序列生成中的表现，评估多个模型家族。


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
