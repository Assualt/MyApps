#编码   utf-8



ord('字符')  把字符串的utf-8d的编码显示出来

#eg  ord('A')      65

chr('字符utf-8编码')  把utf-8的编码还原成字符

#eg chr('65')     'A'


'字符串'.encode('编码规则') 把相应的字符串转化成对应的utf-8编码

#eg  
'中文'.encode('utf-8')   b'\xe4\xb8\xad\xe6\x96\x87'
'abc'.encode('ascii')    b'abc

#注意
'abc'为字符串 为str型  
b'abc'为字节 为byte型
#内容显示得和前者一样，但bytes的每个字符都只占用一个字节。纯英文的str可以用ASCII编码为bytes，内容是一样的，含有中文的str可以用UTF-8编码为bytes。含有中文的str无法用ASCII编码，因为中文编码的范围超过了ASCII编码的范围，Python会报错。在bytes中，无法显示为ASCII字符的字节，用\x##显示。

#相反也有decode(解码操作)

'编码结果'.decode('解码格式')

#eg
>>>b'ABC'.decode('ascii')
>>>'ABC'
>>>b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
>>>'中文


#顺序数组 List   各个下标的值类型可以不一样

#len(字符串数组) 求字符串数组长度

#顺序访问元素下标从0开始 到len()-1结束  
#逆序访问元素时下标为负 最后一个为-1，倒数第二个为-2，依次类推

#eg


>>>classmate['str1','str2','str3'....'strn']
>>>len(classmate)=n
>>>classmate[len(classmate)-1]=strn
>>>classmate[-1]=strn  
   

#字符串的插入  

#str.insert(index,value) 
 index:插入位置 
 value:插入的值

#eg:
>>>classmate=['str1','str2','str3']
>>>classmate.insert(1,'str4')
>>> print(classmate)
['str1', 'str4', 'str2', 'str3']

#字符串的删除

#str.pop() 删除list 末尾的值

#eg:
>>> print(classmate)
['str1', 'str4', 'str2', 'str3']
>>> classmate.pop()
'str3'
>>> print(classmate)
['str1', 'str4', 'str2']

#str.pop(i) 删除指定索引的值

#eg:

>>> print(classmate)
['str1', 'str4', 'str2']
>>> classmate.pop(1)
'str4'
>>> print(classmate)
['str1', 'str2']

#str.appen(vlaue) 追加在末尾
>>> print(a)
[1, 2, 3, 4, 5, 6]
>>> a.append(7)
>>> print(a)
[1, 2, 3, 4, 5, 6, 7]

#修改指定索引的值 直接赋值即可

>>> print(classmate)
['str1', 'str2']
>>> classmate[0]='str0'
>>> print(classmate)
['str0', 'str2']

#list中可以有另一个list 既可以嵌套

#eg:
>>> a=[1,2,3,4,5,6]
>>> b=[1,2,3,a,5,6]
>>> len(a)
6
>>> len(b)
6
>>> b[3][1]   //访问list中的list
2

#tuple 元组 一旦初始化不能更改 其他操作与list相似
#各个下标的值类型可以不一样
>>>a=(1,2,3,4,5,6)
>>> a
(1, 2, 3, 4, 5, 6)
>>> len(a)
6
>>> b=(1,)
>>> b


#条件语句

if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
    <执行3>
else:
    <执行4>

#输入值默认为字符串类型，如果是数字，用int()强转即可

#循环语句

#Python的循环有两种，一种是for...in循环，依次把list或tuple中的每个元素迭代出来，看例子：

#eg:迭代器
>>>names = ['Michael', 'Bob', 'Tracy']
>>>for name in names:
...print(name)

>>>sum = 0
>>>for x in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]:
...sum = sum + x
>>>print(sum)

#循环 while

while 条件：
    语句1
    语句2
    ...
其他语句1
...

#eg
sum=0
n=99
while (n>0):
    sum=sum+n
    n=n-1    
print(sum)

>>>4950

#break

在循环中，break语句可以提前退出循环

#continue

再循环中，continue语句可以跳出本次循环

#dict

Python内置了字典：dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储，具有极快的查找速度。

给定一个名字，要查找对应的成绩，就先要在names中找到对应的位置，再从scores取出对应的成绩，list越长，耗时越长。

如果用dict实现，只需要一个“名字”-“成绩”的对照表，直接根据名字查找成绩，无论这个表有多大，查找速度都不会变慢。

#你可以猜到，这种key-value存储方式，在放进去的时候，必须根据key算出value的存放位置，这样，取的时候才能根据key直接拿到value。
#如果key不存在，dict报错

#通过dict提供的get方法，如果key不存在，可以返回None，或者自己指定的value：

#要删除一个key，用pop(key)方法，对应的value也会从dict中删除：

>>> d={'houxin':95,'zhangjie':80,'yy':40}
>>> d['houxin']
95
>>> d['houxin']=100
>>> print(d)
{'zhangjie': 80, 'yy': 40, 'houxin': 100}
>>> d.get('yy')
40
>>> d.pop('yy')
40
>>> print(d)
{'zhangjie': 80, 'houxin': 100}
 

###请务必注意，dict内部存放的顺序和key放入的顺序是没有关系的。

和list比较，dict有以下几个特点：

#查找和插入的速度极快，不会随着key的增加而变慢；
#需要占用大量的内存，内存浪费多。
#而list相反：

#查找和插入的时间随着元素的增加而增加；
#占用空间小，浪费内存很少。
#所以，dict是用空间来换取时间的一种方法。

#dict可以用在需要高速查找的很多地方，在Python代码中几乎无处不??在，正确使用dict非常重要，需要牢记的第一条就是dict的key必须是不可变对象。

这是因为dict根据key来计算value的存储位置，如果每次计算相同的key得出的结果不同，那dict内部就完全混乱了。这个通过key计算位置的算法称为哈希算法（Hash）。

要保证hash的正确性，作为key的对象就不能变。在Python中，字符串、整数等都是不可变的，因此，可以放心地作为key。而list是可变的，就不能作为key：

#Set也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。 有序

>>> s=set([1,2,3])
>>> s
{1, 2, 3}
>>> s=set([1,2,3,2,3,4,5,1,23])
>>> s
{1, 2, 3, 4, 5, 23}

#add(element)

>>> s.add(123)
>>> s
{1, 2, 3, 4, 5, 23, 123}
>>>s.add(1)
>>> s
{1, 2, 3, 4, 5, 23, 123}

#remove(elements)
{1, 2, 3, 4, 5, 23, 123}
>>> s.remove(1)
>>> s
{2, 3, 4, 5, 23, 123}
>>> s.remove(1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 1

#两个 set可以看成集合 可进行 交并补集合运算

#不可变对象

#str是不变对象，而list是可变对象
>>> a = ['c', 'b', 'a']
>>> a.sort()
>>> a
['a', 'b', 'c']

>>> a = 'abc'
>>> a.replace('a', 'A')
'Abc'
>>> a
'abc'

#调用函数   help(funcName)查看 类似于 man

1.abs(value)//绝对值
2.max(value,value1,value2....)//最大值
3.int(value) float(vlaue) str(value) bool(value)//强转
4.函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”：
>>>a=abs
>>>a(-1)
1

#自定义函数  
在Python中，定义一个函数要使用def语句，依次写出函数名、括号、括号中的参数和冒号:，然后，在缩进块中编写函数体，函数的返回值用return语句返回。

#请注意，函数体内部的语句在执行时，一旦执行到return时，函数就执行完毕，并将结果返回。因此，函数内部通过条件判断和循环可以实现非常复杂的逻辑。

如果没有return语句，函数执行完毕后也会返回结果，只是结果为None。

return None可以简写为return。

def funcName(value,value1,.....):
    函数体
    return ret
//def: 定义函数关键字
//value:函数参数列表
//ret:返回值

#如果你已经把my_abs()的函数定义保存为abstest.py文件了，那么，可以在该文件的当前目录下启动Python解释器，用from abstest import my_abs来导入my_abs()函数，注意abstest是文件名（不含.py扩展名）：

#空函数

如果想定义一个什么事也不做的空函数，可以用pass语句：

def pop():
    pass

#返回多个值


#eg
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny

#import math语句表示导入math包，并允许后续代码引用math包里的sin、cos等函数。

#然后，我们就可以同时获得返回值：

>>> x, y = move(100, 100, 60, math.pi / 6)
>>> print(x, y)
151.96152422706632 70.0

#返回值是一个tuple！但是，在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。


#传递参数 关键字参数
**kw 类似于c中的字符串数组
def person(name, age, **kw):
    print('name:', name, 'age:', age, 'other:', kw)

>>> person('Michael', 30)
name: Michael age: 30 other: {}

#也可以传入任意个数的关键字参数：

>>> person('Bob', 35, city='Beijing')
name: Bob age: 35 other: {'city': 'Beijing'}
>>> person('Adam', 45, gender='M', job='Engineer')
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}

#当然，上面复杂的调用可以用简化的写法：

>>> extra = {'city': 'Beijing', 'job': 'Engineer'}
>>> person('Jack', 24, **extra)
name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}

**extra表示把extra这个dict的所有key-value用关键字参数传入到函数的**kw参数，kw将获得一个dict，注意kw获得的dict是extra的一份拷贝，对kw的改动不会影响到函数外的extra。

#命名关键字参数

对于关键字参数，函数的调用者可以传入任意不受限制的关键字参数。至于到底传入了哪些，就需要在函数内部通过kw检查。

仍以person()函数为例，我们希望检查是否有city和job参数：

def person(name, age, **kw):
    if 'city' in kw:
        # 有city参数
        pass
    if 'job' in kw:
        # 有job参数
        pass
    print('name:', name, 'age:', age, 'other:', kw)

#切片
对这种经常取指定索引范围的操作，用循环十分繁琐，因此，Python提供了切片（Slice）操作符，能大大简化这种操作。

对应上面的问题，取前3个元素，用一行代码就可以完成切片：

>>> L = ['Michael', 'Sarah', 'Tracy', 'Bob', 'Jack']
>>> L[0:3]
['Michael', 'Sarah', 'Tracy']

L[0:3]表示，从索引0开始取，直到索引3为止，但不包括索引3。即索引0，1，2，正好是3个元素。

如果第一个索引是0，还可以省略：

>>> L[:3]
['Michael', 'Sarah', 'Tracy']
也可以从索引1开始，取出2个元素出来：

>>> L[1:3]
['Sarah', 'Tracy']

类似的，既然Python支持L[-1]取倒数第一个元素，那么它同样支持倒数切片，试试：

>>> L[-2:]
['Bob', 'Jack']
>>> L[-2:-1]
['Bob']

记住倒数第一个元素的索引是-1。


#列表生成式

>>> list(range(1, 11))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for循环后面还可以加上if判断，这样我们就可以筛选出仅偶数的平方：

>>> [x * x for x in range(1, 11) if x % 2 == 0]
[4, 16, 36, 64, 100]

运用列表生成式，可以写出非常简洁的代码。例如，列出当前目录下的所有文件和目录名，可以通过一行代码实现：

>>> import os # 导入os模块，模块的概念后面讲到
>>> [d for d in os.listdir('.')] # os.listdir可以列出文件和目录
['.emacs.d', '.ssh', '.Trash', 'Adlm', 'Applications', 'Desktop', 'Documents', 'Downloads', 'Library', 'Movies', 'Music', 'Pictures', 'Public', 'VirtualBox VMs', 'Workspace', 'XCode']
    

#isinstance(value,type)判断value是否为type类型

#生成器
如果列表元素可以按照某种算法推算出来，那我们是否可以在循环的过程中不断推算出后续的元素呢？这样就不必创建完整的list，从而节省大量的空间。在Python中，这种一边循环一边计算的机制，称为生成器：generator

>>> g = (x * x for x in range(10))



#map

map(func,[])  #func 指针函数 []参数列表

def f(x):
    return x*x

>>>a=[1,2,3,4]

>>>map(f,a)
[1,4,9,16]

#把这个list所有数字转为字符串：

>>> list(map(str, [1, 2, 3, 4, 5, 6, 7, 8, 9]))
['1', '2', '3', '4', '5', '6', '7', '8', '9']

#reduce把一个函数作用在一个序列[x1, x2, x3, ...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算，其效果就是：

reduce(f, [x1, x2, x3, x4]) = f(f(f(x1,x2),x3),x4)

reduce(sum,[1,2,3,4])=((1+2)+3)+4=10=sum(sum(sum(1,2),3),4)

#Python内建的filter()函数用于过滤序列。

#和map()类似，filter()也接收一个函数和一个序列。和map()不同的是，filter()把传入的函数依次作用于每个元素，然后根据返回值是True还是False决定保留还是丢弃该元素。

例如，在一个list中，删掉偶数，只保留奇数，可以这么写：

>>>def is_odd(n):
        return n % 2 == 1

>>>list(filter(is_odd, [1, 2, 4, 5, 6, 9, 10, 15]))
[1, 5, 9, 15]

#sorted(排序)Python内置的sorted()函数就可以对list进行排序

>>> sorted([10,9,8,7])
[7, 8, 9, 10]

sorted(iterable, key=None, reverse=False)
    Return a new list containing all items from the iterable in ascending or
der.

    A custom key function can be supplied to customise the sort order, and t
he
    reverse flag can be set to request the result in descending order.

>>>sorted([-91,91,222,3],key=abs)
[3, -91, 91, 222]

#默认情况下，对字符串排序，是按照ASCII的大小比较的，由于'Z' < 'a'，结果，大写字母Z会排在小写字母a的前面。
>>> sorted(['bob', 'about', 'Zoo', 'Credit'])
['Credit', 'Zoo', 'about', 'bob']
#按首字母索引排序，不区分大小写 key=str.lower
>>> sorted(['bob', 'about', 'Zoo', 'Credit'],key=str.lower)
['about', 'bob', 'Credit', 'Zoo']
#逆序  reverse=True
>>> sorted(['bob', 'about', 'Zoo', 'Credit'],key=str.lower,reverse=True)
['Zoo', 'Credit', 'bob', 'about']


#函数作为返回值

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回。

我们来实现一个可变参数的求和。通常情况下，求和的函数是这样定义的

def lazy_sum(*args):
    def sum():
        ax = 0
        for n in args:
            ax = ax + n
        return ax
    return sum

#闭包

#注意到返回的函数在其定义内部引用了局部变量args，所以，当一个函数返回了一个函数后，其内部的局部变量还被新函数引用，所以，闭包用起来简单，实现起来可不容易。

#另一个需要注意的问题是，返回的函数并没有立刻执行，而是直到调用了f()才执行。我们来看一个例子：

def count():
    fs = []
    for i in range(1, 4):
        def f():
             return i*i
        fs.append(f)
    return fs

f1, f2, f3 = count()

>>>f1()
9
>>>f2()
9
>>>f3()
9   
全部都是9！原因就在于返回的函数引用了变量i，但它并非立刻执行。等到3个函数都返回时，它们所引用的变量i已经变成了3，因此最终结果为9。

#匿名函数

当我们在传入函数时，有些时候，不需要显式地定义函数，直接传入匿名函数更方便。

在Python中，对匿名函数提供了有限支持。还是以map()函数为例，计算f(x)=x2时，除了定义一个f(x)的函数外，还可以直接传入匿名函数：

>>> list(map(lambda x: x * x, [1, 2, 3, 4, 5, 6, 7, 8, 9]))
[1, 4, 9, 16, 25, 36, 49, 64, 81]



#class

#由于类可以起到模板的作用，因此，可以在创建实例的时候，把一些我们认为必须绑定的属性强制填写进去。通过定义一个特殊的__init__方法，在创建实例的时候，就把name，score等属性绑上去：

class Student(object):
    def __init__ (self,xx1,xx2....):
        self.x1=xx1
        self.x2==xx2
        .....
    pass

#注意到__init__方法的第一个参数永远是self，表示创建的实例本身，因此，在__init__方法内部，就可以把各种属性绑定到self，因为self就指向创建的实例本身。

#有了__init__方法，在创建实例的时候，就不能传入空的参数了，必须传入与__init__方法匹配的参数，但self不需要传，Python解释器自己会把实例变量传进去：

>>>类中把属性前面加入‘__’变成私有成员 如 __name就位私有成员
>>>外部无法直接访问私有成员

需要注意的是，在Python中，变量名类似__xxx__的，也就是以双下划线开头，并且以双下划线结尾的，是特殊变量，特殊变量是可以直接访问的，不是private变量，所以，不能用__name__、__score__这样的变量名。

#我们来判断对象类型，使用type()函数：

>>>type(123)
<class 'int'>

#路径  dir(dirname)

#如果要获得一个对象的所有属性和方法，可以使用dir()函数，它返回一个包含字符串的list，比如，获得一个str对象的所有属性和方法：

>>>dir('abc')
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']

#使用__slots__

但是，如果我们想要限制实例的属性怎么办？比如，只允许对Student实例添加name和age属性。

为了达到限制的目的，Python允许在定义class的时候，定义一个特殊的__slots__变量，来限制该class实例能添加的属性：

#使用@property 把方法变成属性直接赋值