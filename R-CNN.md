# R-CNN


## 原文链接
 - https://arxiv.org/abs/1311.2524


## 定义
 - region proposal(region of interest): 候选区域
 - ground truth: 样本区域
 - IoU: 计算重叠面积 = (A∩B) / (A∪B)


## 算法流程

### CNN训练
 - 数据集准备
   - 选取训练集中的`ground truth`,并使用`selective search`计算出`region proposals`
   - 计算`ground truth`和`roi`之间的`IoU`,选取其中值大于0.5的`roi`s,然后选取25%计入正样本中
   - 第二步中`IoU`小于0.5中选取正样本3倍的数量记为`background`
 - 训练网络
   - `alex_net`/`VGG-16`
 - 损失函数
   - cross entropy

### SVM训练
 - 数据集准备
   - 按照CNN训练中的,不过这次挑选`IoU`大于0.5的`proposals`, 和`ground truth`一起组成正样本集合
   - `IoU`小于0.3的归为负样本集合
 - 训练m个类别的SVM

### bounding box regression
