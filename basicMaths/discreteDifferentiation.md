# 离散微分和拉普拉斯算子

一阶微分：

![img](https://img-blog.csdn.net/20140725154149944)月

分母是1

求二阶微分：![img](https://img-blog.csdn.net/20140725154309785)

拉普拉斯算子：![img](https://img-blog.csdn.net/20140725154943327)

拉普拉斯算子的旋转不变性：

旋转不变性：内积空间的函数，对于任意旋转，函数数值始终不变。通俗的来讲：假设xyz参考系，固定原点，随意旋转坐标系，函数![f(x,\,y,\,z)=x^{2}+y^{2}+z^{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5e02cf8910f98260282418102a713f5751b54f90)永远不变的，这就是一个具有旋转不变性的函数。

拉普拉斯算子在二维（x，y）情况下：

假设在xyz空间，以z轴为旋转轴，将xy坐标系旋转$\theta$度

![D4EA233C35929A17F4D23605C69E17E9](/home/sunnycc/图片/D4EA233C35929A17F4D23605C69E17E9.jpg)

原p点坐标为（x，y）；坐标系旋转后，p点向两个新坐标轴作垂线，易得：

![x'=x\cos \theta -y\sin \theta ](https://wikimedia.org/api/rest_v1/media/math/render/svg/ea2a2afb8c2c5d404999fe1d9be93838cba5dc4c)

![y'=x\sin \theta +y\cos \theta ](https://wikimedia.org/api/rest_v1/media/math/render/svg/76867df645419a8c64b041271ed4b4cfb968cd09)

把x‘和y’代入拉普拉斯算子公式，易得拉普拉斯算子符合旋转不变性。在图像识别中，旋转不变性有些东西。提取图像特征，即使新的图像中特征旋转了，依然可以识别。