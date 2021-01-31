# 结合物理机制的机器学习水文建模概述

根据[Theory-guided Data Science: A New Paradigm for Scientific Discovery from Data](https://doi.org/10.1109/TKDE.2017.2720168)这篇综述性质的论文，数据驱动和物理机制驱动的模型各有优劣，结合两者成为了进一步推进水文建模研究的重要手段。以下列出近几年在水文建模领域结合物理方程和机器学习算法的文章。更多相对基础一些的文章（机器学习和微分方程结合的基础理论性质的文章）放到最后，因为个人水平目前还比较难直接阐述出来，所以仅列出备查。

## [COMBINING PARAMETRIC LAND SURFACE MODELS WITH MACHINE LEARNING](http://arxiv.org/abs/2002.06141)

为了判断机器学习（ML）模型是否能学习到水文过程中的规律，结合ML和基于物理理解的模型（PBM）是一种可行方式。典型地有两种方式，其一是将物理理解作为ML地约束；其二是整合PBM和ML。这篇文章是第二种，目的是在从ML中学习新物理规律之前，先构建一个可靠的能capture基本物理过程的全局ML模型。具体来说，基于这样一个原则：在和训练数据相似的气候条件下才用ML，否则就退化为纯粹的PBM，为方便，称之为Hybrid-PBM（HPBM）。这种方式还有一个优点，就是非常灵活，有数据就数据驱动，没有的时候退化成PBM即可。为了数字化表达这样的思路，采用了高斯过程（GP）作为ML模型（*高斯过程是如何表达相似和不相似的？*）。
$$\phi (v_t)= f(v_t)+GP(v_t)$$
其中，f是物理模型，$\phi(v_t)$是总模型。等式右边第二项换成白噪声时，就是一个典型的数据同化问题的方程了。所以HPBM是一种数据同化形式。ML模型在使用观测数据来修正PBM。不过和典型的DA还是有区别。该模型增加了随机波动并用了贝叶斯方式来基于观测修正模型。GP是结构化的校正项并能学习模型结构误差（所以这是一种误差校正的方式）。

实例是预测下一时段土壤含水量，物理模型是Noah模型，输入是当前时段土壤含水量。GP训练对象是 $y_{t+1}-f(y_t)$和$y_t$的回归关系。

从图3看结果，HPBM的预测明显和观测更接近，而Noah的预测结果相比较而言弱了很多。

## [A physical process and machine learning combined hydrological model for daily streamflow simulations of large watersheds with limited observation data](https://doi.org/10.1016/j.jhydrol.2020.125206)

这篇文章是在大流域来做径流预测，在物理机制的结合方面，主要是利用了随机降雨生成器和分布式模型作为训练样本的构造器，然后用模拟的结果来训练神经网络，个人理解是起到了一种比较好的预热作用，因为物理基础模型的加入，神经网络的初值在利用了物理知识带来的信息后能达到比较好的状态，所以相比于随机的初始化能够起到更好的训练和验证效果。

表格5展示了个人比较关注的结果，可以看到，有GBHM这一水文模型指导下的ANN在大多数情况下都能展示出比ANN更好的效果。

## [Physics-inspired integrated space-time Artificial Neural Networks for regional groundwater flow modeling](https://doi.org/10.5194/hess-24-5759-2020)

对地下水位的预测通常都是在单个观测井建立预测模型，然后通过地理插值等方式形成这样一种两阶段预测模型来构建能反映时空变化的地下水位预测模型。但是这种方法人为解耦了时间（单个well上的模型）和空间（空间插值或统计等区域化方法）两块变化，会使模型保真性变差。

这篇文章根据地下水控制方程（见原文式1，基本原理可参考[这里](http://ecoursesonline.iasri.res.in/mod/page/view.php?id=1818#:~:text=The%20flow%20of%20fluids%20through,be%20described%20by%20differential%20equations.&text=Thus%2C%20the%20governing%20equations%20of,the%20derivation%20is%20presented%20below.)）的一阶差分形式，设计了ANN的输入，比如位置坐标反映含水层属性，前序水位反映persistence，临近水位反映地下水不同位置的空间关系，Pumping等反映stressors，并在德州100多个地下水观测井进行了模型训练和测试，结果没有对比基准，所以个人没法判断效果，不过图6展示了一些性能指标，KGE可以看到绝大多数还是非常好的（>0.9）。说明从方程出发，直接用ANN就能得到很好的效果。

## [Physics-Constrained Machine Learning of Evapotranspiration](https://doi.org/10.1029/2019GL085291)

这篇文章的新方法是用ANN预测公式中的$r_s$，而不是直接预测Latent heat flux（LE），然后利用Penman-Monteith公式算LE。具体公式是$aH^2+bH+c=0$，是二阶的PM公式表示，a，b，c中有$r_s$项，一元二次方程可以计算出H，最后根据能量平衡公式$R_n=LE+G+H$可以算出来LE。也就是模拟预测的过程中所有量都是正向可以计算出来的。对于观测值，r_s是没有观测的，所以Loss的计算不是根据r_s的，是根据计算H的公式的，即LE已知，那么可以根据平衡公式知道观测的H，H知道了，联立$aH^2+bH+c=0$和a,b,c的关系式，可以计算得到a，b和c，a因为特别小，所以计算loss的时候不考虑，对b和c，一起和预测值进行比较作为loss。

从图2结果看，虽然预测LE的能力和pure ML差别不大，但是因为融入了能量平衡公式，所以可以很好地表达能量平衡。

## [Physics-Informed Deep Neural Networks for Learning Parameters and Constitutive Relationships in Subsurface Flow Problems](https://doi.org/10.1029/2019WR026731)

这篇文章谈到，对于 partially known physics and sparse data 的问题，是比较适合physics-informed machine learning的。具体关注了两个问题，一是未知传导率的异构孔隙介质的饱和流问题，一是未知毛细管压力和不饱和传导率关系的同构孔隙介质的非饱和流问题。总体的方法是利用守恒律和数据一起来训练表示状态（水头或毛细管压力）、空间相关的系数（水力传导率）和本构关系（毛细管压力和相对传导率关系）的DNN。

传统的方法是将以参数估计的形式来解决这些问题，诸如贝叶斯推断等，这些方法太耗时，且初始边界条件由于未知，同样需要参数估计。另外，如何从partially known models和不多的data中学习unknown physics仍值得探索。未知的方程可以根据upscaling从微观的方程得来，也可以从数据学习，这篇文章关注的是后者。

问题的形式可以参考原文式2，就是典型的[扩散方程](https://zh.wikipedia.org/wiki/%E6%89%A9%E6%95%A3%E6%96%B9%E7%A8%8B)。这篇文章关注其两个退化形式，一个是扩散系数K仅和空间相关时（即线性扩散方程），有观测u和K，关注如何学习 K(x)，一个是K仅和方程状态相关时（还是一个非线性方程），u有观测，学习K(u)。

具体方法就是Physics-Informed Neural Network, PINN。PDEs和数据一起用来训练偏微分方程状态、未知参数和本构关系的DNN表示。用两个DNN，一个表示K(x,u)，一个表示u(x)，然后换到方程中去，接着用自动微分来计算等式2的右侧以及边界条件（[Dirichlet BC](https://zh.wikipedia.org/wiki/%E7%8B%84%E5%88%A9%E5%85%8B%E9%9B%B7%E8%BE%B9%E7%95%8C%E6%9D%A1%E4%BB%B6)和[Neumann BC](https://zh.wikipedia.org/wiki/%E8%AF%BA%E4%BC%8A%E6%9B%BC%E8%BE%B9%E7%95%8C%E6%9D%A1%E4%BB%B6)）。

首先，用DNN表示所有的未知量，DNN的表示见原文式3和4，最后DNN的参数$\theta$就是所有权重。每个权重的维度和输入向量是一致的，DNN的输出自然和相应的输出向量要一致。因为用DNN估计二阶PDE的状态，所以需要激活函数二阶可导，因此选了tanh（无限可导）。估计参数$\theta$的过程就是寻找最小化loss的x值的过程。loss函数的表达见原文式6。优化的过程需要梯度下降类算法，都要计算到输出向量对参数的导数。Tensorflow和Pytorch都是用自动微分（AD）来计算这些导数的。以PDE方程的形式实施物理约束需要计算输出向量对输入向量的导数。在PINN方法中，也使用AD来计算DNN的空间导数，这使得物理PDE约束得以实施，而无需进行数值离散和求解PDE（具体的计算过程可能是比较基础的数学过程了，这里确实是没有细说的）。最后形成的loss函数可见原文式13，总之是K,u,两个BC条件和PDE的表达的一个整合。

从结果图8可以看到PINN和最大后验估计（MAP）的对比，PINN还是有优势的。

## [Physics-Informed Neural Networks for Multiphysics Data Assimilation with Application to Subsurface Transport](https://doi.org/10.1016/j.advwatres.2020.103610)

这篇文章主要是利用神经网络求解参数反演问题，由于地下水问题（subsurface flow and transport equations）的高度非线性及状态和参数的非高斯性，使得直接的反演方法和贝叶斯参数估计方法面临一定困难，因此这篇文章从PINN的角度（和上面文章基本方法一致），利用神经网络来推求方程的状态和参数，其中的可观测值用来计算神经网络本身的loss，再利用这些状态和参数带入微分方程及其边界条件，构成另两项破坏方程平滑的惩罚项来作为总体loss中除神经网络本身loss之外的另两项loss，惩罚项系数定为常数1。这样就将物理规则和神经网络结合起来，同时利用两者的信息，具体公式见原文式3。

具体的方法方面，神经网络的loss计算肯定是基于可观测的locations的，对于物理方程的惩罚约束，是针对residual locations的（residual什么意思还需要进一步理解），当然在所有点上执行计算是较好的，但是计算的cost是随着residual points的增多而增加的。物理方程的惩罚loss具体计算由自动微分来执行（个人理解，把公式用pytorch或tensorflow的张量变量写出来，然后loss要加到一起，反向传播回神经网络，就能计算了，更细致内容可以查看code）。各loss项具体的计算公式在原文公式（B.4）到（B.6）。整体的框架可以参考原文图1。

结果上看，MPINN（这篇文章的方法）比PINN（联合darcy公式计算一部分参数来帮助训练DNN模型）的结果好（相对误差小），PINN又明显由于DNN（原文图3，5）。结论是对于数据稀少的研究领域，这种结合的方式能避免overfit的情况，方程能起到非监督训练的效果。文章代码在[这里](https://github.com/qzhe-mechanics/DataAssi-transport)

## [A Framework for Modeling Flood Depth Using a Hybrid of Hydraulics and Machine Learning](http://dx.doi.org/10.1038/s41598-020-65232-5)

这篇文章思路上不复杂，主要是用水动力模型作为surrogate model来快速求解flood depth的建模问题。水力学模型模拟结果作为ML模型的训练样本。

## [Deep Learning of Subsurface Flow via Theory-guided Neural Network](http://arxiv.org/abs/1911.00103)

这篇文章不仅把物理法则等加入到loss函数中，还融合了专家经验等，称为Theory-guided Neural Networks (TgNN)。这篇文章不是构建PDE solver，也不是作surrogate model，而是为了构建更准确的预测模型。

loss函数如原文公式17所示，关于PDE的部分和前面的文章方法一致（具体的执行方法和code还需要进一步的了解）；一些专家经验转换为不等式，配合ReLU函数可以构建适合于计算loss函数的形式，如公式13和14所示。

根据图4的结果，可以看到很明显 TgNN 的预测能力要优于DNN。

## [Performance Enhancement of a Conceptual Hydrological Model by Integrating Artificial Intelligence](http://ascelibrary.org/doi/10.1061/%28ASCE%29HE.1943-5584.0001850)

这篇文章是没有直接利用自动微分来融合神经网络与物理模型，而是采用了一种间接的方式，利用遗传算法来同时优化神经网络和物理模型的参数，这样来整合两者。神经网络替换了物理模型中的一部分（汇流部分）。

从图4结果看，NS可以提高大约0.1，还是很不错的。

## [Deep Learning for Physical Processes: Incorporating Prior Scientific Knowledge](http://arxiv.org/abs/1711.07970)

这篇文章基于对流扩散PDE方程对海温的预测（SST）来设计适合于复杂系统的机器学习结构。

方程可见原文式3，对流方程的介绍可以参考[这里](https://www.cs.cmu.edu/~16385/s17/Slides/14.1_Brightness_Constancy.pdf)；对流扩散方程可以参考[这里](https://en.wikipedia.org/wiki/Convection%E2%80%93diffusion_equation)或者中文的参考可以看[这里](https://zhuanlan.zhihu.com/p/88295639)。原文式4给出了一个方程的通解形式，即任意时刻的I(x,t)可以由初值和高斯概率密度函数的卷积求得。但是在SST中，没有初值，扩散系数也不可知，必须从数据中估计。所以设计了机器学习算法。

设计的ML结构有两块，第一块是用CNN预测通解中的w项（二维变量），第二块是根据通解的一步离散形式，构建一个根据上一步像素值和CNN预测的w计算下一步像素值的方法，来得到预测目标值。

loss函数也包含了对流扩散方程中的几项，见原文式6.

对比的基准是几篇文章中的模型和结果，根据表4可以看到性能和时间两个方面，提出的方法都有很好的表现。

这篇文章确实提供了一种针对时空序列建模问题的较通用的一种建模思路，为复杂系统物理过程的建模提供了新方法，尤其是针对用到对流扩散方程的问题。

## [Physics guided RNNs for modeling dynamical systems: A case study in simulating lake temperature profiles](https://epubs.siam.org/doi/abs/10.1137/1.9781611975673.63)


这篇文章利用了两个并行的RNN来构建湖水温度预测的模型，一个是标准的RNN流，一个是capture能量平衡变化的energy流。RNN来尽可能拟合过程，energy流旨在以物理上一致的方式正则化模型的时序过程。因为数据没有那么多，所以模型还采用了物理模型（General Lake Model，GLM）模拟预热来初始化启动机器学习模型的方法。

具体结构如原文图2所示。RNN是和能量平衡的方程并行的。RNN比较好理解，关键是能量平衡怎么整合进来的。

从原文式4.7可以看出，通过对能量平衡公式左右两侧的差值不为0的情况进行惩罚，并作为loss函数的一部分来实现对物理方程的运用。所以问题的关键就是如何计算等式左右两侧。等式左侧，$U_t$和$U_{t+1}$ 根据RNN的前向计算结果和原文式4.11可以计算得到。等式右侧，$R_{LW_{in}}$和$R_{SW}$在输入中有，E、H、$R_{LW_{out}}$根据一系列公式以及RNN的前向计算结果即可获得。

这样就整合了能量平衡方程和RNN。

从结果表1可以看到RMSE，PGRNN的表现是比较好的，且有GLM预热的表现会更好。

## [Physics-guided Neural Networks (PGNN): An Application in Lake Temperature Modeling](http://arxiv.org/abs/1710.11431)

这篇文章比较详细地介绍了将物理规则引入ML的基本形式：在loss函数中表达不同的物理规则，详见原文式2.1-2.4，形式上和前面介绍的文章差不多，所以这里不赘述。

具体的实例上，物理规则是用的 Temperature-Density Relationship 得到 Density，再根据 Density-Depth的单调性，构建一个不等式约束，以ReLU的形式加入到loss函数中。

从结果图6上看，很容易看到PGNN的性能是由于NN的，且有很高的物理一致性（即有没有违反density-depth关系）。

## [Process-Guided Deep Learning Predictions of Lake Water Temperature](https://doi.org/10.1029/2019WR024922)

这篇文章和 Physics guided RNNs for modeling dynamical systems: A case study in simulating lake temperature profiles 方法基本一致，只是RNN换成了LSTM，所以这里不再赘述。

## []()



## 其他相关文献

- [Data-driven flood emulation: Speeding up urban flood predictions by deep convolutional neural networks](https://doi.org/10.1111/jfr3.12684)
- [Physics-informed GANs for Coastal Flood Visualization](http://arxiv.org/abs/2010.08103)
- [Physics Informed Data Driven model for Flood Prediction: Application of Deep Learning in prediction of urban flood development](https://arxiv.org/abs/1908.10312)
- [Non-intrusive reduced-order modeling using uncertainty-aware deep neural networks and proper orthogonal decomposition: application to flood modeling](https://www.sciencedirect.com/science/article/pii/S0021999120306288?casa_token=hVTuIoa2eRwAAAAA:2QVmvgryimvceLvFb51DF6th1_wVv14PDTfxNZZTIfmbzQS6vcQjtCECQ5lswwQtJCekPY9P2A)
- [Coupled machine learning and the limits of acceptability approach applied in parameter identification for a distributed hydrological model](https://doi.org/10.5194/hess-2019-464)
- [Gradient‐based inverse estimation for a rainfall‐runoff model](https://onlinelibrary.wiley.com/doi/abs/10.1029/2018WR024461)
- [Emulation of the Saint Venant Equations enables rapid and accurate predictions of infiltration and overland flow velocity on spatially heterogeneous surfaces](https://onlinelibrary.wiley.com/doi/abs/10.1029/2019WR025146)
- [Prognostic Validation of a Neural Network Unified Physics Parameterization](https://doi.org/10.1029/2018GL078510)
- []()

## 相对基础理论一些的文献

- [Universal differential equations for scientific machine learning](https://arxiv.org/abs/2001.04385)
- []()