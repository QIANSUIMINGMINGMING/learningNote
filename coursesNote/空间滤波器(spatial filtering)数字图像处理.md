# 空间滤波器(spatial filtering)数字图像处理

空间滤波的过程也就是不断用一个filter kernel h（一般为3X3）在图像上与同样大小的局部patch作用，作用结果更新在中心点上，所以需要m,n为奇数。横过整个图像从而获得最终结果。

线性滤波器：相关correlation![img](https://img2020.cnblogs.com/i-beta/1734363/202003/1734363-20200317105401985-284888657.png)

+号换成-号即是卷积公式convolution。对于对称滤波器两者结果相同。相当于把滤波核旋转了180度再与原函数进行correlation。

滤波器中心1，其余0，结果为原图像。

通常卷积比相关有更好的数学性质与特征[卷积](../basicMaths/convolution.md) 

卷积运算满足交换率，分配率，结合率

### 平滑滤波器：smoothing

两个作用：模糊、降噪（[噪声类型](./噪声类型.md)）

![img](https://img2020.cnblogs.com/i-beta/1734363/202003/1734363-20200317111602936-637080991.png)

常用线性平滑滤波器如上图：平均值滤波和加权滤波

可以通过设立阀值（如大于某值保持不变，小于某值全取0）去除不必要的细节。

我们将其放到频域去考虑的话，其实这是一个很典型的低通滤波器。这个滤波器会滤掉高频成分，所以可以使得图像平滑。其频率响应如下所示。

#### 高斯滤波器：

一种滤波核系数由高斯函数决定的平滑线性滤波器，滤波核距离中心较近的权重较大

高斯公式：$h(x,y) = e ^ {- \frac{x^2 + y^2}{2\sigma ^ 2}}$

$(2k + 1) \times (2k + 1)$的核，元素值$H_{i,j} = \frac{1}{2\pi \sigma ^ 2}e ^{-\frac{(i - k - 1)^2 + (j - k - 1)^2}{2 \sigma ^ 2}}$

计算后需要进行归一化处理，令左上角等于一，所以使用整数的模板时，需要在模板的前面加一个系数，系数为$\frac{1}{\sum\limits_{(i,j)\in w}w_{i,j}}$也就是模板系数和的倒数

如何选取滤波器的大小？高斯分布的$3\sigma$准则：

数值分布在（μ-σ,μ+σ)中的概率为0.6827；
数值分布在（μ-2σ,μ+2σ)中的概率为0.9545；
数值分布在（μ-3σ,μ+3σ)中的概率为0.9973；所以滤波器的half-width大致接近3$\sigma$

separable kernel:高斯滤波可以将二维的滤波核分解为两个一维的滤波核，分别进行两次运算，减少运算次数9->6（不是所有卷积都可以分解）：

滤波核与自己进行卷积会得到一个新的滤波核

![img](https://pic4.zhimg.com/80/v2-6b045f66038065f94a39aa841f0a06df_720w.jpg)

![70F108B4FADEBFEDA42CEA7CA574F64D](/home/sunnycc/图片/70F108B4FADEBFEDA42CEA7CA574F64D.jpg)高斯函数可分解



#### 中值滤波

是一种非线性平滑滤波方法,用于去除salt and pepper noise，将像素值替换为附近像素值的中位数（属于一种统计排序滤波方法）

### 锐化滤波：sharpening

目的：去除模糊化，强化边界

原理：通常基于[离散微分算法discrete differentiation和拉普拉斯算子](../basicMaths/discreteDifferentiation.md)

 拉普拉斯算子为： ![[公式]](https://www.zhihu.com/equation?tex=+%5Cnabla+%5E2f%3D%5Cfrac%7B%5Cpartial+%5E2f%7D%7B%5Cpartial+x%5E2%7D%2B%5Cfrac%7B%5Cpartial+%5E2f%7D%7B%5Cpartial+y%5E2%7D++) ,锐化之后的图像 ![[公式]](https://www.zhihu.com/equation?tex=g%3Df-k+%5Cnabla+%5E2f)

k为扩散效应的系数

拉普拉斯算子的模板图可表示为：

![[公式]](https://www.zhihu.com/equation?tex=+H%3D%5Cleft%5B+%5Cbegin%7Bmatrix%7D+%090%26%09%09-1%26%09%090%5C%5C+%09-1%26%09%094%26%09%09-1%5C%5C+%090%26%09%09-1%26%09%090%5C%5C+%5Cend%7Bmatrix%7D+%5Cright%5D+++)

还有其他的常用拉普拉斯模板：

![[公式]](https://www.zhihu.com/equation?tex=+H%3D%5Cleft%5B+%5Cbegin%7Bmatrix%7D+%090%26%09%09-1%26%09%090%5C%5C+%09-1%26%09%095%26%09%09-1%5C%5C+%090%26%09%09-1%26%09%090%5C%5C+%5Cend%7Bmatrix%7D+%5Cright%5D+++) ![[公式]](https://www.zhihu.com/equation?tex=+H%3D%5Cleft%5B+%5Cbegin%7Bmatrix%7D+%09-1%26%09%09-1%26%09%09-1%5C%5C+%09-1%26%09%098%26%09%09-1%5C%5C+%09-1%26%09%09-1%26%09%09-1%5C%5C+%5Cend%7Bmatrix%7D+%5Cright%5D+++) ![[公式]](https://www.zhihu.com/equation?tex=+H%3D%5Cleft%5B+%5Cbegin%7Bmatrix%7D+%091%26%09%09-2%26%09%091%5C%5C+%09-2%26%09%095%26%09%09-2%5C%5C+%091%26%09%09-2%26%09%091%5C%5C+%5Cend%7Bmatrix%7D+%5Cright%5D+++)

应用这样的算子使比周围亮的像素变得更亮，使比周围暗的像素变得更暗，从而强化边界。