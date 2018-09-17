## Automatic Localization of Casting Defects with Convolutional Neural Networks

### 原文链接
 - http://101.96.10.41/eil.stanford.edu/publications/max_ferguson/IEEE_Casting_Defect_Detection_2017.pdf

### 概要
 - 本文建立在`GRIMA database`的`X-ray images`数据集基础上，使用CNN进行铸件的缺陷检测

### 铸件上可能存在的缺陷
 - `air holes`:气孔
 - `foreign-particle inclusions`:外来颗粒
 - `shrinkage cavities`:收缩孔
 - `cracks`:裂纹
 - `wrinkles`:皱纹
 - `casting fins`

### 需要注意的特征点
 - `air bubbles`:气泡
 - `large oddly shaped voids`:形状巨大的空洞

### 测试采用的框架
 - `Faster R-CNN`
 - `R-FCN`
 - `SSD`
 - `VGG`
 - `ResNet`

### loss function
 -  $L(a,I;θ) = α*y_a*l_loc(φ(b_a;a)-f_loc(I;a,θ))$
 $+β*l_class(y_a,f_class(I;a,θ))$
 - 其中包含了两部分的损失函数:
   - 第一部分是所选定的区域框与实际缺陷的区域框的差
   - 第二部分是选定的缺陷与实际是否为缺陷的差
### 涉及到的算法
 - `NMS`:non-maximum suppression
 - `RPN`:region-based network
 - `RBD`:region-based detector
 - `L1 norm`:绝对值的合
 - `L2 norm`:平方合开根号
### Questions
 -

### 需要注意的衍生论文
