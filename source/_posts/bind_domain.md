title: 如何绑定独立域名
date: 2013-08-10 18:18:11
categories:
- Tool
- FarBox
tags:
- Discovery
- FarBox
- Tool
- Blog
- Domain
- 工具
- 博客
- 域名
---



前天把博客搭好之后总觉得得搞个独立域名才算「高端大气上档次」。今天把绑定的经验分享一下。

------------

## **购买域名**

域名，就是你网站的网址（标识和入口），比如我的是geekplux.com。不是说没有这一串字母就不能访问你的网站，只是用IP访问的话，谁愿意记那一堆数字。相比之下，还是记字母简单。

免费的域名有很多，但是免费的顶级域名真不多。据我所知，`.tk`是很不错的。如果你决定要长期写下去，也想让别人独一无二的网址访问你的博客，那还是买一个吧。

域名提供商很多，国内有[万网](http://www.net.cn/)等，国外有[name](http://www.name.com/)、[GoDaddy](http://www.godaddy.com/)等。不过还是推荐你购买国外厂商的，因为国内要备案，提交各种材料等审核（*国外难道没有监管机制吗？呆在天朝就是安全*），我们只是为了有个博客，没必要这么兴师动众的。我用的是GoDaddy的，因为可以用支付宝支付。买的时候看个人喜好，我用的是`.com`的，也有人追求个性用`.me`、`.us`等（不信可以搜 www.fuck.me ）。不推荐`.info`的，以这个结尾的大部分是垃圾网站，容易被搜索引擎屏蔽，我想宅男都懂。


在GoDaddy选好你的域名之后，一路点continue，到支付页面选支付宝，价钱跟你域名的好坏有关了（BTW，我在支付前特地Google了一下GoDaddy有没有优惠，结果真搜到了GoDaddy的优惠码，6折买的）。。。接下来要将你的域名和IP绑定起来，这里涉及到一个叫**DNS**的东西。

<!-- more -->

## **配置DNS**

DNS可以理解成一个专门破译密码的侦探，把你的域名解析成IP地址，所以只要把你刚买的域名在DNS里设置成指向你的IP，别人就能通过域名访问你的网站了。DNS具体的工作方式太复杂，我是小白，讲不清楚。

GoDaddy默认提供了DNS服务，但是很不稳定，具体原因。。。这个。。。在天朝我还是不要说了吧。。。既然如此，得另选个DNS服务了，穷屌丝总喜欢用免费的东西，于是我打算用[DNSPod](https://www.dnspod.cn/)，虽然是免费，但是谁用谁知道。以下是设置步骤：

### **一、先在GoDaddy里设置**

1. 登录 http://www.godaddy.com
2. 登录后，选择【My Account】，然后单击【DOMAINS】后的【Launch】
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5Cgodaddy_1.jpg)

3. 在域名列表中找到要修改要修改DNS的域名，然后点击该域名后的下拉图标（如下图所示），然后点击下拉列表中的 【Set NameServers】
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5Cgodaddy_2.jpg)

4. 选择【Custom】 ，然后点击右下角的Add Nameserver
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5CQQ%E5%9B%BE%E7%89%8720130810233021.jpg)

5. 输入DNSPod的2个DNS短地址（对应6台服务器），然后点击【Add】，再点击【Save】即可。
f1g1ns1.dnspod.net
f1g1ns2.dnspod.net
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5Cgodaddy_4.jpg)

6. 点击保存，等待全球递归DNS服务器刷新（最多72小时）。
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5CQQ%E5%9B%BE%E7%89%8720130810233128.jpg)

### **二、再在DNSPod里设置**

在【我的域名】页面，点击【添加记录】，然后设置成如下图所示就行了。
![](http://7b1evr.com1.z0.glb.clouddn.com/illustration%5C%E5%A6%82%E4%BD%95%E7%BB%91%E5%AE%9A%E7%8B%AC%E7%AB%8B%E5%9F%9F%E5%90%8D%5C67668a0fjw1e4w9xigzx6j20mc07n756.jpg)

--------

如果一切顺利的话，你就可以在你浏览器的地址栏里华丽的输入你的网址来访问你的网站了。加上上一篇[写博客就用FarBox](http://www.geekplux.com/2013/08/08/写博客就用FarBox/)基本上一个博客就成形了。认真的话几个小时就全部搞定了。没基础的同学可以多去Google一下（什么时候用Google什么时候用百度自己脑补吧）。送大家一句话，多Google，不费电(￣︶￣)。




--------------
本作品采用[知识共享 署名-非商业性使用-禁止演绎 4.0 国际 许可协议](http://creativecommons.org/licenses/by-nc-nd/4.0/)进行许可。
