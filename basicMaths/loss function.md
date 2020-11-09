# loss function

**模型1**：

![img](https://pic3.zhimg.com/80/v2-0c49d6159fc8a5676637668683d41762_720w.jpg)

**模型2**：

![img](https://pic3.zhimg.com/80/v2-6d31cf03185b408d5e93fa3e3c05096e_720w.jpg)

1. 最为直接的损失函数定义为： ![[公式]](https://www.zhihu.com/equation?tex=classification%5C+error%3D%5Cfrac%7Bcount%5C+of%5C+error%5C+items%7D%7Bcount%5C+of+%5C+all%5C+items%7D)
   + **模型1：** ![[公式]](https://www.zhihu.com/equation?tex=classification%5C+error%3D%5Cfrac%7B1%7D%7B3%7D)
   + **模型2：** ![[公式]](https://www.zhihu.com/equation?tex=classification%5C+error%3D%5Cfrac%7B1%7D%7B3%7D)

2. MSE：对所有样本求方差再取平均值

   采用此方法用梯度下降法训练模型在一开始会非常慢

   + **模型1：**![[公式]](https://www.zhihu.com/equation?tex=MSE%3D%5Cfrac%7B0.54%2B0.54%2B1.32%7D%7B3%7D%3D0.8+%5C%5C)
   + **模型2：**![[公式]](https://www.zhihu.com/equation?tex=MSE%3D%5Cfrac%7B0.138%2B0.138%2B0.72%7D%7B3%7D%3D0.332+%5C%5C)

3. 交叉熵损失函数

![img](https://upload-images.jianshu.io/upload_images/4264437-c2d2b6130519f5a5.png?imageMogr2/auto-orient/strip|imageView2/2/w/475/format/webp)