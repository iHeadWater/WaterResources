# 编辑工具介绍

本文介绍git/github以及jupyterlab等工具的使用，以帮助您开启学习、科研的知识贡献之路。

主要内容如下：

- [版本控制工具的基本操作：git, github](#Git和github)；
- [安装使用编辑工具：jupyterlab，markdown](#Jupyterlab和markdown)

工具介绍主要基于Windows10操作系统。安装最新的win10系统时，建议不要直接使用破解软件破解系统，也不要用什么ghost软件安装系统，直接去win10官网下载系统安装即可，买不起正版，某宝可以搜一搜。

Ubuntu等Linux系统以及Mac下操作应该是类似的。

## Git和github

Git 和 github 是 团队协作的有力工具。

Git 是版本控制的工具，简单地说，通过它能完成对不同开发者不同时间写的代码文件（即不同版本）的高效控制与管理，类似于我们日常管理不同时间更新的word不同版本文件，只不过我们一般都是复制粘贴一个新文件，然后命名后面加上日期，以此区分，而git可以自动地帮助记录下不同版本，并随意获取查看不同版本的文件内容。

Github 是代码共享的网站，每个人可以将自己本地电脑中由git控制的代码库（repository，以下简称repo）上传到github上与他人分享，并协作开发。也就是说，github就类似于一个云端的代码库，本地的代码和它上面的代码可以保持同步的关系。使用github前，每个人需要注册一个自己的账号：直接百度搜索github，进入github官网，找到“sign up”标识，进行注册即可，注册后登陆就能进入自己的帐户。由于github服务器不在国内，防火墙对它稍微有一些影响，访问不太稳定，且直接访问常看不到图片，有时候下载repo也不是特别方便，所以推荐科学上网应对，比如使用蓝灯、expressvpn等。

git和github之间是个什么关系呢？

我们写代码或者文档更多地肯定还是在自己本地的电脑上操作，所以我们本地的repo版本需要本地的git软件来管理；github是一个云端代码库，我们可以利用本地的git工具将我们的本地repo上传到github上，这样别人就可以看到我们的repo（各个版本都能看到）；当然我们也能在github上下载别人的代码来使用，还可以修改别人的代码来实现协作。

更多关于git和github的信息，尤其是它们具体的使用方法请点击[这里](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md)查看。

## Jupyterlab和markdown

Jupyter Notebook 是一种用于科学计算的电子笔记本，可以在它其中嵌入代码，数据和文本来记笔记。该笔记本能够提供交互式计算形式，在这种环境中，我们可以执行代码并立刻看到发生了什么，进而能够有效地对代码和文本进行修改，从而在主题，理论，数据和结果之间建立更紧密的联系。可以说jupyter notebook是用于科学和工程计算笔记的杀手级应用程序。

可以认为 JupyterLab 是 Jupyter notebook的新一代版本。相对于 Jupyter Notebook，它的集成性更强，更灵活并且更易扩展。它支持100种多种语言，支持多种文档相互集成。使用 JupyterLab，可以进行数据分析相关的工作，可以进行交互式编程，可以学习社区中丰富的 Notebook 资料（在 GitHub上有超过170万个公共 Jupyter Notebook -- [A gallery of interesting Jupyter Notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks)）。所以这里推荐使用JupyterLab。

Markdown是一种轻量级标记语言，它以纯文本形式(易读、易写、易更改)编写文档，并最终以HTML格式发布。Markdown也可以理解为将以MARKDOWN语法编写的语言转换成HTML内容的工具。简单地说，就是用它，能让您在不费心思调格式的条件下获得整洁美观的文本样式。

关于jupyterlab和markdown的具体使用方法，请点击[这里](https://github.com/waterDLut/WaterResources/blob/master/tools/jupyterlab&markdown.md)查看。

## 快速入手版

假如你对Git、github以及Jupyterlab、markdown这些都有所了解，并在本地安装好Anaconda、Git、terminal等工具，下面这些可帮助你快速实现整个流程的操作。

- 打开github,进入到自己想要下载的repo页面。点击绿色的`Code`,点击`SSH`,将`git@github.com:xxx`开头的地址复制下来。在本地打开terminal，进入你想放置项目的文件夹,鼠标右击选择`Git Bash here`，接着使用 `git clone  <刚刚copy的地址>`命令，就能把代码下载到本地了[clone项目](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md#3-clone%E9%A1%B9%E7%9B%AE)，注意第一次使用 SSH 时，需要配置 `SSH Key`。[配置SSH Key](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md#4%E9%85%8D%E7%BD%AEssh-key)

- 用`conda env create -f environment.yml`为项目创建环境，并用`conda activate XXX<你的环境名>`激活环境,启动jupyter lab。在jupyterlab中，您可以新建notebook、console、teminal或者text文本[jupyter lab启动及相关操作](https://github.com/waterDLut/WaterResources/blob/master/tools/jupyterlab%26markdown.md#12-jupyterlab%E5%90%AF%E5%8A%A8)。如果您发现现有文档上有一些小问题，可以快速修改掉，那么请直接在 dev 分支上编辑更新现有内容；如果有较大改变，那么请创建新的特性分支（feature_xxx）[创建分支并推送到远程分支](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md#42-%E5%88%9B%E5%BB%BA%E5%88%86%E6%94%AF%E5%B9%B6%E6%8E%A8%E9%80%81%E5%88%B0%E8%BF%9C%E7%A8%8B%E5%88%86%E6%94%AF)，然后再在此分支上编辑，这样可以避免混乱。  
    
- 用`git add .`、`git commit -m "本次提交想要说明的东西"`、`git push -u origin xxx` 将本地修改后的代码推送到远程xxx分支[提交你的修改](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md#5-%E6%8F%90%E4%BA%A4%E4%BD%A0%E7%9A%84%E4%BF%AE%E6%94%B9)。如果是一个 feature_xxx 完成，那么请将其合并到dev分支上，最后由 support 小组成员审核后合并到主干master分支上。



## 参考资料

- [如何使用 GitHub？](https://www.zhihu.com/question/20070065/answer/79557687)
- [younghz/Markdown](https://github.com/younghz/Markdown)
- [Why Jupyter is data scientists’ computational notebook of choice](https://www.nature.com/articles/d41586-018-07196-1)
- [利器|JupyterLab 数据分析必备IDE完全指南](https://zhuanlan.zhihu.com/p/67959768)
- [Reactive, reproducible, collaborative: computational notebooks evolve](https://www.nature.com/articles/d41586-021-01174-w)