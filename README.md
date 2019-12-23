### Introduction

#### Summary about Computer Vision Paper

### demo: ./`Crowd Counting Paper Summary.md`

## Traditional methods
 - `cvpr06: Counting Crowded Moving Objects`
   - low-level features
 - `cvpr06: Unsupervised Bayesian Detection of Independent Motion in Crowds`
   - low-level features
 - `cvpr08: Privacy Preserving Crowd Monitoring: Counting People Without People Models or Tracking.`
   - low-level features
   - learn multi-scale features by use different receptive fields.
 - `cvpr08: Counting people without people models or tracking`
   - develop a method counting the crowd number by holistic features and GP regression
 - `iccv09: Bayesian poisson regression for crowd counting`
   - nonlinear mapping
   - A prior distribution is introduced in the proposed Bayesian Poisson regression to estimate the size of inhomogeneous crowds
 - `nips10: Learning to count objects in images`
   - density map
   - nonlinear mapping
   - proposes to count local patches and then integrates them to the final count, which incorporates spatial information better for accurate counting
 - `icpr12: Learning to Count with Regression Forest and Structured Labels`
   - Random Forest based
 - `bmvc12: Feature Mining for Localised Crowd Counting`
   - low-level features
 - `cvpr13: Multi-source multi-scale counting in extremely dense crowd images`
   - single features are insufficient to count crowd numbers in extremely crowd images due to large variations, clutters, and occlusions

## Detection-based
 - `iccv03: Detecting pedestrians using patterns of motion and appearance`
   - rely on hand-crafted features
 - `iccv05: Detection of multiple, partially occluded humans in a single image by bayesian combination of edgelet part detectors`
   - rely on hand-crafted features
   - detect individual heads or bodies and then counting them
 - `icpr08: Estimating the number of people in crowded scenes by mid based foreground segmentation and head-shoulder detection`
   - rely on hand-crafted features
   - detect either the whole body or parts for counting by detection
   - detect human heads and shoulders
 - `cvpr09: Marked point processes for crowd counting`
   - A shape learning process is proposed to detect and count individuals
 - `pami10: Shape-Based Human Detection and Segmentation via Hierarchical Part-Template Matching`
   - detect individual heads or bodies and then counting them
 - `nips11: Airport Detection in Remote Sensing Images Based on Visual Attention`
   - detect individual heads or bodies and then counting them
 - `iccv11: Density-aware oersib detectuib abd tracking in crowds`
   - rely on hand-crafted features
 - `cvpr11: Automatic adaptation of a generic pedestrian detector to a specific traffic scene.`
   - rely on hand-crafted features
 - `cvpr16: End-to-end people detection in crowded scenes.`
   - an end-to-end people detector for crowded scenes
 - `cvpr17: Feature pyramid networks for object detection`
   - object detection
 - `iccv17: Focal Loss for Dense Object Detection`
   - object detection


## Regression-based
 - `cvpr15: Cross-scene crowd counting via deep convolutional neural networks`
   - transfer a well-trained model to a new target scene by a data-driven fine-tuning method
   - use geometric information to adapt the network to different scene geometries
 - `acmmm16: Crowdnet: A deep convolutional network for dense crowd counting`
   - Crowdnet
 - `eccv16: Learning to count with cnn boosting`
   - CNN-boost
 - `eccv16: Towards Perspective-Free Object Counting with Deep Learning`
   - Hydra-CNN
   - image patches extracted at multiple scales as input to a multistream network, and fuse the features for final density prediction
 - `cvpr16: Single-image crowd counting via multi-column convolutional neural network`
   - MCNN
   - the change of view angles as well as the change in density at different regions
   - different CNNs with different kernel size
   - learn multi-scale features by use different receptive fields
 - `iccv17: Switching convolutional neural network for crowd counting`
   - switch-CNN
   - the change of view angles as well as the change in density at different regions
   - Multiple CNNs with different receptive field sizes are proposed to deal with density variations, and a switch network is developed to choose the best one
   - train an extra classifier to assign the best receptive field for each image patch
 - `iccv17: Generating highquality crowd density maps using contextual pyramid cnns`
   - CP-CNN
   - the change of view angles as well as the change in density at different regions
   - utilize global and local contexts to improve the performance
   - learning to prefict pre-designed density levels
   - They discovered that high-quality density maps are useful for further decreasing the counting error
 - `cvpr18: Csrnet: Dilated convolutional neural networks for understanding the highly congested scenes`
   - CSRNet
   - dilated convolutional kernel
   - the change of view angles as well as the change in density at different regions
 - `pr letters: A survey of recent advances in cnn-based single image crowd counting and density estimation`
   - suvery
 - `cvpr18: Decidenet: Counting varying density crowds through attention guided detection and density estimation`
   - take advantage of the results of detection for density map regression
 - `eccv18: Composition loss for counting, density map estimation and localization in dense crowds`
   - their method estimates a binary localization map where head centers correspond to 1’s, and all the rest are 0’s, but its optimization is not easy, and the estimated locations are coarse due to the downsampling layer in CNN
 - `cvpr18: Crowd counting via scale adaptive convolutional neural network`
   - a scale-adaptive network which combines multi-scale features extracted from different layers to deal with scale and perspective changes
 - `cvpr18: Divide and grow: Capturing huge diversity in crowd images with incrementally growing cnn`
   - IG-CNN
   - An Incrementally Growing CNN (IG-CNN) is developed to cope with large diversities in crowd Images
   - train an extra classifier to assign the best receptive field for each image patch
 - `cvpr18: Crowd Counting with Deep Negative Correlation Learning`
   - train a pool of decorrelated regressors
 - `eccv18: Scale Aggregation Network for Accurate and Efficient Crowd Counting`
   - SANet
   - transposed convolution
 - `cvpr18: Crowd Counting via Adversarial Cross-Scale Consistency Pursuit`
   - patches to get different loss
 - `bmvc18: Crowd Counting by Adaptively Fusing Predictions from an Image Pyramid`
   - weight different density maps generated from input images at various scales
 - `cvpr18: Leveraging unlabeled data for crowd counting by learning to
rank`
   - CNN
   - learn to rank
   - unlabeled data
   - learns from unlabeled data through prior knowledge


 ## Both of Regression-based and Detection-based
 - `cvpr18: Decidenet: Counting varying density crowds through attention guided detection and density estimation `
   - combine detection and regression approaches


## Counting Objects
 - `eccv14: Interactive Object Counting`
 - `eccv16: Counting in theWild`
 - `cvpr17: Counting Everyday Objects in Everyday Scenes`


## Others
 - `nips17: Incorporating Side Information by Adaptive Convolution`
   - use geometric information to adapt the network to different scene geometries.


## 2019
- `cvpr19: Leveraging Heterogeneous Auxiliary Tasks to Assist Crowd Counting`
  - 除了backbone本身的loss之外,增加了heterogeneous attributes,包括了
    - `Geometric attribute (depth prediction)`:通过生成辅助depth map来减小perspective
distortion的影响
    - `Semantic attribute (crowd segmentation)`:通过生成语义分割图去除图像中的noise
    - `Numeric attribute (count estimation)`:通过得到预测的数字和ground truth比较
- `cvpr19: Wide-Area Crowd Counting via Ground-Plane Density Maps and Multi-View Fusion CNNs`
  - 解决在单一图片上训练的模型在多摄像头多角度下表现不好的问题, 提供了三个fuse model:
     - late fusion model fuses camera-view density maps: 先将不同角度下的密度图生成出来，再将这几(3)个密度图融合
     - the naive early fusion model fuses camera-view feature maps: 直接融合预测过程中的feature map
     - the multi-view multi-scale early fusion model favors that features aligned to the same ground-plane point have consistent scales:为了解决在不同视角下人物的大小可能不同, 通过获取多场景下的feature map, 通过上采样到相同尺寸, 并且通过Scale selection mask来转换到相同的尺寸, 其中Scale selection mask是根据摄像头位置设定的.
- `cvpr19: Residual Regression with Semantic Prior for Crowd Counting`
  - leverage the semantic prior to improve the performance of crowd counting and adopt adversarial loss
  - 本文主要是探究了不同图像之间的关联关系(correlation relatioinship)
  - 利用support images和input image叠加, support image就是semantic prior, 将不同support images融合的结果做residual loss.
- `cvpr19: Density Map Regression Guided Detection Network for RGB-D Crowd Counting and Localization`
  - RGB-D crowd counting, 利用了D(depth)深度信息
  - 本文提出了一个数据集(ShanghaiTechRGBD): 2,193 images and 144,512 head counts
  - 通过将深度信息不断加到不同尺寸的feature map上来适应不同远近的人群
- `cvpr19: Recurrent Attentive Zooming for Joint Crowd Counting and Precise Localization`
  - Main Net和 RAZNet(Recurrent Attentive Zooming), Main Net负责预测整张图, RAZNet负责选取整张图中的部分区域, 先将其超分到原图尺寸, 在进行预测, 最后将选中区域作为mask覆盖到原预测区域
- `cvpr19: Crowd Counting and Density Estimation by Trellis Encoder-Decoder Network`
  - 本文采用了一个Trellis结构的网络, 通过在网络的不同深度预测, 并将不同的预测结果组成联合loss
  - 采用了一个Multi-scale Encoding Block, 就是将卷积层由一个多种尺寸卷积核组合的模块替代, 类似MCNN
  - 将最后一个密度图预测之前的预测结果以dense connect类型连接在一起
- `cvpr19: Context-Aware Crowd Counting`
  - 本文利用不同大小的average pooling获取multiple receptive field
    - 先使用不同size的average pooling, 再上采样的原图尺寸, 利用输入的feature map做残差, 将残差结果作为权重乘到input feature map中
- `cvpr19: Revisiting Perspective Information for Efficient Crowd Counting`
  - 本文要解决perspective distortion问题
  - 先用摄像头生成perspective map, 将其应用到ground truth上, 再用改变后的gt进行预测
- `cvpr19: Point in, Box out: Beyond Counting Persons in Crowds`
   - detection方法
   - 通过选取人头中心点和附近点的距离来生成bounding box, 利用curriculum learning来训练网络
- `cvpr19: ADCrowdNet: An Attention-Injective Deformable Convolutional Network for Crowd Understanding`
   - 利用attention权重来增强网络, 先用encoder形成一个attention map, 再将attention map乘到feature map上, 用过decoder预测密度图
- `cvpr19: Learning from Synthetic Data for Crowd Counting in the Wild`
   - 利用GTA-5游戏生成了一个新的数据集(GCC), 先生成游戏画面, 在利用Cycle GAN生成真实图像.
- `cvprw19: Dense Crowd Counting Convolutional Neural Networks with Minimal Data
using Semi-Supervised Dual-Goal Generative Adversarial Networks`
   - 利用GAN做半监督
- `iccv19: Pushing the Frontiers of Unconstrained Crowd Counting: New Dataset and Benchmark Method`
   - 主要提出了一个新的数据集: JHU-CROWD
