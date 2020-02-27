# Fast-RCNN

 - `code`:https://github.com/FDU-VTS/CVCode/tree/master/Deep-Learning/Fast-RCNN
 - `summary`:https://github.com/FDU-VTS/CVPaper

## 原文链接
 - https://arxiv.org/pdf/1504.08083.pdf

## 获取数据 | 输入数据
 - 针对输入的image,对比`ground truth`,计算`IoU`值,大于0.5的记为`ground truth`类,介于0.1和0.5之间的记为`background`类,以此输入

## VGG16 + ROI Pool
 - 网络结构为VGG16, 不过在卷积层和全连接层中间加入了ROI Pool层
 - 在ROI Pool层之后加入了两个全连接层，分别用于计算分类和边界框回归
 - 合并分类损失和边界框回归损失，进行反向chuanbo

## ROI Pool实现细节
 - 对于提取到的`feature map`,根据`selective search`获取到的正样例和负样例区域进行合成
 - 选定7*7的输出区域,对应到`feature map`中进行按每一个点进行缩放
 - 在反向传播时,记录你得到的那个`max pool`的位置,将其置为反向传播获得的值,其余的点置为0

## bounding box regression
 - 边界框回归损失主要基于,原有`region proposal`到输出之间的转化和`ground truth`到输出之间转化的差距loss

## NMS
 - 当经过网络输出后的选择框,筛选去掉具有较大重叠面积的候选框
