## 1. 单词的分布式表示与 word2vec (词向量相关)
* 分布式表示 (Distributed Representation)：书中通常不直呼“词向量”，而是使用“单词的分布式表示”，指将单词表示为固定长度的密集向量。

* 语料库 (Corpus)：包含大量用于自然语言处理的文本数据。

* 同义词词典 (Thesaurus)：如 WordNet，通过人工定义单词含义及层级关系（书中指出了其难以顺应时代变化等缺陷）。

* 共现矩阵 (Co-occurrence Matrix)：基于计数的方法中，用于汇总单词上下文中包含的其他单词频数的矩阵。

* 余弦相似度 (Cosine Similarity)：测量单词向量间相似度的常用指标。

* 点互信息 (PMI) / 正的点互信息 (Positive PMI, PPMI)：解决高频词（如the）干扰问题的指标。PPMI 将负值视为 0。

* 奇异值分解 (Singular Value Decomposition, SVD)：一种降维（Dimensionality Reduction）方法，书中用于将稀疏的 PPMI 矩阵转化为密集的单词分布式表示。

* word2vec：书中统一全小写。一种基于推理的方法（神经网络）。

* CBOW 模型 (Continuous Bag-of-Words)：从周围单词（上下文）预测中间单词（目标词）的模型。

* skip-gram 模型：从中间单词（目标词）预测周围多个单词（上下文）的模型。

## 2. 循环神经网络 (RNN) 与时序数据
* RNN (Recurrent Neural Network)：书中称为“循环的神经网络”或直接简称 RNN。

* BPTT (Backpropagation Through Time)：处理时序数据的误差反向传播法。

* Truncated BPTT (截断的 BPTT)：为了解决长序列反向传播内存和计算问题，在适当长度将网络连接“截断”的学习方法。

* 梯度消失 (Vanishing Gradient) / 梯度爆炸 (Exploding Gradient)：RNN 学习过程中的两大难题。应对梯度爆炸的对策书中提到了梯度裁剪 (Gradients Clipping)。

* 语言模型 (Language Model)：计算单词序列发生概率的模型。书中在第 5 章使用 RNN 实现该模型（RNNLM），并通过困惑度 (Perplexity) 进行评价。

# 3. 高级时序网络 (LSTM / GRU)
* LSTM (Long Short-Term Memory)：通过引入记忆单元和“门”结构解决梯度消失问题的层。

* 输入门 (Input Gate)、遗忘门 (Forget Gate)、输出门 (Output Gate)：LSTM 内部的控制机制。书中直接采用直译。

* GRU (Gated Recurrent Unit)：LSTM 的简化版本，参数更少（在本书的附录 C 中有专门介绍）。

## 4. 序列到序列与注意力机制 (seq2seq & Attention)
* seq2seq：书中统一全小写。指将一个时序数据转化为另一个时序数据的模型。

* 编码器 (Encoder) / 解码器 (Decoder)：构成 seq2seq 的两个核心组件，书中也将其封装为对应的类。

* 反转 (Reverse) / 偷窥 (Peeky)：书中第 7 章介绍的两种改进 seq2seq 准确度的小技巧（反转输入数据顺序，以及让解码器所有时刻都能“偷窥”到编码信息）。

* Attention：书中首字母大写且不强制翻译为中文（极少用“注意力机制”），指的是让模型在解码时关注输入序列特定部分的技术结构。

## 5. 书中特有的层 (Layers) 命名规范
本书坚持“像搭建乐高积木一样”用类（Class）构建神经网络，因此很多术语直接保留了代码中的层级命名：

* Embedding 层：取代了低效的 one-hot 表示，直接从权重参数中抽取单词 ID 对应行向量的层（书中不用“词嵌入层”一词，直接叫 Embedding 层）。

* 负采样 (Negative Sampling)：书中第 4 章用于给 word2vec 提速的核心技术，将多分类问题转化为二分类问题，并通过概率分布抽取少数“负例”（错误答案）。

* Softmax with Loss 层 / Sigmoid with Loss 层：将输出层激活函数（Softmax/Sigmoid）和损失函数（交叉熵误差 Cross Entropy Error）组合在一起的计算层，反向传播极其高效。

* Affine 层：执行全连接层的线性变换（矩阵乘积与偏置加法）的层。