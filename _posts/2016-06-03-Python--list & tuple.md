---
layout: post
title: Python--list & tuple
category: Python
comments: true
---

####list & tuple

#####list - 列表

list是python中内置的列表，用法与C语言相似，我们可以很方便的使用.

######list demo

```
#!/usr/bin/python2.7
#python list case - python-list.py

#list family have 3 num
family = ["elvis", "yahui", "baby"]

#print list family
print 'list family num is: ', family

#print list family length
print 'list family len is: ', len(family)

#print list family num
print 'list family[0]:', family[0]
print 'list family[1]:', family[1]
print 'list family[2]:', family[2]

#error
#print 'list family[3]:', family[3]

#you should remember the last num is len(family) - 1.

#also ,if you want to get last num, you can use:
#1: family[len(family) - 1],
#2: family[-1]
#both of 2 ways youcan get last family num.

print '1: get the last family num:', family[len(family) - 1]
print '2: get the last family num:', family[-1]

#according to the above mentioned
print '2: get the last family num:', family[-2]
print '2: get the last family num:', family[-3]
```

一定要搞明白list的界限在哪里，否则很容易出现访问越界的错误.

######list追加

list可以进行追加，即在原来list原有成员的基础上追加成员,使用append可以将成员追加到list末尾:

```
>>>
>>> family = ['elvis', 'yahui', 'baby']
>>> family
['elvis', 'yahui', 'baby']
>>> len(family)
3
>>>
>>> family.append('happy')
>>> family
['elvis', 'yahui', 'baby', 'happy']
>>> len(family)
4
>>>
```

######list插入

list支持插入功能，可以在原来list的基础上随意插入元素，使用命令insert:
在list中的插入一个索引号为1的元素：

```
>>>
>>> family
['elvis', 'yahui', 'baby', 'happy']
>>> family[1]
'yahui'
>>> family.insert(1, 'and')
>>> family
['elvis', 'and', 'yahui', 'baby', 'happy']
>>> len(family)
5
>>> family[1]
'and'
>>>
```

######list删除

要删除list末尾的元素，用pop()方法, 使用pop(i)删除索引为i的元素：

```
>>>
>>> family
['elvis', 'and', 'yahui', 'baby', 'happy']
>>> family.pop()
'happy'
>>> family
['elvis', 'and', 'yahui', 'baby']
>>> family.pop(1)
'and'
>>> family
['elvis', 'yahui', 'baby']
>>>
```

######list替换

要替换list中的一个元素，只要直接赋值就可以了:

```
>>>
>>> family
['elvis', 'yahui', 'baby']
>>> family[2] = 'son'
>>> family
['elvis', 'yahui', 'son']
>>>
```

list中的元素可以有不同的类型:

```
>>>
>>> man=['elvis', 28, 170, True]
>>> woman=['yahui', 27, 158, True]
>>>
>>> man
['elvis', 28, 170, True]
>>> woman
['yahui', 27, 158, True]
>>>
```

######二维数组

list中可以包含list，原理同C语言中的多维数组:

```
>>> home=['hefei', man, woman]
>>> home
['hefei', ['elvis', 28, 170, True], ['yahui', 27, 158, True]]
>>> home[0]
'hefei'
>>> home[1]
['elvis', 28, 170, True]
>>> home[2]
['yahui', 27, 158, True]
>>> home[1][0]
'elvis'
>>> home[1][2]
170
>>> home[2][0]
'yahui'
>>> home[2][2]
158
>>>
```

#####tuple - 元组

tuple和list非常相似，但是tuple和list的不同点是:
1. tuplt一但定义完毕之后就不能再修改
2. tuple定义使用()，而list使用[]
3. tuple没有append，insert，pop等操作

```
>>>
>>> man=['elvis', 28, 170, True]
>>> woman=['yahui', 27, 158, True]
>>>
>>> man
['elvis', 28, 170, True]
>>> woman
['yahui', 27, 158, True]
>>>
>>> home=('hefei', man, woman)
>>> home
('hefei', ['elvis', 28, 170, True], ['yahui', 27, 158, True])
>>> home[1][1]
28
>>> home[1][1] = 29
>>> home[1][1]
29
>>> home
('hefei', ['elvis', 29, 170, True], ['yahui', 27, 158, True])
>>> home[0]
'hefei'
>>> home[0] = 'anhui'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
>>>
```

从上面的代码中可以发现，tuple可以包含list，tuple中的list中的元素是可以修改的，但是list本身不可修改，即不能将man修改为另一个list man1.‘hefei’是tuple的，所以在试图修改的时候，python会报错.

当tuple中只有一个元素的时候，需要在元素后面加上一个逗号“,”，否则的话python会将你定义的tuple当成一个正常的变量赋值:

```
>>> demo=('work')
>>> demo
'work'
>>> demo1=('work1',)
>>> demo1
('work1',)
>>> demo[0]
'w'
>>> demo1[0]
'work1'
>>>
```

使用tuple的好处就是不能随意修改，可以增加代码的安全性，所以以后在编程过程中，如果使用list的地方可以用tuple代替，最好使用tuple.