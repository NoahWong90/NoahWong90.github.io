---
title: Git报错enSSL SSL_read Connection was reset解决方法
categories:
  - git
tags:
  - 脚本
  - git
  - git命令
abbrlink: 78c2ab79
date: 2021-04-26 17:10:20
---

从GitHub开始使用SSL验证以后，如果SSL证书没有第三方验证就会经常报错：

```
fatal: unable to access ‘https://github.com/xxxx‘: OpenSSL SSL_read: Connection was reset
```

解决方式就是关闭SSL验证：

```git
git config --global http.sslVerify "false"
```

关闭SSL以后再使用就会没问题

