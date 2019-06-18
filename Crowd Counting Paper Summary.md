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
 - `iccv05: Detection of Multiple, Partially Occluded Humans in a Single Image by Bayesian Combination of Edgelet Part Detectors`
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
 - `eccv16: Towards perspective-free object counting with deep learning`
   - CNN
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
