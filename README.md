# 深度学习入门，TensorFlow实现与部分项目

课程开始之前有个视频[《一天搞懂深度学习》](https://v.youku.com/v_show/id_XNDM4Mzc4Mjk0NA==.html?spm=a2h0c.8166622.PhoneSokuUgc_1.dscreenshot)，可以用于深度学习粗了解。

本课程中出现了以下相关知识点：

### 神经网络的正向传播与反向传播
每经过一次前向传播和反向传播之后，就会对参数更新一次；然后循环上面的过程，就是神经网络求解。
可见[网址](https://www.jianshu.com/p/765d603c76a0)

### 神经网络中常使用的优化器
**常用优化器**解释见[网址](https://www.jianshu.com/p/b59f40152989)
其中ADAM是一种自适应学习率的方法，综合了之前算法的优点，可以对付稀疏求解与非平稳目标。

### 神经网络中常使用的损失函数
**常用损失函数**解释见[网址](https://www.cnblogs.com/panchuangai/p/12567978.html)，有mse,二分类交叉熵，多分类交叉熵、稀疏多分类交叉熵。

**Focal Loss**是针对于不平衡数据的损失函数，给难分类样本一个更大的权重。
1. 详细的论文解读可见[网址](https://blog.csdn.net/qq_34199326/article/details/83824778)
2. 上述文章基于传统的二分类交叉熵损失函数，其具体的解释可以参见[网址](https://www.jianshu.com/p/b07f4cd32ba6)
3. 多分类交叉熵损失函数可见[网址](https://blog.csdn.net/u014380165/article/details/77284921)

！！！思考一个问题，为何神经网络的损失函数与GBDT之类的不同呢？感觉后者的损失函数更合理，除了衡量预测与实际的偏离程度，还有正则项来防止过拟合。

### 计算图：静态图、动态图和Autograph
图：TensorFlow通过计算图的形式来表述计算的编程系统，其中所有计算都会被转化为计算图上的节点。TensorFlow1.x版本中是静态图，2.x版本中变成了动态图，调试完毕后在函数上面加上@tf.function变成静态图。


静态图与动态图的优缺点：静态图C++编译，运行快；动态图使得调试更容易。


### 卷积神经网络各层的含义及作用
一个完整的神经网络模型通常会包括以下各层：
- 输入后的第一层+激活函数（卷积层）：
  - 卷积核+偏移：现有的深度学习程序会根据训练数据来自动确定；但我并不了解程序是如何确定的
  - [padding](https://blog.csdn.net/baidu_36161077/article/details/81165531)
  - 输入张量的维度（32，255，255，3）的含义：32代表batch,255*255代表图片的大小，3代表通道数（如果是图片转化后的张量，这代表RGB彩色）
  - 输出张量的维度与输入张量相同，不同的是数值：第一位为32batch不变，第二位*第三位为大小，与卷积核大小+padding有关，第四位是通道数，等于卷积核的通道数
- 池化:通常跟在卷积层后，降低输出的特征向量，防止过拟合。具体的解释参见[网址](https://blog.csdn.net/danieljianfeng/article/details/42433475)
- flatten:常用在卷积层到全连接层的过度。具体的解释参见[网址](https://blog.csdn.net/program_developer/article/details/80853425)
- 全连接层与输出层


### 全连接层(Fully Connected Layer)
把分布式特征representation映射到样本标记空间,减少了特征位置对于分类的影响.
通俗易懂的解释可见[网址](https://zhuanlan.zhihu.com/p/33841176)

另外，附上卷积的讲解[网址](https://www.zhihu.com/question/22298352)

### 卷积神经网络常用的网络结构
- [ResNet](https://zhuanlan.zhihu.com/p/31852747)
- [MobileNet](https://zhuanlan.zhihu.com/p/80154731)

### Softmax
softmax是二分类中的sigmoid函数扩充到多分类问题中的对应函数。Softmax函数较简单，可以参见[网址](https://blog.csdn.net/lz_peter/article/details/84574716)

### RNN循环神经网络与CNN的异同
两者都用到了神经元的思想，但是具体实现过程及应用有很大区别。

RNN用于语音识别、NLP、时序预测，根据之前的信息推测未来的信息。
CNN主要用于图像识别，将图像中的特征识别出来。

### LSTM网络(Long Short-Term Memory)
RNN（循环神经网络Recurrent Neural Network）的一种特殊类型,学习长期依赖信息.
中文版原理解释可见[网址](https://www.jianshu.com/p/9dc9f41f0b29)，英文版可见[网址](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)

### GRU(Gate Recurrent Unit)
RNN的一种。类似LSTM，可以解决长期记忆的问题，两者实际表现。那相对于LSTM，GRU 'performs similarly to LSTM but is computationally cheaper'.

中文版介绍可见[网址](https://zhuanlan.zhihu.com/p/32481747)，英文版介绍可见[网址](https://d2l.ai/chapter_recurrent-modern/gru.html)


### 课程的关键网址：
1. 老师个人笔记：https://github.com/hecongqing/TensorFlow2.0-Notes
2. 官方代码文件：https://github.com/JansonYuan/TensorFlow-Camp
3. 百度云代码文件：链接：https://pan.baidu.com/s/1tXmTroPwaiD4dPQ7-0o-ag  提取码：e66v
4. 问题答疑汇总&博客分享:https://shimo.im/docs/pDQrHtycpckcC9qV/
