---
title: Python基础语法
categories:
  - Python
tags:
  - Python
  - 编程
abbrlink: b8a3dfda
date: 2021-05-01 08:53:00
---

记录Python的基础语法知识。



输出输入

```python
import time #引入

name='Noah Wong \n' #string 变量,\转义符
print(name) #输出
time.sleep(2) #定时
age = input('输出我的年龄：') #输入
```



数据类型

```python
#数据类型
s='string' #string型
f=1.1 # 浮点型
a = 10 # int类型
print(0.55+0.3) #浮点型
type(a) #查询类型

#数据类型转换
str(number) #转换成string
int(3.8)#转换成int类型
float('1.5')#转换成float类型

```

<!-- more -->

条件判断

```python
snumber=1
if snumber>=6:
    print('大于等于6')
elif 3<stonenumber<=5:
    print('4到5')
    #嵌套控制
    if stonenumber==4:
    	print("是4")
    else:
    	print("是5")
else:
    print('其他')
```



列表、字段
