---
title: Hexo搭建博客
categories:
  - 网站搭建
tags:
  - Hexo
  - 网站搭建
  - SEO
abbrlink: 178c0d2c
date: 2021-04-28 08:07:01
---

​		Hexo应该是最近非常火的博客搭建程序，Hexo相比其他博客方案有几大优势：

​				1.相比挂在传统博客，不需要自己搭建的博客方案。

​				2.相比其他搭建程序，更加专业，更多主题和挂件。

​				3.只需要域名就可以，把程序放在Gitbub或Netlify，节约空间成本。

<!-- more -->

###### 一、准备工作

​		1.安装好Git。

​		2.准备域名。

​		3.注册GitHub。

​		4.安装Node.js

###### 二、安装Hexo

```git
npm install -g hexo-cli #安装hexo
npm update hexo -g #升级
hexo init blog #hexo 初始化指定文件
hexo clean #清除缓存
hexo g #生成静态文件
hexo s #本地调试服务
hexo d #部署
hexo clean #清除缓存
```

关联Hexo与GitHub，打开站点的配置文件_config.yml

```git
deploy:
	type: git
	repo: https://github.com/xxx.git
	branch: main
```

安装hexo部署插件

```git
npm install hexo-deployer-git --save
```

部署命令

```
hexo clean && hexo g && hexo d
```

###### 二、解析域名

![image.png](https://331.5kst.flxm66.com/Blog/20220427-1.png)

我这里解析的是ping 域名得到的IP地址

185.199.109.153

进入source目录下，创建一个记事本文件，去掉txt扩展名，命名为CNAME，输入你的域名

然后执行部署命令，浏览器输入域名就可以访问了。

###### 三、设置主题

这里使用的主题是icarus，以前流行的Next主题已经很久没有更新了，Icarus相对比较复杂，具体细节操作访问https://github.com/ppoffice/hexo-theme-icarus

###### 四、SEO优化

```
npm install hexo-abbrlink --save #永久链接
```

修改站点配置文件

```
permalink: posts/:abbrlink/
abbrlink:
    alg: crc32   #算法： crc16(default) and crc32
    rep: hex
```

站点地图

```
#站点地图
npm install hexo-generator-baidu-sitemap --save
npm install hexo-generator-sitemap --save
```

修改配置文件

```
url: https://xxxx.com
# sitemap
Plugins:
  - hexo-generator-baidu-sitemap
  - hexo-generator-sitemap
baidusitemap:
  path: baidusitemap.xml
sitemap:
  path: sitemap.xml
```

部署用户查看/sitemap.xml文件是否存在



打开www.google.com/webmasters/选择验证方式

验证以后提交网站地图



提交百度验证，先做好备案，不然很难录入



###### 新文章自动提交百度收录

```
npm install hexo-baidu-url-submit --save #自动提交百度收录
```

修改站点配置文件

```
baidu_url_submit:
  count: 3 ## 比如3，代表提交最新的三个链接
  host: https://flyraty.github.io ## 在百度站长平台中注册的域名
  token: xxxxx ## 请注意这是您的秘钥， 请不要发布在公众仓库里!
  path: baidu_urls.txt ## 文本文档的地址， 新链接会保存在此文本文档里
```

