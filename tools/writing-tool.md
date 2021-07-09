# 推荐给贡献者的写作工具

本文推荐两种编辑工具以编辑适用于本repo的文本，并介绍相关环境搭建及git/github的使用。

主要内容如下：

1. 搭建基础的系统环境: windows环境；
2. 灵活使用常用工具：git, github, markdown；
3. 安装必要的编辑工具：vscode/jupyterlab
4. 联合使用以上工具

## 搭建基础的系统环境

我们大部分人日常还是使用windows来办公，除非电脑某些老软件要求特别的系统，否则个人建议还是用win10，更便于办公。

安装最新的win10系统，建议不要直接使用破解软件破解系统，也不要用什么ghost软件安装系统，直接去win10官网下载系统安装即可，买不起正版，某宝可以搜一搜。

## 灵活使用常用工具

这里主要介绍git、github和markdown的基本使用方法。

### Git和github

Git 和 github 是 团队协作科研开发的有力工具。

Git 是版本控制的工具，简单地说，通过它能完成对不同开发者不同时间写的代码文件（即不同版本）的高效控制与管理，类似于我们日常管理不同时间更新的word不同版本文件，只不过我们一般都是复制粘贴一个新文件，然后命名后面加上日期，以此区分，而git可以自动地帮助记录下不同版本，并随意获取查看不同版本的文件内容。

Ubuntu或者win10下的Ubuntu里已经安装了git，所以我们就不必再装了。

Github 是代码共享的网站，每个人可以将自己本地电脑由git控制的代码库（repository，以下简称repo）上传到github上与他人分享，并协作开发。也就是说，github就类似于一个云端的代码库，本地的代码和它上面的代码可以保持同步的关系。使用github前，每个人需要注册一个自己的账号：直接百度搜索github，进入github官网，找到“sign up”标识，进行注册即可，注册后登陆就能进入自己的帐户。github服务器不在国内，所以防火墙对它稍微有一些影响，直接访问常看不到图片，有时候下载repo也不是特别方便，所以还是推荐科学上网，可以参考[这里](https://github.com/OuyangWenyu/elks/blob/master/common-sense/else/vpn.md)选择一些工具。

那么git和github之间是个什么关系呢？

我们写代码或者文档更多地肯定还是在自己本地的电脑上操作，所以我们本地的repo版本需要本地的git软件来管理；github是一个云端代码库，我们可以利用本地的git工具将我们的本地repo上传到github上，这样别人就可以看到我们的repo（各个版本都能看到）；当然我们也能在github上下载别人的代码来使用，还可以修改别人的代码来实现协作。

那么这些功能如何具体操作呢？下面根据实际使用的情况慢慢简介一些git和github的具体使用方法。

1. 关于github的使用，我还是推荐去这里看看：https://www.zhihu.com/question/20070065/answer/79557687 ，一个简单的使用是进入到自己想要下载的repo页面后，点击绿色的“Code”，然后把地址copy下来，接着使用 “git clone <刚刚copy的地址>”命令，就能把代码下载到本地了；
2. 本地git常用的命令就是add/commit/push 三连了，相关具体操作可以参考：https://www.runoob.com/git/git-basic-operations.html  

在**git&github.md**中记录了自己从小白到入门GitHub的历程，如果想要一起学习，可点击[这里](https://github.com/waterDLut/WaterResources/blob/master/tools/git%26github.md)。
### markdown

markdown 是一个编写简单文档的语言，其通过简单的标记来实现对格式的控制，从而让内容创作者更关注于自己的写作而不用分心到格式的调整上。

本文就是markdown编写的，非常简单地格式控制即可起到不错地视觉效果。

markdown的语法非常简单，自己尝试写一个文档就基本上知道怎么回事了，具体可以参考这里：https://github.com/younghz/Markdown  

在**markdown.md**中介绍了jupyterlab下markdown的使用，可点击[这里](https://github.com/waterDLut/WaterResources/blob/master/tools/markdown)。
## 安装编辑工具

本repo下面的文件主要是markdown，个人推荐使用 vscode + markdown插件。

如果更喜欢浏览器端编辑，可以安装jupyterlab。

两种工具的具体安装使用方法如下。

待更新……

## 联合使用上述工具

待更新……
