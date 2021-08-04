---
title: "Life is short, you need Python."
author: [L.Li]
date: "2021-05-21"
keywords: [Python]
header-center: "北京交通大学"
footer-center: "Beijing Jiaotong University"
...



``` python
# 这是我的第一个Python语言代码
print("Hello World")
```

``` python

```



# python install


## python on Win10
在Microsoft Store中搜索Python，安装Python3.9。安装好后即可在cmd中使用python、pip等命令。  

说明 | cmd命令  
-|-
pip版本 | >pip --version 
pip升级 | >python -m pip install --upgrade pip
设置镜像源 | >pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
已安装的库 | >pip list



## python on OSX

MAC OS自带python 2.7。



## Jupyter Lab
概要：Jupyter是一个风格类似Matlab的基于网页的python IDE，在功能上更偏向于数据分析。JupyterLab是一个交互式的开发环境，是Jupyter notebook的下一代产品，集成了更多的功能，  
官网：https://jupyter.org/index.html  
参考：https://www.cnblogs.com/lskreno/p/10844315.html  
参考：https://zhuanlan.zhihu.com/p/67959768  

  
说明 | cmd命令（win10） | Terminal命令（OSX）
- | - | -
安装jupyterlab | >pip install jupyterlab |
打开jupyterlab | >jupyter lab |

### Jupyter VScode配置
VSCode支持Python功能，非常简单。首先，要在Windows系统中配置python，然后安装VSCode。 打开VSCode，安装插件jupyter。新建（.ipynb）文件，可执行JupyterNote界面 。打开VSCode，安装插件python。新建（.py）文件,输入代码即可运行；输入，可在python代码中插入Cell。  



## Python on VSCode



# 语法


## 数据类型


Python中的数据类型可以分为五大类：数字、字符串、容器、布尔、None。


### 数字

整型、浮点型和复数。

1. 整型：正整数或负整数
2. 浮点型：由整数部分和小数部分组成
3. 复数：由实数部分和虚数部分组成



### 字符串

可以使用单引号或双引号创建字符串，可以用加号将两个字符串合并。

``` python
name = '小明'
age = '9岁'
print('合并字符串:', name + age)

# 格式化字符串 %s
a = "I'm %s, %s years old. " % ('xiaoming', 'nine')
print(a)
```



### 容器

List(列表)、Tuple(元组)、Sets(集合)、Dictionary(字典)




#### List

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。列表可以修改，可以用于切片、增、删、改、查等，用法特别多，这里就不一一列举了。


``` python
list_1 = ['a', 'b', 'c', 'd', 'e']   # 创建列表
list_2 = [int(n) for n in input().split()]  # 输入不定长一维整数数组，以空格作分隔，以回车作结束
# 两种打印形式，后面默认带回车“\n”的
print(list_1)   # ['a', 'b', 'c', 'd', 'e']
print(*list_1)  # a b c d e
```



列表切片
``` python
#格式：【start:end:step】
#start:起始索引，从0开始，-1表示结束#end：结束索引
#step：步长，end-start，步长为正时，从左向右取值。步长为负时，反向取值
#注意切片的结果不包含结束索引，即不包含最后的一位，-1代表列表的最后一个位置索引
a = [1, 2, 3, 4, 5, 6]
b = a[0:5:3] 
print(b)    # [1, 4]
```

列表增加
``` python
a=[1,2,3,4,5,6]
a.append(18)
print(a)
```

列表删除
``` python
del a[-1]
print(a)
```

列表修改
``` python
print("未修改之前第一个元素为：",a[0])
a[0] = '66'
print("修改之后第一个元素为：",a[0])
```

列表查询
``` python
a1 = a[0]
print("查询出列表第一个元素为：", a1)
```




去除list中的重复项，可能会打乱list顺序。
``` python
my_list = list(set(list_1))
```

排序
``` python
my_list.sort()   # 排序，排序后的数组为 my_list
```

将list2接到list1的后面
``` python
list_1.extend(list_2)   # 列表合并
```

#### Tuple

元组和列表类似，但是不同的是元组不能修改，元组使用小括号。

``` python
#创建元组
tup = (1, 2, 3, 4, 5)
print(tup)
```

元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当作运算符使用。
``` python
#查询元组,下标索引从0开始
print("查询出列表第一个元素为：", tup[0])
```





元组中的元素值是不允许修改的，但可以对元组进行连接组合。
``` python
tup1 = (23, 78);
tup2 = ('ab', 'cd')
tup3 = tup1 + tup2
print (tup3)
```


















#### Sets

Set是无序的集合，不能有重复的元素，也不能排序。
``` python
#创建集合
s1 = set(['A','B','C','D'])
print(s1)

#增加元素:update
s1.update(['E'])
print(s1)

#删除元素:discard
s1.discard('E')
print(s1)

#修改元素：先删除，后增加
s1.discard('D')
s1.update(['D'])
print(s1)

#查询元素
ss = 'B' in s1
print(ss)
```








#### Dictionary



字典是另一种可变容器模型，且可存储任意类型对象。
字典的格式如下所示：`d = {key1 : value1, key2 : value2 }`。
键（Key）必须是唯一的，但值（Value）则不必。值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。
``` python
#创建字典
d = {'01': 'xiaoming', '02': 'xiaohong', '03': 'xiaowang'}
print(d)
#增加
d['04'] = 'xiangfang'
print(d)

#删除
del d['04']
print(d)

#修改
print("修改之前：",d['01'])
d['01'] = 'xiaolin'
print("修改之后：",d['01'])

#查询
d1 = d['01']
print(d1)

```


### Bool


True、False

主要应用在条件判断上面，发生即为True，未发生即为False。Python严格区分大小写，所以一定要注意不要写错。

### None

Python里面特殊的空值，不能理解为0。



## Judge

### if

``` python
a = 25
if a >= 20:
    print("Yes")
else:
    print ("No")
```



### elif

elif语句可以检查多个表达式的真值，并执行一个代码块的条件之一计算结果为true。
if...elif 语句是可选的。然而不像else，对此可以有最多一个语句，if语句下边可以有任意数量elif语句。

``` python
x = "上海"
if x == "上海":
    print ("大")
elif x == "北京":
    print ("特别大")
else:
    print("无")
```



## loop

### for loop
for循环可以遍历任何序列的项目：
``` python
x = list(["小明","小红","小张","小李"])
for b in x:
    print (b)
```



### while loop
while循环，只要条件满足，就不断循环，条件不满足时退出循环：

``` python
sum = 0
n = 99
while n > 0:
    sum = sum + n
    n = n - 2
print(sum)
```


### break

break和continue语句：

break可以用来终止当前的循环语句，即使循环没结束，执行了break语句这个循环就终止了，直接跳出整个循环。

``` python
for i in range(10):
    print(i)
    if i == 8:
        break
print('end')
```


### continue

continue语句是用来告诉程序跳出本次循环，然后执行下一轮循环，不同与break，break是跳出整个循环，continue是结束这一次循环，继续下一次循环。

``` python
for i in range(10):
    if i == 6:
        print('good')
        continue
    print(i)    
print('end')
```





## Function

函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。

在Python中，定义一个函数要使用 def 语句，依次写出函数名、括号、括号中的参数和冒号 : ，然后，在缩进块中编写函数体，函数的返回值用 return 语句返回。

``` python
def threeNumAdd(x,y,z):
    numSum = x + y + z
    return numSum

a = threeNumAdd(10,20,30)
print(a)
```





函数参数：不可变数据类型，如 整数、字符串、元组。
``` python
def ChangeInt(a):
    a = 10
b = 2
ChangeInt(b)
print(b)
```


函数参数：可变数据类型，如 列表，字典。
``` python
def changelist(alist):
    alist.append([1, 2])

blist = ['10', '20']
print('调用函数之前的值：', blist)
changelist(alist = blist)
print('调用函数之后的值：', blist)
```




### 变量作用域
一般在函数体外定义的变量成为全局变量，在函数内部定义的变量称为局部变量。

全局变量所有作用域都可读，局部变量只能在本函数可读。

函数在读取变量时，优先读取函数本身自有的局部变量，再去读全局变量。

``` python
name = 'Tim' #全局变量

def f1():
    age = 18 #局部变量
    print(age,name)
    
def f2():
    age = 19 #局部变量
    print(age,name)
    
f1()
f2()
```




### 模块

模块引入
#import 语句,用于导入整个模块
import math

#from-import 语句,常用于只导入指定模块的部分属性或模糊导入：
#from 模块名 import 函数名1,函数名2....
from random import choice,random




## Data Structure

### 队列

``` python
from  collections import deque
#定义队列：排队吃饭人的编号
queue = deque(['001','002','003','004','005'])
#入队：在队列尾部插入元素
queue.append('006')
print(queue)
#出队：在队列头部删除元素
queue.popleft()
print(queue)
```




### 栈

``` python
#定义栈：浏览个人知乎主页的顺序
stack = deque(['知乎动态','知乎回答','知乎文章'])
#入栈：在栈顶加入元素
stack.appendleft('知乎专栏')
print(stack)
#出栈
stack.pop()
print(stack)
```




### 排序字典

Python默认的字典（key无序）

``` python
#6家公司名称及股票代码
gafatadict = {'腾讯':'HK:00700', '阿里巴巴':'baba', '苹果':'Apple', '谷歌':'GOOGLE', 'Facebook':'fb', '亚马逊':'amzn'}
gafatadict
```




Collection中的排序字典（key有序）

``` python
from collections import OrderedDict
#定义有序字典
gafataodDict=OrderedDict({'腾讯':'HK:00700', '阿里巴巴':'baba', '苹果':'Apple', 
                  '谷歌':'GOOGLE', 'Facebook':'fb', '亚马逊':'amzn'})
gafataodDict
OrderedDict([('腾讯', 'HK:00700'), ('阿里巴巴', 'baba'), ('苹果', 'Apple'), ('谷歌', ':GOOGLE'), ('Facebook', 'fb'), ('亚马逊', 'amzn')])
```




### 计数器

``` python
from collections import Counter
cdict = Counter('好好学习，天天向上')
cdict
#出现次数最多的2个词
cdict.most_common(2)
```

























## 常用函数






基本类型：
控制：
自定义类型：
修饰词：
运算符：+, -, *, /, %, ++, --, &, |, ~, ^, &&, ||, !, <, >, <=, >=, ==, !=, <<, >>, ., ->, ?:, sizeof. 
复合运算符 
预处理器：#include, #define, #undef,#if/#ifdef/#ifndef...#elif...#else...#endif, defined, #pragma,#error 

有极少数关键字有多种语义，例如static、void，算是麻烦一点。还有指针相关的类型和使用也算是比较麻烦点。其他都没有太复杂的东西。看着床头上832页、两寸厚的《C++ Templates》第二版，几乎只涉及几个C++关键字（template, typename, decltype, using），然后就会觉得上面的都太简单了。



变量

| 基本类型     | 关键字   | 占用字节 | 范围         |
| ------------ | -------- | -------- | ------------ |
| 整型         | int      | 4 byte   | -65537~65537 |
| 字符型       | char     | byte     |              |
| 单精度浮点型 | float    | byte     |              |
| 双精度浮点型 | double   | byte     |              |
| 短           | short    | byte     |              |
| 长           | long     | byte     |              |
| 有符号       | signed   | byte     |              |
| 无符号       | unsigned | byte     |              |
| 空           | void     | byte     |              |








### input, output


``` python
n = int(input())        # 输入二维数组的行数和列数

line = [[0]*n]*n        # 初始化二维数组

for i in range(n):
    line[i] = input().split(" ")       # 输入二维数组，同行数字用空格分隔，不同行则用回车换行
    line[i] = [int(j) for j in line[i]]    # 将数组中的每一行转换成整型

print(line[0][0])            # 打印二维数组

```





# 算法



## ACM


输入一维数组
``` python
#方法1
num = [int(n) for n in input().split()]

#方法二
num = list(map(int, input().strip().split()))

print num
```

``` python

```

``` python

```

``` python

```

``` python

```

``` python

```

``` python

```




## Sort

比较类排序：通过比较来决定元素间的相对次序，由于其时间复杂度不能突破O(nlogn)，因此也称为非线性时间比较类排序。
交换排序（冒泡排序、快速排序）、插入排序（简单插入排序、希尔排序）、选择排序（简单选择排序、堆排序）、归并排序（二路归并排序、多路归并排序）。

非比较类排序：不通过比较来决定元素间的相对次序，它可以突破基于比较排序的时间下界，以线性时间运行，因此也称为线性时间非比较类排序。
计数排序、桶排序、基数排序。


``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```

``` c++

```


# python 库




## Matplotlib
Matplotlib 是 Python 的绘图库。 通常与 NumPy 一起使用  
导入数据，数据由行和列组成，在数据库中，一般行被称作记录 (record)，列被称作字段 (field)。  

``` python
# Way1 通过NumPy导入CSV文件。
from numpy import loadtxt
filename=input("文件名：")
data=loadtxt(raw_data,delimiter=',')
print(data)

# Way2 通过Pandas导入CSV文件。★
# 参考： https://www.jianshu.com/p/ebb64a159104
import pandas
df = pandas.read_csv('test.csv',header=None,sep=',')
# for i in range(0,3):print(df[i][0]) # 循环提取
# a = np.array(df) # 转换成array
x1 = ai[:,[0]] # 取出第一列数据
```


``` python
# 二维图表
# https://www.runoob.com/numpy/numpy-matplotlib.html
import numpy as np 
from matplotlib import pyplot as plt 
x = np.arange(1,11)
y =  2  * x +  5
# 绘制一条斜线
# 默认不支持中文
plt.title("Matplotlib demo") # 图片标题
plt.xlabel("x axis caption") # 横轴说明
plt.ylabel("y axis caption") # 纵轴说明
plt.plot(x,y) # 开始绘图
plt.show()  #展示图片
```


``` python
# 三维散点图
# https://blog.csdn.net/qq_35170267/article/details/82881735 
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
# 构造数据
X1 = np.arange(-4, 4, 0.1);
X2 = np.random.rand(len(X1))*5;
Y = X1 + 3 * X2 + 3*np.random.randn(len(X1))
# 三维图示例
fig = plt.figure(figsize=(8, 6)) #设置图标大小，必须，4:3好像是个不错的比例
ax = fig.add_subplot(111, projection='3d') # 111是把画布分为1行、1列、第1个方格。
# 散点图
ax.scatter(X1, X2, Y, c='r') # 可以直接画更多的点
# 设置坐标轴的名称
ax.set_xlabel('X label'); ax.set_ylabel('Y label'); ax.set_zlabel('Z label');
plt.show() # 展示图片
```


``` python
# 在一张图上画多组点 
import numpy
import matplotlib.pyplot as plt
import pandas
df = pandas.read_csv('test.csv',header=None,sep=',') # 获取3维数组
ai = numpy.array(df) # 转成numpy数组
x1 = ai[:,[0]];x2 = ai[:,[1]];x3 = ai[:,[2]]; # 获取3列数据
ax = plt.figure().add_subplot(111,projection='3d') # 一张画布
ax.scatter(x1,x2,x3, c='r') # 这两步必须
ax.scatter(x2,x3,x1, c='b') # 这样就能只生成一张画布
plt.show() # 展示图片
```



``` python

```
库 | 介绍 | Win安装 | OSX安装
- | - | - | -
numpy | | pip install numpy |
pandas | | pip install pandas |
scipy | | pip install scipy |
matplotlib | | pip install matplotlib |
scikit-learn | | pip install –U scikit-learn |




## SKlearn
scikit-learn




### 数据集

sklearn.datasets

自带的小数据集（packaged dataset）：sklearn.datasets.load_<name>
可在线下载的数据集（Downloaded Dataset）：sklearn.datasets.fetch_<name>
计算机生成的数据集（Generated Dataset）：sklearn.datasets.make_<name>
svmlight/libsvm格式的数据集:sklearn.datasets.load_svmlight_file(...)
从买了data.org在线下载获取的数据集:sklearn.datasets.fetch_mldata(...)



**数据集导入**  

python导入csv格式数据全部方法总结  
**1.采用标准Python类库导入数据**  
Python提供了一个标准类库CSV，用来处理CSV文件。这个类库中的reader()函数用来读入CSV文件  
``` python
from csv import reader
import numpy as np 
#使用标准的Python类库导入csv数据
filename = 'pima_data.csv'
with open(filename,'rt') as raw_data:
	readers = reader(raw_data,delimiter=',')
	x = list(readers)
	data = np.array(x).astype('float')
	print(data.shape)
```

**2.采用NumPy导入数据**  
也可以使用Numpy的loadtxt()函数导入数据。使用这个函数处理的数据没有文件头，并且所有的数据结构是一样的，也就是说，数据类型是一样的。代码如下:
``` python
from numpy import loadtxt
#使用NumPy导入csv数据
filename = 'pima_data.csv'
with open(filename,'rt') as raw_data:
	data = loadtxt(raw_data,delimiter=',')
	print(data.shape)
```

**3.采用Pandas导入数据**  
通过Pandas来导入csv文件要使用pandas.read_csv()函数.这个函数的返回值是DataFrame,可以很方便的进行下一步处理。  

`pandas.read_csv(filepath, sep=',', delimiter=None, header='infer', names=None, index_col=None, usecols=None, squeeze=False, prefix=None, mangle_dupe_cols=True, dtype=None, engine=None, converters=None, true_values=None, false_values=None, skipinitialspace=False, skiprows=None, nrows=None, na_values=None, keep_default_na=True, na_filter=True, verbose=False, skip_blank_lines=True, parse_dates=False, infer_datetime_format=False, keep_date_col=False, date_parser=None, dayfirst=False, iterator=False, chunksize=None, compression='infer', thousands=None, decimal=b'.', lineterminator=None, quotechar='"', quoting=0, escapechar=None, comment=None, encoding=None, dialect=None, tupleize_cols=None, error_bad_lines=True, warn_bad_lines=True, skipfooter=0, doublequote=True, delim_whitespace=False, low_memory=True, memory_map=False, float_precision=None)`

**参数详解**  
filepath : 可以是URL，可用URL类型包括：http, ftp, s3和文件。对于多文件正在准备中

sep : str, default ‘,’  指定分隔符。如果不指定参数，则会尝试使用逗号分隔。分隔符长于一个字符并且不是‘\s+’,将使用python的语法分析器。并且忽略数据中的逗号。正则表达式例子：'\r\t'
 
delimiter : str, default None
定界符，备选分隔符（如果指定该参数，则sep参数失效）
 
delim_whitespace : boolean, default False.
指定空格(例如’ ‘或者’ ‘)是否作为分隔符使用，等效于设定sep='\s+'。如果这个参数设定为Ture那么delimiter 参数失效。
在新版本0.18.1支持
 
header : int or list of ints, default ‘infer’
指定行数用来作为列名，数据开始行数。如果文件中没有列名，则默认为0，否则设置为None。如果明确设定header=0 就会替换掉原来存在列名。header参数可以是一个list例如：[0,1,3]，这个list表示将文件中的这些行作为列标题（意味着每一列有多个标题），介于中间的行将被忽略掉（例如本例中的2；本例中的数据1,2,4行将被作为多级标题出现，第3行数据将被丢弃，dataframe的数据从第5行开始。）。
注意：如果skip_blank_lines=True 那么header参数忽略注释行和空行，所以header=0表示第一行数据而不是文件的第一行。
 
names : array-like, default None
用于结果的列名列表，如果数据文件中没有列标题行，就需要执行header=None。默认列表中不能出现重复，除非设定参数mangle_dupe_cols=True。
 
index_col : int or sequence or False, default None
用作行索引的列编号或者列名，如果给定一个序列则有多个行索引。
如果文件不规则，行尾有分隔符，则可以设定index_col=False 来是的pandas不适用第一列作为行索引。
 
usecols : array-like, default None
返回一个数据子集，该列表中的值必须可以对应到文件中的位置（数字可以对应到指定的列）或者是字符传为文件中的列名。例如：usecols有效参数可能是 [0,1,2]或者是 [‘foo’, ‘bar’, ‘baz’]。使用这个参数可以加快加载速度并降低内存消耗。
 
as_recarray : boolean, default False
不赞成使用：该参数会在未来版本移除。请使用pd.read_csv(...).to_records()替代。
返回一个Numpy的recarray来替代DataFrame。如果该参数设定为True。将会优先squeeze参数使用。并且行索引将不再可用，索引列也将被忽略。
 
squeeze : boolean, default False
如果文件值包含一列，则返回一个Series
 
prefix : str, default None
在没有列标题时，给列添加前缀。例如：添加‘X’ 成为 X0, X1, ...
 
mangle_dupe_cols : boolean, default True
重复的列，将‘X’...’X’表示为‘X.0’...’X.N’。如果设定为false则会将所有重名列覆盖。
 
dtype : Type name or dict of column -> type, default None
每列数据的数据类型。例如 {‘a’: np.float64, ‘b’: np.int32}
 
engine : {‘c’, ‘python’}, optional
Parser engine to use. The C engine is faster while the python engine is currently more feature-complete.
使用的分析引擎。可以选择C或者是python。C引擎快但是Python引擎功能更加完备。
 
converters : dict, default None
列转换函数的字典。key可以是列名或者列的序号。
 
true_values : list, default None
Values to consider as True
 
false_values : list, default None
Values to consider as False
 
skipinitialspace : boolean, default False
忽略分隔符后的空白（默认为False，即不忽略）.
 
skiprows : list-like or integer, default None
需要忽略的行数（从文件开始处算起），或需要跳过的行号列表（从0开始）。
 
skipfooter : int, default 0
从文件尾部开始忽略。 (c引擎不支持)
 
skip_footer : int, default 0
不推荐使用：建议使用skipfooter ，功能一样。
 
nrows : int, default None
需要读取的行数（从文件头开始算起）。
 
na_values : scalar, str, list-like, or dict, default None
一组用于替换NA/NaN的值。如果传参，需要制定特定列的空值。默认为‘1.#IND’, ‘1.#QNAN’, ‘N/A’, ‘NA’, ‘NULL’, ‘NaN’, ‘nan’`.
 
keep_default_na : bool, default True
如果指定na_values参数，并且keep_default_na=False，那么默认的NaN将被覆盖，否则添加。
 
na_filter : boolean, default True
是否检查丢失值（空字符串或者是空值）。对于大文件来说数据集中没有空值，设定na_filter=False可以提升读取速度。
 
verbose : boolean, default False
是否打印各种解析器的输出信息，例如：“非数值列中缺失值的数量”等。
 
skip_blank_lines : boolean, default True
如果为True，则跳过空行；否则记为NaN。
 
parse_dates : boolean or list of ints or names or list of lists or dict, default False
boolean. True -> 解析索引
list of ints or names. e.g. If [1, 2, 3] -> 解析1,2,3列的值作为独立的日期列；
list of lists. e.g. If [[1, 3]] -> 合并1,3列作为一个日期列使用
dict, e.g. {‘foo’ : [1, 3]} -> 将1,3列合并，并给合并后的列起名为"foo"
 
infer_datetime_format : boolean, default False
如果设定为True并且parse_dates 可用，那么pandas将尝试转换为日期类型，如果可以转换，转换方法并解析。在某些情况下会快5~10倍。
 
keep_date_col : boolean, default False
如果连接多列解析日期，则保持参与连接的列。默认为False。
 
date_parser : function, default None
用于解析日期的函数，默认使用dateutil.parser.parser来做转换。Pandas尝试使用三种不同的方式解析，如果遇到问题则使用下一种方式。
1.使用一个或者多个arrays（由parse_dates指定）作为参数；
2.连接指定多列字符串作为一个列作为参数；
3.每行调用一次date_parser函数来解析一个或者多个字符串（由parse_dates指定）作为参数。
 
dayfirst : boolean, default False
DD/MM格式的日期类型
 
iterator : boolean, default False
返回一个TextFileReader 对象，以便逐块处理文件。
 
chunksize : int, default None
文件块的大小， See IO Tools docs for more informationon iterator and chunksize.
 
compression : {‘infer’, ‘gzip’, ‘bz2’, ‘zip’, ‘xz’, None}, default ‘infer’
直接使用磁盘上的压缩文件。如果使用infer参数，则使用 gzip, bz2, zip或者解压文件名中以‘.gz’, ‘.bz2’, ‘.zip’, or ‘xz’这些为后缀的文件，否则不解压。如果使用zip，那么ZIP包中国必须只包含一个文件。设置为None则不解压。
新版本0.18.1版本支持zip和xz解压
 
thousands : str, default None
千分位分割符，如“，”或者“."
 
decimal : str, default ‘.’
字符中的小数点 (例如：欧洲数据使用’，‘).
 
float_precision : string, default None
Specifies which converter the C engine should use for floating-point values. The options are None for the ordinary converter, high for the high-precision converter, and round_trip for the round-trip converter.
指定
 
lineterminator : str (length 1), default None
行分割符，只在C解析器下使用。
 
quotechar : str (length 1), optional
引号，用作标识开始和解释的字符，引号内的分割符将被忽略。
 
quoting : int or csv.QUOTE_* instance, default 0
控制csv中的引号常量。可选 QUOTE_MINIMAL (0), QUOTE_ALL (1), QUOTE_NONNUMERIC (2) or QUOTE_NONE (3)
 
doublequote : boolean, default True
双引号，当单引号已经被定义，并且quoting 参数不是QUOTE_NONE的时候，使用双引号表示引号内的元素作为一个元素使用。
 
escapechar : str (length 1), default None
当quoting 为QUOTE_NONE时，指定一个字符使的不受分隔符限值。
 
comment : str, default None
标识着多余的行不被解析。如果该字符出现在行首，这一行将被全部忽略。这个参数只能是一个字符，空行（就像skip_blank_lines=True）注释行被header和skiprows忽略一样。例如如果指定comment='#' 解析‘#empty\na,b,c\n1,2,3’ 以header=0 那么返回结果将是以’a,b,c'作为header。
 
encoding : str, default None
指定字符集类型，通常指定为'utf-8'. List of Python standard encodings
 
dialect : str or csv.Dialect instance, default None
如果没有指定特定的语言，如果sep大于一个字符则忽略。具体查看csv.Dialect 文档
 
tupleize_cols : boolean, default False
Leave a list of tuples on columns as is (default is to convert to a Multi Index on the columns)
 
error_bad_lines : boolean, default True
如果一行包含太多的列，那么默认不会返回DataFrame ，如果设置成false，那么会将改行剔除（只能在C解析器下使用）。
 
warn_bad_lines : boolean, default True
如果error_bad_lines =False，并且warn_bad_lines =True 那么所有的“bad lines”将会被输出（只能在C解析器下使用）。
 
low_memory : boolean, default True
分块加载到内存，再低内存消耗中解析。但是可能出现类型混淆。确保类型不被混淆需要设置为False。或者使用dtype 参数指定类型。注意使用chunksize 或者iterator 参数分块读入会将整个文件读入到一个Dataframe，而忽略类型（只能在C解析器中有效）
 
buffer_lines : int, default None
不推荐使用，这个参数将会在未来版本移除，因为他的值在解析器中不推荐使用
 
compact_ints : boolean, default False
不推荐使用，这个参数将会在未来版本移除
如果设置compact_ints=True ，那么任何有整数类型构成的列将被按照最小的整数类型存储，是否有符号将取决于use_unsigned 参数
 
use_unsigned : boolean, default False
不推荐使用：这个参数将会在未来版本移除
如果整数列被压缩(i.e. compact_ints=True)，指定被压缩的列是有符号还是无符号的。
memory_map : boolean, default False
如果使用的文件在内存内，那么直接map文件使用。使用这种方式可以避免文件再次进行IO操作。


``` python
import csv
from pandas import read_csv

#使用Pandas导入csv数据
filename = 'pima_data.csv'
names = ['preg','plas','pres','skin','test','mass','pedi','age','class']
data = read_csv(filename,names = names)
print(data.shape)

# 下面是按照列属性读取的
d = read_csv(filename, usecols=['case', 'roi', 'eq. diam.','x loc.','y loc.','slice no.'])

# 这是表示读取前10行
d = read_csv(filename, usecols=['case', 'roi', 'eq. diam.','x loc.','y loc.','slice no.'],nrows=10)
```


### 降维算法

``` python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from matplotlib.ticker import NullFormatter
from sklearn import manifold, datasets
from sklearn.datasets import samples_generator
 
n_points = 1000 # X 是一个(1000, 3)的 2 维数据，color 是一个(1000,)的 1 维数据
X, color = samples_generator.make_s_curve(n_points, random_state=0)
n_neighbors = 10
n_components = 2
 
fig = plt.figure(figsize=(8, 8)) # 创建了一个 figure，标题为"Manifold Learning with 1000 points, 10 neighbors"
 
'''绘制 S 曲线的 3D 图像'''
ax = fig.add_subplot(211, projection='3d')
ax.scatter(X[:, 0], X[:, 1], X[:, 2], c=color, cmap=plt.cm.Spectral)
ax.view_init(4, -72)  # 初始化视角

t0 = time()
tsne = manifold.TSNE(n_components=n_components, init='pca', random_state=0)
Y = tsne.fit_transform(X)  # 转换后的输出
t1 = time()
ax = fig.add_subplot(2, 1, 2)
plt.scatter(Y[:, 0], Y[:, 1], c=color, cmap=plt.cm.Spectral)
plt.title("t-SNE (%.2g sec)" % (t1 - t0))   # 显示算法耗时,735G5测试时为3.9 sec。
ax.xaxis.set_major_formatter(NullFormatter())  # 设置标签显示格式为空
ax.yaxis.set_major_formatter(NullFormatter())

plt.show()  # 显示2副图像。
```

### model训练







### model导出（模型持久化）
在训练完 scikit-learn 模型之后，最好有一种方法来将模型持久化以备将来使用，而无需重新训练。  
以下部分为您提供了有关如何使用 pickle 来持久化模型的示例。  
在使用 pickle 序列化时，我们还将回顾一些安全性和可维护性方面的问题。  
pickle的另一种方法是使用相关项目中列出的模型导出工具之一将模型导出为另一种格式。  
与pickle不同，一旦导出，就不能恢复完整的Scikit-learn estimator对象，但是可以部署模型进行预测，通常可以使用支持开放模型交换格式的工具，如“ONNX”或“PMML”。

格式 | 说明 | 特点
- | - | -
csv | 文本表格数据 | 可以使用excel打开，易于阅读，CSV文件内容仅仅是一些用逗号分隔的原始字符串值。
json | 数据交换格式 | 可用于网页上这种数据传输，支持跨语言，存储一些结构化数据
pickle | 二进制文件 | python专属，读写效率高于一般文件，存储大小也更小



``` python
# pickle  
# pickle是二进制序列化格式，而JSON是人类可读的文本序列化格式，
# JSON是可互操作的，并且在Python生态系统之外广泛使用，而pickle是特定于Python的
from sklearn import svm
from sklearn import datasets
import pickle #pickle模块

clf = svm.SVC()
iris = datasets.load_iris()
X, y = iris.data, iris.target
clf.fit(X,y)
#保存Model(注:save文件夹要预先建立，否则会报错)
with open('save/clf.pickle', 'wb') as f:
    pickle.dump(clf, f)

#读取Model
with open('save/clf.pickle', 'rb') as f:
    clf2 = pickle.load(f)
    #测试读取后的Model
    print(clf2.predict(X[0:1]))
```

将对象转换为可通过网络传输或可以存储到本地磁盘的数据格式（如：XML、JSON或特定格式的字节串）的过程称为序列化；反之，则称为反序列化。  
参考链接：https://www.cnblogs.com/gcgc/p/10973418.html

python | json
- | -
dict | object
list/tuple | array
str/unicode | string
int/long/float | number
True/False | true/false
None | null





``` python
# 将数组编码为JSON格式数据
import json
data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]
jsons = json.dumps(data)
print (jsons) # [{"a": 1, "b": 2, "c": 3, "d": 4, "e": 5}]
```


``` python
# 解码 JSON 对象：
import json
jsonData = '{"a":1,"b":2,"c":3,"d":4,"e":5}';
text = json.loads(jsonData)
print (text) # {u'a': 1, u'c': 3, u'b': 2, u'e': 5, u'd': 4}
```

``` python
import json
import pickle
 #json dumps序列化方法  loads反序列化方法
dic = {'k1':'v1'}
print(type(dic),dic)  #序列化  <class 'dict'> {'k1': 'v1'}
str_d =json.dumps(dic)
print(type(str_d),str_d) #  <class 'str'> {"k1": "v1"} #注 json 转换成str时 单引号都会变成双引号
dic_d = json.loads(str_d) #反序列化
print(type(dic_d),dic_d)

#json dump load   序列化 --到文件
dic = {1:'a',2:'b'}
f=open ('fff','w',encoding='utf-8')
json.dump(dic,f)
f.close()

#反序列化
f = open('fff')
res = json.load()

#pick模块的使用方法几乎和json一致，唯一区别就是pickle 使用字节集读写，需要注意。
```















### model加载




### SVM
支持向量机(support vector machine)是一种分类算法，根据输入的数据不同可做不同的模型（输入标签为连续值则做回归，输入标签为分类值则做分类SVC）。  
通过寻求结构化风险最小来提高学习机泛化能力，实现经验风险和置信范围的最小化，从而达到在统计样本量较少的情况下，亦能获得良好统计规律的目的。  
通俗来讲，它是一种二类分类模型，其基本模型定义为特征空间上的间隔最大的线性分类器，即支持向量机的学习策略便是间隔最大化，最终可转化为一个凸二次规划问题的求解。

一阶多项式核函数的拟合效果更好，消耗的时间也更久，一阶多项式计算代价比高斯核函数的SVC运算事件多出了好多倍。


#### 参数说明

学习器模型中一般有两个参数：已知参数（可以从数据中学习估计得到），超参数（无法从数据中估计，只能靠人的经验进行指定） 

参数 | 默认值 | 说明
 - | - | - 
C | 1.0 | C-SVC 分类错误项的惩罚参数
kernel | 'rbf' | 核函数，'linear','poly', 'rbf'
degree | 3 | 多项式poly函数的维度，选择其他核函数时会被忽略。
gamma | 'auto_deprecated' | 'rbf','poly'和'sigmoid'的核函数参数，则会选择1/n_features
coef0 | 0.0 | 核函数的常数项,对于'poly'和'sigmoid'有用。
probability | False | 是否采用概率估计
shrinking | True | 是否采用shrinking heuristic方法，
tol | 0.001 | 停止训练的误差值大小
cache_size | 200 | 核函数cache缓存大小
class_weight | None | 类别的权重，字典形式传递。设置第几类的参数C为weight*C(C-SVC中的C)
verbose | False | 允许冗余输出
max_iter | -1 | 最大迭代次数。-1为无限制
decision_function_shape | 'ovr' | 'ovo','ovr' or None
random_state | None | 数据洗牌时的种子值，int值

**C**  
C越大，相当于惩罚松弛变量，希望松弛变量接近0，即对误分类的惩罚增大，趋向于对训练集全分对的情况，这样对训练集测试时准确率很高，但泛化能力弱。C值小，对误分类的惩罚减小，允许容错，将他们当成噪声点，泛化能力较强。  
C越大，一旦分类错误，惩罚越严重，C越大，越容易过拟合，越容易欠拟合。  

**kernel**  
liner – 线性核函数：u'v
poly – 多项式核函数：(gamma*u'*v + coef0)^degree
rbf – RBF高斯核函数：exp(-gamma|u-v|^2)

线性核函数：
高斯核函数：训练开销大、时间长，针对数据维度大于数据量的数据（自然语义处理），
多项核函数：依靠升维使得原本线性不可分的数据线性可分；


**二元分类**  
``` python
from sklearn.svm import SVC  # 因为只用SVC  # from sklearn import svm  # svm.SVC
clf = SVC()  # 可以缺省，也有其他参数选项
clf.fit(X_train, y_train)  # X是数据集，Y是分类集 [n_samples, n_features]

# 训练好后，可以进行预测
clf.predict([[2., 2.]])  # >array([1])

# 获得支持向量
clf.support_vectors_  # array([[ 0.,  0.],[ 1.,  1.]])
# 获得支持向量的索引
clf.support_  # array([0, 1]...)
# 为每一个类别获得支持向量的数量
clf.n_support_  # array([1, 1]...)
```

多元分类  
``` python
X = [[0], [1], [2], [3]]
Y = [0, 1, 2, 3]
clf = svm.SVC(gamma='scale', decision_function_shape='ovo')
clf.fit(X, Y)
'''
SVC(C=1.0, cache_size=200, class_weight=None, coef0=0.0,
 decision_function_shape='ovo', degree=3, gamma='scale', kernel='rbf',
 max_iter=-1, probability=False, random_state=None, shrinking=True,
 tol=0.001, verbose=False)
 '''

dec = clf.decision_function([[1]])
dec.shape[1] # 4 classes: 4*3/2 = 6
# 6

clf.decision_function_shape = "ovr"
dec = clf.decision_function([[1]])
dec.shape[1] # 4 classes
# 4
```


``` python
import numpy
from pandas import read_csv
filename = 'test.csv'
data = read_csv(filename, header=None, ) # 按行提取csv中数据
list=data.values.tolist() # 数据转数组
a=numpy.array(list) # 二维数组转矩阵
b=a.transpose() # 矩阵转置
c=b.tolist() # 矩阵转数组
print(c)
```


#### 参数调优


**GridSearchCV**  
GridSearchCV官方网址：http://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html  
自动调参，只要把参数输进去，就能给出最优化的结果和参数。但是这个方法适合于小数据集，一旦数据的量级上去了，很难得出结果。这个时候就是需要动脑筋了。数据量比较大的时候可以使用一个快速调优的方法——坐标下降。它其实是一种贪心算法：拿当前对模型影响最大的参数调优，直到最优化；再拿下一个影响最大的参数调优，如此下去，直到所有的参数调整完毕。这个方法的缺点就是可能会调到局部最优而不是全局最优，但是省时间省力。  
后续可以再拿bagging再优化。回到sklearn里面的GridSearchCV，GridSearchCV用于系统地遍历多种参数组合，通过交叉验证确定最佳效果参数。

`from sklearn.model_selection import GridSearchCV`

**默认参数**  
class sklearn.model_selection.GridSearchCV(estimator, param_grid, scoring=None, fit_params=None, n_jobs=1, iid=True, refit=True, cv=None, verbose=0, pre_dispatch=‘2*n_jobs’, error_score=’raise’, return_train_score=’warn’)

（1）estimator
选择使用的分类器，并且传入除需要确定最佳的参数之外的其他参数。每一个分类器都需要一个scoring参数，或者score方法：estimator=RandomForestClassifier(min_samples_split=100,min_samples_leaf=20,max_depth=8,max_features='sqrt',random_state=10),
（2）param_grid
需要最优化的参数的取值，值为字典或者列表，例如：param_grid =param_test1，param_test1 = {'n_estimators':range(10,71,10)}。
（3）scoring=None
模型评价标准，默认None,这时需要使用score函数；或者如scoring='roc_auc'，根据所选模型不同，评价准则不同。字符串（函数名），或是可调用对象，需要其函数签名形如：scorer(estimator, X, y)；如果是None，则使用estimator的误差估计函数。具体值的选取看本篇第三节内容。
（4）fit_params=None
（5）n_jobs=1
n_jobs: 并行数。  -1：跟CPU核数一致, 1:默认值
（6）iid=True
iid:默认True,为True时，默认为各个样本fold概率分布一致，误差估计为所有样本之和，而非各个fold的平均。
（7）refit=True
默认为True,程序将会以交叉验证训练集得到的最佳参数，重新对所有可用的训练集与开发集进行，作为最终用于性能评估的最佳模型参数。即在搜索参数结束后，用最佳参数结果再次fit一遍全部数据集。
（8）cv=None
交叉验证参数，默认None，使用三折交叉验证。指定fold数量，默认为3，也可以是yield训练/测试数据的生成器。
（9）verbose=0, scoring=None
verbose：日志冗长度，int：冗长度，0：不输出训练过程，1：偶尔输出，>1：对每个子模型都输出。
（10）pre_dispatch='2*n_jobs'
指定总共分发的并行任务数。当n_jobs大于1时，数据将在每个运行点进行复制，这可能导致OOM，而设置pre_dispatch参数，则可以预先划分总共的job数量，使数据最多被复制pre_dispatch次
（11）error_score='raise'
（12）return_train_score='warn'
如果“False”，cv_results_属性将不包括训练分数

**示例代码**  
比较基础的示例代码  
``` python
import pandas as pd
from sklearn import svm, datasets
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import classification_report

iris = datasets.load_iris()
parameters = {'kernel':('linear', 'rbf'), 'C':[1, 2, 4], 'gamma':[0.125, 0.25, 0.5 ,1, 2, 4]}
svr = svm.SVC()
clf = GridSearchCV(svr, parameters, n_jobs=-1)
clf.fit(iris.data, iris.target)
cv_result = pd.DataFrame.from_dict(clf.cv_results_)
with open('cv_result.csv','w') as f:
    cv_result.to_csv(f)
    
print('The parameters of the best model are: ')
print(clf.best_params_)

y_pred = clf.predict(iris.data)
print(classification_report(y_true=iris.target, y_pred=y_pred))

''' 运行结果
The parameters of the best model are: 
{'C': 4, 'gamma': 0.125, 'kernel': 'rbf'}
              precision    recall  f1-score   support

           0       1.00      1.00      1.00        50
           1       1.00      0.98      0.99        50
           2       0.98      1.00      0.99        50

    accuracy                           0.99       150
   macro avg       0.99      0.99      0.99       150
weighted avg       0.99      0.99      0.99       150
'''
```












