title: Windows8.1下Cocos2d-x环境搭建
date: 2013-10-16 17:54:30
categories:
- Cocos2d-x
tags:
- Cocos2d-x
- 开发环境
- 游戏开发
- Guide
- 入门
- Game Development
- Development Environment
---


Cocos2d-x是一个开源的2d游戏引擎，基于Cocos2d-iPhone设计，MIT许可证下发布。其最明显的特点是**跨平台**，只需要编写一次代码，就可以无缝地部署在包括iOS、Android、Windows、OSX在内的许多主流游戏平台上。在移动终端多样化的今天，跨平台是大势所趋。接下来开始正题：如何搭建Cocos2d-x开发环境。


## **准备**

- 正确安装Visual Studio 2012（2010也可以，以下简称VS）
- 官网[下载Cocos2d-x](http://www.cocos2d-x.org/download)（本文使用的是C++2.2版本）

## **步骤**

- 解压Cocos2d-x压缩包：将下好的引擎解压到你认为合适的地方，比如说D盘或者E盘。
- 打开解压后的Cocos2d-x引擎的目录，可看到如下文件：



![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016170507.jpg)

如果你装的是VS2010，则打开cocos2d-win32.vc2010.sln；如果你装的是VS2012，则打开cocos2d-win32.vc2012.sln，如上图红色框表示的。此时会自动打开VS2012（或VS2010），稍等片刻后你会看到Cocos2d-x自带的例子都已经自动加载到VS的工程目录下了。如下图：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016215353_%E5%89%AF%E6%9C%AC.jpg)


<!-- more -->


- 加载完毕后，在Solution 'cocos2d-win32.vc2012' （解决方案） 处右击鼠标，选择“Build solution”(生成解决方案)，如下图：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016213126.jpg)

第一次编译会需要较长时间，请耐心等待。
- 等全部编译完后，环境基本算是搭好了，可以运行Cocos2d-x自带的例子看一下：右击TestCpp --> 设为启动项目  --> Ctrl+F5（还有另一种方式）

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016172327_%E5%89%AF%E6%9C%AC.jpg)

如果之前的步骤都没有错，那么这时Cocos2d-x自带的Demo就会跑起来，你会看到如下所示画面：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016172443.jpg)

当然你还可以这样运行，这次换HelloCpp：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016172502_%E5%89%AF%E6%9C%AC.jpg)

如果前面的步骤都没有错，会出现如下画面：

![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5CWindows8.1%E4%B8%8BCocos2d-x%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%5CQQ%E5%9B%BE%E7%89%8720131016214249.jpg)

至此，开发环境就算搭建成功了，下篇来介绍如何创建一个新项目，就是广为人知的Hello World！[如何新建一个Cocos2d-x项目](http://www.geekplux.com/2013/10/17/如何新建一个Cocos2d-x项目/)



--------------
本作品采用[知识共享 署名-非商业性使用-禁止演绎 4.0 国际 许可协议](http://creativecommons.org/licenses/by-nc-nd/4.0/)进行许可。
