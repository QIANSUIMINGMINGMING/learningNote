# Fourier‘s unique ideas

## 傅立叶分析

### 傅里叶级数（Fourier series）

公式：

![[公式]](https://www.zhihu.com/equation?tex=%5Cbegin%7Bequation%7D+%5Cbegin%7Bsplit%7D+f%28t%29%26%3D%5Cfrac%7Ba_%7B0%7D%7D%7B2%7D%2Ba_%7B1%7Dcos%28%5Comega+t%29%2Bb_%7B1%7Dsin%28%5Comega+t%29+%5C%5C+%26%2Ba_%7B2%7Dcos%282%5Comega+t%29%2Bb_%7B2%7Dsin%282%5Comega+t%29+%5C%5C+%26%2B...%5C%5C+%26%3D%5Cfrac%7Ba_%7B0%7D%7D%7B2%7D%2B%5Csum_%7Bn%3D1%7D%5E%7B%5Cinfty%7D%7B%5Ba_%7Bn%7Dcos%28n%5Comega+t%29%2Bb_%7Bn%7Dsin%28n%5Comega+t%29%5D%7D+%5Cend%7Bsplit%7D+%5Cend%7Bequation%7D%5Ctag%7B1%7D)

其中：

![[公式]](https://www.zhihu.com/equation?tex=+%5Cbegin%7Balign%7D+%26a_%7Bn%7D%3D%5Cfrac%7B2%7D%7BT%7D%5Cint_%7Bt_%7B0%7D%7D%5E%7Bt_%7B0%7D%2BT%7Df%28t%29cos%28n%5Comega+t%29dt+%5Ctag%7B2%7D+%5C%5C+%26b_%7Bn%7D%3D%5Cfrac%7B2%7D%7BT%7D%5Cint_%7Bt_%7B0%7D%7D%5E%7Bt_%7B0%7D%2BT%7Df%28t%29sin%28n%5Comega+t%29dt+%5Ctag%7B3%7D%5C%5C+%5Cend%7Balign%7D)

推导过程：

傅立叶假设：任意周期函数都可以用一系列不同的![[公式]](https://www.zhihu.com/equation?tex=f%28t%29%3DAsin%28%5Comega+t%2B%5Cpsi%29++%5Ctag%7B4%7D)

表示，即![[公式]](https://www.zhihu.com/equation?tex=f%28t%29%3DA_%7B0%7D%2B%5Csum_%7Bn%3D1%7D%5E%7B%5Cinfty%7D%7BA_%7Bn%7Dsin%28n%5Comega+t%2B%5Cpsi_%7Bn%7D%29%7D%5Ctag%7B5%7D)

展开后得![[公式]](https://www.zhihu.com/equation?tex=A_%7Bn%7Dsin%28n%5Comega+t%2B%5Cpsi_%7Bn%7D%29%3D%7B%5Ccolor%7Bblue%7D%7BA_%7Bn%7Dsin%5Cpsi_%7Bn%7D%7D%7Dcos%28n%5Comega+t%29%2B%5Ccolor%7Bblue%7D%7BA_%7Bn%7Dcos%5Cpsi_%7Bn%7D%7Dsin%28n%5Comega+t%29%5C%5C)

令：![[公式]](https://www.zhihu.com/equation?tex=a_%7Bn%7D%3D%5Ccolor%7Bblue%7D%7BAn%5Ccdot+sin%5Cpsi_%7Bn%7D%7D)![[公式]](https://www.zhihu.com/equation?tex=b_n%3D%5Ccolor%7Bblue%7D%7BA_n%5Ccdot+cos%5Cpsi_n%7D)就得到了傅立叶级数；由此可见$a_n,b_n$是某数乘一个二维空间中的[标准正交基](./正交基.md)

对某一周期函数解傅立叶级数公式中的未知数：

