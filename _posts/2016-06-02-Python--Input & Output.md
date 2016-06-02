---
layout: post
title: Python--Input & Output
category: Python
comments: true
---

####Input & Output

#####Output
首先启动Python(注:我们使用的python3):

```
elvis@T430:/backup/github/local/python$ python3
Python 3.4.0 (default, Apr 11 2014, 13:05:18)
[GCC 4.8.2] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

使用print()在括号中加入字符串就可以向屏幕上打印字符串:

```
>>> print('hello, yahui')
hello, yahui
>>>
```

注意：这里字符串两边的的引号可以使用单引号，也可以使用双引号，但是不可以混合使用，否则会报语法错误

```
>>> print("hello, yahui")
hello, yahui
>>>
>>> print('hello, yahui")
  File "<stdin>", line 1
    print('hello, yahui")
                       ^
SyntaxError: EOL while scanning string literal
>>>
```

print()里也可以接多个字符串，各个字符串用“，”隔开:

```
>>> print('hello', 'yahui', '!', 'nice', "!")
hello yahui ! nice !
>>>
```

print()打印整数:

```
>>> print(300 + 200)
500
>>> print('300 + 200 = ', 300 + 200)
300 + 200 =  500
>>>
```

#####Input

使用input()输入一个字符串，并且保存到一个变量中:

```
>>> my_name = input()
elvis
>>> print(my_name)
elvis
>>>
```

上面的代码使用input()函数接收用户输入的字符串，然后将字符串传给变量my_name.再使用print()将my_name的值打印出来.

上面的input()执行之后，没有任何提示，当你输入my_name = input()并敲回车之后，命令行就处于等待用户输入的状态，等输入完毕之后，回到 >>> 状态.

我们可以在input中加入一些字符，提示用户输入:

```
>>> my_name = input('Input your name: ' )
Input your name: elvis
>>> print("hello,", my_name)
hello, elvis
>>>
```

也可以使用文件的方式，将python写入以.py结尾的文件中:

```
#!/usr/bin/python3
#file: python-input.py

my_name = input('Input your name: ')
print("hello," ,my_name)
```

执行结果:

```
elvis@T430:~/github/python$ ./python-input.py
Input your name: elvis
hello, elvis
elvis@T430:~/github/python$
```