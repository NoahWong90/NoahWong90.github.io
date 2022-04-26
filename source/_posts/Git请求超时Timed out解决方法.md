---
title: Git请求超时Timed out解决方法
categories:
  - git
tags:
  - 脚本
  - git
  - git命令
abbrlink: 78c2ab79
date: 2021-04-26 20:10:20
---

​		最近在使用git的时候多次报错：

```git
git push origin master fatal: unable to access 'https://github.com/xxx.git/':
Failed to connect to github.com port 443: Timed out
```

提示连接超时。

<!-- more -->

尝试了多种方式解决：

​		1.配置和删除git proxy的方式，不行！

​		2.使用科学上网的方式，不行！

最后，使用如下方法解决：

​		1.打开https://www.ipaddress.com（科学上网）；

​		2.分别查询github.com和github.global.ssl.fastly.net的IP，并记录下来；

​		3.快捷键Win+R,输入drivers；

​		4.找到etc文件夹下的hosts文件；

​		5.输入ip和对应的域名，如：

```git
140.82.113.4	github.com
199.232.69.194	github.global.ssl.Fastly.net
```

现在再次连接不会超时了。



估计是DNS无法正确解析到正确的IP造成的连接超时！