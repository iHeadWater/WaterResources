# Streamflow Prediction in Dammed Basins

本文简单review关于 Streamflow Prediction in Dammed Basins（SPDB）问题相关的文献。

## Determining watershed response in data poor environments with remotely sensed small reservoirs as runoff gauges（2009）

这篇文章直接把小水库当作了水文模拟的径流站点，这样既化解了其影响，还为水文模拟贡献。

使用遥感图像估计小水库库容变化，方法就是下面曹明亮师兄的文章中利用的方法。

## Research and application of flood detention modeling for ponds and small reservoirs based on remote sensing data（2011）

这篇文章是教研室师兄的文章。使用Landsat来识别小水体以增强洪水预报的精度。

为了分析小水库的调度，首先建立小水库的库容面积关系，使用的是一种简单的方式，另一篇文章中的terrain 分类和水体分析方法，具体关系可以参考表4.

面积变化就使用Landsat的相邻两个图像之间的水体变化。这样就能获得水体体积的变化。

预报模型使用的是简单的 （P+Pa）~R 关系模型，所以直接对产流值进行校正即可。

可以发现，经过校正后，误差从之前的31.8%变为了10.1%。

## Simulating streamflow on regulated rivers using characteristic reservoir storage patterns derived from synthetic remote sensing data（2015）

这篇文章介绍了一种基于遥感数据来估计被水库调节的流域径流的方法。

主要针对一场洪水事件上分析，所以考虑的站点是一个，以及该流域里8个水库。

原文表3列出了基本上所有能用的水面高程卫星遥感数据，目前（2021年初）来看除了SWOT，都已经在运行或者结束运行了。

水库调度模型也是基于水量平衡公式，利用历史遥感卫星的数据来提取水位的平均调度模式，然后提炼一个简单的调度规则，再利用这个规则计算水库库容变化，以此来执行水库模块。

根据图5结果显示，有该水库模块的明显RMSE小很多。

## Development and evaluation of a physically-based lake level model for water resource management: A case study for Lake Buchanan, Texas（2015）

这是一篇预报水库水位变化的文章。类似的文章依据方法可以分为三类：

- 使用统计的机器学习类的方法基于历史数据来模拟水位的变化
- 基于遥感和GIS技术推求水位-面积-库容等关系来分析
- 基于物理模型的方法，气象预报和陆面模型来预报（也是这篇文章的方法）

模型是月尺度。水库的模拟用一个出流与入流和需求之间线性回归的公式来表示。

入流由陆面模型和汇流模型一起来获取。

湖面蒸发和降水也由陆面模型给出，估算的时候水面面积应该是在线模式的。

出流的相关系数还可以，在更高分辨率的模型条件下能达到0.822.

上游几个站点的R2也能在0.27到0.91之间。

## Recent progresses in incorporating human land-water management into global land surface models toward their integration into Earth system models（2016）



## Combining Landsat observations with hydrological modelling for improved surface water monitoring of small lakes（2018）


## The role of satellite-based remote sensing in improving simulated streamflow: A review（2019）

这篇文章是一篇不错的介绍遥感卫星数据在径流模拟中作用的综述，对regulated basin还专门做了一些分析。第一部分就是介绍的 高度regulated basins中径流模拟的困难。

其他的是各种遥感数据在水文模型中的应用，以及数据同化的应用。

## Hydrological model calibration for dammed basins using satellite altimetry information（2020）


## Improving Reservoir Outflow Estimation for Ungauged Basins Using Satellite Observations and a Hydrological Model（2020）


## Water resources management in a reservoir-regulated basin : Implications of reservoir network layout on stream flow and hydrologic alteration（2020）

这篇文章是一篇分析水库影响的文章，我这里主要关注下其reservoir scheme

水库的库容面积关系很难每个水库都知道，所以直接使用 empirical correlation。作者用遥感数据来拟合其中的系数，但是论文里包括他文中引用的他自己的论文里都没给出详细地处理遥感数据的过程。

水库调度模块用的是Zhao2016那篇文章中的模式。
