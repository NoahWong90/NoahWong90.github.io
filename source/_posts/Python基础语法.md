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



列表

```python
students = ['小明','小红','小刚']
students[0]#下标索引取一个元素
list2 = [5,6,7,8,9]

print(list2[:])
# 打印出[5,6,7,8,9]
print(list2[2:])
# 打印出[7,8.9]
print(list2[:2])
# 打印出[5,6]
print(list2[1:3])
#打印出[6,7]
print(list2[2:4])    
#打印出[7,8]

#在列表后面加元素
list3.append(3)
print(list3)
#list3.append(4,5)
list3.append([4,5])

#删除
del students[1]

```



字典（键值对）

```python
#数组
students = ['小明','小红','小刚']
#字典
scores = {'小明':95,'小红':90,'小刚':90}
#len计算 长度
print(len(students))
print(len(scores))
#打印键值
print(scores['小明'])
#删除字典键值
del scores['小明']
#新增字典键值
scores['小明'] = 66


#数组和字典的异同
students1 = ['小明','小红','小刚']
students2 = ['小刚','小明','小红']
print(students1 == students2)
scores1 = {'小明':95,'小红':90,'小刚':100}
scores2 = {'小刚':100,'小明':95,'小红':90}
print(scores1 == scores2)
#列表有序，要用偏移量定位；字典无序，便通过唯一的键来取值。


#列表嵌套
students = [['小明','小红','小刚','小美'],['小强','小兰','小伟','小芳']]
print(students[1][1]) 

#字典嵌套
scores = {
    '第一组':{'小明':95,'小红':90,'小刚':100,'小美':85},
    '第二组':{'小强':99,'小兰':89,'小伟':93,'小芳':88}
    }
print(scores['第二组']['小芳'])

#字典列表嵌套
scores = [
    {'小明':95,'小红':90,'小刚':100,'小美':85},
    {'小强':99,'小兰':89,'小伟':93,'小芳':88}
    ]
print(scores[1]['小强'])
```



for...in...循环语句

```python
dict = {'日本':'东京','英国':'伦敦','法国':'巴黎'}
for i in dict:
    print(i)
    
range(x) #生成一个从0到x-1的整数序列
range(a,b)#[取头不取尾]的整数序列
range(0,10,3)#从0数到9（取头不取尾），数数的间隔为3
```



while循环

```python
password = ''  # 变量password用来保存输入的密码
while password != '816':
    password = input('请尝试输入密码：')
print('欢迎回家！')
```



and 和 or

```python
if a<b and c<d:
    print('True')
else:
    print('False')
    
if a<b or c<d:
	print('True')
else:
	print('False')
```



in和not in

```python
dict = {'法国':'巴黎','日本':'东京','中国':'北京'}
a = '法国'
print(bool(a in dict))
```



break 提前 结束循环

```python
for i in range(5):
    print('明日复明日')
    if i==3:  # 当i等于3的时候触发
        break # 结束循环
```

 continue # 回到循环开头  结束本次循环

pass #什么都不做



定义函数

```python
def greet(name): #定义函数
    print(name+'早上好')
    return
```



变量作用域

```python
x=99
def num():
    x=88
    print(x)
num() 
#打印局部变量x
print(x) 
#打印全局变量x
```

try…except… 异常补捉

```python
#不用修改代码，直接运行即可，尝试多输入几次非数字
while True:
    try:
        age = int(input('你今年几岁了？'))
        break
    except ValueError:
        print('你输入的不是数字！')
if age < 18:
    print('不可以喝酒噢')
```

类

