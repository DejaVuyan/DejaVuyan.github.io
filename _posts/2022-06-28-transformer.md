# Transformer和Attention



##### attention

首先transformer与传统RNN的不同在于他不是将输入语序转换成一个 **定长的embbding向量**，他是 **关注全局信息**的，每一次丛所有的输入里选取自己需要关注的词语进行encoding?



参考：

Attention机制详解（一）——Seq2Seq中的Attention - 川陀学者的文章 - 知乎 https://zhuanlan.zhihu.com/p/47063917



最早的attention是在RNN上进行改进的，目的就是要解决RNN最大的问题,长程梯度消失问题，对于较长的句子，我们很难寄希望于将输入的序列转化为定长的向量而保存所有的有效信息，所以随着所需翻译句子的长度的增加，这种结构的效果会显著下降。



而实现这种注意力机制的数学原理就是 加权，跟RNN类似，每一个输出都受前面输出输出序列的影响，

![image-20220628192137830](https://raw.githubusercontent.com/DejaVuyan/blog.img/main/image-20220628192137830.png)

算相关系数，decoder的hidden state是St-1,而encoder的hidden state为h，算相关系数的时候需要对所有encoder的节点计算相关系数，然后更具相关系数求出attention系数，根据attention系数去计算下一个decoder的hidden state



##### self attention

Attention机制详解（二）——Self-Attention与Transformer - 川陀学者的文章 - 知乎 https://zhuanlan.zhihu.com/p/47282410

