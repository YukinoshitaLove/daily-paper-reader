<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-09-01
- 运行时间：2026-09-01 22:27:45 UTC
- 运行状态：成功
- 本次总论文数：17
- 精读区：6
- 速读区：11

### 今日简报（AI）
今日精读17篇，重点聚焦图像超分与JPEG恢复，其中《PixelIR》以满分10分领跑。

最值得关注的方向是像素级流匹配实现单步超分，以及小波域均值流加速JPEG修复，二者均达9分以上高分。

建议优先精读《PixelIR》验证其高效性，再按兴趣浏览扩散桥与3D风格化等速读选题。
- 详情：[/202609/01/README](/202609/01/README)

### 精读区论文标签
1. [PixelIR: Fidelity-Perception Decoupling via Pixel-Space Image-Residual Flow Matching for Efficient One-Step Real-World Super-Resolution](/202609/01/2608.30782v1-pixelir-fidelity-perception-decoupling-via-pixel-space-image-residual-flow-matching-for-efficient-one-step-real-world-super-resolution)  
   标签：评分：10.0/10、query:real-ir
   evidence：直接面向真实世界超分辨率，采用生成式流匹配
2. [Efficient JPEG Restoration in the Wavelet Domain via Mean Flows](/202609/01/2608.28730v1-efficient-jpeg-restoration-in-the-wavelet-domain-via-mean-flows)  
   标签：评分：9.0/10、query:real-ir
   evidence：用小波域均值流生成式恢复器进行JPEG去压缩伪影，高效且高质量
3. [DARD: Zero-Shot Degradation-Aware Retinex-Guided Diffusion for Low-Light Image Enhancement](/202609/01/2608.29243v1-dard-zero-shot-degradation-aware-retinex-guided-diffusion-for-low-light-image-enhancement)  
   标签：评分：9.0/10、query:real-ir
   evidence：基于扩散模型和Retinex引导的低光图像增强，直接匹配扩散/生成式图像修复需求
4. [Learning to Restore More: Continual Capability Expansion for Pretrained Image Restoration Models](/202609/01/2608.30305v1-learning-to-restore-more-continual-capability-expansion-for-pretrained-image-restoration-models)  
   标签：评分：9.0/10、query:real-ir
   evidence：预训练图像恢复模型的持续能力扩展
5. [sRGB Real Noise Modeling via Noise-Aware Sampling with Normalizing Flows](/202609/01/2608.29038v1-srgb-real-noise-modeling-via-noise-aware-sampling-with-normalizing-flows)  
   标签：评分：8.0/10、query:real-ir
   evidence：用归一化流生成真实噪声，支撑图像去噪
6. [RegionCache: Semantic-Aware Region Reuse for Efficient Multi-Turn Image Generation](/202609/01/2608.29809v1-regioncache-semantic-aware-region-reuse-for-efficient-multi-turn-image-generation)  
   标签：评分：8.0/10、query:real-ir
   evidence：基于扩散Transformer的多轮图像编辑，语义感知区域复用

### 速读区论文标签
1. [Discrete Diffusion Bridges for Spatiotemporally Aligned Image Translation and Generation](/202609/01/2608.29997v1-discrete-diffusion-bridges-for-spatiotemporally-aligned-image-translation-and-generation)  
   标签：评分：8.0/10、query:real-ir
   evidence：面向图像翻译与生成的时空对齐离散扩散框架
2. [DReSG: Diffusion Residuals for Stylized Gaussian Splatting](/202609/01/2608.29048v1-dresg-diffusion-residuals-for-stylized-gaussian-splatting)  
   标签：评分：7.0/10、query:real-ir
   evidence：基于扩散的三维场景风格化与外观编辑
3. [Manifold-Constrained PET Reconstruction with Learned Flow-Matching Priors](/202609/01/2608.29158v1-manifold-constrained-pet-reconstruction-with-learned-flow-matching-priors)  
   标签：评分：7.0/10、query:real-ir
   evidence：用流匹配生成模型先验求解PET图像重建的逆问题，与生成模型驱动的图像恢复高度相关
4. [Mapping-Based Image Diffusion](/202609/01/2608.29164v1-mapping-based-image-diffusion)  
   标签：评分：7.0/10、query:real-ir
   evidence：基于张量的变分模型用于图像去噪与定向增强
5. [Generalization over Memorization: Generalization-Aware Diffusion Adaptation for Single-Image Multi-View Synthesis](/202609/01/2608.29233v1-generalization-over-memorization-generalization-aware-diffusion-adaptation-for-single-image-multi-view-synthesis)  
   标签：评分：7.0/10、query:real-ir
   evidence：基于扩散适配的单图多视角合成，强调泛化与记忆的区分
6. [Elastic Token Compression for Pixel-Space Diffusion Transformers](/202609/01/2608.29281v1-elastic-token-compression-for-pixel-space-diffusion-transformers)  
   标签：评分：7.0/10、query:real-ir
   evidence：面向像素空间扩散Transformer的令牌压缩方法，是扩散模型效率改进，可广泛应用于生成与恢复
7. [OrnaStyler: Ornament-Aware Latent Editing for Content-Preserving 3D Stylization](/202609/01/2608.29905v1-ornastyler-ornament-aware-latent-editing-for-content-preserving-3d-stylization)  
   标签：评分：7.0/10、query:real-ir
   evidence：基于修正流生成模型和反演引导编辑的文本驱动的3D纹样风格化，属于生成式编辑模型
8. [Dior: Drawing the Light of Image via Material-Decoupled Illumination Representation](/202609/01/2608.29925v1-dior-drawing-the-light-of-image-via-material-decoupled-illumination-representation)  
   标签：评分：7.0/10、query:real-ir
   evidence：可控图像重打光，直接属于图像编辑模型
9. [Attribute Token Arithmetic: Disentangled and Continuous Semantic Control for Visual Autoregressive Models](/202609/01/2608.28082v1-attribute-token-arithmetic-disentangled-and-continuous-semantic-control-for-visual-autoregressive-models)  
   标签：评分：6.0/10、query:real-ir
   evidence：通过属性令牌算术在视觉自回归模型中实现语义属性控制，支持类似图像编辑的操作
10. [FLM: Frequency-Aware Language Models for Generative Image Compression](/202609/01/2608.28687v1-flm-frequency-aware-language-models-for-generative-image-compression)  
   标签：评分：6.0/10、query:real-ir
   evidence：基于频率域语言模型的生成式图像压缩
11. [PathGuide: Dynamic Classifier-Free Guidance via On-Policy Transport Alignment](/202609/01/2608.29107v1-pathguide-dynamic-classifier-free-guidance-via-on-policy-transport-alignment)  
   标签：评分：6.0/10、query:real-ir
   evidence：在基于流的生成模型中动态选择无分类器引导尺度，提升条件生成的推理控制


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
