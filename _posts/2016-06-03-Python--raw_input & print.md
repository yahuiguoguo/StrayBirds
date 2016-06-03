---
layout: post
title: Python--raw_input & print
category: Python
comments: true
---

####raw_input & print

刚开始学习python，今天练习raw_input和print的发现要想使用raw_input输入一个数字，像下面这样写是不对的:

	age = raw_input("Input your age: ")

后来上网查了资料才知道不应该这么写，下面将raw_input和print的代码贴上来:

#####raw_input

[代码来源](http://www.pythonclub.org/python-basic/raw-input)
- 输入字符串

```
#13222319810101****
nID = ''
while 1:
    nID = raw_input("Input your id: ")
    if len(nID) != len("13222319810101****"):
        print 'wring length of id,input again'
    else:
        break

print 'your id is %s' % (nID)
```

- 输入整数

```
nAge = int(raw_input("input your age: \n"))
if nAge > 0 and nAge < 120:
    print 'thanks!'
else:
    print 'bad age'
print 'your age is %d\n' % nAge
```

- 输入浮点型

```
fWeight = 0.0
fWeight = float(raw_input("input your weight\n"))
print 'your weight is %f' % fWeight
```

- 输入16进制数据

```
nHex = int(raw_input('input hex value(like 0x20):\n'),16)
print 'nHex = %x,nOct = %d\n' %(nHex,nHex)
```

- 输入8进制数据

```
nOct = int(raw_input('input oct value(like 020):\n'),8)
print 'nOct = %o,nDec = %d\n' % (nOct,nOct)
```

#####print

- 格式化输出整数

python print也支持参数格式化，与C言的printf相似:

```
strHello = "the length of (%s) is %d" %('Hello World',len('Hello World'))
print strHello
#输出果：the length of (Hello World) is 11
```

- 格式化输出16制整数

```
nHex = 0x20
#%x --- hex 十六进制
#%d --- dec 十进制
#%d --- oct 八进制

print "nHex = %x,nDec = %d,nOct = %o" %(nHex,nHex,nHex)

#输出结果：nHex = 20,nDec = 32,nOct = 40
#使用整数的各个制打印同一个数
```

如果需要输出二进制的话，可以使用python函数 bin()

```
>>> bin(789)
'0b1100010101'
>>>
```

- 格式化输出浮点数(float)

```
import math
#default
print "PI = %f" % math.pi
#width = 10,precise = 3,align = left
print "PI = %10.3f" % math.pi
#width = 10,precise = 3,align = rigth
print "PI = %-10.3f" % math.pi
#前面填充字符
print "PI = %06d" % int(math.pi)
 
#输出结果
#PI = 3.141593
#PI =      3.142
#PI = 3.142
#PI = 000003
#浮点数的格式化，精度、度和
```

- 格式化输出字符串(string)

```
#precise = 3
print "%.3s " % ("jcodeer")
#precise = 4
print "%.*s" % (4,"jcodeer")
#width = 10,precise = 3
print "%10.3s" % ("jcodeer")
#输出结果：
#jco
#jcod
#       jco
#同一字符串也存在精度、度和.
```

- 输出列表(list)

```
l = [1,2,3,4,'jcodeer']
print l
#输出结果：[1, 2, 3, 4, 'jcodeer']
#list直接打印即可

#字典(dictionary)
d = {1:'A',2:'B',3:'C',4:'D'}
print d
#输出结果：{1: 'A', 2: 'B', 3: 'C', 4: 'D'}
```

- python print自动换行

print 会自动在行末加上回车,如果不需回车，只需在print语句的结尾添加一个逗号”,“，就可以改变它的行为。

```
for i in range(0,5):
    print i,
```

或直接使用下面的函数进行输出:

```
sys.stdout.write("输出的字串")
```

- 万能的 %r



有个同事问我python里面print ”%r” 是什么用途，被问倒了。

用了这么些年的python，还没用过print %r。

网上查了一下，发现%r是一个万能的格式付，它会将后面给的参数原样打印出来，带有类型信息。

######案例

```
formatter = "%r %r %r %r"

print formatter % (1, 2, 3, 4)
print formatter % ("one", "two", "three", "four")
print formatter % (True, False, False, True)
print formatter % (formatter, formatter, formatter, formatter)
print formatter % (
"I had this thing.",
"That you could type up right.",
 "But it didn't sing.",
 "So I said goodnight."
 )
```

######结果

```
$ python ex8.py
1 2 3 4
'one' 'two' 'three' 'four'
True False False True
'%r %r %r %r' '%r %r %r %r' '%r %r %r %r' '%r %r %r %r'
'I had this thing.' 'That you could type up right.' "But it didn't sing." 'So I said goodnight.'
$
```