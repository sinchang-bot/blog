title: 如何新建一个Cocos2d-x项目
date: 2013-10-17 16:43:30
categories:
- Cocos2d-x
tags:
- Cocos2d-x
- 游戏开发
- Game Development
- Guide
- 入门
---




作为一名程序猿的，凡事都得从Hello World开始！接下来就由我来演示一遍如何创建一个Hello World项目。

**要想创建一个Cocos2d-x项目就必须有它的模板**，如果你使用过Cocos2d-x2.1.4以前的版本就知道其官方自带有模板安装文件，所以你可以下载2.1.4以前的版本（如cocos2d-x 2.1.3），将cocos2d-x 2.1.3\template目录下的`msvc`文件夹复制到cocos2d-x 2.2.0\template下，再复制cocos2d-x 2.1.3目录下的文件`install-templates-msvc.bat`到cocos2d-x 2.2.0下，点击运行，结束后你就可以在VS2012的新建项目中发现有Cocos2d-x模板了。

但是新版的已经没有了，**官方推荐用脚本新建项目**。所以我们还是参照官方文档用最新的方法吧。一个脚本生成所有平台的项目文件，非常方便！


## **准备**
- 按照上一篇[《Windows8.1下Cocos2d-x环境搭建》](http://www.geekplux.com/2013/10/16/Windows8.1下Cocos2d-x环境搭建/)先搭建好环境
- 下载Python[官网下载](http://www.python.org/download/)
- 安装Python：
一路next就行了，安装目录默认为 `C:\Python27\`

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017155948_%E5%89%AF%E6%9C%AC.jpg)

<!-- more -->

- 配置环境变量：
这一步我相信大部分人都不陌生，新建变量名为 `PYTHON_HOME` 的系统变量，值为你Python的安装目录，如图：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017160806_%E5%89%AF%E6%9C%AC.jpg)

然后编辑Path变量，在变量值最后加 `%PYTHON_HOME%` ，如果之前没分号记得加上（＃－.－）

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161151_%E5%89%AF%E6%9C%AC.jpg)

*为了检测是否配置成功，你可以在cmd中输入python，如果出现如下显示则配置成功。*

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161225_%E5%89%AF%E6%9C%AC.jpg)



## **步骤**
- 打开命令提示符（win+R，输入cmd，回车），切换到你Cocos2d-x目录所在盘符（我的是D）， `D: `
- 输入 `cd D:\cocos2dx_2.2.0\tools\project-creator`  进入 `create_project.py` 脚本所在目录。
- 输入 `python create_project.py -project HelloWorld -package com.cocos2dx.org -language cpp` 运行脚本，生成Hello World项目，其中HelloWorld为**工程名**，com.cocos2dx.org为**android版本取的包标识名**。这两处你可以自己修改。

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161406_%E5%89%AF%E6%9C%AC.jpg)

然后你就可以在 D:\cocos2dx_2.2.0\projects 路径下找到你刚才新建的项目了，目录如下图 ：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161456_%E5%89%AF%E6%9C%AC.jpg)

- 打开目录，运行HelloWorld.sln。

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161637_%E5%89%AF%E6%9C%AC.jpg)
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AACocos2d-x%E9%A1%B9%E7%9B%AE%5CQQ%E5%9B%BE%E7%89%8720131017161912.jpg)



至此，熟悉的几个大字Hello World映入眼帘，证明运行成功！接下来就可以开始你的Cocos2d-x游戏开发之旅了！~(￣▽￣)~




--------------
本作品采用[知识共享 署名-非商业性使用-禁止演绎 4.0 国际 许可协议](http://creativecommons.org/licenses/by-nc-nd/4.0/)进行许可。
