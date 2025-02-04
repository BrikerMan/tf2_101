<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<h1 align="center">
    <a>Tensorflow 2.0 技术实战详解</a>
</h1>

这里整理了本书所有的代码、基础数据集、扩展数据集和一些扩展阅读资源。建议在阅读每一章之前先把基础数据集下载到指定的路径，再配合该章节的笔记本阅读书上内容。

**本书所有代码除特殊说明均在 jupyer lab 上执行**

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->

- [第 1 章 环境配置](#第-1-章-环境配置)
  - [1.1 云端 Notebook 环境介绍](#11-云端-notebook-环境介绍)
  - [1.2 本地 Notebook 环境准备](#12-本地-notebook-环境准备)
  - [1.3 代码规范介绍](#13-代码规范介绍)
- [第 2 章 常见工具介绍](#第-2-章-常见工具介绍)
  - [2.1 扩展资料](#21-扩展资料)
- [第 3 章 从零搭建神经网络](#第-3-章-从零搭建神经网络)
  - [3.1 扩展资料](#31-扩展资料)
- [第 4 章 深度学习基础](#第-4-章-深度学习基础)
  - [4.1 扩展资料](#41-扩展资料)
- [第 5 章 泰坦尼克幸存者预测](#第-5-章-泰坦尼克幸存者预测)
  - [5.1 扩展资料](#51-扩展资料)
- [第 6 章 TensorFlow 2.0 介绍](#第-6-章-tensorflow-20-介绍)
  - [6.1 扩展资料](#61-扩展资料)
- [第 7 章 图像识别入门](#第-7-章-图像识别入门)
  - [7.1 扩展资料](#71-扩展资料)
- [第 8 章 图像识别进阶](#第-8-章-图像识别进阶)
  - [8.1 扩展资料](#81-扩展资料)
- [第 9 章 图像画风迁移](#第-9-章-图像画风迁移)
  - [9.1 扩展资料](#91-扩展资料)
- [第 10 章 自然语言处理入门](#第-10-章-自然语言处理入门)
  - [10.1 扩展资料](#101-扩展资料)
  - [10.2 论文](#102-论文)
- [第 11 章 语音助手意图分类](#第-11-章-语音助手意图分类)
  - [11.1 扩展资料](#111-扩展资料)
- [第 12 章 自然语言生成实战](#第-12-章-自然语言生成实战)
  - [12.1 扩展资料](#121-扩展资料)
- [第 13 章 中文实体识别实战](#第-13-章-中文实体识别实战)
- [第 14 章 生成对抗网络](#第-14-章-生成对抗网络)
  - [14.1 扩展资料](#141-扩展资料)
- [第 15 章 强化学习](#第-15-章-强化学习)
  - [15.1 扩展资料](#151-扩展资料)

# 第 1 章 环境配置

在本章中，你将学习如何准备和使用深度学习 Notebook 环境以及本书的代码规范。
本书代码环境为 Python 3.6+ 和 Tensorflow 2.0，所有的代码需要在 Notebook 环境中执行。

## 1.1 云端 Notebook 环境介绍

配置本地 GPU 环境比较麻烦，推荐读者们使用云端 Notebook 平台。
云 Notebook 环境都提供了 CPU 环境和 GPU 环境，对于不要求很大算力的项目，建议使用 CPU 环境，以免浪费资源。

| 平台                | 是否收费 | 需要外网 | 相关文章                            |
| ------------------- | -------- | -------- | -----------------------------------|
| [OpenBayes]（推荐） | 是       | 否       | [OpenBayes 下识别手写数字]          |
| [Kaggle]            | 否       | 否       | [如何用 Kaggle Kernels 免费使用GPU] |
| [Colab]             | 否       | 是       | [设置Google-colab使用免费GPU]       |

## 1.2 本地 Notebook 环境准备

配置本地 Notebook 环境建议使用 Anaconda，在 Ubuntu/Mac OS X 系统环境安装。

- [Anaconda 官网](https://www.anaconda.com/distribution/#download-section)

## 1.3 代码规范介绍

- [PEP8 代码规范](https://juejin.im/post/58b129b32f301e006c035a62)
- [全面理解 Python 中的类型提示（Type Hints）](https://sikasjc.github.io/2018/07/14/type-hint-in-python/)

# 第 2 章 常见工具介绍

在本章中，你将学习 Python 数据处理中最常用的三个工具 Numpy, Pandas, Matplotlib。几乎每一个实验都会用到这几个工具。熟练掌握它们是学习深度学习中的第一步。

- [代码 Notebook 文件](chapter-02.ipynb) 建议使用 CPU 运行环境。

## 2.1 扩展资料

- [NumPy 官方快速入门教程(译)](https://juejin.im/post/5a76d2c56fb9a063557d8357)
- [十分钟的 pandas 入门教程](https://ericfu.me/10-minutes-to-pandas/)
- [Matplotlib 教程 | 菜鸟教程](https://www.runoob.com/w3cnote/matplotlib-tutorial.html)
- [Pandas Profiling-一键生成数据报告](https://mathpretty.com/11152.html)

# 第 3 章 从零搭建神经网络

在本章中您将通过动手实现一个神经网络来学习神经网络基础知识。由于本章重点在于动手实现，有不少知识点一带而过，所以实现过程遇到不懂的概念和公式不要慌，继续按照代码示例把神经网络实现了。实现完成后继续看第4章，看完第4章回过头来再看一遍第3章就能理解大部分内容。至于数学公式和推导，您只需要知道哪个阶段用了什么公式即可，并不要求掌握具体的推导过程。

- [代码 Notebook 文件](chapter-03.ipynb) 建议使用 CPU 运行环境。

## 3.1 扩展资料

- [Machine Learning for Beginners: An Introduction to Neural Networks](https://victorzhou.com/blog/intro-to-neural-networks/)

# 第 4 章 深度学习基础

本章您将学习深度学习的基本概念、模型评估方案以及如何解决模型的欠拟合过拟合。尽管深度学习中概念非常多，背后涉及大量的数学知识，但初学阶段不用太担心，建议先大体了解这些概念，再通过一个个实践项目去深入理解。

## 4.1 扩展资料

- [Google 机器学习速成课程 - 机器学习简介](https://developers.google.cn/machine-learning/crash-course/ml-intro)

# 第 5 章 泰坦尼克幸存者预测

在本章中你将通过搭建一个神经网络模型，了解深度学习的工作流程。读者们如果能够按照本章代码重现实验结果，完成 hello world 项目，就达成了学习目标。

- [代码 Notebook 文件](chapter-05.ipynb) 建议使用 CPU 运行环境。

## 5.1 扩展资料

- [Kaggle 竞赛 - Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic)

# 第 6 章 TensorFlow 2.0 介绍

在本章中，您将学习 TensorFlow 2.0 版本的新特性，模型保存方法，训练回调函数和可视化。模型保存和训练回调是所有深度学习任务必须要掌握的技能，训练可视化则可以帮助您更好地理解和调试模型。

- [代码 Notebook 文件](chapter-06.ipynb) 建议使用 CPU 运行环境。

## 6.1 扩展资料

- [初学者的 TensorFlow 2.0 教程](https://www.tensorflow.org/tutorials/quickstart/beginner)

# 第 7 章 图像识别入门

在本章中，您将构建一个简单的模型入门图像识别，然后用卷积神经网络来优化图像识别的效果。

- [代码 Notebook 文件](chapter-07.ipynb) 建议使用 CPU 运行环境。

## 7.1 扩展资料

- [cs231n - Convolutional Neural Networks (CNNs/ConvNets)](https://cs231n.github.io/convolutional-networks/)

# 第 8 章 图像识别进阶

本章我们通过一个花朵种类分类问题进一步学习图像识别。真实的图像识别问题中，需要从磁盘读取图片文件，进行预处理和数据增强才能开始训练模型。除了数据增强，我们还可以通过迁移学习的方案大幅度降低训练成本，快速获得表现很好的模型。

**数据集下载**

下载 TensorFlow 官方提供的花分类数据集
（[https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz](https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz)），
并且解压到 `data/flower_photos` 目录下。

**新增依赖**

```bash
pip install pillow
pip install tensorflow_hub
```

- [代码 Notebook 文件](chapter-07.ipynb) 建议使用 GPU 运行环境。

## 8.1 扩展资料

- [Pillow 框架介绍](https://www.liaoxuefeng.com/wiki/1016959663602400/1017785454949568)
- [TensorFlow Hub 官网](https://www.tensorflow.org/hub)

# 第 9 章 图像画风迁移

- [代码 Notebook 文件](chapter-09.ipynb) 建议使用 GPU 运行环境。

**数据集**

数据已经下载并且存到 `data/style-tranfer` 目录下。如果想换别的图像做风格转换，可以从 [无版权图库 unsplash](https://unsplash.com/) 下载图像使用。

## 9.1 扩展资料

- [无版权图库 unsplash](https://unsplash.com/) 该章节内容图来自该站点。

# 第 10 章 自然语言处理入门

在本章中，我们将学习文本数据预处理，向量表示和循环神经网络的概念基础。

- [代码 Notebook 文件](chapter-10.ipynb) 建议使用 CPU 运行环境。

**数据集**

- 预训练词嵌入：从仓库 [Chinese-Word-Vectors](https://github.com/Embedding/Chinese-Word-Vectors) 下载微博词嵌入，选择 Word2vec / Skip-Gram with Negative Sampling (SGNS) 分类下 Word + Character + Ngram 方式训练的词向量。下载词向量为 bz2 格式的压缩文件，解压压缩文件 `sgns.weibo.bigram-char.bz2` 到 `data/word2vec/sgns.weibo.bigram-char` 路径下。

## 10.1 扩展资料

- [Word2Vec 可视化](https://projector.tensorflow.org/)
- [The Illustrated Word2vec](https://jalammar.github.io/illustrated-word2vec)
- [The Illustrated BERT, ELMo, and co. (How NLP Cracked Transfer Learning)](https://jalammar.github.io/illustrated-bert/)
- [理解 LSTM 网络](https://www.jianshu.com/p/9dc9f41f0b29)

## 10.2 论文

- [Semi-supervised sequence tagging with bidirectional language models](https://arxiv.org/abs/1705.00108)
- [Learned in Translation: Contextualized Word Vectors](https://arxiv.org/abs/1708.00107)
- [Deep contextualized word representations](https://arxiv.org/pdf/1802.05365.pdf)

# 第 11 章 语音助手意图分类

在本章中，我们通过解决一个语音助手类场景下的意图分类问题学习中文文本分类建模流程。对于短文本小语料类场景，我们通常使用预训练词嵌入提高模型性能和泛化能力。

- [代码 Notebook 文件](chapter-11.ipynb) 建议使用 CPU 运行环境。

**数据集**

- [中文人机对话技术评测语料 SMP2018-ECDT-TASK1](https://worksheets.codalab.org/worksheets/0x27203f932f8341b79841d50ce0fd684f/) ：用于本实验，已经下载保存到 `data/SMP2018-Task-1` 目录。
- [THUCNews 数据集子集](https://pan.baidu.com/s/1hugrfRu)：密码: qfud，THUCNews 的子集。该数据集包括 `体育, 财经, 房产, 家居, 教育, 科技, 时尚, 时政, 游戏, 娱乐` 十分类的数据，每个分类包括 6500 条新闻。感谢 [@gaussic](https://github.com/gaussic) 分享。如果需要完整数据集请自行到 [THUCTC：一个高效的中文文本分类工具包](http://thuctc.thunlp.org/) 下载。可以自行在这个数据集上做分类实验。

## 11.1 扩展资料

- [Natural Language Processing: Text Classification](https://paperswithcode.com/task/text-classification)
- [What is Text Classification?](https://monkeylearn.com/text-classification/)
- [TensorFlow Guides: Text classification](https://developers.google.com/machine-learning/guides/text-classification)

# 第 12 章 自然语言生成实战

在本章中，读者将学习如何使用编码-解码架构构建一个自然语言生成模型。通过写诗和翻译两个实例，分别了解 LSTM 语言模型和 Seq2Seq。

- [代码 Notebook 文件 - LSTM 写诗](chapter-12-1.ipynb) 建议使用 GPU 运行环境。
- [代码 Notebook 文件 - Seq2Seq 翻译](chapter-12-2.ipynb) 建议使用 GPU 运行环境。

**数据集**

- 古诗数据集：下载 [古诗-简体](https://github.com/chinese-poetry/chinese-poetry-zhCN) 仓库，复制  `poetry` 目录到 `data/poetry`。
- 翻译数据集：从 http://www.manythings.org/anki/ 下载中文-英文翻译数据集，并解压到 `data/cmn-eng` 目录。

## 12.1 扩展资料

- [循环神经网络（RNN）文本生成: 莎士比亚作品](https://www.tensorflow.org/tutorials/text/text_generation)
- [Beginners Guide to Text Generation using LSTMs](https://www.kaggle.com/shivamb/beginners-guide-to-text-generation-using-lstms)

# 第 13 章 中文实体识别实战

命名实体识别是自然语言处理中最基础的任务之一。本章中我们以人民日报语料实体识别任务为例，学习如何实现文本序列标注。同时学习如何使用BERT实现迁移学习来提高模型效果。

- [代码 Notebook 文件](chapter-13.ipynb) 建议使用 GPU 运行环境。

**数据集**

- 人民日报 NER 数据集：经典的命名实体识别数据集， 流传时间很长，比较难以确定数据来源。已下载到 `data/peoples-daily-ner`。
- BERT 中文模型：从 [BERT 官网](https://github.com/google-research/bert) 下载 `BERT-Base, Chinese` 模型，解压到 `data/bert/chinese_L-12_H-768_A-12` 目录下。

**新增依赖**

```bash
pip install keras_bert
```

<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
[OpenBayes]: https://openbayes.com/
[OpenBayes 下识别手写数字]: https://openbayes.com/docs/tutorial-mnist/
[Kaggle]: https://www.kaggle.com
[如何用 Kaggle Kernels 免费使用GPU]: https://zhuanlan.zhihu.com/p/36824585
[Colab]: https://colab.research.google.com/
[设置Google-colab使用免费GPU]: https://gabriel1225.github.io/%E8%AE%BE%E7%BD%AEGoogle-colab%E4%BD%BF%E7%94%A8%E5%85%8D%E8%B4%B9GPU.html
<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->

# 第 14 章 生成对抗网络

本章将通过生成手写数字图像实践，学习生成式对抗网络原理和训练方法。

## 14.1 扩展资料

- [Keras GAN](https://github.com/eriklindernoren/Keras-GAN)
- [DCGAN - TensorFlow 官方教程](https://www.tensorflow.org/tutorials/generative/dcgan)
- [pix2pix - TensorFlow 官方教程](https://www.tensorflow.org/tutorials/generative/pix2pix)
- [CycleGAN - TensorFlow 官方教程](https://www.tensorflow.org/tutorials/generative/cyclegan)

# 第 15 章 强化学习

本章将通过 gym 强化学习环境，学习如何利用 Q-Learning 和 Deep Q Network 解决简单强化学习任务。

## 15.1 扩展资料

- [Gym 框架](https://gym.openai.com/)
- [Introduction to RL and Deep Q Networks - TensorFlow 官方教程](https://www.tensorflow.org/agents/tutorials/0_intro_rl)
