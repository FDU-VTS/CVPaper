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
 - 坐标和尺度变换: <a href="http://www.codecogs.com/eqnedit.php?latex=$$\\&space;${G_x}'&space;=&space;P_wd_x(P)&space;&plus;&space;P_x&space;$\\&space;${G_y}'&space;=&space;P_hd_y(P)&space;&plus;&space;P_y&space;$\\&space;${G_w}'&space;=&space;P_we^{d_w(P)}&space;$\\&space;${G_h}'&space;=&space;P_he^{d_h(P)}&space;$\\" target="_blank"><img src="http://latex.codecogs.com/svg.latex?$$\\&space;${G_x}'&space;=&space;P_wd_x(P)&space;&plus;&space;P_x&space;$\\&space;${G_y}'&space;=&space;P_hd_y(P)&space;&plus;&space;P_y&space;$\\&space;${G_w}'&space;=&space;P_we^{d_w(P)}&space;$\\&space;${G_h}'&space;=&space;P_he^{d_h(P)}&space;$\\" title="$$\\ ${G_x}' = P_wd_x(P) + P_x $\\ ${G_y}' = P_hd_y(P) + P_y $\\ ${G_w}' = P_we^{d_w(P)} $\\ ${G_h}' = P_he^{d_h(P)} $\\" /></a>
 - 损失函数: <a href="http://www.codecogs.com/eqnedit.php?latex=w_*&space;=&space;\min_{w_*'}\sum_i^N(t_*^i&space;-&space;w_*'^T\phi_5(P^i))^2&space;&plus;&space;\lambda||w_*'||^2" target="_blank"><img src="http://latex.codecogs.com/svg.latex?w_*&space;=&space;\min_{w_*'}\sum_i^N(t_*^i&space;-&space;w_*'^T\phi_5(P^i))^2&space;&plus;&space;\lambda||w_*'||^2" title="w_* = \min_{w_*'}\sum_i^N(t_*^i - w_*'^T\phi_5(P^i))^2 + \lambda||w_*'||^2" /></a>
 - 正确值: <a href="http://www.codecogs.com/eqnedit.php?latex=$$\\&space;$t_x&space;=&space;(G_x&space;-&space;P_x)/P_w&space;$\\&space;$t_y&space;=&space;(G_y&space;-&space;P_y)/P_h&space;$\\&space;$t_w&space;=&space;log(G_w/P_w)&space;$\\&space;$t_h&space;=&space;log(G_h/P_h)" target="_blank"><img src="http://latex.codecogs.com/svg.latex?$$\\&space;$t_x&space;=&space;(G_x&space;-&space;P_x)/P_w&space;$\\&space;$t_y&space;=&space;(G_y&space;-&space;P_y)/P_h&space;$\\&space;$t_w&space;=&space;log(G_w/P_w)&space;$\\&space;$t_h&space;=&space;log(G_h/P_h)" title="$$\\ $t_x = (G_x - P_x)/P_w $\\ $t_y = (G_y - P_y)/P_h $\\ $t_w = log(G_w/P_w) $\\ $t_h = log(G_h/P_h)" /></a>
