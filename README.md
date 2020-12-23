# 超分辨领域数据集，论文，代码整理

- ### **数据集**


#### 1、图像超分辨

**训练集**

| 名称       | 描述                                                         | 格式 | 下载链接                                                     | 使用程度 |
| ---------- | ------------------------------------------------------------ | ---- | ------------------------------------------------------------ | -------- |
| DIV2K      | 1000张2048$\times$1080图，其中800张作为训练，100张作为验证，100张作为测试。 | png  | https://data.vision.ee.ethz.ch/cvl/DIV2K/                    | 常用     |
| Flickr2K   | 2650 张 2K图                                                 | png  | http://cv.snu.ac.kr/research/EDSR/Flickr2K.tar               | 常用     |
| RealSR     | 真实场景数据集，通过相机变焦，对齐操作得到LR-HR图像对，且LR和HR分辨率相同 | -    | https://github.com/csjcai/RealSR                             | -        |
| T91        | 91张图像                                                     | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 不常用   |
| BSDS200    | [BSD500](https://www2.eecs.berkeley.edu/Research/Projects/CS/vision/bsds/)的一个子集，共200张训练图像 | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 不常用   |
| General100 | 100张训练图像                                                | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 不常用   |

**测试集**

| 名称       | 描述                           | 格式 | 下载链接                                                     | 使用程度 |
| ---------- | ------------------------------ | ---- | ------------------------------------------------------------ | -------- |
| Set5       | 5张图像                        | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 常用     |
| Set14      | 14张图像                       | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 常用     |
| BSD100     | 100张图像，BSD500的一个子集    | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 常用     |
| Urban100   | 100张建筑图像                  | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 常用     |
| manga109   | 109张日本动漫图像              | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 常用     |
| historical | 10张灰度图像，没有Ground Truth | png  | https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u | 未知     |

#### 2、视频超分辨数据集

**训练集**

| 名称     | 描述                                                         | 格式 | 下载链接                                         | 使用程度 |
| -------- | ------------------------------------------------------------ | ---- | ------------------------------------------------ | -------- |
| Vimeo90K | 包含91,701个视频，每个视频总共有 7帧，分辨率为448$\times$256，只有高分辨视频，低分辨视频需要手动人为合成。 | png  | http://toflow.csail.mit.edu/                     | 常用     |
| REDS     | 这在CVPR2019视频增强挑战赛上所提出，由240个视频作为训练集，30个视频作为验证集，30个视频作为测试集，分辨率为1280$\times$720，每个视频100帧 | png  | https://seungjunnah.github.io/Datasets/reds.html | 常用     |

**测试集**

| 名称       | 描述                                                         | 格式 | 下载链接                                                | 使用程度 |
| ---------- | ------------------------------------------------------------ | ---- | ------------------------------------------------------- | -------- |
| Vid4       | 由四个视频组成，分别是Walk，City，Calendar，foliage          | png  | https://people.csail.mit.edu/celiu/CVPR2011/videoSR.zip | 常用     |
| Vimeo90K-T | Vimeo90K的测试集部分，总共有7824个视频，每个七帧 ，分辨率为448$\times$256 | png  | http://toflow.csail.mit.edu/                            | 常用     |
| REDS4      | 这是EDVR算法提出的，他将原有REDS的训练集和测试集合并起来作为新的训练集，同时从原始的训练集中提取四个代表性的视频作为测试集，视频编号分别是000, 011, 015, 020 | png  |                                                         | 常用     |
| UDM10      | 10个视频，每个32帧，分别率为1272 × 720                       | png  | https://github.com/psychopa4/PFNL                       | 一般     |

#### 3、评价指标

| 名称                   | 描述                                     | 实现代码                                                     |
| ---------------------- | ---------------------------------------- | ------------------------------------------------------------ |
| PI（感知指数）         | 用来评估超分结果视觉上的好坏             | https://github.com/roimehrez/PIRM2018  根据quick start进行操作即可，这个仅能计算PI指标，另一个是工具包，内部实现了多种指标的计算https://github.com/Maclory/SPSR/tree/master/metrics |
| LPIPS                  | 用于评估超分结果视觉上的好坏             | https://github.com/Maclory/SPSR/tree/master/metrics          |
| PSNR（峰值信噪比）     | 用于评估超分结果的保真度（像素上的差异） | https://github.com/Maclory/SPSR/tree/master/metrics          |
| SSIM（结构相似性指数） | 用于评估超分结果纹理结构上的完整性       | https://github.com/Maclory/SPSR/tree/master/metrics          |

- ### 主流算法

**视频超分**

2020

| 名称                                                         | 出处 | 文章链接                                                     | 代码链接                                                     |
| ------------------------------------------------------------ | ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Revisiting Temporal Modeling for Video Super-resolution      |      | [pdf](https://arxiv.org/pdf/2008.05765v2.pdf)                | [code](https://github.com/junpan19/RRN)                      |
| A Single Frame and Multi-Frame Joint Network for 360-degree Panorama Video Super-Resolution |      | [pdf](https://arxiv.org/pdf/2008.10320v1.pdf)                | [code](https://github.com/lovepiano/SMFN_For_360VSR)         |
| iSeeBetter: Spatio-Temporal Video Super Resolution using Recurrent-Generative Back-Projection Networks |      | [pdf](https://arxiv.org/pdf/2006.11161v4.pdf)                | [code](https://github.com/amanchadha/iSeeBetter)             |
| TDAN: Temporally-Deformable Alignment Network for Video Super-Resolution | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Tian_TDAN_Temporally-Deformable_Alignment_Network_for_Video_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/YapengTian/TDAN-VSR-CVPR-2020)     |
| Deformable 3D Convolution for Video Super-Resolution         |      | [pdf](https://arxiv.org/pdf/2004.02803v5.pdf)                | [code](https://github.com/XinyiYing/D3Dnet)                  |
| Deep Space-Time Video Upsampling Networks                    | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123550698.pdf) | [code](https://github.com/JaeYeonKang/STVUN-Pytorch)         |
| Space-Time-Aware Multi-Resolution Video Enhancement          | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Haris_Space-Time-Aware_Multi-Resolution_Video_Enhancement_CVPR_2020_paper.pdf) | [code](https://github.com/alterzero/STARnet)                 |
| Across Scales & Across Dimensions: Temporal Super-Resolution using Deep Internal Learning | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123520052.pdf) | [code](https://github.com/eyalnaor/DeepTemporalSR)           |
| Zooming Slow-Mo: Fast and Accurate One-Stage Space-Time Video Super-Resolution | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Xiang_Zooming_Slow-Mo_Fast_and_Accurate_One-Stage_Space-Time_Video_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/Mukosame/Zooming-Slow-Mo-CVPR-2020) |
| BasicVSR: The Search for Essential Components in Video Super-Resolution and Beyond |      | [pdf](https://arxiv.org/pdf/2012.02181v1.pdf)                |                                                              |
| EVRNet: Efficient Video Restoration on Edge Devices          |      | [pdf](https://arxiv.org/pdf/2012.02228v1.pdf)                |                                                              |
| DynaVSR: Dynamic Adaptive Blind Video Super-Resolution       |      | [pdf](https://arxiv.org/pdf/2011.04482v1.pdf)                |                                                              |
| Deformable Kernel Convolutional Network for Video Extreme Super-Resolution |      | [pdf](https://arxiv.org/pdf/2010.00154v1.pdf)                |                                                              |
| Understanding Deformable Alignment in Video Super-Resolution |      | [pdf](https://arxiv.org/pdf/2009.07265v1.pdf)                |                                                              |
| AIM 2020 Challenge on Video Extreme Super-Resolution: Methods and Results |      | [pdf](https://arxiv.org/pdf/2009.06290v1.pdf)                |                                                              |
| Video Super-Resolution with Recurrent Structure-Detail Network | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123570630.pdf) | [code](https://github.com/junpan19/RSDN)                     |
| Video Super Resolution Based on Deep Learning: A comprehensive survey |      | [pdf](https://arxiv.org/pdf/2007.12928v1.pdf)                |                                                              |
| MuCAN: Multi-Correspondence Aggregation Network for Video Super-Resolution | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123550341.pdf) |                                                              |
| Video Super-resolution with Temporal Group Attention         | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Isobe_Video_Super-Resolution_With_Temporal_Group_Attention_CVPR_2020_paper.pdf) | [code](https://github.com/junpan19/VSR_TGA)                  |
| Is There Tradeoff between Spatial and Temporal in Video Super-Resolution? |      | [pdf](https://arxiv.org/pdf/2003.06141v1.pdf)                |                                                              |
| Deep Blind Video Super-resolution                            |      | [pdf](https://arxiv.org/pdf/2003.04716v1.pdf)                |                                                              |
| Video Face Super-Resolution with Motion-Adaptive Feedback Cell |      | [pdf](https://arxiv.org/pdf/2002.06378v1.pdf)                |                                                              |
| End-To-End Trainable Video Super-Resolution Based on a New Mechanism for Implicit Motion Estimation and Compensation |      | [pdf](https://arxiv.org/pdf/2001.01162v1.pdf)                |                                                              |
| Deep Video Super-Resolution using HR Optical Flow Estimation | TIP  | [pdf](https://arxiv.org/pdf/2001.02129.pdf)                  | [code](https://github.com/LongguangWang/SOF-VSR)             |
| Deep Slow Motion Video Reconstruction with Hybrid Imaging System |      | [pdf](https://arxiv.org/pdf/2002.12106v2.pdf)                | [code](https://github.com/avinashpaliwal/Deep-SloMo)         |
| Deep Learning Techniques for Super-Resolution in Video Games |      | [pdf](https://arxiv.org/ftp/arxiv/papers/2012/2012.09810.pdf) |                                                              |
| Learnable Sampling 3D Convolution for Video Enhancement and Action Recognition |      | [pdf](https://arxiv.org/pdf/2011.10974v1.pdf)                |                                                              |
| Deformable Kernel Convolutional Network for Video Extreme Super-Resolution |      | [pdf](https://arxiv.org/pdf/2010.00154v1.pdf)                |                                                              |
| Efficient and Phase-aware Video Super-resolution for Cardiac MRI |      | [pdf](https://arxiv.org/pdf/2005.10626v4.pdf)                |                                                              |
| Exploit Camera Raw Data for Video Super-Resolution via Hidden Markov Model Inference |      | [pdf](https://arxiv.org/pdf/2008.10710v1.pdf)                |                                                              |
| Learning a Deep Dual Attention Network for Video Super-Resolution | TIP  | [pdf](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8995790) |                                                              |
| VESR-Net The Winning Solution to Youku Video Enhancement and Super-Resolution Challenge |      | [pdf](https://arxiv.org/pdf/2003.02115.pdf)                  |                                                              |
| Blind Video Temporal Consistency via Deep Video Prior        | NIPS | [pdf](https://arxiv.org/pdf/2010.11838.pdf)                  | [code](https://github.com/ChenyangLEI/deep-video-prior)      |

**图像超分**

2020

| 名称                                                         | 出处 | 文章链接                                                     | 代码链接                                                     |
| ------------------------------------------------------------ | ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Learning Spatial Attention for Face Super-Resolution         |      | [pdf](https://arxiv.org/pdf/2012.01211v2.pdf)                | [code](https://github.com/chaofengc/Face-SPARNet)            |
| Lightweight Single-Image Super-Resolution Network with Attentive Auxiliary Feature Learning | ACCV | [pdf](https://arxiv.org/pdf/2011.06773v1.pdf)                | [code](https://github.com/wxxxxxxh/A2F-SR)                   |
| Efficient Image Super-Resolution Using Pixel Attention       |      | [pdf](https://arxiv.org/pdf/2010.01073v1.pdf)                | [code](https://github.com/zhaohengyuan1/PAN)                 |
| Interpretable Detail-Fidelity Attention Network for Single Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2009.13134v1.pdf)                | [code](https://github.com/YuanfeiHuang/DeFiAN)               |
| Residual Feature Distillation Network for Lightweight Image Super-Resolution | ECCV | [pdf](https://arxiv.org/pdf/2009.11551v1.pdf)                | [code](https://github.com/njulj/RFDN)                        |
| GSR-Net: Graph Super-Resolution Network for Predicting High-Resolution from Low-Resolution Functional Brain Connectomes |      | [pdf](https://arxiv.org/pdf/2009.11080v1.pdf)                | [code](https://github.com/basiralab/GSR-Net)                 |
| AIM 2020 Challenge on Efficient Super-Resolution: Methods and Results |      | [pdf](https://arxiv.org/pdf/2009.06943v1.pdf)                |                                                              |
| Deep Cyclic Generative Adversarial Residual Convolutional Networks for Real Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2009.03693v1.pdf)                | [code](https://github.com/RaoUmer/SRResCycGAN)               |
| Deep Iterative Residual Convolutional Network for Single Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2009.04809v1.pdf)                | [code](https://github.com/RaoUmer/ISRResCNet)                |
| MDCN: Multi-scale Dense Cross Network for Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2008.13084v1.pdf)                | [code](https://github.com/MIVRC/MDCN-PyTorch)                |
| Multi-Attention Based Ultra Lightweight Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2008.12912v2.pdf)                | [code](https://github.com/AbdulMoqeet/MAFFSRN)               |
| Single Image Super-Resolution via a Holistic Attention Network | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123570188.pdf) | [code](https://github.com/wwlCape/HAN)                       |
| Component Divide-and-Conquer for Real-World Image Super-Resolution | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123530103.pdf) | [code](https://github.com/xiezw5/Component-Divide-and-Conquer-for-Real-World-Image-Super-Resolution) |
| Sub-Pixel Back-Projection Network For Lightweight Single Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2008.01116v1.pdf)                | [code](https://github.com/supratikbanerjee/SubPixel-BackProjection_SuperResolution) |
| HighRes-net: Multi-Frame Super-Resolution by Recursive Fusion | ICLR | [pdf](https://openreview.net/pdf?id=HJxJ2h4tPr)              | [code](https://github.com/ElementAI/HighRes-net)             |
| Frequency Domain-based Perceptual Loss for Super Resolution  |      | [pdf](https://arxiv.org/pdf/2007.12296v1.pdf)                | [code](https://github.com/sdv4/FDPL)                         |
| Cross-Attention in Coupled Unmixing Nets for Unsupervised Hyperspectral Super-Resolution | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123740205.pdf) | [code](https://github.com/danfenghong/ECCV2020_CUCaNet)      |
| Lightweight image super-resolution with enhanced CNN         |      | [pdf](https://arxiv.org/pdf/2007.04344v3.pdf)                | [code](https://github.com/hellloxiaotian/LESRCNN)            |
| Multi-image Super Resolution of Remotely Sensed Images using Residual Feature Attention Deep Neural Networks |      | [pdf](https://arxiv.org/pdf/2007.03107v2.pdf)                | [code](https://github.com/EscVM/RAMS)                        |
| Cross-Scale Internal Graph Neural Network for Image Super-Resolution | NIPS | [pdf](https://proceedings.neurips.cc//paper/2020/file/23ad3e314e2a2b43b4c720507cec0723-Paper.pdf) | [code](https://github.com/sczhou/IGNN)                       |
| Hyperspectral Image Super-resolution via Deep Progressive Zero-centric Residual Learning |      | [pdf](https://arxiv.org/pdf/2006.10300v2.pdf)                | [code](https://github.com/zbzhzhy/PZRes-Net)                 |
| Learning Sparse Masks for Efficient Image Super-Resolution   |      | [pdf](https://arxiv.org/pdf/2006.09603v1.pdf)                | [code](https://github.com/LongguangWang/SMSR)                |
| Neural Sparse Representation for Image Restoration           | NIPS | [pdf](https://proceedings.neurips.cc//paper/2020/file/b090409688550f3cc93f4ed88ec6cafb-Paper.pdf) | [code](https://github.com/ychfan/nsr)                        |
| Learning Texture Transformer Network for Image Super-Resolution | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Yang_Learning_Texture_Transformer_Network_for_Image_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/researchmm/TTSR)                   |
| Image Super-Resolution with Cross-Scale Non-Local Attention and Exhaustive Self-Exemplars Mining | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Mei_Image_Super-Resolution_With_Cross-Scale_Non-Local_Attention_and_Exhaustive_Self-Exemplars_Mining_CVPR_2020_paper.pdf) | [code](https://github.com/SHI-Labs/Cross-Scale-Non-Local-Attention) |
| Dual Super-Resolution Learning for Semantic Segmentation     | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Wang_Dual_Super-Resolution_Learning_for_Semantic_Segmentation_CVPR_2020_paper.pdf) | [code](https://github.com/wanglixilinx/DSRL)                 |
| Residual Feature Aggregation Network for Image Super-Resolution | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Liu_Residual_Feature_Aggregation_Network_for_Image_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/njulj/RFANet)                      |
| ESRGAN+ : Further Improving Enhanced Super-Resolution Generative Adversarial Network |      | [pdf](https://arxiv.org/pdf/2001.08073v2.pdf)                | [code](https://github.com/ncarraz/ESRGANplus)                |
| Perceptual Extreme Super Resolution Network with Receptive Field Block |      | [pdf](https://arxiv.org/pdf/2005.12597v1.pdf)                | [code](https://github.com/Lornatang/RFB_ESRGAN-PyTorch)      |
| Iterative Network for Image Super-Resolution                 |      | [pdf](https://arxiv.org/pdf/2005.09964v2.pdf)                | [code](https://github.com/yuqing-liu-dut/ISRN)               |
| Learning Spatial-Spectral Prior for Super-Resolution of Hyperspectral Imagery |      | [pdf](https://arxiv.org/pdf/2005.08752v2.pdf)                | [code](https://github.com/junjun-jiang/Hyperspectral-Image-Super-Resolution-Benchmark) |
| Invertible Image Rescaling                                   | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123460120.pdf) | [code](https://github.com/pkuxmq/Invertible-Image-Rescaling) |
| Scene Text Image Super-Resolution in the Wild                | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123550647.pdf) | [code](https://github.com/JasonBoy1/TextZoom)                |
| NTIRE 2020 Challenge on Real-World Image Super-Resolution: Methods and Results |      | [pdf](https://arxiv.org/pdf/2005.01996v1.pdf)                |                                                              |
| Rethinking Data Augmentation for Image Super-resolution: A Comprehensive Analysis and a New Strategy | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Yoo_Rethinking_Data_Augmentation_for_Image_Super-resolution_A_Comprehensive_Analysis_and_CVPR_2020_paper.pdf) | [code](https://github.com/clovaai/cutblur)                   |
| DHP: Differentiable Meta Pruning via HyperNetworks           | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123530596.pdf) | [code](https://github.com/ofsoundof/dhp)                     |
| Structure-Preserving Super Resolution with Gradient Guidance | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Ma_Structure-Preserving_Super_Resolution_With_Gradient_Guidance_CVPR_2020_paper.pdf) | [code](https://github.com/Maclory/SPSR)                      |
| Deep Unfolding Network for Image Super-Resolution            | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Zhang_Deep_Unfolding_Network_for_Image_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/cszn/USRNet)                       |
| Closed-loop Matters: Dual Regression Networks for Single Image Super-Resolution | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Guo_Closed-Loop_Matters_Dual_Regression_Networks_for_Single_Image_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/guoyongcs/DRN)                     |
| Hierarchical Neural Architecture Search for Single Image Super-Resolution |      | [pdf](https://arxiv.org/pdf/2003.04619v3.pdf)                | [code](https://github.com/guoyongcs/HNAS-SR)                 |
| **PULSE: Self-Supervised Photo Upsampling via Latent Space Exploration of Generative Models** | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Menon_PULSE_Self-Supervised_Photo_Upsampling_via_Latent_Space_Exploration_of_Generative_CVPR_2020_paper.pdf) | [code](https://github.com/adamian98/pulse)                   |
| Meta-Transfer Learning for Zero-Shot Super-Resolution        | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Soh_Meta-Transfer_Learning_for_Zero-Shot_Super-Resolution_CVPR_2020_paper.pdf) | [code](https://github.com/JWSoh/MZSR)                        |
| Unpaired Image Super-Resolution using Pseudo-Supervision     | CVPR | [pdf](https://openaccess.thecvf.com/content_CVPR_2020/papers/Maeda_Unpaired_Image_Super-Resolution_Using_Pseudo-Supervision_CVPR_2020_paper.pdf) |                                                              |
| LAPAR: Linearly-Assembled Pixel-Adaptive Regression Network for Single Image Super-resolution and Beyond | NIPS | [pdf](https://proceedings.neurips.cc//paper/2020/file/eaae339c4d89fc102edd9dbdb6a28915-Paper.pdf) |                                                              |
| Learning with Privileged Information for Efficient Image Super-Resolution | ECCV | [pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123690460.pdf) |                                                              |
| LOSSLESS SINGLE IMAGE SUPER RESOLUTION FROM LOW-QUALITY JPG IMAGES | ICLR | [pdf](https://openreview.net/pdf?id=r1l0VCNKwB)              |                                                              |
| Interpretable Deep Multimodal Image Super-Resolution         |      | [pdf](https://arxiv.org/pdf/2009.03118v1.pdf)                |                                                              |

**注：这里仅收集了2020年主要会议上的论文，更多的或者以前的论文可以从这个([网址](https://www.paperswithcode.com/task/image-super-resolution/codeless#code))里查看，里面收纳了很多文章，并对该领域最好的算法进行了排名。**

打开如图：

![image1](https://github.com/lovepiano/ImageVideo_SR/blob/main/image-20201223170229102.png)

点击上面想要查看的数据集或者方法就可以查看具体数据集下的排名情况，如下图：

![image2](https://github.com/lovepiano/ImageVideo_SR/blob/main/image-20201223170452484.png)



### 常用的数据预处理代码

陆续整理中

### 训练测试日志管理代码

陆续整理中

### 超分代码模板

陆续整理中
