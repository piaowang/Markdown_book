

一个个函数方法是不知道的就不知道，去查查好了。







# 字典元组列表





列表list1 = \['physics', 'chemistry', 1997, 2000\];

字典d = {key1 : value1, key2 : value2 }

元组tup1 = ('physics', 'chemistry', 1997, 2000);

Python的类型是在运行过程中自动决定的，而不是通过代码声明

变量对象：这就相当于创建a，给a赋值3，3是对象，而a是变量名；类型属于对象而不是变量，向对象分配内存；所以Python中是针对对面而言，不同的对象可以有同一个变量名；但是不同的类型改变随之而来的是收回内存

L =\[‘sd’,’we’\]

K =l\[:\] \# 这是对l进行一个拷贝，是创建了一个新的对象，分配了新内存空间



# class



类同时也可以起到模板的作用，我们可以在创建一个类的时候，把一些认为公共的东西写进类定义中去，在python中通过一个特殊的`__init__`方法实现：

```Python
class Student(object):
    """__init__ sample."""
    def __init__(self, name, score):
        self.name = name
        self.score = score
```

如果想让内部属性不被外部访问，可以把属性的名称前加上两个下划线`__`，在Python中，实例的变量名如果以双下划线开头，就变成了一个私有变量(`private`)，只有内部可以访问，外部不能访问：

需要注意的是，Python中如果变量名以双下划线开头和结尾的，是特殊变量`__XXX__`。特殊变量是可以直接从类内部访问的。

类的的方法如果和父类的方法重名，子类会覆盖掉父类。因为这个特性，就获得了一个继承的好处”多态”

当我们定义一个class的时候，实际上也就是定义了一种数据类型。跟`list str dict`一个意思。使用`isinstance(待判断值, 数据类型)`可以做数据类型判定。

为了达到限制的目的，Python允许在定义class的时候，**定义一个特殊的slots变量，来限制该class实例能添加的属性：**

```python
class Student(object):
    __slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称

"""实际执行效果"""
>>> class Student(object):
...     __slots__ = ('name', 'age')
...
>>> s = Student()
>>> s.name = 'digg'
>>> s.age = '19'
>>> s.score = 99 #’score’没有被放到__slots__中，所以不能绑定score属性
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'score'
>>>
```






# 基础函数

*执行*一个函数会引入一个用于函数的局部变量的新符号表。更确切地说，函数中的所有的赋值都是将值存储在局部符号表；而变量引用首先查找局部符号表，然后是上层函数的局部符号表，然后是全局符号表，最后是内置名字表。然而，在函数内部无法给一个全局变量直接赋值（除非在一个[`global`](http://python.usyiyi.cn/documents/python_278/reference/simple_stmts.html#global)语句中命名），虽然可以引用它们。

函数调用的实际参数在函数被调用时引入被调函数的局部符号表；因此，参数的传递使用*传值调用*（这里的*值*始终是对象的*引用*，不是对象的值）。[[1\]](http://python.usyiyi.cn/documents/python_278/tutorial/controlflow.html#id2)一个函数调用另一个函数时，会为该调用创建一个新的局部符号表。

如果你使用过其他语言，你可能会反对说：`fib`不是一个函数，而是一个过程(子程序)，因为它并不返回任何值。事实上，没有[`return`](http://python.usyiyi.cn/documents/python_278/reference/simple_stmts.html#return)语句的函数也返回一个值，尽管是一个很无聊的值。此值被称为`None`（它是一个内置的名称）。如果 `None`只是唯一的输出，解释器通常不会打印出来。如果你真的想看到这个值，可以使用[`print`](http://python.usyiyi.cn/documents/python_278/reference/simple_stmts.html#print) 语句：



## str.rjust`(*width*[, *fillchar*])



返回字符串的长度*宽度*中右对齐的字符串。做了填充使用指定的*fillchar* （默认为一个空格）。返回原始字符串*宽度*是否小于或等于`len(s)`。

它通过在左侧填充空格使字符串在给定宽度的列右对齐。



  ```

  

# 内置函数、方法

## isinstance

使用内建的 isinstance 函数可以判断一个变量是不是字符串

## lower

把字符串的大写全部换为小写



## list中append()与extend()用法



 

列表是以类的形式实现的。“创建”列表实际上是将一个类实例化。因此，列表有多种方法可以操作。

1\. 列表可包含任何数据类型的元素，单个列表中的元素无须全为同一类型。

1. append() 方法向列表的尾部添加一个新的元素。只接受一个参数。

3\.  extend()方法只接受一个列表作为参数，并将该参数的每个元素都添加到原有的列表中

## reduce（）



内建函数是一个二元操作函数，他用来将一个数据集合（链表，元组等）中的所有数据进行下列操作：用传给reduce中的函数 func()（必须是一个二元操作函数）先对集合中的第1，2个数据进行操作，得到的结果再与第三个数据用func()函数运算，最后得到一个结果。
如：



1. 
   def myadd(x,y):   
   	return x+y   

   sum=reduce(myadd,(1,2,3,4,5,6,7))   
   	print sum  
  ```







```Python
#结果就是输出1+2+3+4+5+6+7的结果即28\

#当然，也可以用lambda的方法，更为简单：


sum=reduce(lambda x,y:x+y,(1,2,3,4,5,6,7))   
print sum  
stdout.write()
```

## abs

以Python内置的求绝对值的函数 abs() 为例，调用该函数用以下代码：

```
>>> abs(-10)
10
```

函数本身也可以赋值给变量，即：变量可以指向函数。

## strip

Python strip() 方法用于移除字符串指定的字符（默认为空格）。

## sorted 重整排序——小到大

Python内置的 sorted() 函数就可以对**list进行**排序

```python
>>> k = [36,25,14,89]
>>> sorted(k)
[14, 25, 36, 89]
```

## upper()将字符串小写换为大写 

Python upper() 方法将**字符串**中的小写字母转为大写字母。

```python
>>> k='amdif'
>>> k.upper()
'AMDIF'
```





# 基础知识

## 4.2.布尔运算 — [`and`](http://python.usyiyi.cn/documents/python_352/reference/expressions.html#and), [`or`](http://python.usyiyi.cn/documents/python_352/reference/expressions.html#or), [`not`](http://python.usyiyi.cn/documents/python_352/reference/expressions.html#not)

下面是 Boolean 操作, 按照优先级升序排列

| 操作        | 结果                                       | 备注   |
| --------- | ---------------------------------------- | ---- |
| `x or y`  | 若 *x* 为 False, 则结果为 *y*, 否则结果为 *x*       | （1）  |
| `x and y` | 若*x* 为 false, 则结果为 *x*, 否则结果为 *y*        | （2）  |
| `not x`   | 若 *x* 为 false, 则结果为`True`, 否则结果为 `False` | （3）  |

备注:

1. 这是短路运算符，所以如果第一个参数是 [`False`](http://python.usyiyi.cn/documents/python_352/library/constants.html#False)，它就只计算第二个参数。
2. 这是短路运算符，所以如果第一个参数是 [`True`](http://python.usyiyi.cn/documents/python_352/library/constants.html#True)，它就只计算第二个参数。
3. `not` 是一个低优先级的布尔运算符，所以 `not a = = b` 解释为 `not (a = = b)`，以及`a = = not b` 是一个语法错误。

循环语句中的else，在不出现break的时候会继续执行。

```
>>> for i in [2,6]:
...   if i%2 ==0:
...     print i
... else: print 'hello world'
...
2
6
hello world
```





```
if __name__ == '__main__'

Every Python module has it's __name__ defined and if this is '__main__', it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.

这句的工作原理就是当它是被import 时，他的__ name __ 属性是文件名；但是当他等于__main__的时候就以为这需要直接执行。
```



如果你前面带有\的字符被当作特殊字符，你可以使用*原始字符串*，方法是在第一个引号前面加上一个`r`:

\>>>

```
>>> print 'C:\some\name'  # here \n means newline!
C:\some
ame
>>> print r'C:\some\name'  # note the r before the quote
C:\some\name
```

```
>>> s= 'python'
>>> s[2:]
'thon'
>>> s[:2] #切片的特点
'py'
>>>
```





## tuple



如果用t= (1) ，那么定义的不是tuple，是 1 这个数！这是因为括号 () 既可以表示tuple，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python规定，这种情况下，按小括
号进行计算，计算结果自然是 1 。

所以，只有1个元素的tuple定义时必须加一个逗号 , ，来消除歧义：

```
t = （1，）
```

## 输入



从 raw_input() 读取的内容永远以字符串的形式返回，把字符串和整数比较就不会得到期待的结果，必须先用 int() 把字符串转换为我们想要的整型



```
str.format()方法的基本用法如下所示：
>>> print 'We are the {} who say "{}!"'.format('knights', 'Ni')
We are the knights who say "Ni!"

花括号及其中的字符（称为格式字段）将被替换为传递给str.format()方法的对象。括号中的数字指传递给str.format()方法的对象的位置。
>>> print '{0} and {1}'.format('spam', 'eggs')
spam and eggs
>>> print '{1} and {0}'.format('spam', 'eggs')
eggs and spam


如果str.format()方法使用关键字参数，那么将通过参数名引用它们的值。
>>> print 'This {food} is {adjective}.'.format(
...       food='spam', adjective='absolutely horrible')
This spam is absolutely horrible.
位置参数和关键字参数可以随意组合：

>>>
>>> print 'The story of {0}, {1}, and {other}.'.format('Bill', 'Manfred',
...                                                    other='Georg')
The story of Bill, Manfred, and Georg.

'!s'（适用str()）和'!r'（适用repr()）可以用于值被格式化之前对值进行转换。
>>>
>>> import math
>>> print 'The value of PI is approximately {}.'.format(math.pi)
The value of PI is approximately 3.14159265359.
>>> print 'The value of PI is approximately {!r}.'.format(math.pi)
The value of PI is approximately 3.141592653589793.


':'后面紧跟一个整数可以限定该字段的最小宽度。这在美化表格时很有用。
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 7678}
>>> for name, phone in table.items():
...     print '{0:10} ==> {1:10d}'.format(name, phone)
...
Jack       ==>       4098
Dcab       ==>       7678
Sjoerd     ==>       4127


如果你有一个实在是很长的格式字符串但又不想分开写，要是可以按照名字而不是位置引用变量就好了。有个简单的方法，可以传入一个字典，然后使用'[]'访问。
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 8637678}
>>> print ('Jack: {0[Jack]:d}; Sjoerd: {0[Sjoerd]:d}; '
...        'Dcab: {0[Dcab]:d}'.format(table))
Jack: 4098; Sjoerd: 4127; Dcab: 8637678

这也可以用‘**’符号将这个字典以关键字参数的方式传入。
>>>
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 8637678}
>>> print 'Jack: {Jack:d}; Sjoerd: {Sjoerd:d}; Dcab: {Dcab:d}'.format(**table)
Jack: 4098; Sjoerd: 4127; Dcab: 8637678
这种方式与内置函数vars()组合起来将更加有用，该函数返回一个包含所有局部变量的字典。


```

### 打开文件



[`open()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#open)返回一个文件对象，最常见的用法带有两个参数：`open(filename, mode)`。

\>>>

```
>>> f = open('workfile', 'w')
>>> print f
<open file 'workfile', mode 'w' at 80a0960>

```

第一个参数是一个含有文件名的字符串。第二个参数也是一个字符串，含有描述如何使用该文件的几个字符。*mode*为`'r'`时表示只是读取文件；`w `表示只是写入文件（已经存在的同名文件将被删掉）；`'a'`表示打开文件进行追加，写入到文件中的任何数据将自动添加到末尾。` 'r+'`表示打开文件进行读取和写入。*mode* 参数是可选的，默认为`'r'`。

在 Windows 平台上，模式后面追加` 'b'`表示以二进制方式打开文件，所以也有像`'rb'`、 `'wb'`和`'r+b'`这样的模式。Python 在 Windows 平台上区分文本文件和二进制文件；读取或写入文本文件中时，行尾字符会被自动地稍加改变。这种修改对 ASCII 文本文件没有问题，但会损坏`JPEG`或`EXE`这样的二进制文件中的数据。在读写这些文件时一定要记得以二进制模式打开。在 Unix 平台上，在模式后面附加一个`'b'`也不会有坏处，这样你可以用写好的文件访问代码来读写任何平台上的所有二进制文件。

## 删除



要删除一个key，用 pop(key) 方法，对应的value也会从dict中删除

## 逻辑判断

可以作为0或者1的计算

```python
>>> a = 20
>>> b = 10
>>> (a >b)*b #这a>b 作为一种逻辑判断存在，值为1或0
10
```

## 参数

* 正常的叫必选参数


* 默认参数，必须指向不变的

```
这时候的n=2就是默认函数。
>>> def power(x,n=2):
...   s =1
...   while n >0 :
...      n =n -1
...      s =s*x
...   return s
...
>>> power(8)
64
一是必选参数在前，默认参数在后，否则Python的解释器会报错（思考一下为什么默认参数不能放在必选参数前面）；
二是如何设置默认参数。当函数有多个参数时，把变化大的参数放前面，变化小的参数放后面。变化小的参数就可以作为默认参数。

使用默认参数有什么好处？最大的好处是能降低调用函数的难度。
设置默认的可以减少输入，那些都一样的就可以忽略点输入。
```





* 可变参数：在参数前家*号，表示传入的不管类型，在函数调用时自动组装为一个tuple。


传入的时候可以不考虑它的数据类型；0个或任意个参数



```
一般情况
>>> def calc(numbers):
...   sum = 0
...   for n in numbers:
...     sum = sum + n *n
...   return sum
...
>>> calc([1,2,3])
14


运用可变参数
>>> def calc(*numbers):
...   sum = 0
...   for n in numbers:
...     sum = sum + n *n
...   return sum
...
>>> calc(1,2,3)
14

定义可变参数和定义list或tuple参数相比，仅仅在参数前面加了一个 * 号。在函数
内部，参数 numbers 接收到的是一个tuple，因此，函数代码完全不变。但是，调
用该函数时，可以传入任意个参数，包括0个参数
>>> calc()
0
>>>

```



* 关键字参数：参数前加两个*号 ，传入方式是通过等号，变成一个dict类型输出

```python
扩展了函数的功能
>>> def person(name, age, **kw):
...   print 'name:', name, 'age:', age, 'other:', kw

实际使用：
>>> person('chen',128)
name: chen age: 128 other: {}
>>> person('chen',128,love = 'mick')#输入的格式要用dict格式
name: chen age: 128 other: {'love': 'mick'}

可以传入无数参数
>>>person('Adam', 45, gender='M', job='Engineer')
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}

```

关键字参数既可以直接传入： func(a=1, b=2) ，又可以先组装dict，再通过 **kw 传入： func(**{'a': 1, 'b': 2}) 。使用 *args 和 **kw 是Python的习惯写法，当然也可以用其他参数名，但最好使
用习惯用法。

* 参数组合，python定义函数可以用各种类型的参数组合





## 切片

```python
>>> [L[0], L[1], L[2]]
['Michael', 'Sarah', 'Tracy'] ##成为一个list

切片的实例，截取前面、后面，选定位置、间隔（：：（间隔比例））
>>> L[0:3]
['Michael', 'Sarah', 'Tracy']
```

## 迭代

一般用for……in：这种迭代不仅可以迭代range，基本上成行的都是可迭代的对象；

for 循环不仅可以用在list或tuple上，还可以作用在其他可迭代对象上

最后一个小问题，如果要对list实现类似Java那样的下标循环怎么办？Python内置
的 enumerate 函数可以把一个list变成索引-元素对，这样就可以在 for 循环中同
时迭代索引和元素本身：

```
for i, value in enumerate(['a', 'b', 'c']):
...     print i, value
...
0 a
1 b
2 c
```

```
#符合迭代条件的都是可以的，还包括自定义的数据类型
>>> for x, y in [(1, 1), (2, 4), (3, 9)]:
... print x, y
...
1 1
2 4
3 9

```

## 列表生成

写列表生成式时，把要生成的元素 x * x 放到前面，后面跟 for 循环，就可以把list创建出来，十分有用，多写几次，很快就可以熟悉这种语法。

```python
>>> [ x * x for x in range (1,11)]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
#还可以加上偶数判定
>>> [ x * x for x in range (1,11 ) if x % 2==0   ]
[4, 16, 36, 64, 100]
```

可以生成文件列表，字母组合

```python
#for 循环其实可以同时使用两个甚至多个变量，比如 dict 的 iteritems() 可以同时迭代key和value：

>>> d = {'x': 'A', 'y': 'B', 'z': 'C' }
>>> for k, v in d.iteritems():
... print k, '=', v
...
y = B
x = A
z = C

```



## 生成器

通过列表生成式，我们可以直接创建一个列表。但是，受到内存限制，列表容量肯定是有限的。而且，创建一个包含100万个元素的列表，不仅占用很大的存储空间，如果我们仅仅需要访问前面几个元素，那后面绝大多数元素占用的空间都白白浪费了。

所以，如果列表元素可以按照某种算法推算出来，那我们是否可以在循环的过程中不断推算出后续的元素呢？这样就不必创建完整的list，从而节省大量的空间。在Python中，这种一边循环一边计算的机制，称为生成器（Generator）。

**方法一：**要创建一个generator，有很多种方法。第一种方法很简单，**只要把一个列表生成式的 [] 改成 () ，就创建了一个generator：**

```python
>>> L = [ x*x for x in range(10)]#这是一个list
>>> L
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

>>> L = ( x*x for x in range(10))#这就是一个生成器
>>> L
<generator object <genexpr> at 0x0000000002B7C3A8>
>>> L.next()#可以通过调用next函数查询得到包含的值
0
#但是太麻烦了，可以通过for直接打印出来
>>> for n in L:
...    print n
...
1
4
9
16
25
36
49
64
81
```



**方法二：**如果一个函数定义中包含 yield 关键字，那么这个函数就不再是一个普通函数，而是一个generator：

```python
def fib(max):
	n, a, b = 0, 0, 1
	while n < max:
		yield b
		a, b = b, a + b
		n = n + 1
>>> fib(5)
<generator object fib at 0x0000000002B7C3F0>
```

最难理解的就是generator和函数的执行流程不一样。函数是顺序执行，遇到return语句或者最后一行函数语句就返回。

而变成generator的函数，在每次调用 next() 的时候执行，遇到 yield 语句返回，再次执行时从上次返回的 yield 语句处继续执行。

```python
>>> def odd():
...    print 'step 1 '
...    yield 1
...    print 'step 2 '
...    yield 2
...    print 'step 3 '
...    yield 5
...
>>> O= odd()
>>> O.next()
step 1
1
>>> O.next()
step 2
2
>>> O.next()
step 3
5
>>>
```

要理解generator的工作原理，它是在 for 循环的过程中不断计算出下一个元素，并在适当的条件结束 for 循环。对于函数改成的generator来说，遇到return语句或者执行到函数体最后一行语句，就是结束generator的指令， for 循环随之结束。

## 匿名函数



```python
关键字 lambda 表示匿名函数，冒号前面的 x 表示函数参数。匿名函数有个限制，就是只能有一个表达式，不用写 return ，返回值就是该表达式的结果
>>> map(lambda x: x * x, [1, 2, 3, 4, 5, 6, 7, 8, 9])
[1, 4, 9, 16, 25, 36, 49, 64, 81]
#其中的lambda函数等于下面的函数
def f(x):
	return x * x

#匿名函数没有名称也就不用担心命名重复，同时还可以赋值给其他变量，通过变量调用函数
>>> f = lambda x : x * x
>>> f(5)
25
```

## 装饰器

这种在**代码运行期间动态增加功能的方式，称之为“装饰器**”（Decorator）。本质上，decorator就是一个返回函数的高阶函数。所以，我们要定义一个能打印日志的decorator，可以定义如下：

```Python
#先定义一个函数
>>> def now():
...    print '2012-12-12'
...
>>> f =  now()
2012-12-12


#再定义一个函数，这是个能接受函数的函数
>>> def log(func):
...    def  wrapper(*args, **kw):
...      print 'call %s():' %func.__name__
...      return func(*args, **kw)
...    return wrapper

#当在定义函数的时候用Python的@语法加一行
>>> @log
... def now():
...    print '2012-12-12'
>>> now()  
call now():
2012-12-12
#再次调用函数的时候就会调用log（）,把 @log 放到 now() 函数的定义处，相当于执行了语句： now = log(now)
#由于 log() 是一个decorator，返回一个函数，所以，原来的 now() 函数仍然存在，只是现在同名的now变量指向了新的函数，于是调用 now() 将执行新函数，即在 log() 函数中返回的wrapper() 函数。
#wrapper() 函数的参数定义是 (*args, **kw) ，因此， wrapper() 函数可以接受任意参数的调用。在 wrapper() 函数内，首先打印日志，再紧接着调用原始函数。
```

## 偏函数



```Python
>>> import functools
>>> int2 = functools.partial(int, base=2)#把传入的参数变为，base =2 二进制的意思
>>> int2('1001')
9
#简单总结 functools.partial 的作用就是，把一个函数的某些参数给固定住（也就是设置默认值），返回一个新的函数，调用这个新函数会更简单。
```

# 模块

模块可以同名，为了避免冲突用按目录来组织模块的方法来管理，这个方法叫做包(package)

每一个包目录下面都会有一个 ___ init ___.py 的文件，这个文件是必须存在的，否则，Python就把这个目录当成普通目录，而不是一个包。 __ init __ . py 可以是空文件，也可以有Python代码，因为 __ init__.py 本身就是一个模块，而它的模块名就是 mycompany 。



```python
创建一个hello.py的模块
#-*- coding: utf-8 -*- 

'a test module' #这行代表文档注释，任何模块的第一行字符串都是这个意味

__author__ = 'chenming' #标明作者

import sys
def test():
    args = sys.argv
    if len(args) ==1:
        print('hello ,world')
    elif len(args) == 2:
        print("hello ,%s!"%args[1])
    else:
        print('too many')

if __name__ == '__main__':
    test()
    
    
  测试：导入hello
>>> import hello
>>> hello.test()
hello ,world
>>>
```



在一个模块中，我们可能会定义很多函数和变量，但有的函数和变量我们希望给别人使用，有的函数和变量我们希望仅仅在模块内部使用。在Python中，是通过 _ 前缀来实现的。

正常的函数和变量名是公开的（public），可以被直接引用，比如： abc ， x123 ， PI 等；

类似 --xxx-- **这样的变量是特殊变量，可以被直接引用，但是有特殊用途，比如上面            的 --__author__ --，-- name-- 就是特殊变量， hello 模块定义的文档注释也可以用特殊变量 --__doc__-- --访问，我们自己的变量一般不要用这种变量名；

```Python
>>> hello.__doc__
'a test module'
```

类似 _xxx 和 _xxx 这样的函数或变量就是非公开的（private），不应该被直接引用，比如 _abc ， __abc 等；之所以我们说，private函数和变量“不应该”被直接引用，而不是“不能”被直接引用，**是因为Python并没有一种方法可以完全限制访问private函数或变量**，但是，从编程习惯上不应该引用private函数或变量。



##**collections**

使用 list 存储数据时，按索引访问元素很快，但是插入和删除元素就很慢了，因为 list 是线性存储，数据量大的时候，插入和删除效率很低。

**deque**是为了高效实现插入和删除操作的双向列表，适合用于队列和栈：

```
>>> from collections import deque
>>> q = deque(['a', 'b', 'c'])
>>> q.append('x')
>>> q
deque(['a', 'b', 'c', 'x'])

>>> q.appendleft('x') #左边添加
>>> q
deque(['x', 'a', 'b', 'c', 'x'])

deque 除了实现list的 append() 和 pop() 外，还支
持 appendleft() 和 popleft() 
```



**defaultdict** 默认内容

```
>>> from collections import defaultdict
>>> dd = defaultdict(lambda : 'N\A')
>>> dd['key1']= 'abc'
>>> dd['key1']
'abc'
>>> dd['key2']
'N\\A'
>>>
```

* OrderedDict 自动排序

Key会按照插入的顺序排列

* counter

```
>>> from collections import Counter
>>> c = Counter()
>>> for ch in 'programming':
...   c[ch] = c[ch] + 1
...
>>> c
Counter({'g': 2, 'm': 2, 'r': 2, 'a': 1, 'i': 1, 'o': 1, 'n': 1, 'p': 1})
>>>
```

## base64

用记事本打开 exe 、 jpg 、 pdf 这些文件时，我们都会看到一大堆乱码，因为二进制文件包含很多无法显示和打印的字符，所以，如果要让记事本这样的文本处理软件能处理二进制数据，就需要一个二进制到字符串的转换方法。Base64是一种最常见的二进制编码方法。

## struck

准确地讲，Python没有专门处理字节的数据类型。但由于 str 既是字符串，又可以表示字节，所以，字节数组＝str。而在C语言中，我们可以很方便地用struct、union来处理字节，以及字节和int，float的转换。

## hashlib

加密

## itertools

提供几种无限迭代，itertools 模块提供的全部是处理迭代功能的函数，它们的返回值不是list，而是迭代对象，只有用 for 循环迭代的时候才真正计算。

```
无限加1，直到按出control +  c
>>> natuals = itertools.count(1)
>>> for n in natuals:
...    print n
...
1
2
3
4
5


>>> import itertools
>>> cs = itertools.cycle('ABC') # 注意字符串也是序列的一种
>>> for c in cs:
... print c
...
'A'
'B'
'C'
'A'



repeat() 负责把一个元素无限重复下去，不过如果提供第二个参数就可以限定重
复次数：
>>> ns = itertools.repeat('A', 10)
>>> for n in ns:
... print n
...
打印10次'A'


无限序列只有在 for 迭代时才会无限地迭代下去，如果只是创建了一个迭代对
象，它不会事先把无限个元素生成出来，事实上也不可能在内存中创建无限多个元
素。
无限序列虽然可以无限迭代下去，但是通常我们会通过 takewhile() 等函数根据
条件判断来截取出一个有限的序列：
>>> natuals = itertools.count(1)
>>> ns = itertools.takewhile(lambda x: x <= 10, natuals)
>>> for n in ns:
... print n
...
打印出1到10
```



**itertools提供的迭代器操作函数**

```python
chain连接两个字符串
>>> from itertools import chain
>>> for c in chain('ABC', 'CYZ'):
...   print c
...
A
B
C
C
Y
Z


groupby() 把迭代器中相邻的重复元素挑出来放在一起：
>>> from itertools import groupby
>>> for key, group in itertools.groupby('AAAAABBBBCCSDFF'):
...   print key , list(group)
...
A ['A', 'A', 'A', 'A', 'A']
B ['B', 'B', 'B', 'B']
C ['C', 'C']
S ['S']
D ['D']
F ['F', 'F']



imap就是map的惰性计算，只有在需要的时候才计算好迭代出来

当你调用 imap() 时，并没有进行任何计算：
>>> r = itertools.imap(lambda x: x*x, [1, 2, 3])
>>> r
<itertools.imap object at 0x103d3ff90>
# r只是一个迭代对象
必须用 for 循环对 r 进行迭代，才会在每次循环过程中计算出下一个元素：
>>> for x in r:
... print x
...
1
4
9

ifilter也是filter的惰性计算

```







# 面向对象编程

**OOP把对象作为程序的基本单元，一个对象包含了数据和操作数据的函数。**

面向过程的程序设计把计算机程序视为一系列的命令集合，即一组函数的顺序执行。为了简化程序设计，面向过程把函数继续切分为子函数，即把大块函数通过切割成小块函数来降低系统的复杂度。

而面向对象的程序设计把计算机程序视为一组对象的集合，而每个对象都可以接收其他对象发过来的消息，并处理这些消息，计算机程序的执行就是一系列消息在各个对象之间传递。类的概念是面向对象这的重要概念，它代表了重用，封装，和方便。

在Python中，所有数据类型都可以视为对象，当然也可以自定义对象。自定义的对象数据类型就是面向对中的类（Class）的概念。

举例：

```Python
#如果要打印学生的名字和成绩，面向过程的写法是每个人的名字和成绩都存入不同的dict，然后打印
>>> std1 = { 'name':'make','score':90}
>>> std2 = { 'name':'wht' ,'score':89}
>>> def print_score(std):
...   print '%s: %s' % (std['name'],std['score'])
...
>>> print_score(std1)
make: 90
>>> print_score(std2)
wht: 89


    
    
#面向对象首先要考虑的是学生这个对象，对象具有的属性——名字和成绩。而具体的学生就是实例
#-*- coding: utf-8 -*-

class Student(object):
    def __init__(self,name, score):
        self.name = name
        self.score =score

    def print_score(self):
        print('%s: %s'%(self.name,self.score))#给对象发送消息，这种要调用对象对应的关联函数，就是对象的方法。

bart =Student('bare',89)
lisa =Student('lisa',90)

bart.print_score()
lisa.print_score()
    
```



**面向对象的抽象程度又比函数要高，因为一个Class既包含数据，又包含操作数据的方法。**

类要实例化才能起作用，不然它就是一个抽象概念。

## 类和实例

类是抽象的模板，而实例是根据类创建出来的一个个具体的“对象”，每个对象都拥有相同的方法，但各自的数据可能不同。

> ```Python
> class Student(object):
> 	pass
> #class 后面紧接着是类名，即 Student ，类名通常是大写开头的单词，紧接着是 (object)，表示该类是从哪个类继承下来的，继承的概念我们后面再讲，通常，如果没有合适的继承类，就使用 object 类，这是所有类最终都会继承的类。
>
> >>> bart = student()
> >>> bart
> <__main__.student instance at 0x0000000002C9BBC8>#bart是student的一个实例
> >>> student
> <class __main__.student at 0x0000000002C93168>#而student就是一个class
>
>
> #可以自由地给一个实例变量绑定属性，比如，给实例 bart 绑定一个 name 属性：
> >>> bart.name = 'bart simpson' #student是没有这个属性的，是bart新绑定的
> >>> bart.name
> 'bart simpson'
>
>
> #由于类可以起到模板的作用，因此，可以在创建实例的时候，把一些我们认为必须绑定的属性强制填写进去。通过定义一个特殊的 __init__ 方法，在创建实例的时候，就把 name ， score 等属性绑上去：
> >>> class Student(object):
> ...   def __init__(self,name, score):
> ...      self.name =name
> ...      self.score =score
> #注意到 __init__ 方法的第一个参数永远是 self ，表示创建的实例本身，因此，在 __init__ 方法内部，就可以把各种属性绑定到 self ，因为 self 就指向创建的实例本身。
>
> 有了 __init__ 方法，在创建实例的时候，就不能传入空的参数了，必须传入与 __init__ 方法匹配的参数，但 self 不需要传，Python解释器自己会把实例变量传进去：
> >>> brat = student('chenming',589)
> >>> brat.name
> 'chenming'
>
> 要定义一个方法，除了第一个参数是 self 外，其他和普通函数一样。要调用一方法，只在实例变量上直接调用，除了 self 不用传递，其他参数正常传入：
> class Student(object):
> 	def __init__(self, name, score):
> 		self.name = name
> 		self.score = score
> 	def print_score(self):
> 		print '%s: %s' % (self.name, self.score)
> ```
>



## 访问限制

如果要让内部属性不被外部访问，可以把属性的名称前加上**两个下划线 __** ，在Python中，实例的变量名如爽哦同果以 __ 开头，就变成了一个私有变量（private），只有内部可以访问，外部不能访问，所以，我们把Student类改一改：

```Python
class Student(object):
	def __init__(self, name, score):
		self.__name = name
		self.__score = score
	def print_score(self):
		print '%s: %s' % (self.__name, self.__score)
        
>>> bart = student('chen',90)
>>> bart.name #这个name就变成了内部才能访问的数值了
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'student' object has no attribute 'name'

如果允许外部代码获取name就用写多一个方法
def get_name(self):
...     return self._name
>>> lisa =student('chen',90)
>>> lisa.get_name()
'chen'


```

在Python中，变量名类似 __ xxx__ 的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量，所以，不能用 __ name__ 、 __ score__ 这样的变量名。有些时候，你会看到以**一个下划线开头**的实例变量名，比如 _name ，这样的实例变量外是可以访问的，但是，按照约定俗成的规定，当你看到这样的变量时，意思就是，“虽然我可以被访问，但是，请把我视为私有变量，不要随意访问”。



## 继承和多态



```Python
#先定义一个Animal类
>>> class Animal(object):
...   def run(self):
...     print 'animal is running'

#再定义一个cat类继承Animal
>>> class cat(Animal):
...  pass

#实例化redcat
>>> redcat=cat()
>>> redcat.run()#redcat就拥有的Animal的run方法
animal is running

对于cat来说，Animal就是它的父类，对于Animal来说，cat就是它的子类。继承最大的好处是子类获得了父类的全部功能。

#第二个好处是先进行修改，比如cat要输出‘cat is running'
>>> class cat(Animal):
...    def run(self):
...      print'cat is running'
...
>>> cat = cat()
>>> cat.run()
cat is running
当子类和父类都存在相同的 run() 方法时，我们说，子类的 run() 覆盖了父类的 run() ，在代码运行的时候，总是会调用子类的 run() 。这样，我们就获得了继承的另一个好处：多态。

```

要理解什么是多态，我们首先要对数据类型再作一点说明。当我们定义一个class的时候，我们实际上就定义了一种数据类型。我们定义的数据类型和Python自带的数据类型，比如str、list、dict没什么两样：

```Python
>>> b = Animal()
>>> a = list()
>>> isinstance(a,list)
True
>>> isinstance(b, Animal)
True

接着
>>> c = cat()
>>> isinstance(c, animal)
True

所以，在继承关系中，如果一个实例的数据类型是某个子类，那它的数据类型也可以被看做是父类。但是，反过来就不行：
>>> b = Animal()
>>> isinstance(b, cat)
False# cat可以是Animal的，但Animal不可以归cat

>>> def cat(Animal):
...  animal.run()
>>> class dog(Animal):
...   def run(self):
...     print 'dog is runnint'
>>> cat(dog)
dog is runnint # dog是Animal的之类。cat函数的传入参数需要的就是Animal类。

对于一个变量，我们只需要知道它是Animal类型，无需确切地知道它的子类型，就可以放心地调用 run() 方法，而具体调用的 run() 方法是作用在Animal、Dog、Cat上，由运行时该对象的确切类型决定，这就是多态真正的威力：
#调用方只管调用，不管细节，而当我们新增一种Animal的子类时，只要确保 run() 方法编写正确，不用管原来的代码是如何调用的。

这就是著名的“开闭”原则：
对扩展开放：允许新增Animal子类；
对修改封闭：不需要修改依赖Animal类型的 run_twice() 等函数。
```



## 获取对象信息

**type()**

```python
>>> type(123)
<type 'int'>
>>> type('i')
<type 'str'>
>>> type(abs)
<type 'builtin_function_or_method'>

也可比较
>>> type(123)==type(456)
True
```



**使用isinstance()**
对于class的继承关系来说，使用type()就很不方便。我们要判断class的类型，可以使用 isinstance() 函数。

```Python
>>> isinstance(c, animal)# 继承和多态一节有详细，即是判断c是不是animal的子类
True

使用type（）判断的也可以用instance
>>> isinstance(123,int)
True
```



**使用dir()**
如果要获得一个对象的所有属性和方法，可以使用 dir() 函数，它返回一个包含字符串的list，比如，获得一个str对象的所有属性和方法：

```
>>> dir('str')
['__add__', '__class__', '__contains__', '__delattr__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getslice__', '__gt__', '__hash__', '__init__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '_formatter_field_name_split', '_formatter_parser', 'capitalize', 'center', 'count', 'decode', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'index', 'isalnum', 'isalpha', 'isdigit', 'islower', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
>>>s = 'abc'
>>> len(s)
3
>>> s.__len__()
3
```

把属性和方法列出来是不够的，配合 getattr() 、 setattr() 以及 hasattr() ，我们可以直接操作一个对象的状态：

```python
>>> class Myobject(object):
...   def __init__(self):
...     self.x = 9
...   def power(self):
...     return self.x * self.x
...
>>> obj = Myobject()
>>> obj
<__main__.Myobject object at 0x0000000002B9CBE0>

#obj有属性'x'吗
>>> hasattr(obj,'x')
True
>>> obj.x
9
>>> hasattr(obj, 'y')
False

#设置属性‘y’
>>> setattr(obj , 'y', 19)
>>> hasattr(obj, 'y')
True

#获取属性'y'
>>> getattr(obj,'y')
19
>>> obj.y
19

#通过getattr，如果属性z不再，触发AttributeError，也可以设置没有这个属性就返回404
>>> getattr(obj,'z')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Myobject' object has no attribute 'z'
>>> getattr(obj,'z',404)
404

获取对象的方法
>>> hasattr(obj, 'power')
True
>>> getattr(obj,'power')
<bound method Myobject.power of <__main__.Myobject object at 0x0000000002B9CBE0>>

#绑定fn到power方法，即是fn指向了power
>>> fn = getattr(obj,'power')
>>> fn
<bound method Myobject.power of <__main__.Myobject object at 0x0000000002B9CBE0>>
>>> fn()
81

要正确使用这几个方法，几何计算如果能得出就尽量直接
一个正确的用法的例子如下：
def readImage(fp):
	if hasattr(fp, 'read'):
		return readData(fp)
	return None
```

# 面向对象高级编程



```python
>>> class Student(object):
...   pass
...
>>> s = Student()
>>> s.name = 'chen' #给实例绑定属性
>>> print s.name
chen

#绑定一个实例的方法，但是对另外的实例就没有用了
>>> def set_age(self,age):
...  self.age = age
...
>>> from types import MethodType
>>> s.set_age = MethodType(set_age,s, Student)
>>> s.set_age(25)
>>> s.age
25

#只对一个实例有用
>>> s2 = Student()
>>> s2.set_age(2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'set_age'
    
 # 用classde 方式绑定就通用
>>> Student.set_age = MethodType(set_age, None, Student)#None是关键字，不能小写的
>>> s2.set_age(25)
>>> s2.age
25
>>> s.set_age(45)
>>> s.age
45
```

## 限制class的属性——slots



但是，如果我们想要限制class的属性怎么办？比如，只允许对Student实例添加 name 和 age 属性。为了达到限制的目的，Python允许在定义class的时候，定义一个特殊的 __ slots__ 变量，来限制该class能添加的属性：

```python
>>> class Student(object):
...   __slots__ = ('name', 'age') #表示只允许属性name和属性age出现
...
>>> s = Student()
>>> s.name = 'chen'
>>> s.age = 89
>>> s.score =90
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'score'
>>>
```

但是slots对继承子类无效，如果需要达到效果，还需在子类添加。



## @property 

把一个getter方法变成属性，只需要加上 @property 就可以了，此时， @property 本身又创建了另一个装饰器 @score.setter ，负责把一个setter方法变成属性赋值

装饰器本质上是一个 Python 函数或类，它可以让其他函数或类在不需要做任何代码修改的前提下增加额外功能，装饰器的返回值也是一个函数/类对象。它经常用于有切面需求的场景，比如：插入日志、性能测试、事务处理、缓存、权限校验等场景，装饰器是解决这类问题的绝佳设计。有了装饰器，我们就可以抽离出大量与函数功能本身无关的雷同代码到装饰器中并继续重用。概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能。

## 多重继承

通过多重继承，一个子类就可以同时获得多个父类的所有功能。

```python
>>> class Animal(object):
...  def run(self):
...    print 'It can run.'
...
>>> class Flyable(object):
...   def fly(self):
...     print 'it is a bird'
...

#chicken继承了Flyable和Animal两个类
>>> class chicken(Animal,Flyable):
...   pass
...
>>> a = chicken()

>>> a.fly()
it is a bird
>>> a.run()
It can run.
```



在设计类的继承关系时，通常，主线都是单一继承下来的，例如， Ostrich 继承自 Bird 。但是，如果需要“混入”额外的功能，通过多重继承就可以实现，比如，让 Ostrich 除了继承自 Bird 外，再同时继承 Runnable 。这种设计通常称之为Mixin。

Mixin的目的就是给一个类增加多个功能，这样，在设计类的时候，我们优先考虑通
过多重继承来组合多个Mixin的功能，而不是设计多层次的复杂的继承关系。





## class 内部特色



这是因为直接显示变量调用的不是 __ str__ () ， _ repr__ () ，两者的区别是 __ str__ () 返回用户看到的字符串，而 __ repr__ () 返回程序开发者看到的字符串，也就是说， __ repr__() 是为调试服务的。

```python
>>> class Student(object):
...   def __init__(self,name):
...     self.name = name
...   def __str__(self):#返回一个好看的字符串
...     return 'student object (name =%s)' %self.name
...
>>> a= Student() # 没有传入参数
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: __init__() takes exactly 2 arguments (1 given)
>>> a= Student('chen')

>>> print Student('chen')
student object (name =chen)
```



**iter**

如果一个类想被用于 for ... in 循环，类似list或tuple那样，就必须实现一个 __ iter __() 方法，该方法返回一个迭代对象，然后，Python的for循环就会不断调用**该迭代对象的 next() 方法**拿到循环的下一个值，直到遇到StopIteration错误时退出循环。

```
>>> class Fib(object):
...   def __init__(self):
...     self.a, self.b = 0,1
...   def __iter__(self):
...     return self
...   def next(self):
...     self.a , self.b = self.b, self.a+self.b
...     if self.a >1000:
...       raise StopIteration()
...     return self.a
...

>>> for n in Fib():#将Fib里面的数字打印出来
...   print n
...
1
1
2
3
5
8
13
21
34
55
89
144
233
377
610
987
```





**getitem**

```python
Fib实例虽然能作用于for循环，看起来和list有点像，但是，把它当成list来使用还是
不行，比如，取第5个元素：
>>> Fib()[5]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'Fib' object does not support indexing


要表现得像list那样按照下标取出元素，需要实现 __getitem__() 方法：
>>> class Fib(object):
...   def __getitem__(self, n):
...     a , b = 1,1
...     for x in range(n):
...       a , b = b , a+b
...     return a
...
>>> f = Fib()
>>> f[0]
1

切片的时候回出现错误，因为判断传入的是一个切片还是一个int，需要写出判定
```



**getattr**

```python
>>> class Student(object):
...   def __init__(self):
...      self.name = 'Michael'
...   def __getattr__(self, attr):#假设出现这个属性的时候，返回99
...     if attr == 'score':
...       return 99
...

>>> t=Student()
>>> t.name = 'chenming'
>>> t.name
'chenming'
>>> t.score = 99
>>> t.score
99
```



**call**

```
一个对象实例可以有自己的属性和方法，当我们调用实例方法时，我们用 instance.method() 来调用。能不能直接在实例本身上调用呢？类似 instance() ？在Python中，答案是肯定的。

>>> class  Student(object):
...   def __init__(self, name):
...     self.name=name
...   def __call__(self):
...     print('My name is %s .' %self.name)
...
>>> s =Student('chaneming')
>>> s.name
'chaneming'
>>> s()
My name is chaneming .
>>>
```



## 使用元类

type()

```python
>> class  Student(object):
...   def __init__(self, name):
...     self.name=name
...   def __call__(self):
...     print('My name is %s .' %self.name)
...
>>> type(Student)
<type 'type'>
>>> type(h)
<class '__main__.Student'>

type() 函数可以查看一个类型或变量的类型， Studnet 是一个class，它的类型就是 type ，而 h 是一个实例，它的类型就是class Student 。


type() 函数既可以返回一个对象的类型，又可以创建出新的类型，比如，我们可以通过 type() 函数创建出 Hello 类，而无需通过 classHello(object)... 的定义：
#先定义一个方法
>>> def fn(self, name='world'):
...   print('hello,  %s.' %name)
...

要创建一个class对象， type() 函数依次传入3个参数：
1. class的名称；
2. 继承的父类集合，注意Python支持多重继承，如果只有一个父类，别忘了tuple
的单元素写法；
3. class的方法名称与函数绑定，这里我们把函数 fn 绑定到方法名 hello 上。
>>> Hello = type('Hello', (object,), dict(hello = fn))
>>> h = HELLO（）
  File "<stdin>", line 1
    h = HELLO（）
             ^
SyntaxError: invalid syntax
>>> h = Hello()
>>> h.hello()
hello,  world.
>>> print(type(Hello))
<type 'type'>
>>> print(type(h))
<class '__main__.Hello'>
>>>
```

## metaclass



除了使用 type() 动态创建类以外，要控制类的创建行为，还可以使用metaclass。
metaclass，直译为元类，简单的解释就是：当我们定义了类以后，就可以根据这个类创建出实例，所以：先定义类，然后创建实例。

但是如果我们想创建出类呢？那就必须根据metaclass创建出类，所以：先定义metaclass，然后创建类。连接起来就是：先定义metaclass，就可以创建类，最后创建实例。所以，metaclass允许你创建类或者修改类。换句话说，你可以把**类看成是metaclass创建出来的“实例”**。

看不懂……



# 新知识

在计算机的层次上，CPU执行的是加减乘除的指令代码，以及各种条件判断和跳转指令，所以，汇编语言是最贴近计算机的语言。
而计算则指数学意义上的计算，越是抽象的计算，离计算机硬件越远。

## 大小写转化

**Python中转变大小写的直接函数有以下方法**：

upper()——所有字母大写   

lower()——所有字母小写

capitalize()——首字母大写，其他字母小写

title()——所有单词首字母大写，其他小写



## \转义



在交互模式下，最近一次表达式的值被赋给变量`_`

除了数值，Python 还可以操作字符串，可以用几种方法来表示。它们可以用单引号(`'...'`)或双引号(`"..."`)括起来，效果是一样的。符号`\`可以用来转义引号。

如果你前面带有\的字符被当作特殊字符，你可以使用*原始字符串*，方法是在第一个引号前面加上一个`r`:

\>>>

```
>>> print 'C:\some\name'  # here \n means newline!
C:\some
ame
>>> print r'C:\some\name'  # note the r before the quote
C:\some\name

```



## 连接

相邻的两个或多个*字符串字面量*（用引号引起来的）会自动连接。



```
>>> 'Py' 'thon'
'Python'

```

然而这种方式只对两个字符或常量有效，变量或者表达式是不行的。



```
>>> prefix = 'Py'
>>> prefix 'thon'  # can't concatenate a variable and a string literal
  ...
SyntaxError: invalid syntax
>>> ('un' * 3) 'ium'
  ...
SyntaxError: invalid syntax
```

**如果你想连接多个变量或者连接一个变量和一个常量，使用`“+”`：**



```
>>> prefix + 'thon'
'Python'

```

这个功能在你想切分很长的字符串的时候特别有用：

\>>>

```
>>> text = ('Put several strings within parentheses '
            'to have them joined together.')
>>> text
'Put several strings within parentheses to have them joined together.'
```

## 字符串的索引

字符串可以*索引*，第一个字符的索引值为0。Python没有单独的字符类型；一个字符就是一个简单的长度为1的字符串。

\>>>

```
>>> word = 'Python'
>>> word[0]  # character in position 0
'P'
>>> word[5]  # character in position 5
'n'

```

索引也可以是负值，此时从右侧开始计数：

\>>>

```
>>> word[-1]  # last character
'n'
>>> word[-2]  # second-last character
'o'
>>> word[-6]
'P'

```

注意，因为-0和0是一样的，负的索引从-1开始。

除了索引，还支持*切片*。索引用于获得单个字符，*切片*让你获得一个子字符串。

## 字符串自己可以进行比较

```python
#按照字母序排序
>>> 'abc' > 'bd'
False

```

## 方法和函数的区别

从定义的角度上看，我们知道函数(function)就相当于一个数学公式，它理论上不与其它东西关系，它只需要相关的参数就可以。所以普通的在module中定义的称谓函数是很有道理的。

那么方法的意思就很明确了，它是与某个对象相互关联的，也就是说它的实现与某个对象有关联关系。这就是方法。虽然它的定义方式和函数是一样的。也就是说，在Class定义的函数就是方法。

# 函数式编程





函数式编程就是一种抽象程度很高的编程范式，纯粹的函数式编程语言编写的函数没有变量，因此，任意一个函数，只要输入是确定的，输出就是确定的，这种纯函数我们称之为没有副作用。而允许使用变量的程序设计语言，由于函数内部的变量状态不确定，同样的输入，可能得到不同的输出，因此，这种函数是有副作用的。函数式编程的一个特点就是，允许把函数本身作为参数传入另一个函数，还允许返回一个函数！

Python对函数式编程提供部分支持。由于Python允许使用变量，因此，Python不是纯函数式编程语言。

变量可以指向函数，同时，函数也可以调用变量；所以默认函数不能随意赋值，否则会发生错误。**把函数作为参数传入，这样的函数称为高阶函数，函数式编程就是指这种高度抽象的编程范式**

```python
>>> def add(x, y, f):
...    return f(x) + f(y)
>>> add(-5,6 ,abs)#abs是一个绝对值函数
11
。
```



在使用列表时有三个函数非常有用：[`filter()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#filter)、[`map()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#map)和[`reduce()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#reduce)。

### filter





filter() 也接收一个函数和一个序列。和 map() 不同的时， filter() 把传入的函数依次作用于每个元素，然后根据返回值是 True 还是 False 决定保留还是丢弃该元素。**关键在于正确实现一个“筛选”函数**

```python
#取被2和3整除后余数不为零的
>>> def f(x): return x % 2 != 0 and x % 3 != 0
...
>>> filter(f, range(2, 25))
[5, 7, 11, 13, 17, 19, 23]
```

### map



map(function, sequence)` 为序列中的每一个元素调用 `function(item)` 函数并返回结果的列表。例如，计算列表中所有元素的立方值：



```python
#返回列表，关键是map中的函数是对map中的list每一个值起作用而不是对一个list直接起作用
>>> def cube(x): return x*x*x
...
>>> map(cube, range(1, 11))
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]
```



```python
'''可以传入多个序列；此时，传入的函数也必须要有和序列数目相同的参数，执行时会依次用各序列上对应的元素来调用函数（如果某个序列比另外一个短，就用 None 代替）。例如：'''

>>> seq = range(8)
>>> def add(x, y): return x+y
...
>>> map(add, seq, seq)
[0, 2, 4, 6, 8, 10, 12, 14]
```



```python
'''map() 作为高阶函数，事实上它把运算规则抽象了，因此，我们不但可以计算简单的f(x)=x*x，还可以计算任意复杂的函数，比如，把这个list所有数字转为字符串：'''
>>> map(str,[1,2,3,4,5])
['1', '2', '3', '4', '5']
```

### reduce



reduce(function, sequence)` 只返回一个值，

它首先以序列的前两个元素调用函数 *function*，然后再以返回的结果和下一个元素继续调用，依此执行下去。例如，若要计算数字 1 到 10 的总和：

```python

>>> def add(x,y): return x+y
...
>>> reduce(add, range(1, 11))
55
```

如果序列中只有一个元素，将返回这个元素的值；如果序列为空，则引发异常。



```python
'''可以传入第三个参数作为初始值。在这种情况下，如果序列为空则返回起始值，否则会首先以初始值和序列的第一个元素调用function，然后是返回值和下一个元素，依此执行下去。如，'''

>>> def sum(seq):
...     def add(x,y): return x+y
...     return reduce(add, seq, 0)
...
>>> sum(range(1, 11))
55
>>> sum([])
0
```



不要使用示例中定义的[`sum()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#sum)：由于计算数字的总和是一个如此常见的需求，Python提供了内置的函数`sum(sequence)`，其工作原理和示例几乎一样。

```python
'''reduce把一个函数作用在一个序列[x1, x2, x3...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算，其效果就是：'''
>>> reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```



# 类

命名空间是从名称到对象的映射。当前命名空间主要是通过 Python 字典实现的，不过通常不会引起任何关注（除了性能方面），它以后也有可能会改变。以下有一些命名空间的例子：内置名称集（包括函数名例如[`abs()`](http://python.usyiyi.cn/documents/python_278/library/functions.html#abs)和内置异常的名称）；模块中的全局名称；函数调用中的局部名称。在某种意义上，对象的属性也形成一个命名空间。关于命名空间需要知道的重要一点是不同命名空间内的名称(如函数名)绝对没有任何关系；例如，两个不同模块可以都定义函数`maximize`而不会产生混淆 —— 模块的使用者必须以模块名为前缀引用它们。

每个值都是一个对象，因此每个值都有一个*类*（也称为*类型*）。它存储为`object.__class__`。

# GUI

bind（）将键盘点击和函数关联

## label

**3.1 Label**

**说明**

　　标签

**用法**

　　Label(根对象, [属性列表])

**属性**

- text　   要现实的文本
- bg　　  背景颜色
- font　   字体(颜色, 大小)
- width　 控件宽度
- height　控件高度

## frame



**3.2 Frame**

**说明**

　　在屏幕上创建一块矩形区域,多作为容器来布局窗体

**用法**

　　Frame(根对象, [属性列表])

## Entry







**说明**

　　创建单行文本框

**用法**

- 　　创建:lb =Entry(根对象, [属性列表])
- 　　绑定变量 var=StringVar()    lb=Entry(根对象, textvariable = var)
- 　　获取文本框中的值   var.get()
- 　　设置文本框中的值   var.set(item1)

## text

**Text**

**说明**

　　向该空间内输入文本

**用法**

　　t = Text(根对象)

　　插入:t.insert(mark, 内容)

　　删除:t.delete(mark1, mark2)

　　其中,mark可以是行号,或者特殊标识,例如

- INSERT:光标的插入点CURRENT:鼠标的当前位置所对应的字符位置

- END:这个Textbuffer的最后一个字符

- SEL_FIRST:选中文本域的第一个字符，如果没有选中区域则会引发异常

- SEL_LAST：选中文本域的最后一个字符，如果没有选中区域则会引发 异常

  button



## Button**



**说明**

　　创建按钮

**用法**

　　Button(根对象, [属性列表])

## **Listbox**

**Listbox**

**说明**

　　列表控件,可以含有一个或多个文本想,可单选也可多选

**用法**

- 　　创建:lb = ListBox(根对象, [属性列表])
- 　　绑定变量 var=StringVar()    lb=ListBox(根对象, listvariable = var)
- 　　得到列表中的所有值   var.get()
- 　　设置列表中的所有值   var.set((item1, item2, .....))
- 　　添加:lb.insert(item)
- 　　删除:lb.delete(item,...)
- 　　绑定事件 lb.bind('<ButtonRelease-1>', 函数)
- 　　获得所选中的选项 lbl.get(lb.curselection())

**属性**

　　selectmode可以为BROWSE MULTIPL SINGLE

## CGI

例如  /new.py 就是上一个目录的意识，对比是本来应该调用此目录下的文件，但是文件实际在上一层，可以加**/**表示



# 测试、错误、调试

有的错误是程序编写有问题造成的，比如本来应该输出整数结果输出了字符串，这种错误我们通常称之为bug，bug是必须修复的。

有的错误是用户输入造成的，比如让用户输入email地址，结果得到一个空字符串，这种错误可以通过检查用户输入来做相应的处理。

还有一类错误是完全无法在程序运行过程中预测的，比如写入文件的时候，磁盘满了，写不进去了，或者从网络抓取数据，网络突然断掉了。这类错误也称为**异常**，

在程序中通常是必须处理的，否则，程序会因为各种问题终止并退出。

Python内置了一套异常处理机制，来帮助我们进行错误处理。

此外，我们也需要跟踪程序的执行，查看变量的值是否正确，这个过程称为调试。Python的pdb可以让我们以单步方式执行代码。
最后，编写测试也很重要。有了良好的测试，就可以在程序修改后反复运行，确保
程序输出符合我们编写的测试。

## 错误处理

在程序运行的过程中，如果发生了错误，可以事先约定返回一个错误代码，这样，就可以知道是否有错，以及出错的原因。在操作系统提供的调用中，返回错误码非常常见。比如打开文件的函数 open() ，成功时返回文件描述符（就是一个整数），出错时返回 -1 。用错误码来表示是否出错十分不便，因为函数本身应该返回的正常结果和错误码混在一起，造成调用者必须用大量的代码来判断是否出错。所以高级语言通常都内置了一套 t**ry...except...finally...** 的错误处理机制，Python也不例外。



## 调试



```python
#使用断言assert 的意思是，表达式 n != 0 应该是 True ，否则，后面的代码就会出
错。
# err.py
def foo(s):
	n = int(s)
	assert n != 0, 'n is zero!'
	return 10 / n
def main():
	foo('0')
```

```python
#使用logging
import logging
logging.basicConfig(level=logging.INFO)
s = '0'
n = int(s)
logging.info('n = %d' % n)
print (10 / n)

run结果是
H:\anaconda\envs\test_py3\python.exe H:/project/hello.py
INFO:root:n = 0
Traceback (most recent call last):
  File "H:/project/hello.py", line 6, in <module>
    print (10 / n)
ZeroDivisionError: division by zero

就是 logging 的好处，它允许你指定记录信息的级别，有 debug ， info ， warning ， error 等几个级别，当我们指定 level=INFO 时， logging.debug 就不起作用了。同理，指定 level=WARNING 后， debug 和 info 就不起作用了。这样一来，你可以放心地输出不同级别的信息，也不用删除，最后统一控制输出哪个级别的信息。
```

```python
使用pdb
# err.py
import pdb
s = '0'
n = int(s)
pdb.set_trace()
print 10 / n

run结果：
H:\anaconda\python.exe H:/project/hello.py
> h:\project\hello.py(6)<module>()
-> print 10 / n
(Pdb) #接着回车，写c
(Pdb) c
Traceback (most recent call last):
  File "H:/project/hello.py", line 6, in <module>
    print 10 / n
```

## 单元测试

单元测试是用来对一个模块、一个函数或者一个类来进行正确性检验的测试工作。

一旦编写好单元测试，我们就可以运行单元测试。最简单的运行方式是在 mydict_test.py 的最后加上两行代码：
if __ name __ == '__ main __':
​       unittest.main()
这样就可以把 mydict_test.py 当做正常的python脚本运行：



setUp与tearDown
可以在单元测试中编写两个特殊的 setUp() 和 tearDown() 方法。这两个方法会分别在每调用一个测试方法的前后分别被执行。
setUp() 和 tearDown() 方法有什么用呢？设想你的测试需要启动一个数据库，这时，就可以在 setUp() 方法中连接数据库，在 tearDown() 方法中关闭数据库，这样，不必在每个测试方法中重复相同的代码：

```python
class TestDict(unittest.TestCase):
	def setUp(self):
		print 'setUp...'
	def tearDown(self):
		print 'tearDown...'
```

# IO编程

IO在计算机中指Input/Output，也就是输入和输出。由于程序和运行时数据是在内存中驻留，由CPU这个超快的计算核心来执行，涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口。

由于CPU和内存的速度远远高于外设的速度，所以，在IO编程中，就存在速度严重不匹配的问题。举个例子来说，比如要把100M的数据写入磁盘，CPU输出100M的数据只需要0.01秒，可是磁盘要接收这100M数据可能需要10秒，怎么办呢？有两种办法：

1. 第一种是CPU等着，也就是程序暂停执行后续代码，等100M的数据在10秒后写入磁盘，再接着往下执行，这种模式称为同步IO；
2. 另一种方法是CPU不等待，只是告诉磁盘，“您老慢慢写，不着急，我接着干别的事去了”，于是，后续代码可以立刻接着执行，这种模式称为异步IO。

**同步和异步的区别就在于是否等待IO执行的结果。**很明显，使用异步IO来编写程序性能会远远高于同步IO，但是异步IO的缺点是编程模型复杂。想想看，你得知道什么时候通知你“汉堡做好了”，而通知你的方法也各不相同。如果是服务员跑过来找到你，这是回调模式，如果服务员发短信通知你，你就得不停地检查手机，这是轮询模式。总之，异步IO的复杂度远远高于同步IO。

## 文件读写

读写文件前，我们先必须了解一下，在磁盘上读写文件的功能都是由操作系统提供的，现代操作系统不允许普通的程序直接操作磁盘，所以，读写文件就是请求操作系统打开一个**文件对象**（通常称为文件描述符），然后，通过操作系统提供的接口从这个文件对象中读取数据（读文件），或者把数据写入这个文件对象（写文件）。



**读文件**

要以读文件的模式打开一个文件对象，使用Python内置的 open() 函数，传入文件名和标示符：

```python
>>> f = open('/Temp/waht.txt','r')
>>> f.read()
'Fuck\n\n'
>>> f.close()
>>> f.read()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: I/O operation on closed file


由于文件读写时都有可能产生 IOError ，一旦出错，后面的 f.close() 就不会调用。所以，为了保证无论是否出错都能正确地关闭文件，我们可以使用 try ...finally 来实现：
>>> try:
...     f = open('/Temp/waht.txt', 'r')
...     print f.read()
... finally:
...     if f:
...          f.close()
...
Fuck


但是每次都这么写实在太繁琐，所以，Python引入了 with 语句来自动帮我们调用 close() 方法：
>>> with open('/Temp/waht.txt', 'r')as f:
...   print f.read()
...
Fuck
```

调用 read() 会一次性读取文件的全部内容，如果文件有10G，内存就爆了，所以，要保险起见，可以反复调用 read(size) 方法，每次最多读取size个字节的内容。另外，调用 readline() 可以每次读取一行内容，调用 readlines() 一次读取所有内容并按行返回 list 。因此，要根据需要决定怎么调用。

**打开二进制文件**，如图片视频之类的

```python
>>> f= open('/Temp/dier.jpg', 'rb')
>>> f.read()
'\xff\xd8\xff\xe0\……
```

**字符编码**
要读取非ASCII编码的文本文件，就必须以二进制模式打开，再解码。





**写文件**

写文件和读文件是一样的，唯一区别是调用 open() 函数时，传入标识符 'w' 或者 'wb' 表示写文本文件或写二进制文件：

```python

>>> f= open('/Temp/waht.txt', 'w')
>>> f.write('hello ,world')
>>> f.close()

#我发现直接这样写入是会把原文全部替换
如果不进行f.close(）的话，这个文件会被系统锁定，无法打开，原理：
             你可以反复调用 write() 来写入文件，但是务必要调用 f.close() 来关闭文
            件。当我们写文件时，操作系统往往不会立刻把数据写入磁盘，而是放到内存缓存
            起来，空闲的时候再慢慢写入。只有调用 close() 方法时，操作系统才保证把没
            有写入的数据全部写入磁盘。忘记调用 close() 的后果是数据可能只写了一部分
            到磁盘，剩下的丢失了。
用with就不用写关闭：
             with open('/Users/michael/test.txt', 'w') as f:
  				f.write('Hello, world!')            
```



## 操作文件和目录





## 序列化

在程序运行的过程中，所有的变量都是在内存中，比如，定义一个dict：

```
d = dict(name='Bob', age=20, score=88)
```

可以随时修改变量，比如把 name 改成 'Bill' ，但是一旦程序结束，变量所占用的内存就被操作系统全部回收。如果没有把修改后的 'Bill' 存储到磁盘上，下次重新运行程序，变量又被初始化为 'Bob' 。

**我们把变量从内存中变成可存储或传输的过程称之为序列化**，在Python中叫pickling，在其他语言中也被称之为serialization，marshalling，flattening等等，都是一个意思。

序列化之后，就可以把序列化后的内容写入磁盘，或者通过网络传输到别的机器上。
反过来，把变量内容从序列化的对象重新读到内存里称之为反序列化，即unpickling。

Python提供两个模块来实现序列化： cPickle 和 pickle 。这两个模块功能是一样的，区别在于 cPickle 是C语言写的，速度快， pickle 是纯Python写的，速
度慢，

### JSON

如果我们要在**不同的编程语言之**间传递对象，就必须把对象序列化为标准格式，比如XML，但更好的方法是序列化为JSON，因为JSON表示出来就是一个字符串，可以被所有语言读取，也可以方便地存储到磁盘或者通过网络传输。**JSON不仅是标准格式，并且比XML更快，而且可以直接在Web页面中读取，非常方便。**



# 线程、进程

现在，多核CPU已经非常普及了，但是，即使过去的单核CPU，也可以执行多任务。由于CPU执行代码都是顺序执行的，那么，单核CPU是怎么执行多任务的呢？

答案就是操作系统轮流让**各个任务交替执行**，任务1执行0.01秒，切换到任务2，任务2执行0.01秒，再切换到任务3，执行0.01秒……这样反复执行下去。表面上看，每个任务都是交替执行的，但是，由于CPU的执行速度实在是太快了，我们感觉就像所有任务都在同时执行一样。

真正的并行执行多任务只能在多核CPU上实现，但是，由于任务数量远远多于CPU的核心数量，所以，操作系统也会自动把很多任务轮流调度到每个核心上执行。

对于操作系统来说，一**个任务就是一个进程（**Process），比如打开一个浏览器就是启动一个浏览器进程，打开一个记事本就启动了一个记事本进程，打开两个记事本就启动了两个记事本进程，打开一个Word就启动了一个Word进程。

有些进程还不止同时干一件事，比如Word，它可以同时进行打字、拼写检查、打印
等事情。在一个进程内部，要同时干多件事，就需要同时运行多个“子任务”，我们
把进程内的这些“子任务”称为**线程**（Thread）。（哦，python说的多线程）

python要完成多任务的方法主要有：

1. 开多个进程；
2. 一个进程多个线程；
3. 就是启动多个进程，每个进程再启动多个线程




- CPython的线程是[操作系统](https://zh.wikipedia.org/wiki/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F)的原生线程。在[Linux](https://zh.wikipedia.org/wiki/Linux)上为pthread，在[Windows](https://zh.wikipedia.org/wiki/Windows)上为Win thread，完全由操作系统调度线程的执行。一个Python解释器进程内有一个主线程，以及多个用户程序的执行线程。即便使用[多核心CPU](https://zh.wikipedia.org/wiki/%E5%A4%9A%E6%A0%B8%E5%BF%83CPU)平台，由于GIL的存在，也将禁止多线程的并行执行。[[1\]](https://zh.wikipedia.org/wiki/%E5%85%A8%E5%B1%80%E8%A7%A3%E9%87%8A%E5%99%A8%E9%94%81#cite_note-1)

- Python解释器进程内的多线程是以协作多任务方式执行。当一个线程遇到[I/O](https://zh.wikipedia.org/wiki/I/O)任务时，将释放GIL。计算密集型（CPU-bound）的线程在执行大约100次解释器的计步（ticks）时，将释放GIL。计步（ticks）可粗略看作Python虚拟机的指令。计步实际上与时间片长度无关。可以通过sys.setcheckinterval()设置计步长度。

- 无论是多进程还是多线程，只要数量一多，效率肯定上不去，为什么呢？
  我们打个比方，假设你不幸正在准备中考，每天晚上需要做语文、数学、英语、物
  理、化学这5科的作业，每项作业耗时1小时。
  ​
  如果你先花1小时做语文作业，做完了，再花1小时做数学作业，这样，依次全部做
  完，一共花5小时，这种方式称为单任务模型，**或者批处理任务模型**。

  假设你打算切换到多任务模型，可以先做1分钟语文，再切换到数学作业，做1分钟，再切换到英语，以此类推，只要切换速度足够快，这种方式就和单核CPU执行多任务是一样的了，以幼儿园小朋友的眼光来看，你就正在同时写5科作业。

  但是，切换作业是有代价的，比如从语文切到数学，要先收拾桌子上的语文书本、钢笔（这叫保存现场），然后，打开数学课本、找出圆规直尺（这叫准备新环境），才能开始做数学作业。

  操作系统在切换进程或者线程时也是一样的，**它需要先保存当前执行的现场环境（CPU寄存器状态、内存页等），然后，把新任务的执行环境准备好（恢复上次的寄存器状态，切换内存页等），才能开始执行。这个切换过程虽然很快，但是也需要耗费时间。**如果有几千个任务同时进行，操作系统可能就主要忙着切换任务，根本没有多少时间去执行任务了，这种情况最常见的就是硬盘狂响，点窗口无反应，系统处于假死状态。所以，多任务一旦多到一个限度，就会消耗掉系统所有的资源，结果效率急剧下降，所有任务都做不好。


**计算密集型 vs. IO密集型**
是否采用多任务的第二个考虑是任务的类型。我们可以把任务分为计算密集型和IO密集型。

计算密集型任务的特点是要进行大量的计算，消耗CPU资源，比如计算圆周率、对视频进行高清解码等等，全靠CPU的运算能力。这种计算密集型任务虽然也可以用多任务完成，但是任务越多，花在任务切换的时间就越多，CPU执行任务的效率就越低，所以，要最高效地利用CPU，**计算密集型任务同时进行的数量应当等于CPU的核心数**。

计算密集型任务由于主要消耗CPU资源，因此，代码运行效率至关重要。Python这样的脚本语言运行效率很低，完全不适合计算密集型任务。对于计算密集型任务，最好用C语言编写。

**第二种任务的类型是IO密集型，涉及到网络、磁盘IO的任务都是IO密集型任务，这类任务的特点是CPU消耗很少，任务的大部分时间都在等待IO操作完成**（因为IO的速度远远低于CPU和内存的速度）。对于IO密集型任务，任务越多，CPU效率越高，但也有一个限度。常见的大部分任务都是IO密集型任务，比如Web应用。

IO密集型任务执行期间，99%的时间都花在IO上，花在CPU上的时间很少，因此，用运行速度极快的C语言替换用Python这样运行速度极低的脚本语言，完全无法提升运行效率。对于IO密集型任务，最合适的语言就是开发效率最高（代码量最少）的语言，脚本语言是首选，C语言最差。

**异步IO**
考虑到CPU和IO之间巨大的速度差异，一个任务在执行的过程中大部分时间都在等待IO操作，单进程单线程模型会导致别的任务无法并行执行，因此，我们才需要多进程模型或者多线程模型来支持多任务并发执行。

现代操作系统对IO操作已经做了巨大的改进，最大的特点就是支持异步IO。如果充分利用操作系统提供的异步IO支持，就可以用单进程单线程模型来执行多任务，这种全新的模型称为事件驱动模型，Nginx就是支持异步IO的Web服务器，它在单核CPU上采用单进程模型就可以高效地支持多任务。在多核CPU上，可以运行多个进程（数量与CPU核心数相同），充分利用多核CPU。由于系统总的进程数量十分有限，因此操作系统调度非常高效。用异步IO编程模型来实现多任务是一个主要的趋势。

**对应到Python语言，单进程的异步编程模型称为协程**，有了协程的支持，就可以基
于事件驱动编写高效的多任务程序。我们会在后面讨论如何编写协程。

## 异步

异步IO模型需要一个消息循环，在消息循环中，主线程不断地重复“读取消息-处理
消息”这一过程：

loop = get_event_loop()
while True:
​	event = loop.get_event()
​	process_event(event)

在“发出IO请求”到收到“IO完成”的这段时间里，同步IO模型下，主线程只能挂起，
但异步IO模型下，主线程并没有休息，而是在消息循环中继续处理其他消息。这
样，在异步IO模型下，一个线程就可以同时处理多个IO请求，并且没有切换线程的
操作。对于大多数IO密集型的应用程序，使用异步IO将大大提升系统的多任务处理
能力。

- 协程

**第一个问题：yield怎么用的？**

解析：汉语中生产的意思，它作为一个生成器的标志,也是迭代器，遇到yield表示暂停，开始迭代出数

```python
#!/usr/bin/env Python
# coding=utf-8

def fibs(max):
    """
    斐波那契数列的生成器
    """
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1

if __name__ == "__main__":
    f = fibs(10)
    for i in f:
        print i ,
```

- yield方法

  ```python
  def consumer():
      r = ''
      while True:
          n = yield  r
          if not n:
              return
          print ('[consumer] consumer %s ... ' % n)
          r = '200 ok'

  def produce(c):
      c.send(None)
      n = 0
      while n < 5:
          n = n + 1
          print('[producer] producing %s ...' % n)
          r = c.send(n)#r = c 发送出去后返回的
          print('[producer consumer return :%s' %r)
      c.close()

  c =consumer()
  produce(c)

  1. 首先调用 c.send(None) 启动生成器；
  2. 然后，一旦生产了东西，通过 c.send(n) 切换到 consumer 执行；
  3. consumer 通过 yield 拿到消息，处理，又通过 yield 把结果传回；
  4. produce 拿到 consumer 处理的结果，继续生产下一条消息；
  5. produce 决定不生产了，通过 c.close() 关闭 consumer ，整个过程结
  束。
  ```

  ```python
  def yield_test(n):
      for i in range(n):
          yield call(i)
          print ('i=',i)
      print ('do some')
      print ('end')
  def call(i):
      return  i*2

  for i in yield_test(5):
      print (i,'*')#一旦进入迭代，就关键在yield处返回值输出
  ```

  ​

# 问题

一个类cat（）

```
x = cat（）和x = cat 有什么区别？
```




1. surper()搞不懂这个

2. try ……except怎么用的

   ​




机器学习从业务入手pygame入手学习numpy  用pygame尝试写一个rpg游戏，对你面向对象和numpy这两块都会有促进

- property

*class `property`(*fget=None*, *fset=None*, *fdel=None*, *doc=None*)

返回一个property 属性。

*fget*是获取属性值的函数。*fset*是用于设置属性值的功能。*fdel*是用于删除属性值的功能。并且*doc*为属性创建一个docstring。

典型的用法是定义一个托管属性`x`：

```
class C:
    def __init__(self):
        self._x = None

    def getx(self):
        return self._x

    def setx(self, value):
        self._x = value

    def delx(self):
        del self._x

    x = property(getx, setx, delx, "I'm the 'x' property.")

```

如果*c*是*C*的实例，则`c.x`将调用getter，`c.x = value`将调用setter，`del c.x`将调用deleter。

如果给出*doc*，它将是该属性的文档字符串。否则，该属性将拷贝*fget*的文档字符串（如果存在）。这使得可以使用[`property()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#property)作为[装饰器](http://python.usyiyi.cn/documents/python_352/glossary.html#term-decorator)轻松创建只读属性：

```
class Parrot:
    def __init__(self):
        self._voltage = 100000

    @property
    def voltage(self):
        """Get the current voltage."""
        return self._voltage

```

`@property`装饰器将`voltage()`方法转换为具有相同名称的只读属性的“getter”，并设置为*voltage*的文档字符串为“Get the current voltage.”。

Property对象具有可用作装饰器的`getter`、`setter`和`deleter`方法，用于创建property的副本，并将相应的访问器函数设置为装饰的功能。最好的解释就是使用一个例子：

```
class C:
    def __init__(self):
        self._x = None

    @property
    def x(self):
        """I'm the 'x' property."""
        return self._x

    @x.setter
    def x(self, value):
        self._x = value

    @x.deleter
    def x(self):
        del self._x

```

这段代码与第一个例子完全相等。请务必给予附加函数与原始属性相同的名称（在本例中为`x`）。

返回的property对象还具有对应于构造函数参数的属性`fget`、`fset`和`fdel`。

在3.5版本中已更改：属性对象的docstrings现在是可写的。





- `eval`(*expression*, *globals=None*, *locals=None*)

  参数是字符串和可选的全局变量和局部变量。如果有全局变量，*globals*必须是个字典。如果有局部变量，*locals*可以是任何映射类型对象。*expression*参数被当作Python表达式来解析并演算（技术上来说，是个条件列表），使用*globals*和*locals*字典作为全局和局部的命名空间。如果*globals*字典存在，且缺少‘__builtins__’，在*expression*被解析之前，当前的全局变量被拷贝进*globals*。这意味着*expression*通常具有对标准[`builtins`](http://python.usyiyi.cn/documents/python_352/library/builtins.html#module-builtins)的完全访问权限，并且传播受限环境。如果*locals*字典被忽略，默认是*globals*字典。如果两个字典都省略，则在调用[`eval()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#eval)的环境中执行表达式。返回值是被演算的表达式的结果。语法错误报告成异常。例子：>>>`>>> x = 1>>> eval('x+1')2`此函数也可用于执行任意代码对象（例如由[`compile()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#compile)创建的代码对象）。在这种情况下，传递代码对象而不是字符串。如果代码对象已使用`'exec'`作为*mode*参数编译，则[`eval()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#eval)的返回值将为`None `。提示：[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)函数支持语句的动态执行。[`globals()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#globals)和[`locals()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#locals)函数分别返回当前的全局和局部字典，可以用于传递给[`eval`](http://python.usyiyi.cn/documents/python_352/library/functions.html#eval)或[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)。请参见[`ast.literal_eval()`](http://python.usyiyi.cn/documents/python_352/library/ast.html#ast.literal_eval)这个函数，它可以安全地计算只包含字面值表达式的字符串。


- `exec`(*object*[, *globals*[, *locals*]])

  这个函数支持动态执行Python代码。*object*必须是一个字符串或代码对象。如果它是一个字符串，该字符串被解析为一套Python语句，然后执行（除非语法错误发生）。[[1\]](http://python.usyiyi.cn/documents/python_352/library/functions.html#id2)如果它是一个代码对象，只是简单地执行它。在所有情况下，执行的代码应该可以作为有效的文件输入（参见“参考手册”中的“文件输入”部分）。请注意，即使在传递给[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)函数的代码上下文中，函数定义外面的[`return`](http://python.usyiyi.cn/documents/python_352/reference/simple_stmts.html#return)和[`yield`](http://python.usyiyi.cn/documents/python_352/reference/simple_stmts.html#yield) 语句可能不被执行。返回值为`None`。在所有情况下，如果省略可选部分，则代码在当前作用域中执行。如果只提供*globals*，它必须是一个字典，它将用于全局变量和局部变量。如果提供*globals*和*locals*，它们分别用于全局变量和局部变量。如果存在，*locals*可以是任意的映射类型对象。记住在模块级别，全局和局部字典是同一个字典。如果exec的*globals*和*locals*是独立的两个对象，代码的执行就像它嵌入在类定义中一样。如果*globals*字典的`__builtins__`键没有值，则会给这个赋予一个内置模块[`builtins`](http://python.usyiyi.cn/documents/python_352/library/builtins.html#module-builtins)字典的引用。这样，你可以在将*globals*传递给[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)之前插入自己的`__builtins__`字典，来控制执行的代码可访问的builtins。注内置函数[`globals()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#globals)和[`locals()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#locals)分别返回当前全局和局部字典，它们可以用做传递给[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)的第二和第三个参数。注意默认的*locals*的行为和下述的[`locals()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#locals)函数一样：不应该尝试修改默认的*locals*字典。如果在函数[`exec()`](http://python.usyiyi.cn/documents/python_352/library/functions.html#exec)返回后，需要在*locals*上查看代码的效果，请传递一个明确的*locals*字典。

# 机器学习



# 问题解决、代码

## 路径编码

那么该如何解决呢？
第一种办法：
在字符串前加一个字母 r，如下：
path=r"C:\Users\Administrator\Desktop"
在字符串前加个 r 是为了告诉编译器这个string是个raw string，不要转义。
第二种办法：
将字符串中的反斜杠换成正斜杠，如下：
写路径问题
path="C:/Users/Administrator/Desktop"
关于路径问题，在不同系统中，写法都大同小异。而这些问题无外乎源于这两方面：正反斜
杠，编码（无法识别中文等）。

## 下载图片

```
#爬取百度贴吧一些小图片  
#urllib.urlretriev---将远程数据下载到本地  
import urllib  
import urllib2  
import re  
  
#http://tieba.baidu.com/p/3868127254  
a = raw_input('inpt url:')  
s = urllib2.urlopen(a)  
s1 = s.read()  
  
def getimg(aaa):  
        reg = re.compile(r'img.src="(.*?)"')  
        #reg = re.compile(r'<title>')  
        l = re.findall(reg, aaa)  
        tmp =0  
        for x in l:  
                tmp += 1  
                urllib.urlretrieve(x, '%s.jpg' % tmp)  #这一个函数和这一段命名我													很需要
  
#print s1  
getimg(s1)  





```



图片乱码的时候处理

*#*coding:utf-8

import requests
resp = requests.get("http://image.3001.net/images/20160608/14653769669317.jpg")
with open("test.jpg","wb") as img:
​	img.write(resp.content)

## 网址中文

```
 x 其实两种url都是可以正常访问的，没有必要处理，如真是想进行处理的话，可以如以下方式处理：
 from urllib.parse import 
 unquoteUrls=['http://bj.ganji.com/ershoubijibendiannao/z1/_%E6%88%B4%E5%B0%94/','http://jixie.huangye88.com/tag/%E5%9C%B0%E4%B8%AD%E8%A1%A1/']
 for url in Urls:    
 	print(unquote(url,encoding="utf-8"))
+++++++
输出结果
++++++++
http://bj.ganji.com/ershoubijibendiannao/z1/_戴尔/
http://jixie.huangye88.com/tag/地中衡/
```

## 爬虫断点出错

断点详解
当我们针对一个大的网站写好爬虫程序时，往往需要使用很多时间去爬取我们所需要的信息，因为一旦停止运行，所有保存在内存中的已经爬取过的链接以及其他数据将不存在，所以我们得保证我们的程序不会中途终止运行，否则将会前功尽弃。可是在爬取的过程中，我们很难能避开所有的错误使程序完美的运行。
在课程中，我们介绍了一种断点的方法，代码如下：
db_urls = [item['url'] for item in url_list.find()] #取出所有目标地址链接
index_urls = [item['url'] for item in item_info.find()]#取出已经爬取过的地址链接
x = set(db_urls)
y = set(index_urls)
rest_of_urls = x-y#还需爬取的地址链接

那么这段程序应该如何使用呢？ 将该程序放在抓取网页信息的程序段之前，并且只需执行一次即可，如下：
if name == 'main':
    db_urls = [item['url'] for item in ganji_url.find()]
    index_urls = [item['url'] for item in ganji_data1.find()]
    x = set(db_urls)
    y = set(index_urls)
    rest_of_urls = x - y
    pool = Pool()
    pool.map(get_item_info_from, rest_of_urls)
注意事项： 1、请勿将断点程序直接加入我们爬取信息的函数中，这将使我们的程序多做无用
功。 2、在使用断点程序之前，请先将目标url，和已经爬取过的url存入数据库。
那么除了加上断点程序，还可以做些什么，来使我们的程序更有健壮性吗？ 答案是有的，那
就是使用try...except...这是一个捕抓错误的程序，当问题出现时，捕抓它，并且处理，而不
至于使我们的程序直接停止运行。代码如下：
断点详解
63
def get_item_info_from(url, data=None):
    try:
        wb_data = requests.get(url)
    except Exception as e:
        print(e)
这样就可以避免我们在访问网站时，出现错误而导致程序停止运行的尴尬局面了。
而try...except...的范围还可以继续扩大。

