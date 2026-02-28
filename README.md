深度学习入门②：自然语言处理篇（Deep Learning From Scratch 2）
==========================

[<img src="https://raw.githubusercontent.com/oreilly-japan/deep-learning-from-scratch-2/images/deep-learning-from-scratch-2.png" width="200px">](https://www.oreilly.co.jp/books/9784873118369/)

本书是[深度学习入门②—— 自然语言处理篇](https://www.oreilly.co.jp/books/9784873118369/)（ O'Reilly Japan 出版）的配套支持网站。本仓库包含了书中所使用的全部源代码。


## 目录结构

|文件夹名称 |说明                         |
|:--        |:--                          |
|ch01       |第1章使用的源代码    |
|ch02       |第2章使用的源代码    |
|...        |...                          |
|ch08       |第8章使用的源代码    |
|common     |各章节共用的函数及类   |
|dataset    |数据集相关的源代码 |

训练好的权重文件（用于第 6 章和第 7 章）可以从以下 URL 获取：
<https://www.oreilly.co.jp/pub/9784873118369/BetterRnnlm.pkl>

注意： 关于源代码的详细讲解，请参阅原书内容。


## Python 与外部依赖库
运行源代码需要以下软件环境：

* Python 3.x（版本 3 系列）
* NumPy
* Matplotlib
 
此外，还可以选择性地使用以下库（可选）：

* SciPy（可选）
* CuPy（可选）

## 运行方法

进入各章节对应的文件夹，运行相应的 Python 命令。

```
$ cd ch01
$ python train.py

$ cd ../ch05
$ python train_custom_loop.py
```

## 开源协议

本仓库中的源代码采用[MIT 许可证](http://www.opensource.org/licenses/MIT)。
无论是商业还是非商业用途，均可自由使用。

## 勘误表

本书的勘误信息发布在以下页面：

https://github.com/oreilly-japan/deep-learning-from-scratch-2/wiki/errata

如果您发现了页面中未列出的排版错误或内容疏漏，请通过邮件告知：[japan@oreilly.co.jp](<mailto:japan@oreilly.co.jp>)
