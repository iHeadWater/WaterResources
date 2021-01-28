# 结合物理机制的机器学习水文建模概述

根据[]()这篇综述性质的论文，数据驱动和物理机制驱动的模型各有优劣，结合两者成为了进一步推进水文建模研究的重要手段。以下列出近几年在水文建模领域结合物理方程和机器学习算法的文章。更多相对基础一些的文章（机器学习和微分方程结合的基础理论性质的文章）放到最后，因为个人水平目前还比较难直接阐述出来，所以仅列出备查。

## [Physics-Informed Neural Networks for Multiphysics Data Assimilation with Application to Subsurface Transport](https://doi.org/10.1016/j.advwatres.2020.103610)

这篇文章主要是利用神经网络求解参数反演问题，由于地下水问题（subsurface flow and transport equations）的高度非线性及状态和参数的非高斯性，使得直接的反演方法和贝叶斯参数估计方法面临一定困难，因此这篇文章从PINN的角度，利用神经网络来推求方程的状态和参数，其中的可观测值用来计算神经网络本身的loss，再利用这些状态和参数带入微分方程及其边界条件，构成另两项破坏方程平滑的惩罚项来作为总体loss中除神经网络本身loss之外的另两项loss，惩罚项系数定为常数1。这样就将物理规则和神经网络结合起来，同时利用两者的信息，具体公式见原文式3。

具体的方法方面，神经网络的loss计算肯定是基于可观测的locations的，对于物理方程的惩罚约束，是针对residual locations的（个人模糊理解就是一个范围，神经网络loss的那些locations之外的任一个到包含神经网络的loss计算的那些locations的所有locations），当然在所有点上执行计算是较好的，但是计算的cost是随着residual points的增多而增加的。物理方程的惩罚loss具体计算由自动微分来执行（个人理解，把公式用pytorch或tensorflow的张量变量写出来，然后loss要加到一起，反向传播回神经网络，就能计算了，更细致内容可以查看code）。各loss项具体的计算公式在原文公式（B.4）到（B.6）。整体的框架可以参考原文图1。

因为我对这篇文章的问题不是很清楚，所以其输入是啥一直没看到，结果上看，MPINN（这篇文章的方法）比PINN（联合darcy公式计算一部分参数来帮助训练DNN模型）的结果好（相对误差小），PINN又明显由于DNN（原文图3，5）。结论是对于数据稀少的研究领域，这种结合的方式能避免overfit的情况，方程能起到非监督训练的效果。文章代码在[这里](https://github.com/qzhe-mechanics/DataAssi-transport)

## [COMBINING PARAMETRIC LAND SURFACE MODELS WITH MACHINE LEARNING](http://arxiv.org/abs/2002.06141)

为了判断机器学习（ML）模型是否能学习到水文过程中的规律，结合ML和基于物理理解的模型（PBM）是一种可行方式。典型地有两种方式，其一是将物理理解作为ML地约束；其二是整合PBM和ML。这篇文章是第二种，目的是在从ML中学习新物理规律之前，先构建一个可靠的能capture基本物理过程的全局ML模型。具体来说，基于这样一个原则：在和训练数据相似的气候条件下才用ML，否则就退化为纯粹的PBM，为方便，称之为Hybrid-PBM（HPBM）。这种方式还有一个优点，就是非常灵活，有数据就数据驱动，没有的时候退化成PBM即可。为了数字化表达这样的思路，采用了高斯过程（GP）作为ML模型（*高斯过程是如何表达相似和不相似的？*）。
$$\phi (v_t)= f(v_t)+GP(v_t)$$
其中，f是物理模型，$\phi(v_t)$是总模型。等式右边第二项换成白噪声时，就是一个典型的数据同化问题的方程了。所以HPBM是一种数据同化形式。ML模型在使用观测数据来修正PBM。不过和典型的DA还是有区别。该模型增加了随机波动并用了贝叶斯方式来基于观测修正模型。GP是结构化的校正项并能学习模型结构误差（所以这是一种误差校正的方式）。

实例是预测下一时段土壤含水量，物理模型是Noah模型，输入是当前时段土壤含水量。GP训练对象是 $y_{t+1}-f(y_t)$和$y_t$的回归关系。

从图3看结果，HPBM的预测明显和观测更接近，而Noah的预测结果相比较而言弱了很多。

## 其他相关文献

- [Coupled machine learning and the limits of acceptability approach applied in parameter identification for a distributed hydrological model](https://doi.org/10.5194/hess-2019-464)
- []()