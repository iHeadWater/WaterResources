# 大坝水库（湖泊）数据

- Surface Water Body Detection in Polarimetric SAR Data Using Contextual Complex Wishart Classification
- A reservoir storage estimation algorithm using digital elevation data and image classifications
- AltEx: An open source web application and toolkit for accessing and exploring altimetry datasets
- Water-volume variations of Lake Hulun estimated from serial Jason altimeters and Landsat TM/ETM+ images from 2002 to 2017
- A global lake and reservoir volume analysis using a surface water dataset and satellite altimetry
- A novel water body extraction neural network ( WBE-NN ) for optical high- resolution multispectral imagery
- Four decades of wetland changes in Dongting Lake using Landsat observations during 1978–2018
- Evaluation of a new 18-year MODIS-derived surface water fraction dataset for constructing Mediterranean wetland open surface water dynamics
- Research and application of flood detention modeling for ponds and small reservoirs based on remote sensing data
- Dataset of Georeferenced Dams in South America (DDSA)
- Global Characterization of Inland Water Reservoirs Using ICESat ‐ 2 Altimetry and Climate Reanalysis
- Mapping and sampling to characterize global inland water dynamics from 1999 to 2018 with full Landsat time-series
- Remote sensing estimation of catchment-scale reservoir water impoundment in the upper Yellow River and implications for river discharge alteration
- Surface water monitoring in small water bodies: Potential and limits of multi-sensor Landsat time series
- Determining watershed response in data poor environments with remotely sensed small reservoirs as runoff gauges
- Assessment of the geometry and volumes of small surface water reservoirs by remote sensing in a semi-arid region with high reservoir density
- An approach for global monitoring of surface water extent variations in reservoirs using MODIS data
- Hydrological model calibration for dammed basins using satellite altimetry information
- Estimating reservoir evaporation losses for the United States: Fusing remote sensing and modeling approaches
- Automatic Correction of Contaminated Images for Assessment of Reservoir Surface Area Dynamics
- Combining Landsat observations with hydrological modelling for improved surface water monitoring of small lakes
- SOLS: A lake database to monitor in the Near Real Time water level and storage variations from remote sensing data
- Constructing long-term high-frequency time series of global lake and reservoir areas using Landsat imagery
- Dynamic Waterline Mapping of Inland Great Lakes Using Time-Series SAR Data from GF-3 and S-1A Satellites: A Case Study of DJK Reservoir, China
- Monitoring reservoir storage in South Asia from multisatellite remote sensing
- Spatiotemporal densification of river water level time series by multimission satellite altimetry
- MAPPING SURFACE WATER IN COMPLEX AND HETEROGENEOUS ENVIRONMENTS USING REMOTE SENSING
- An improved approach to monitoring Brahmaputra River water levels using retracked altimetry data
- A global lake and reservoir volume analysis using a surface water dataset and satellite altimetry
- Potential and limitations of satellite altimetry constellations for monitoring surface water storage changes – A case study in the Mississippi basin
- Modelling Freshwater Resources at the Global Scale: Challenges and Prospects
- A predictive model for Lake Chad total surface water area using remotely sensed and modeled hydrological and meteorological parameters and multivariate regression analysis
- Monthly estimation of the surface water extent in France at a 10-m resolution using Sentinel-2 data
- Tracking Multidecadal Lake Water Dynamics with Landsat Imagery and Topography/Bathymetry
- Analysis of water clarity decrease in Xin'anjiang Reservoir, China, from 30-Year Landsat TM, ETM+, and OLI observations
- Construction of the 500-m Resolution Daily Global Surface Water Change Database (2001–2016)
- Lake Topography and Active Storage From Satellite Observations of Flood Frequency
- Detecting, Extracting, and Monitoring Surface Water From Space Using Optical Sensors: A Review
- Water body extraction from very high spatial resolution remote sensing data based on fully convolutional networks
- A high-resolution bathymetry dataset for global reservoirs using multi-source satellite imagery and altimetry
- Surface water detection and delineation using remote sensing images: a review of methods and algorithms
- Analysis of the Dynamic Changes of the Baiyangdian Lake Surface Based on a Complex Water Extraction Method
- Assessing the impacts of reservoir operation on downstream water diversions using a simplified flow model
- A data-driven analysis of frequent patterns and variable importance for streamflow trend attribution
- Development and evaluation of a physically-based lake level model for water resource management: A case study for Lake Buchanan, Texas
- Simulating streamflow on regulated rivers using characteristic reservoir storage patterns derived from synthetic remote sensing data
- Incorporating reservoir impacts into flood frequency distribution functions
- Improving Reservoir Out flow Estimation for Ungauged Basins Using Satellite Observations and a Hydrological Model Water Resources Research
- Influence of Reservoir Operation in the Upper Reaches of the Yangtze River (China) on the Inflow and Outflow Regime of the TGR-based on the Improved SWAT Model
- Water resources management in a reservoir-regulated basin : Implications of reservoir network layout on stream fl ow and hydrologic alteration
- Recent progresses in incorporating human land-water management into global land surface models toward their integration into Earth system models
- Estimating Small Reservoir Evaporation Using Machine Learning Models for the Brazilian Savannah
- The role of satellite-based remote sensing in improving simulated streamflow: A review

## High-resolution mapping of the world's reservoirs and dams for sustainable river-flow management (2011)

GRanD 数据库的文章。GRanD数据库以及成为了水库调度运行、水库数据分析等一系列研究的基础数据库。里面的DOR等概念的分析也很经典。

## Global monitoring of large reservoir storage from satellite remote sensing (2012)

这也是一篇经典的水库库容遥感观测的文章。这篇文章观测34个大水库，有来自USDA/CNES/ESA 美国和欧洲的一些大水窟的表面高程数据，从MODIS卫星数据可以得到面积数据，进而推求出高程面积关系，然后推求库容变化数据。

## Understanding satellite-based monthly-to-seasonal reservoir outflow estimation as a function of hydrologic controls (2015)

Bonnema, Matthew 有一系列从遥感数据推断水库运行的文章。这篇文章主要介绍了如何根据 EnviSat 测高数据、TRMM降雨数据、以及水库蒸发数据和水量平衡公式等在月和年尺度推断水库的出流。

水库入流使用VIC和curve number来估算。蒸发数据基于能量平衡（原文附录B）估算。水库库容面积关系曲线由高程数据、LandSat的面积数据和DEM共同推算。结合水量平衡公式就可以推算出流和实际数据对比。

结果发现不论是年尺度还是月尺度，大部分的NSE还都是负数，还很差，很难获取到水库的运行规律来推算出流。

## DAHITI - An innovative approach for estimating water level time series over inland waters using multi-mission satellite altimetry（2015）

DAHITI 是一个水库湖泊水位时间序列数据集。源数据来自 Envisat、ERS-2、Jason-1 和2、TOPEX/Poseidon以及SARAL/AltiKa。还有 Geosat、ERS-1、HY-2A、ICESat以及Cyrosat-2可以使用，但是由于准确度低，无或者长repeat cycle等原因这里没有用这些数据。

根据轨道特点，Envisat、ERS-2、Jason-1 和2、TOPEX/Poseidon以及SARAL/AltiKa可以分成两拨，第一波是TOPEX/Poseidon 以及Jason-1 和2，repeat cycle大约10天，赤道上的track separation约300km。第二组是 ERS-2、Envisat、SARAL/AltiKa，他们repeat cycle是35天，赤道上的track separation约80km

包含250个河流湖泊水库湿地的水位时间序列数据。

原文table1可以查看各项源数据的特点。

## Satellite remote sensing of large lakes and reservoirs: from elevation and area to storage（2015）

一篇综述，介绍了水库 elevation，area，storage 的计算的各类方法，并展望了未来。



## Inferring reservoir operating patterns across the Mekong Basin using only space observations （2016）

这篇文章主要根据遥感数据，通过计算两个重要参数：residence time 和flow alteration分析了湄公河流域水库对径流的影响。

所以关键就是这两个指标怎么根据遥感数据计算出来。

residence time 就是一个月进入水库的水离开水库所花的时间，flow alteration 就是 入流出流的差。

这些值的计算需要的值有：水库入流（forcing+VIC model来算）/水库库容（根据DEM构建水位库容关系曲线，然后有测高的就用测高数据比如Jason2，没有的可以使用 LandSat，使用NDWI就可以从遥感图像中提取出水体）。没有考虑蒸发。

从结果看，卫星观测的库容的RMSE还是很大的，在Sirindhorn水库还仍然在15%-20%的总库容。

关于两个指标的启示可进一步参考原文。

## A novel algorithm for monitoring reservoirs under all-weather conditions at a high temporal resolution through passive microwave remote sensing (2016)

通过被动微波遥感数据分析，结合其他遥感卫星，能获取所有气象条件下的4天一个步长的水库库容数据。

被动微波遥感数据没有被用的原因在于其分辨率相对较低，所以这篇文章使用weighted horizontal ratio（WHR）来估计水库水面面积。WHR和total surface water area相关，可以调整权重系数。这个系数是通过一些有数据的地区根据机器学习的方法率定的（训练数据来自MODIS和ICESat卫星），然后用到目标水库上。最后根据设置的水位库容关系并结合卡尔曼滤波算法等得到最终结果。

图4结果显示，R2 可以达到0.41-0.74，还是相当不错了。

## High-resolution mapping of global surface water and its long-term changes (2016)

这是nature一篇分析全球水面长期变化数据的文章。使用了300万张landsat图片，在30m分辨率上分析了 1984－2015 32年的地表水变化。月尺度和年尺度的数据。数据集可能后续用得上。

## A remote sensing method for estimating regional reservoir area and evaporative loss (2018)

这篇文章结合 GEE/区域的观测/遥感数据LandSat5和8 来分析月尺度的多水库蒸发数据。

主要的难点在于如何分析水库的水面面积。

Landsat的景有可能一个景就包含了水库，也可能两个景才包括一个水库，所以这块用了一个算法来处理两景的情况 Fmask算法，这部分后面用到再补充，总之，最终能挑出来要去分析的景，把一些云层遮盖的也都剔除。

对这些景，计算各个像素的 MNDWI 值，但是哪个threshold作为水的条件，在空间上是heterogeneous的，对有本地观测的，就将卫星观测和本地观测比较，来率定这个threshold值，然后用率定的各个水库的threshold均值作为其他无观测的地方的threshold值。

这两步都是在 Google Earth Engine上完成的。完成后就可以计算蒸发损失了。蒸发损失是直接根据水库的观测的蒸发率和蒸发面积相乘，再减去降雨率得到的。如果一个月里有多个对面积的估算，就取均值。

结果上，就 reservoir area来说，图4比较展示了几到上百平方公里不同大小水库的卫星估计面积和高程估计面积（地面观测水位+水位面积曲线），发现两者高度吻合。

关于蒸发损失，200个水库的蒸发损失年度水平能达到水库总库容的20%，还是相当大的。

## A New Global Storage-Area-Depth Data Set for Modeling Reservoirs in Land Surface and Earth System Models (2018)

这篇文章推算了GRanD数据库里面的水库的水位库容关系。

提供了5种备选的水库形状，然后根据迭代尝试对每个水库选择最合适的，进而拟合出关系曲线。50%的水库的库容估计误差都能控制在5%以下。

## A Nationwide Analysis of U.S. Army Corps of Engineers Reservoir Performance in Meeting Operational Targets (2018)

这篇文章主要是提到了CONUS上水库的库容、水位变化的时间序列数据。

## Measuring River Wetted Width from Remotely Sensed Imagery at the Sub-pixel Scale with a Deep Convolutional Neural Network （2018）

这篇文章主要是用CNN做了降尺度的分析。其他的暂略描述。

## Satellite Remote Sensing for Water Resources Management （2018）

这篇文章Satellite Remote Sensing for Water Resources Management: Potential for Supporting Sustainable Development in Data-Poor Regions介绍了很多现在正在WRM中用的，可以用的以及将来可能会用到的遥感数据，并阐述了益处和面临的问题。

首先，是**Data needs for WRM**。

主要参考原文table1。个人觉得比较不错，因此copy一遍。

|水资源管理决策|用于决策的水相关数据|传统数据源|
|-|-|-|
|**规划设计**|-|-|
|防洪|降雨径流长期记录，cold regions长期SWE|雨量站、径流站网，snow courses and pillows|
|水电系统|径流长期记录，cold regions长期SWE|同上|
|灌溉系统|降雨、径流和地下水长期记录，crop用水估计|雨量站、径流站网，wells、piezometers，气象网|
|污水处理系统|径流、地下水等的feed sources的记录|径流站网，wells、piezometers|
|供水系统|降雨径流和地下水记录|雨量站、径流站网；wells、piezometers|
|跨境水|长期径流和地下水记录，用水记录|径流站网，wells、piezometers|
|**管理运行**|-|-|
|水资源管理（满足需水）|实时降水、蒸发、径流和地下水|雨量站网，eddy-covariance towers, 径流站网， wells、piezometers|
|供水调度（保证可靠性）|实时降水、蒸发和地下水|同上|
|水电调度|实时降水、蒸发、径流、降水预报|雨量站，径流站，气象站，天气预报|
|防洪调度|实时降水、径流和SWE、降水预报|雨量站，径流站，snow courses and pillows，天气预报|
|污水管理|实时径流和地下水数据|径流站，wells、piezometers|
|灌溉系统调度|实时降水、径流、地下水和土壤含水量，蒸发估计|雨量站、径流站网，wells、piezometers，土壤含水量probes，eddy-covariance towers，气象站|
|生态系统管理|近期降水、径流、水位、土壤含水量和水质数据|雨量站、径流站、水位站、水质采样|
|**灾害管理**|-|-|
|crop监测和粮食安全|实时vegetation特征、crop需水、土壤含水量、降水预报|田间crop采样，eddy-covariance towers，气象站，土壤含水量probes，天气预报|
|干旱早期预警和管理|实时降水、土壤含水量、径流、地下水、降水预报|雨量站，土壤含水量probes，径流站，wells、piezometers，天气预报|
|洪水早期预警和管理|实时降水，径流和降水预报|雨量站、径流站、天气预报|
|水健康|实时降水、地表水和水质参数|雨量站、径流站、水位站、水质采样|

table2总结了**WRM需要的变量以及数据源**，也copy一遍。

|变量|数据源|空间覆盖|时间覆盖|Utility for WRM|
|-|-|-|-|-|
|**降水**|测站网|国家测站网|年到几十年；实时受限|必要，但是实时和空间覆盖上可用性受限|
||遥感|极地外全球|10-15年亚日尺度数据，近实时|在站点稀疏地区必要，但受限于较大不确定性和短时间范围|
||模型|区域到全球|可变，近实时|全球和几十年的范围但较大不确定性|
|**ET,PET**|测站网（pan PET）|国家测网|年到几十年|对评价crop需水有必要|
||Flux towers（ET）|有限测点|1-10年|数量有限，空间代表性有限，主要用于验证|
||遥感（ET,PET）|区域到全球|几十年，近实时|全球和几十年的范围但较大不确定性|
||模型（ET,PET）|区域到全球|几十年，近实时|全球和几十年的范围但较大不确定性，需要前提知识|
|**径流**|测站网|国家测站网|几十年，近实时|必要，但很多地区不可用|
||遥感|仅大河|年到几十年，实时性有限|较大不确定性，范围有限，但可用处还是必要的|
||模型|区域到全球|几十年，近实时|在无观测地区只能用它，有很大不确定性，代表性差|
|**水位**|测站网|特定水体|年到十年，实时性有限|必要但是许多地区没有|
||遥感|受限于大河和水体|年到十年，实时|范围有限，但对特定水体有用|
||模型||几十年，近实时|较大不确定性但在许多地方是唯一数据源|
|**土壤含水量**|测站网|有限空间覆盖|年，实时性有限|对局部应用有用，用作验证很有必要|
||遥感|全球|年到几十年，近实时|有限深度，但是如果和模型结合很有用|
||模型|全球|几十年，近实时|较大不确定性，但是对干旱应用有用|
|**雪和冰**|测站网|区域的|年到几十年，一些站点近实时|测站较密是有必要||
||遥感|全球|年到几十年，近实时|必要，但是SWE有较大不确定性，对snow covered地区更准确|
||模型|全球|几十年，近实时|较大不确定性，但是可以和in-situ及遥感互补|
|**地下水**|well测网|区域性||必要，但覆盖有限，可用于验证|
||遥感|来源于全球重力测量，但空间分辨率低|年，低分辨率|测量的是TWSA，地下水需要进一步建模，粗分辨率使得不能直接使用，但是结合模型可用于研究|
||模型|区域到全球|年到几十年，有时近实时|较大不确定性，但是对与区域应用有用|
|**水质**|采样点|有限的空间覆盖|年，实时上受限|必要但是覆盖率差|
||遥感|全球|年，近实时|仅仅表面水变量，有的变量不确定性大|
||模型|取决于变量|年到几十年，近实时|有的变量不确定性较大|

接着，记录下具体的目前可用的遥感技术和产品。都在table3，这里也copy下，最后引用就不copy了，看原文。

|名称|发射和服役时间|空间分辨率|时间分辨率|
|-|-|-|-|
|**Precipitation**||||
|TMPA|2000-2018|0.25° 60°S to 60°N|3h|
|PERSIANN|2000-|0.25° 60°S to 60°N|1h
|CMORPH|2002-|0.07° 60°S to 60°N|30min|
|GSMAP|2005-|0.1°  global|1h|
|GPM/IMERG|2015-|0.1° 60°S to 60°N|30min|
|CHIRPS|1979-|0.05°|daily|
|MSWEP|1979-|0.1°|3h|
|**Land Surface Temperature(for ET)**|-|-|-|
|Landsat|2013(Landsat-8),2022(Landsat-9)|30(multisoectral)-100m(thermal)|16d|
|AVHRR|NOAA_19 2009发射，MetOp-B 2012发射|1km|1d|
|ASTER|2000|90m|16d|
|MODIS|2000|1km/6km|1d,8d|
|VIIRS|2011|375-750m|1d|
|Sentinel-3|2015/2017|1km|<2d|
|ECOSTRESS|2018,1y expected|38×69m|平均4天，focus区域亚日尺度|
|**ET Products**||||
|RS-PM|1983-2010|0.5°|daily|
|MOD16 ET|2000-2014|1km|8d|
|PT-JPL|1984-2006|1-0°|Monthly|
|GLEAM|1980-2016,2003-2015,2011-2015|0.25°|Daily|
|SSEBop|2003-|1km|10d|
|ALEXI-DisALEXI|Various regional data sets|30m(Landsat),1km(MODIS)|Hourly/daily|
|Global ESI|2001-|0.05°|4- and 12-week composites updated weekly|
|**Soil moisture**||||
|AMSR-E|2002-2011|25km|1d revisit|
|AMSR2|2012|25km|1d revisit|
|SMOS|2010|15,25,50km|1- to 3-day revisit; daily, 9-d and monthly|
|SMAP , SMAP L4 root zone soil moisture|36km,9km|1-3d revisit, 3h|
|Sentinel-1|2014/2016|<1km$^2$|8d|
|**Surface water height and extent**||||
|Jason-2/3(surface water height)|2008/2016|Lakes>100km$^2$|10d|
|Sentinel-3(surface water height)|2016|350m along track|27d|
|Landsat(surface water height)|2013(Landsat-8),2022(Landsat-9)|30(multisoectral)-100m(thermal)|16d|
|MODIS(surface water height)|2000-|500m|Daily|
|Sentinel-2(surface water height)|2015/2017|10-60m|5/10d|
|**Snow**||||
|MODIS SCE|2000-|500m, 0.05°|daily and 8d composite|
|VIIRS SCE|2012-|375m(swath),500m|daily and 8d composite|
|AMSR-E SWE|2000-2011|25km|daily, 5d, monthly|
|**Groundwater**||||
|GRACE|2002|500000km$^2$|30d|
|GRACE FO|2017|500000km$^2$|30d|
|**Vegetation**||||
|Landsat|2013(Landsat-8),2022(Landsat-9)|15m|16d|
|AVHRR/GIMMS|1979-2015|1km|7/14d composites|
|MODIS|2000|250m, 1km, 0.05°|16d,mongthly|
|VIIRS|2012|375m(swath),500m|daily and 8d composite|
|SPOT/PROBA-V|1990-2017|1km|10d|
|Sentinel-2|2015/2017|10-60m|5/10d|

## Recognizing Global Reservoirs From Landsat 8 Images: A Deep Learning Approach （2019）

这是一篇Deep Learning 来识别一个水体是水库还是湖泊的文章。可参考：[Jack-Chen-435/Reservoirs-Lake-Recognizing](https://github.com/Jack-Chen-435/Reservoirs-Lake-Recognizing)

## Evaluation of Sentinel-3 SRAL SAR altimetry over Chinese rivers （2019）

简单说明下，Sentinel-3是第一个 radar altimetry mission operating with a synthetic aperture radar (SAR) altimeter at global scale and with a new on-board tracking system (i.e. open-loop)。有很高的潜力为未来20年提供可靠的内陆水体观测。

## Assimilation of Satellite Altimetry Data for Effective River Bathymetry （2020）

这篇文章暂时只关注下用到的数据，问题方面可能能和PINN有点关联，以后再看。在原文 3.4 节。

表1列出了常用的 altimetry missions，包括：ENVISAT/JASON2/ICESAT

JASON2时间分辨率更高一些，ENVISAT的观测范围更多一些，ICESAT是lidar的，所以很容易受天气影响，有效观测更少，但是精度更高。

## Using GRanD Database and Surface Water Data to Constrain Area – Storage Curve of Reservoirs (2020)

这篇文章利用 GRanD 数据库 和 Landsat 推求的面积数据来推求面积库容关系。

用到的数据集有 GRanD、GSW（2016那篇nature的数据集）以及 ETOPO1（DEM数据集）

方法是先直接根据DEM推出一个 水深-面积关系，然后可以推算库容面积关系，这时候得到一个未率定的关系，其误差主要来自DEM。

然后根据GRanD的面积和库容数据来线性比例地率定刚得到地曲线。

最后和观测值对比，根据图5可以看到，最小的R2也有0.778了，可以说很不错了。

## GOODD, a global dataset of more than 38,000 georeferenced dams （2020）

一个新的大坝的全球数据库。可参考：[Jack-Chen-435/Reservoirs-Lake-Recognizing](https://github.com/Jack-Chen-435/Reservoirs-Lake-Recognizing)

## The global lake area, climate, and population dataset（2020）

这是一个GLCP数据集的论文。数据集中包括 湖泊水库面积数据（来自Hydrolakes和GSW数据集）和 其相关的流域级别的温度、降水和人口数据。

## Surface water detection and delineation using remote sensing images: a review of methods and algorithms（2020）

这是一篇小综述性质的从遥感数据提取水体的文章，所以值得看看。

重点关注下表1和表2

## Extraction of connected river networks from multi-temporal remote sensing imagery using a path tracking technique （2020）

这篇文章有用到 machine learning 和 water surface data，所以虽然不是水库水体的识别也有必要了解下。

首先，Landsat 是最常用的mapping water surface的遥感数据，16天时间间隔，30m的分辨率，能很好地反映水体表面的动态变化。

Sentinel-2A和2B 是2015年和2017年发射的，能提供10m分辨率的可见光和broad NIR波段，20m 的 red edge，narrow NIR和 SWIR波段。两个卫星一起可以提供5天分辨率数据。

这篇文章用了随机森林（RF）来提取水体。传统的方法都是基于 index thresholding methods的，但是对空间异构性判断不够好，所以用ML的方法。原文table2给出了RF算法的自变量。训练数据由手动提取，样本来自不同地区不同时间，尽可能地包含不同的情况。

其余的暂时就不关注了。

## Monitoring lake level changes in China using multi-altimeter data (2016–2019) (2020)

暂时只关注下 原文表1中的卫星数据：

Jason-2和Jason-3（2016发射）、CryoSat-2、Sentinel-3A（February 2016发射）

Repeat cycle (day)分别是10、10、369 (subcycle30) 和27

## Performance assessment of ICESat-2 laser altimeter data for water-level measurement over lakes and reservoirs in China (2020)

看看ICESat-2数据在国内水库上有哪些。

三峡、碧流河、大伙房、丰满都有ICESat-2的数据。所以测高卫星还是可以多多关注的。

## GrabRiver: Graph-Theory-Based River Width Extraction From Remote Sensing Imagery (2020)

这篇文章是提取河流的，我重点关注下它里面如何提取水体以及如何把非河流的要素排除的，排除的正好也有我关注的。

这篇文章用的提取水体的指标是 MuWI，基于 Sentinel-2 的多波段数据，能获取10m分辨率的数据。然后用一种算法选择threshold值来指定水体。它排除非河流水体的方法是简单地将小于2km2地水体排除。所以这块对我们用处不大。

## Intelligent identification of effective reservoirs based on the random forest classification model（2020）

这篇文章提到了一个防洪方面还比较有用的概念：effective reservoir，即防洪库容较多的水库，并使用随机森林的方法识别出区域中的 effective reservoir。这个概念来自一篇更早的文章，是为了梯级防洪联合调度降维运算提出的方法。如果能在流域防洪态势感知里用到这个概念，利用遥感数据分析流域水库库容，进而判断防洪形势，还是不错的。

## 未读文献

- Remote Sensing‐Based Modeling of the Bathymetry and Water Storage for Channel‐Type Reservoirs Worldwide (2020)
- Lake and reservoir volume variations in South America from radar altimetry, ICESat laser altimetry, and GRACE time-variable gravity (2021)
- Deep learning technique for fast inference of large-scale riverine bathymetry
- Connectivity-Informed Drainage Network Generation Using Deep Convolution Generative Adversarial Networks
- Tracking Lake Surface Elevations with Proportional Hypsometric Relationships, Landsat Imagery, and Multiple DEMs
- Deriving high-resolution reservoir bathymetry from ICESat-2 prototype photon-counting lidar and landsat imagery
- Synoptic assessment of water resource variability in reservoirs by remote sensing: General approach and application to the runoff harvesting systems of south India
- Deriving three dimensional reservoir bathymetry from multi-satellite datasets
