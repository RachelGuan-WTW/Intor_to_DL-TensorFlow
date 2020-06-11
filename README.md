# TF-IntrodutionCourse

课程开始之前有个视频[《一天搞懂深度学习》](https://v.youku.com/v_show/id_XNDM4Mzc4Mjk0NA==.html?spm=a2h0c.8166622.PhoneSokuUgc_1.dscreenshot)，可以用于深度学习粗了解。

本课程中出现了以下相关知识点：
### LSTM网络(Long Short-Term Memory)
RNN（循环神经网络Recurrent Neural Network）的一种特殊类型,学习长期依赖信息.
原理解释可见[网址](https://www.jianshu.com/p/9dc9f41f0b29)

### 全连接层(Fully Connected Layer)
把分布式特征representation映射到样本标记空间,减少了特征位置对于分类的影响.
通俗易懂的解释可见[网址](https://zhuanlan.zhihu.com/p/33841176)


### 神经网络的正向传播与反向传播
每经过一次前向传播和反向传播之后，就会对参数更新一次；然后循环上面的过程，就是神经网络求解。
可见[网址](https://www.jianshu.com/p/765d603c76a0)

### 神经网络中常使用的优化器与损失函数
常用优化器解释见[网址](https://www.jianshu.com/p/b59f40152989)
其中ADAM是一种自适应学习率的方法，综合了之前算法的优点，可以对付稀疏求解与非平稳目标。

常用损失函数解释见[网址](https://www.cnblogs.com/panchuangai/p/12567978.html)
！！！思考一个问题，都是分类问题，为何神经网络的损失函数与GBDT之类的不同（至少名称不同）呢？

### 计算图：静态图、动态图和Autograph
图：TensorFlow通过计算图的形式来表述计算的编程系统，其中所有计算都会被转化为计算图上的节点。TensorFlow1.x版本中是静态图，2.x版本中变成了动态图，调试完毕后在函数上面加上@tf.function变成静态图。

静态图与动态图的优缺点：静态图C++编译，运行快；动态图使得调试更容易。
