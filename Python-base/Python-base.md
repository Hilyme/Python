
Day01

一、软件开发的常识

1.DOS命令

cd	进入指定目录

cd..	返回上一级目录

    cd..\..	向上退回两级目录

切换盘符		盘符名称：

    d:

dir	列出当前文件夹下所有的子文件夹和文件

md	创建目录

copy	初始路径	目标路径

    copy a\1.txt b\2.txt

move	初始路径	目标路径

rd/s/p	同时删除文件夹和其下所有子文件（慎用）

	/S 表示删除该目录下所有遍历的子目录和文件

	/Q 删除目录时不提示确认，直接删除

rd	删除指定目录

二、python概述

1.python简介

java：	1995年

python：	1991年

2.python的特点

a.是一种解释型语言【开发过程中没有了编译的环节】

b.是交互式的语言【可以直接互动执行python程序】

c.是面向对象的语言

d.是跨平台语言【可运行于不同的操作系统】

3.python的优缺点

3.1优点

a.可移植性

b.可扩展性，可嵌入性

c.标准库

d.数据库

e.GUI编程【图形化编程】

3.2缺点

a.运行速度慢

b.代码不能加密

三、数据的存储

1.内存

1.1数据是存储在计算机的内存中的

1.2内存是和cpu进行沟通的

1.3单位：

	计算机中表示数据的最小单位：bit---b，比特位

	计算机中处理数据的最小单位：字节 【Byte---B】

	1B=8b

2.进制

进制就是进制位，一种进位的方法

3.进制转换

a.十进制---》二进制

转换原理：

	对于小数：乘以2取整，直到结果为1

b.二进制----》八进制

转换原理：

	每三位二进制按权展开相加得到一位八进制，从右向左进行分组，每三位为一组，不足时需要进行补0操作

4.原码反码补码

正数的原码反码补码相同

负数：

	原码：符号位为1，其它位与其对应正数一致

	反码：将原码除符号位外的其余部分按位取反

	补码：反码+1

	同一数字的正负数只有其补码相加才为0，第九位的1表示溢出

结论：计算机中处理数据采用的是补码形式

5.编码

ASCII码：0---》48

		a---》97

		A---》65

Unicode，可以支持中文

四、开发前的准备工作

1.python的版本

- [ ] - [ ] python2.X，python3.X。高版本不能向下兼容	
      - [ ] 2.环境安装

配置环境变量的目的：为了可以在任意的目录下随意访问python命令



Day02

一、Python的编码规范

1.分号：尽量不加分号

2.尽量不要多条语句出现在同一行代码中

3.括号：不能省略必要的括号

4.缩进：不是tab键【主要用于区分代码块】

5.尽量避免在对应的文件名中出现中文和空格

二、注释

注释是编写程序是，给代码做的一些解释性的说明

特点：程序不会执行

优点：能够提高代码的可读性，便于以后的修改和阅读

分类：

	单行注释：#

	多行注释【块注释】：“”“ ”“”	

			  		       ‘’‘  ’‘’

注意：中文出现在代码中，要么是字符串，要么是注释

三、关键字和标识符

1.关键字【保留字】

在python中，已经被系统赋予了特殊含义的英文单词

举例：True、False、break、continue、import、form、finally等

注意：字母的大小写

2.标识符

2.1什么是标识符

在python程序中自定义的一些英文单词

2.2定义合法标识符的规则

硬性规则：

	a.只能有数字、字母、下划线组成

	b.开头不能是数字

	c.不能是python的关键字

	d.不能出现空格

	e.严格区分大小写

非硬性规则：

	f.尽量做到见名知意，具有描述性

	g.用小写字母拼写，不同单词之间使用下划线分隔

		【也可用驼峰命名法则】

2.3作用

主要用于给变量、函数、类等进行命名

四、变量的使用

1.Python中的数据类型

通过不同的数据类型来表示不同的数据

	Number：数字类型【整型，浮点型，复数】

	String：字符串

	Boolean：布尔值【True、False】

	None：空值

	list：列表

	tuple：元组

	dict：字典

	set：集合

基础数据类型：

	整型：python中的整型可以处理任意大小的整数【Python3.x中只有int一种类型】

而且支持二进制

	浮点型：就是小数，之所以称为浮点数，是因为用科学计数法，一个小数的小数点的位置是浮动的，可以改变的

	字符串型：使用单引号或双引号括起来的任意文本

	布尔型：True和False，注意区分大小写

	复数型：形如3+5j的格式，在数学上为3+5i

2.常量

程序在运行的过程中，值永远不会发生改变

3.变量

3.1概述

程序在运行中，值可以随时发生改变的标识符

变量的作用：本身就是一种存储数据的载体

3.2定义

格式：变量名=初始值【整型局部变量定义与数学上的格式一致】

	变量名：实质上是标识符，也被称为引用

	初始值：给变量第一次赋予的值，决定了当前变量的数据类型

3.3内存中的变量

age=18

需要在内存中开辟一块空间，将类型确定，但值不确定的数据存储到这块空间中

变量的作用：为了存储程序运行过程中的一些中间结果，暂时存储起来

结论：在python中，数据通过定义变量都会有指向一弄，如果没有引用指向的话，则会变成垃圾等待系统的垃圾回收机制【GC】回收，会被销毁【python中所有的基本数据类型变量也是对象，一切皆对象】

3.4删除变量

当变量被删除之后，变量将无法使用，相当于未被定义

格式：del 变量名

4.变量的类型转换

int(xxx):转换为整型

float(xxx):转换为浮点型

str(xxx):转换为字符串

chr(xxx):转换为字符【character】

ord(xxx):将字符串转换为对应的编码

type(xxx):查看变量的类型

id(xxx):查看变量的地址

五、输入输出

1.print()

输出

作用：可以将信息打印到控制台上

特点：可以使用占位符格式化输出字符串

print("a + b = ",a + b)

print("%d + %d = %d"%(a,b,a+b))

2.input()

输入

作用：

语法：name = input("姓名：")

注意：通过input()获取的数据全部都是字符串

六、运算符和表达式

1.表达式

就是由操作数和运算符组合起来的语句

作用：可以进行求值

2.运算符

2.1算术运算符

    + - * /【除完为浮点型】 %  **【求幂】 //【取整】

进行相应的数学运算，不会改变变量原来的值

2.2赋值运算符

格式：变量=值【表达式】

作用：给变量进行赋值

复合赋值运算符：+=  -=  *=  /= ……

2.3关系运算符【条件运算符，比较运算符】

==  !=  <  >  <=  >=

注意：对应的关系运算符计算的结果为布尔值

2.4位运算符

&【按位与】  |【按位或】

^【按位异或】  ~【按位取反】

<<【左移】  >>【右移】

七、if语句

1.概念

如果

属于一个条件控制语句

2.使用

2.1简单if语句

语法：

	if 表达式:

		语句

说明：也称单分支，要么执行，要么不执行

何为真假？

	假：False	0	0.0	None	''	""

2.2if-else语句

语法：

	if 表达式：

		语句1

	else：

		语句2

说明：也称双分支

2.3if-elif语句

语法：

	if 表达式1：

		语句1

	elif 表达式2：

		语句2

	……

	else：

		语句n

说明：也称多分支【实现了多选一的操作】

2.4嵌套if语句

语法：

	if 表达式1：

		if 表达式2：

			语句

Day03

一、运算符和表达式二

1.逻辑运算符

作用：主要用于进行逻辑运算，计算的结果为布尔值

运算符：

	逻辑与：and	【&】

	逻辑或：or【|】

	逻辑非：not【!】

短路原则：

	出现的时机：逻辑运算符and/or一旦不止一个【只有一个不会执行短路原则】，其运算的核心就是短路原则

2.成员运算符

in：如果在指定的列表中找到指定的值，则返回True，否则返回False

not in：与in相反

3.身份运算符

is：判断对应的两个标识符是否引用自同一个对象

is not：判断两个标识符是不是引用自不同的对象

注意：is和==的区别

is用于判断两个变量引用对象是否为同一个【id】

==用于判断两个变量的值是否相等

4.运算符的优先级

注意：

	a.尽量不要把一个表达式写的过于复杂，如果遇到复杂的需求，最好分步运算

	b.不要过于依赖运算符的优先级，开发中一般使用（）

二、循环控制语句【while语句】

1.概念

广义：一个周期现象或者重复出现的情况，这种状态被称为循环

狭义：在满足条件的情况下，反复执行某一段代码，在编程语言中出现的这种现象被称为循环。被反复执行的这段代码被称为循环体

2.使用

2.1while 语法

while 表达式：

	语句

2.2while-else

while 表达式：

	语句1

else：

	语句2

说明：

	相当于 

	while 表达式：

		语句1

	语句2		

2.3while嵌套循环

while 表达式1：

	while 表达式2：

		语句

Day04

一、list列表

1.概述

引出：存储一个数据可以采用变量

问题：需要同时存储多个数据，该怎么做

解决：容器【Python提供了一种数据结构list，可以同时存储多个数据】

本质：一种有序的集合【可存储重复元素】

2.创建列表

语法：列表名=[列表选项一，列表选项二...]

说明：使用[]表示列表，列表名就是标识符

	    将列表中的列表选项称为元素

	    列表中的元素分别被编了号【索引，下标，角标】，从0开始

3.列表中元素的访问

3.1取值

语法：列表名【索引】

3.2替换

列表名[下标]=xx

3.3列表组合：使用+号

list = list1+list2

3.4列表重复：*

list = list1*2

3.5列表截取：列表名[开始下标:结束下标]，前闭后开【包头不包尾】

			列表名[开始下标:]

			列表名[:结束下标]

3.6追加：

  3.6.1append

追加元素：list1.append(100)

追加列表：list1.append(list2):将列表作为一个元素添加进去

  3.6.2extend

list1.extend([1,2,3])：将1,2,3三个元素添加进去

  3.6.3insert

list1.insert(2,55):在索引为2的位置插入55

list1.insert(2,[55,100]):在索引为2的位置插入列表

3.7移除

  pop：移除指定下标处元素

list1.pop():默认移除最后一个元素

list1.pop(1)

  remove:移除指定元素

list1.remove(元素)

  clear:清空列表

list1.clear()

3.8查找

  index:从列表中查询第一个匹配的元素的索引

list1.index(元素值)

部分区域查找

list1.index(元素值，开始索引，结束索引)

3.9获取

  len：获取列表长度

len(list1)

  max：

max（list）

  min：

min（list）

  count：计算元素在列表中出现的次数

list1.count(元素值)

3.10反转

  reverse

list1.reverse()

3.11排序

  sorted:默认实现升序排序,会生成一个新的list

sorted(list1)

sorted(list1，reverse=True):倒序排序

sorted(list1,key=len)：根据字符串长度排序

  sort：将list本身进行排序

list1.sort()

list1.sort(reverse=True)

3.12拷贝

  浅拷贝：一改皆改，引用的同一块内存空间

list1 = list2	# 所有值的均是引用的地址

list1 = list2.copy() # number复制新值，其它为地址引用

深拷贝：deepcopy：两个内存空间不同

import copy

list1 = copy.deepcopy(list2)

对list中嵌套list有用，但对list中的tuple和string无效，其均为不可变的数据python不会创建新的进行额外管理

3.13列表生成器

range([start,]end[,step])

说明：开始值，结束值，步长【每次增长的值】

其中start和step可以省略，start默认为0，step默认为1

4.二维列表

实质上还是一个简单列表：一维列表中嵌套多个一维列表

二、for-in循环

1.用法：

语法：

for 变量名 in 列表：

	语句

说明：主要用于遍历列表【遍历：依次访问列表中每一个元素】

同时遍历list的下标和元素

for index,num in enumerate(list)

	print(index,num)

2.嵌套for循环

Day05

一、break和continue、pass

1.break

作用：跳出循环【直接跳出当前整个循环（就近原则），执行后面代码】

特殊情况：当循环中有break时，else分支亦不会执行

2.continue

作用：跳出当前执行的这次循环，继续下次循环

3.标志位

作用：为了处理嵌套循环中的break和continue，跳出外层循环

shell脚本中，break2

java中，给循环起别名

ptyhon中无标志位，可以人为在最外面定义一个flag=False，当里层想要跳出外层循环是

让flag=True，外层每次都判断flag值，是True就break

4.pass

表示空语句，为了保持程序结构的完整性

注意：pass不做任何事情，只是相当于一个占位符

		常用：if，while，for-in，函数等代码块中

二、布尔值和空值

1.布尔值

也是一种数据类型，只有两个值True和False

作用：主要用于分支语句和循环语句中

2.空值

None：是Python中一种特殊的数据类型

三、Number

1.分类

1.整型

	可以处理任意小的整数，也包括负整数

	语法：num1 = num2 = 100

		   num1，num2 = 60,70【交互对称】

2.浮点型

	注意：浮点数的运算会涉及四舍五入的误差

3.复数

	a+bj

2.数字类型转换

int（）

float（）

正负号也适用

3.功能

3.1数学功能

求绝对值：abs()

求最值：max  min

求x的y次方：pow(x,y)

求四舍五入：round(值，小数位数)



需要导入math：import math

1.math.ceil（x）：向上取整(去小数整数+1)

2.math.floor（x）：向下取整(去小数)

3.math.modf（x）：获取一个浮点数的小数部分和整数部分，结果为一个元组

4.math.sprt（x）：求平方根，结果为浮点数

3.2随机数

1.choice()

作用：从指定列表中随机取出一个数

import random

random.choice（list）

random.choice（"hello"），hello也相当于一个元组【字符串底层相当于一个元组】

2.random()

random.random():产生一个[0,1]之间的随机数，结果为浮点型

3.randrange（start,end,step）

4.shuffle:将对应列表中的元素进行随机排序

random.shuffle(list)

5.uniform:随机产生一个实数[3,9],结果为浮点型

random.uniform(3,9)

3.3三角函数

四、tuple元组

1.概念

元组本质上也是有序的集合，和列表非常相似

区别：

	a.列表用[]表示，元组使用()表示

	b.列表可以修改元素值，但是元组不可以

注意：元组一旦被初始化之后，就不能发生改变【地址不可更改】

2.创建元组

语法：元组名=（元素1，元素2，……）

注意：只有一个元素时，必须加一个逗号取消歧义

3.元组元素的访问

语法：

	tuple[index]

4.元组的操作

1.元组的连接：+

2.元组的重复：*

3.判断指定元素是否在元组中：in

4.元组元素的截取【切片】：tuple[1:4]包头不包尾

5.获取元组长度：len(tuple)

6.遍历元组：

	for index in range(len(tuple)):

		print(tuple[index])

7.最值：max(tuple)  min(tuple)

8.列表和元组之间的相互转换：

	tuple(list)

	list(tuple)

5.二维元组

跟二维列表类似

tuple1 = ((1,2,3),(4,5,6),(7,8))

6.和list的功能区别

1.元组中的元素是无法修改的【多线程时更多倾向于操作不变的数据】

2.元组在创建时间和占用时间上相对来说优于列表

五、dict字典

1.概述

思考：存储多个学生的成绩

也是一种存储数据的数据结构，但字典是无序的【在内存中元素的顺序和存放的顺序不一定相同】

字典采用的是键-值对【key-value】的形式存储数据

优点：具有极快的查找速度

2.key的特点

a.字典中的key是唯一的

b.key必须是不可变的实体

	例如：字符串，整数，元组都是不可变的

		    但list是可变的，故而不能作为字典的key

3.字典的创建

语法：字典名={键1：值1，键2：值2……}

4.字典的操作

1.获取

语法：字典名【key】

	dict1["Tom"]

	    字典名.get(key)

	dict2["Tom"]

2.添加

dict1["jerry"] = 80

若key存在，则覆盖

3.删除

dict1.pop("Tom")

通过键直接删除整个键值对

4.遍历

方式一、只获取键

for key in dict1:

	value = dict1[key]

	print(key,value)

方式二、只获取值

values：得到的结果是一个列表

dict1.values()

for value in dict1.values():

	print(value)

方式三、同时获取键和值

items：得到的结果是一个由元组组成的列表

dict1.items()

for key,value in dict1.items():

	print(key,value)

方式四、

for index,key in enumerate(dict1):

	print(index,key)

Day06

一、set集合

1.概述

和数学上的集合概念是类似的

特点：不允许有重复元素，如果添加重复元素，则会自动过滤，可以进行交集、并集的运算

本质：无序且无重复元素的数据结构

2.集合的创建和操作

    #注意1：创建set需要一个已知的list、tuple或者dict作为输入集合
    #注意2：重复元素在set中会被自动过滤
    s1 = set([12, 35, 45])
    print(s1)
    s2 = set((12, 45, 45))
    print(s2)
    
    #set和dict类似，区别在于只存储key不存储value
    s3 = set({1: "a", 2: "b"})
    print(s3)
    
    #添加 add()
    #set的元素不能使列表和字典，因为列表和字典中均有可变元素，但可以为元组
    s1.add(9)
    print(s1)
    s1.add((2, 3, 4))
    print(s1)
    
    #update()  插入整个list、tuple或者字符串，打碎插入【只插入元素】
    set2 = set([1, 2, 3, 4])
    #插入list
    set2.update([100, 200])
    print(set2)
    set2.update("hello")
    print(set2)
    #注意：update()不能插入数字
    
    #删除 remove(元素)
    s1.remove(35)
    print(s1)
    
    #遍历  集合不支持索引【元素是无序的】
    for i in s1:
        print(i)
        
    #求交集和并集
    #  &  |
    s1 = set([12, 40, 56, 86])
    s2 = set([20, 40, 56, 90])
    print(s1 & s2)
    print(s1 | s2)



二、简单算法

1.排序

1.1冒泡排序

思路：比较两个相邻下标所对应的元素，如果符合条件则交换位置，最值会出现在最右边

    list1 = [12, 25, 33, 85, 9, 45]
    #冒泡排序
    for i in range(len(list1)-1):
        for j in range(len(list1)-1-i):
            if list1[j] > list1[j+1]:
                temp = list1[j]
                list1[j] = list1[j+1]
                list1[j+1] = temp
    print(list1)

1.2选择排序

思路：从头开始依次与其后面所有进行比较，最小（大）值往前跑

    #选择排序
    for i in range(len(list1)-1):
        for j in range(i+1, len(list1)):
            if list1[i] > list1[j]:
                temp = list1[i]
                list1[i] = list1[j]
                list1[j] = temp
    print(list1)

2.查找

2.1顺序查找

思路：遍历列表，依次把每一个元素和指定元素进行比对

2.2二分法查找

注意：前提：必须是一个排好序的列表

查找思路：通过折半来缩小查找范围，提高查找效率

    #折半查找
    list1 = [9, 12, 25, 33, 45, 85]
    key = 45
    left = 0
    right = len(list1)-1
    while left <= right:
        mid = (left + right)//2
        if key > list1[mid]:
            left = mid + 1
        elif key < list1[mid]:
            right = mid - 1
        else:
            print("下标为：", mid)
            break
        if left > right:
            print("未找到")

三、String

1.概述

字符串就是由若干个不同的字符组成的有限序列

用单引号或双引号括起来的任意文本

注意：字符串是不可变的，一旦创建之后就不能改变

2.创建字符串

    str1 = "hello world"
    str1 = 'hello world'
    #注意：Python中不支持单字符类型，如果是单个字符，则同样用字符串表示
    str1 = 'c'

3.字符串运算

    #字符串运算
    #1.字符串连接
    s1 = 'welcome'
    s2 = 'to China'
    s3 = s1 + s2
    print(s3)
    
    #2.字符串重复
    s4 = s1 * 3
    print(s4)
    
    #3.获取字符串中的字符
    #语法：字符串名[索引]
    print(s1[3])
    
    # 4.截取字符串【切片】s4[start,end,step]
    print(s4[2:6])   #包头不包尾
    print(s4[2::2])  #若步长为负，则倒序输出
    
    #5.判断是否存在某字符串
    print("we" in s4)

4.字符串操作

    #1.转换：eval（）
      num = eval("123")		#123
      num = eval("-123")	#-123
      num = eval("12+6")	#18
    
    #2.计算长度、计算某子字符串在父字符串中出现的个数
      len("123")
      print(s4.count("is",2,5))#在某一区间中查找
    
    #3.大小写字母转换
      s.lower()#大-->小
      s.upper()#小-->大
      s.swapcase()#大-->小同时小-->大
      s.capitalize()#只有首个单词的首字母大写
      s.title()#将每个单词的首字母大写
    
    #4.填充字符串
      #center(width,fillchar) 将原字符串居中显示，剩余部分用指定字符串fillchar填充，总长度为width
    
      #ljust(width,fillchar)  将原字符串居左对齐……
      #rjust(width,fillchar)  将原字符串居右对齐……
    
      #zfill(width)  返回一个长度为width的字符串，原字符串居右对齐，前面都用0填充
    
    #5.查找
      #find()  默认从头到尾查找，可以指定查找区间
        s4.find("day",1,9)#返回的是子字符串在原字符串中第一个字母出现的下标；如果未查找到，则返回-1
    
      #rfind()  从右往左边查找 若无重复元素结果与find()相同
    
      #index(),类似于find() 但是若未找到会报错
      #rindex(),类似于rfind() 但是若未找到会报错
    
    #6.截取
      #strip()  剔除头尾指定字符串，默认为空格
        s5 = "***sssd***"
        print(s5.strip("*"))  #sssd
    
      #lstrip()  剔除左边指定的字符串
      #rstrip()  剔除右边指定的字符串
    
    #7.分割和合并
      #split()  通过指定的字符串进行分割，结果为列表
        s.split(" ")
        s.split(" ",3)#只分割前三个，后面的为一个整体
    
      #splitlines()	识别行\r \n \r\n	根据换行符分割
        s = '''tomorrow
        is
        a
        sunny
        day
        '''
        s.splitlines()
    
      #join()
        s1 = "*"
        s2 = "tomorrow"
        print(si.join(s2))#t*o*m*o*r*r*o*w
      
    #8.替换
      #replace(old,new,max)  使用new的字符串替换old的字符串，最大的替换次数不能超过max
      #映射替换
      #maketrans() 创建字符映射表
      t = str.maketrans('ac','68')
      #translate()
      s.translate(t)#将s中的a全都换成6，c全都换成8
      
    #9.判断
      #isalpha()  判断是否都是字母
      #isdigit()/#isnumeric()  判断是否都是数字
      #isalnum()  判断是否都是字母或数字
      #isupper()  判断是否都是大写字母
      #islower()  判断是否都是小写字母
      #istitle()  判断是否每个单词首字母都是大写字母
      #isspace()  判断是否都是空格
    
    #10.前缀和后缀
      #startswith()
      #endswith()

Day07

一、字符串

    #1.格式化输出
    #通过%来改变某些字母的含义
    '''
    %d	整型	也可以用%.2d 控制保留位数
    %f	浮点型，可以指定精确的小数位数
    %s	字符串
    '''
    
    f = 12.23564
    #%.nf	如果n==0，则取到的是整数，如果n>=1,则表示保留小数点后n位
    print("f = %.1f"%(f))
    
    #2.常用的转义字符
    #通过\来改变某些字母的含义
    '''
    \t:	相当于tab键
    \n:	换行，相当于enter键
    '''
    print("\\")
    #想要单引中用单引或者双引中用双引都可以用\转义
    
    #\r:	Linux
    #\n	\r\n	Windows
    
    #文件路径
    s = r"C:\Users\asus\Desktop\千锋python教程\Day5\Day5笔记"
    #r的作用：不需要对字符串中的特殊字符进行转义
    
    #3.编码和解码
    #encode()
    str1 = "Hello Python !你好，python"
    #utf-8	GBK
    print("str1.encode('utf-8')")
    #bytes.decode()

二、函数

1.概述

在一个完整的项目中，某些功能会被重复使用，那么僵这个功能对应的代码封装成函数，当再次使用这个功能的时候，只需要使用这个函数即可

本质：对代码的功能封装

优点：

	a.简化代码结构，提高应用的模块性

	b.提高代码的复用性

	c.提高代码的可维护性

2.定义

语法：

	def 函数名（参数1，参数2……）:

		函数体

		return 变量或常量

说明：

	a.一个完整的函数包括声明部分和实现部分

	b.函数代码块以def关键字为开头，是definition的缩写

	c.函数名：遵循标识符的规则即可，尽量做到见文知意

	d.（参数1，参数2……）参数列表，参数数量不受限制，也可没有

	e. ：表示函数内容的开始【以缩进区分】

	f.函数体：封装起来的功能代码

	g.return：返回某一结果给调用者，也可不写

3.函数的使用

3.1最简单的函数

无参，无return

    def myFunc():
      print(" ")
    #函数的调用
    myFunc()
    #在同一文件中可以定义同名函数，但是后定义的会覆盖之前的函数

3.2函数的参数

参数列表：未知项，会改变的

分类：

	形参：在函数中定义的【参数列表】，用于接收实际参数的变量

	实参：在函数外定义的，需要参与运算的变量，给函数传的值

传参：实参给形参赋值的过程

注意：python中，形参的类型由实参的类型决定，一般情况下，按照函数体中具体的功能来决定

3.3参数的传递

值【数据】传递：传递的是不可变的数据类型，比如number，String，tuple

引用【地址】传递：传递的是可变类型，比如list，dict，set

3.4参数的类型

1>必需参数

必须以正确的顺序进行使用，实参的数量和形参的数量保持一致

2>关键字参数

    def fun1(name,age):
      print()
    fun1(age=18, name= 'jack')
    fun2(18, name= 'jack')
    # 注意：有位置参数时位置参数必须在前面，关键字参数之间可无序

3>默认参数

    def fun2(name, age=10);
    	print()
    #注意：在参数列表中，默认参数只能出现在最后面，最多出现一个默认参数

4>不定长参数【可变参数】：	*

能处理比当初声明函数更多的参数

    def fun3(name,*hobby):
    	pass
    #注意：*的不定长参数被当做元组处理，第一个参数赋给name，其它的全部给hobby
    # **【关键字参数】
    def fun4(**args):
      #注意：**的不定长参数被当做字典处理
    fun4(x=1, y=2)
    # **的实参，需要通过key=value的形式传参

4.函数的返回值

表示一个函数执行完毕之后得到的结果；可以同时返回多个数据，此时返回的数据类型是一个元组

使用return关键字返回函数的返回值，用于结束整个函数，将最终的结果返回给调用者

注意：如果return的后面没有具体的变量或者数值，则return表示结束当前函数，则后面的任何语句都不会执行；若函数无返回值，强行打印的话，会打印出None

5.匿名函数

不再使用def函数名()这种形式定义函数，而是lambda表达式来创建匿名函数

特点：

	a.lambda只是一个表达式，函数体比def简单得多

	b.lambda的函数体不再是代码块

	c.lambda只有一行，增加运行效率

语法：lambda[arg1,arg2……]:函数体

    sum = lambda num1, num2:num1 + num2
    print(sum(10,20))
    # 匿名函数也可以使用关键字参数、默认参数
    print(sum(num2=20,num1=10))
    # 匿名函数必有返回值，返回值就是函数体的运行结果

6.空函数

什么功能都不实现的函数，借助于pass语句

    def test():
    	pass

7.主函数

每一个程序都有程序入口，main函数，会把对应的代码从头执行到尾（在python中main函数不会显示出来，文件一创建就自动存在）

    if _name_ == "_main_"	#查看当前是否在主函数中运行
    	print("main")

对于Python语言而言，一个.py文件就相当于一个简单的Python程序，所有的代码默认都在主函数中运行

Day08

一、函数的特殊用法

1.变量也可以指向函数

    #将函数的结果赋给某个变量
    num = abs(-10)
    #将函数本身赋值给一个变量
    f = abs
    print(f(-10))
    '''
    结论：
    1.函数本身也可以赋值给变量，换句话说，变量也可以指向一个函数
    2.如果一个变量指向了一个函数，那么，则可以通过这个变量去调用这个函数
    '''

2.函数名是变量

函数名其实就是一个指向函数实体的一个变量，若给系统内置函数的函数名重新赋值，则会使其失去本身的作用

3传入函数

一个函数能接收另一个函数作为参数，这种函数被称为高阶函数

    def add(x, y, f):
      return f(x) + f(y)
    
    add(-10, 20, abs)

二、偏函数

1.概述

对参数做一些控制的函数【比如：默认参数】称为偏函数

偏函数一般不需要自己定义，直接使用

模块functools其中就有偏函数的功能

	int() 将字符串或浮点型转换为整形，当传入字符串时，默认按照十进制转换，默认十进制输出

	事实上，int() 中还有另一个参数base，默认是10

	int(s, base = 10)可以用int进行n进制转十进制【函数的结果都是十进制数】

    import functools
    #functools.partial:帮助我们创建一个偏函数
    binary_int = functools.partial(int, base=2)

总结：functools.partial的作用:当函数的参数过多，需要简化时，使用它可以创建一个新的函数，把一个函数的某些参数固定【设为默认值】，返回一个新的函数，则以后使用的时候就可以根据不同的需求调用不同的函数

三、变量的作用域【访问权限】

1.概述

变量的作用域是指变量有效的范围

2.变量的简单分类

按照作用范围划分

变量的作用域决定了哪一部分程序可以访问哪个特定的变量

分类：

	L：Local，局部作用域

	E：Enclosing，函数的作用域【闭包】

	G：Global，全局作用域

	B：Built-in，内建作用域【内置作用域】

    #闭包
    #你调用了一个函数A，这个函数A里定义了一个函数B，且返回了一个函数B，这个返回的函数B就被称为闭包【函数的嵌套】
    x = int(2.9)		#B
    count = 0			#G
    def outer():
      num = 1			#E
      def inner():
        n = 2			#L
      return inner()
    
    #4.內建作用域
    x = int(12)
    
    m = 0
    def outer():
        j = 1
        def inner():
            i = 2
            print(x)  #12
        return inner
    
    demo = outer()
    demo()

3.变量查找规则

L---->E--->G--->B

4.注意问题

Python中只有模块、类以及函数才会引入变量的作用域的问题，其他的代码块，比如：if语句，while语句、for-in语句、try-except语句中是不会引入新的作用域的【在这些语句中定义的变量在外面也可使用】

5.全局变量和局部变量

定义在函数外的称为全局变量，定义在函数内部的称为局部变量

6.global和nonlocal

主要为了解决局部变量和全局变量

    #1.在Python中，当内部作用域想修改外部作用域的变量的时候，则就要使用global关键字进行声明
    num = 1
    def fun():
      global num	#1
      print(num)
      num = 123
      print(num)	#123
      
    #2.如果要修改函数作用域中的变量，则使用nonlocal
    #需要明确的是，nonlocal关键字定义在闭包中
    x = 0
    
    
    def outer():
        x = 1
    
        def inner():
            nonlocal x
            x = 2
            print("inner", x)   #2
        inner()
        print("outer", x)       #2
    
    
    outer()
    print("全局:", x)           #0
    #nonlocal关键字：声明了该变量不只是在inner函数内部才有效，而是在整个outer函数中有效

四、列表生成式、生成器和迭代器

1.列表生成式

    list1 = [x * x for x in range(1, 11)]	#[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
    
    list2 = [x * x for x in range(1, 11) if x % 2 == 0]	#[4, 16, 36, 64, 100]
    
    list3 = [m + n for m in "abc" for n in "xyz"]
    
    list4 = [key + "=" + value for key,value in dict.items()]

2.生成器

    #生成器【generator】
    #()
    #方式一、将列表生成式的[]换成()
    ge = (x for x in range(1, 6))
    print(type(ge))#generator
    
    #生成器需要通过next()方法获取数据，调用一次返回一次
    print(next(ge))
    #注意：如果通过next函数获取生成器中的数据，当数据取完之后，将不能在调用next函数，否则会报StopIteration
    
    #生成器也可以通过for-in的方式进行遍历
    for x in ge:
      print(x)
      
    #方式二、通过函数和yield【让步】关键字
    def test(n):
      for i in range(1, n+1):
      	yield i
        
    result = test(10)
    print(result)
    for i in result:
        print(i)  

Day09

一、迭代器

1.可迭代对象

a.可直接作用于for-in循环的数据类型都被称为可迭代对象：Iterable

b.可以使用isinstance()判断一个对象是否是可迭代对象

c.可以直接作用于for-in循环的数据类型

	1.数据结构：list、set、tuple、dict、string

	2.generator【生成器】【（），函数结合yield】

    #导入模块
    #collections： 包
    from collections import Iterable
    print(isinstance([x for x in range(10)],Iterable))

2.迭代器

a.迭代器：Iterator

b.不但可以作用于for-in循环，还可以使用next()函数将其中的元素获取出来

c.可以使用isinstance()判断一个对象是否是迭代器

结论：list、set、tuple、dict、string是可迭代对象，但是，不是迭代器，只有生成器才是迭代器

3.将可迭代对象转换为迭代器

迭代器一定是可迭代对象，但是，可迭代对象不一定是迭代器

iter():将可迭代对象转化为迭代器【主要针对list、set、tuple、dict、string】

	iter(list)

4.总结

a.凡是可以通过for-in循环进行遍历元素的数据类型都是Iterable类型【可迭代对象】

b.凡是可以使用next()的数据类型都是Iterator类型

c.list、set、tuple、dict、string是Iterable类型，但是，可以通过iter()函数转换为iterator类型

二、装饰器

对于一个现有的函数，如果想要增强此函数的功能，但是不允许修改次函数源代码的时候，使用装饰器来解决这个问题

装饰器：在程序代码的运行期间动态增加功能的方式

本质：就是一个闭包，还是一个返回函数的高阶函数

好处：就是在不用修改函数源代码的前提下，，提高了代码的可扩展性，提高了代码的复用性和可维护性

    def now(num):
      print(num)
    # 1.简单的装饰器
    def wrapper(func):	# wrapper就是装饰器
      def inner(num):	# 负责修饰的部分【新增加的功能】
        print("……")
        func(num)
       return inner
    f = wrapper(now)
    f(10)
    # 此时f为now函数的增强版本
    '''
    步骤
    1.闭包
    2.明确需求：需要增加什么功能【写在inner的函数体中】
    3.需要给原函数增加功能，则在inner中调用原函数
    4.将inner返回
    5.在外面调用【注意：调用到inner】
    '''
    
    # 2.使用 @ 标识符直接将装饰器应用到指定函数上
    # 用法：在需要被装饰的函数前面加上： @装饰器的名字【外层函数的名字】
    
    
    def wrapper(func):	
      def inner(num):	
        print("……")
        func(num)
       return inner
    
    @wrapper
    def now(num):
      print(num)
    now(10)
    # 注意：使用@的时候，如果装饰器和需要被装饰的函数在同一个.py文件中的时候，
    # 装饰器一定要出现在被装饰函数的前面【python中的代码是从上往下依次执行的】
    
    #3.带有不定长参数的装饰器
    def wrapper(func):
      	def inner(*args,**kwargs):
          # 新增的功能
          print("believe yourself")
          
          # 调用原函数
          func(*args,**kwargs)
         return inner
    @wrapper  
    def func1(a, b, c, d = 1):
      print("result is %d" % (a + b + c + d))
      
    func1(1, 2, 3)
    
    # 4.多个装饰器可以应用于同一函数
    @wrapper1
    @wrapper2
    def text():
      print("sda")
    # 结论：多个装饰器同时作用于同一个函数的时候，从第一个装饰器开始，依次往下执行，但是无论如何text函数都只会执行一次

三、函数递归

函数递归：一个函数的函数体中调用了函数本身

递归中包含了一种隐式的循环，他会重复执行某段代码，但是这种循环无需用循环语句进行控制

使用递归解决问题的简单思路：

	a.写出临界条件

	b.需要找到当前的循环和上一次循环之间的关系

	c.根据规律实现

    # 斐波那契数列：1、1、2、3、5、8、13、21、34、……
    def num(index):
    	if index == 1 or index == 2:
          return 1
        else :
          num(index) = num(index-1)+num(index-2)

四、栈和队列

1.栈：先进后出

stack

抽象成一个开口向上的容器

    # 创建一个栈【列表底层就是一个栈】
    my_stack = []
    # 入栈（压栈）【向栈中存数据】：append
    my_stack.append(23)
    my_stack.append(30)
    my_stack.append(50)
    #[23, 30, 50]
    # 出栈（弾栈）【取出数据】：pop
    my_stack.pop()	#50

2.队列【管道】

queue

先进先出

    import collections
    # 创建列表
    queue = collections.deque([12, 43, 8, 10])
    # 入队：append
    queue.append(66)
    # 出队:popleft
    queue.popleft()

五、目录的遍历

    import os
    # os:操作系统的内容
    dir = r"D:\千锋python教程\python书籍"
    # listdir:列出指定目录下所有的文件夹及文件【dir】,返回的结果是列表
    fileslist = os.listdir(dir)
    print(fileslist)
    # join:拼接路径
    fpath = os.path.join(dir,"Day5Code")
    print(fpath)	# D:\千锋python教程\python书籍\Day5Code
    # isdir()：判断是否是目录
    if os.path.isdir(fpath)

1.递归遍历目录

    import os
    path = r"D:\千锋python教程\python书籍"
    def get_all_file(path):
    	fileslist = os.listdir(path)
    	print(fileslist)
    for filename in fileslist:
    	fpath = os.path.join(dir,filename)
    	print(fpath)	
    	if os.path.isdir(fpath):
        	get_all_file(fpath)

2.栈模拟递归遍历【深度遍历：竖着一条线遍历完】

    import os
    path = r"D:\千锋python教程\python书籍"
    def get_all_file(path):
        # 创建一个空栈
        stack = []
        # 将初始路径添加到栈中
        stack.append(path)
        while len(stack) != 0:
    		# 从栈中取出数据
            dirpath = stack.pop()
            # 获取当前路径下所有的文件夹以及文件
            filelist = os.listdir(dirpath)
            # 遍历列表
            for filename in filelist:
                # 拼接路径，二级目录下的文件路径
                filepath = os.path.join(dirpath,filename)
                # 判断是否是目录
                if os.path.isdir(filepath):
                    # 将新的路径添加到栈中
                    print("目录", filename)
                    stack.append(filepath)
                else:
                    print("普通文件"， filename)

3.队列模拟递归遍历【广度遍历：横着遍历】

    import collections
    import os
    path = r"D:\千锋python教程\python书籍"
    def get_all_file(path):
        # 创建一个空队列
        queue = collections.deque
        # 将初始路径添加到队列中
        queue.append(path)
        while len(queue) != 0:
    		# 从栈中取出数据
            dirpath = queue.popleft()
            # 获取当前路径下所有的文件夹以及文件
            filelist = os.listdir(dirpath)
            # 遍历列表
            for filename in filelist:
                # 拼接路径，二级目录下的文件路径
                filepath = os.path.join(dirpath,filename)
                # 判断是否是目录
                if os.path.isdir(filepath):
                    # 将新的路径添加到栈中
                    print("目录", filename)
                    queue.append(filepath)
                else:
                    print("普通文件"， filename)
                    
    深度优先遍历（栈，先压右节点，再压左节点）
    广度优先遍历二叉树（队列：先压左节点，再压右节点）

Day10

一、包

包是Python中用来管理模块命名空间的形式

    #在Python中，包和普通文件夹的区别就在于：包下有一个特殊的文件，__init__.py
    #__init__.py文件存在的意义：若什么内容都不写，则只是为了告诉编译器这不是一个普通文件夹，而是一个包

二、模块

1.概述

主要是为了将功能相似的函数进行分组，放到不同的文件中，这样的话每个文件中的内容就相对较少【维护性高】，每一个文件的文件名用相应的功能来进行命名

本质：一个.py文件其实就是一个模块

2.优点

a.提高了代码的可维护性

b.提高了代码的复用度【当一个模块书写完毕，可以在多处使用】

c.引用其他的模块【内置模块，第三方模块，自定义模块】

d.借助于包，可以避免文件命名重复【函数和变量命名重复的情况】

    调用模块
    import aaa.testDemo
    

3.日期和时间模块

time：时间

datetime：日期

calendar：日历

时间间隔是以秒为单位的

每个时间戳都以自从1970.1.1经历了多长时间计算的

时间戳：当前时间距离1970.1.1的秒数

3.1time时间模块

UTC：格林威治天文时间，世界标准时间，在中国UTC+8

DST：夏令时

时间的表示形式：

	a.以整数或者浮点数表示一个以秒为单位的时间间隔，这个时间的基础值1970.1.1的零时零分零秒

	b.采用Python中的数据结构表示，采用元组，元组中可以有9个不同的元素，表示不同的含义

	c.格式化的时间字符串

    import time
    # 1.获取当前时间的时间戳
    c = time.time()
    # 2.将时间戳转化为UTC时间
    g = time.gmtime(c)
    # 3.将时间戳生成时间元组
    l = time.localtime(c)
    # 4.将时间元组转换为时间戳
    c2 = time.mktime(l)
    # 5.将时间戳转换为字符串
    time.ctime(c2)
    # 6.格式化字符串
    time.strftime("%Y-%m-%d %H:%M:%S", l)
    # 7.将指定格式的时间字符串转换为时间元组
    time,strptime("2018-04-02 10:35:35", "%Y-%m-%d %H:%M:%S")
    # 8.休眠
    # 使用情景：多线程
    # 参数的单位是秒
    time.sleep(5)	# 休眠5秒
    # 9.用来衡量不同程序的耗时
    time.clock()	
    # 第一次调用，返回的是进程运行的实际时间。而第二次之后的调用是自第一次调用以后到现在的运行时间

3.2datetime日期模块

对time模块进行了一个进一步的封装，比time更高级

    # 1.获取当前时间
    import datetime
    d1 = datetime.datetime.now()
    print(d1)	# 2018-04-02 10:59:29.047767
    # 2.获取指定时间
    print(datetime.datetime(2018,4,2,10,59,29,47767))
    # 3.将指定的时间转换为字符串
    d2 = d1.strftime("%Y-%m-%d")
    
    datetime.datetime.strptime(d2, "%Y-%m-%d")
    # 4.两个时间相减，可以得到时间间隔
    d5 = d3 - d4
    print(d5)	# 3 days, 0:00:00
    # 整数天之外的秒数
    print(d5.seconds)

3.3calendar日历模块

    import calendar
    # 1.直接返回指定年和月万年历表示形式
    print(calendar.month(2018, 4))
    # 2.返回万年历的二维列表表示形式【横向】
    print(calendar.monthcaclendar(2018, 4))
    # 3.直接返回指定年份的万年历表示形式
    print(calendar.calendar(2018))
    # 4.判断某年是否为闰年
    print(calendar.isleap(2010))
    	# 获取两个年份之间的闰年个数
    	print(calendar.leapdays(2000, 2020))
    # 5.返回指定月的第一天为week的第几天和这个月的所有的天数
    print(calendar.monthrange(2018, 4))
    #当前日是星期几
    print(calendar.weekday(2018, 4, 2))

4.os模块

    import os
    # 1.name属性表示当前的操作系统 nt--->Windows, posix--->Linux
    print(os.name)
    # 2.获取系统环境变量
    print(os.environ)
    # 3.获取指定路径下所有的文件及文件夹
    # 注意：返回值的类型为列表
    print(os.listdir(r"C:\Users"))
    # 4.在当前目录下创建一个新的目录	md
    os.mkdir(r"C:\Users\aaa")
    # 5.删除指定目录
    os.rmdir(r"C:\Users\aaa")
    # 6.重命名
    # 参数1：原路径 参数2：新路径
    os.rename(参数1，参数2)
    
    # os.path
    # a.查看当前的绝对路径
    print(os.path.abspath("/aaa"))
    # b.拼接路径
    print(os.path.join(r"C:\Users\aaa", "Demo"))
    # c.拆分路径,将最后面文件名字分割出去
    # 注意：得到的结果是元组
    print(os.path.split(r"C:\Users\aaa\Demo"))
    # "C:\Users\aaa", "Demo"
    # d.获取文件的扩展名，返回结果为元组，如果是文件夹，则为空
    print(os.path.splitext(r"C:\Users\aaa\Demo\Demo01.py"))
    # e.判断是否为目录
    os.path.isdir("")
    # f.判断是否为文件
    os.path.isfile("")
    # g.判断指定路径是否存在
    os.path.exists("")
    # h.获取文件的大小，单位为字节
    os.path.getsize("")
    # i.父路径
    os.path.dirname("")
    # 文件名
    os.path.basename("")

5.自定义模块

本质：将相应的函数封装好，然后在其他的文件中调用，自定义模块的目的是为了管理函数

5.1import

import Demo01

.py文件其实就是一个模块。文件名其实就是模块名

模块中函数的调用方式：模块名.函数名()

模块的好处：方便管理函数，如果修改需求，则只需要修改模块

如果需要导入的模块在包下，则通过包名.模块名导入即可

当使用一个import关键字导入一个模块的时候，这个模块中的所有的代码会被执行一遍

5.2from...import...	从模块名导入函数名

    from MyPacage01.MyFile01 import func1

使用此导入模块方法，可以直接用函数名调用模块中函数

func1()

如果在当前文件中出现和模块中同名的函数时，调用的是当前文件的函数【覆盖】

因为在import的时候就会在当前文件中先将导入的模块加载一遍

5.3from...import *

    from MyFile import *
    # 注：这种用法少用，避免资源的浪费

5.4

    __name__
    在模块使用的过程中，如果想屏蔽掉一些语句的执行
    作用：不想让模块中的部分代码执行，可以使用它来使得程序只执行模块中的部分内容
    注意：每个模块其实都有__name__，当且仅当__name__的值为"__main__"的时候表示模块自身正在执行，如果不是的话，则表示是其他模块在执行
    

6.第三方模块的安装

步骤：

1.在终端中输入命令：pip -V     【检查版本，这个步骤在安装Python环境的时候如果勾选了Add path选项，则已自动安装】

2.安装第三方模块：pip install pillow    【pillow为一个图形处理的第三方模块，需要联网下载】

	如果此步出错，则执行命令pip install --upgrade pipi

3,.如果不使用第三方模块，则可以执行命令：pip uninstall pillow  ，卸载第三方模块

Day11

一、面向对象的思想

1.面向对象思想的设计

万物皆对象

面向过程：process(处理)，过程

2.面向过程和面向对象的区别

2.1面向过程

在生活案例中：

	一种看待问题的思维方式，在思考问题的时候，侧重于问题是怎样一步一步解决的，然后亲力亲为的去解决问题

在程序中：

	代码从上往下依次执行

	各个模块之间的关系尽可能简单，在功能上相互独立

	每一个模块内部均是由顺序语句，分支语句和循环语句组成

	程序的流程在开始书写过程的时候就已经定了

2.2面向对象

在生活案例中：

	也是一种看待问题的思维方式，侧重于找到一个具有特殊功能的个体，委托对应的个体帮忙完成某件事情

	面向对象更符合人类的思考方式【懒人思想】，将复杂的问题简单化，将程序员从执行者变成了指挥者

在程序中：

	对同类的对象进行抽取，形成类

	程序的执行流程由用户在使用中决定

	使用面向对象的思想进行开发，先要这道具有特殊功能的个体

	具有特殊功能的实体被称为对象，先要找到这个实体，如果存在直接使用，若没有，则创建

	具有特殊功能的个体被称为对象，也成为实例

注意：面向对象只是一种编程思想，不是编程语言【python、java、OC都是面向对象的语言】

	【类和对象是面向对象的核心】

二、类和对象

1.概念

类：一个具有特殊功能的实体的集合

对象：在一个类中，一个具有特殊功能的实体，能够帮忙处理某件特定事件

在程序中一般先定义类，然后通过类创建对象

理解：类是一种数据类型，只不过是我们自己定义的，list、set、tuple、string

2.类的定义

语法：

	class 类名():

		类体

说明：

	a.在Python中定义类使用class关键字

	b.类名只要是一个合法的标识符即可

		官方要求：标识符用下划线分隔不同的英文单词【my_class】

		大多数程序员：使用大驼峰命名法【所有单词的首字母大写，MyClass】

	c.通过缩进来体现类体的存在

	d.类体一般包含两部分内容：对类的特征描述，对类的行为的描述

注：在同一个.py文件中，可以定义多个类【一般情况下，为了代码的可读性，一个文件中只定义一个类，使用时可作为模块导入】

三、类中的成员变量和成员方法

1.定义

定义类其实就是定义类中的成员变量和成员方法

成员变量：类中定义的变量，用于描述特征【需要给每个变量初始值，可以暂时认为是默认值】

成员方法：类中定义的函数【方法】，用于描述行为【区别于普通方法，成员方法必须含一个参数self，且必须在参数列表第一位，这个参数不须传参；self代表类的实例，只是一个标识符而已，习惯上用self，可任意更改】

结论：拥有相似的特征和行为的对象就可以提取出来一个类【类是模板（抽象的），对象是一个实体（具体存在）】，每个对象拥有的数据可能不同

2.使用

对象的创建过程也被称为对象的实例化过程【instance】

语法：对象名=类名()

list=[2,25,56]	说明：对象名其实就是一个变量名，只不过这里的数据类型为类

    # 1.对象的创建
    # p1其实就是一个变量名，也被称为引用，指向真正的对象，其中存储了实际对象的地址
    p1 = Person()
    # 2.对象访问和调用类中成员变量
    # 取值：
    p1.age
    # 赋值
    p1.age = 18
    # 3.调用成员方法
    p1.run()

3.内存中的对象

扩展：内存的分类

	a.寄存器：最快的存储区，由编译器根据需求进行分配，我们在程序中无法控制

	b.栈：存放的是引用【变量名】

		特点：被执行完成之后，该函数或者变量所占有的空间会立马被销毁

	c.堆：存放的是实际的对象【所有创建出来的对象】

		特点：执行完成之后不会立马被销毁，当使用完成之后，会被标上垃圾的印记，等待GC回收

	d.方法区

		静态域

		常量池：主要存储常量

结论：成员变量是随着对象的出现而出现的，成员变量在堆空间中开辟空间，对象名【引用】在栈空间开辟空间

四、构造函数和析构函数

1.构造函数

创建函数：p1 = Person()

    很多的类倾向于将对象创建为有初始状态的。所以，在类中会定义一个构造函数【__init__函数】
    作用：
    	a.创建对象
    	b.将对象的数据初始化【给成员变量进行赋值】
    构造函数也被称为构造器，调用的时机：当实例化一个对象【创建对象】的过程中第一个被自动调用的函数
    
    注意：当在类中没有显式的定义构造函数的时候，系统会默认提供一个无参的构造函数
    语法：
    	def __init__(self,arg1，arg2...):
        	函数体
    说明：
    	a.如果要将无参的构造函数显式的定义出来，其实类似于下面的写法,其实是一个空函数：
      		def __init__(self):
          		pass
        b.arg1，arg2...表示需要初始化的变量，一般情况下，这些参数都和成员变量有关
    注意：如果在类中显式的定义了有参的构造函数，则系统将不再提供无参构造函数，一个类只能怪只能有一个构造函数

2.self的使用

注意：self代表的是实例【对象】，而不是类本身，那个对象调用函数self就代表那个对象

用法：

	在有参构造函数中：相当于java中的this

	self.name = name

总结：

a.创建对象的时候第一个自动调用的函数

b.系统会默认提供一个无参构造函数

c.自定义一个有参构造函数后，系统将不再自动提供无参构造函数

d.self主要用在构造函数中可以定义成员变量并给成员变量赋值

e.以后在使用的时候，一般选用有参的构造函数结合self来进行使用



3.析构函数

    和构造函数相反，当对象被销毁的时候自动调用的函数__del__，被称为析构函数
    
    通过del 变量名	可以手动销毁对象
    
    使用情景：对象即将被销毁的时候需要做的一些清理操作，比如：数据库的关闭、文件的关闭

Day12

一、属性动态绑定和限制

    # 1.动态绑定属性，在程序的运行过程中动态的给一个类添加属性
    m = MyClass()
    m.num = 100	# MyClass类中没有num属性，这条语句可以直接动态的给m对象添加一个属性num，但不是给这个类添加了属性
    # 2.限制属性的绑定：__slots__
    # 使用tuple来限制需要绑定的属性
    class Customer():
      __slots__ = ("name", "age")	# 说明只可以动态绑定name和age属性,此时类中可同时读写的属性也只能有动态绑定的这两个,同时不能绑定类中已声明的属性

二、封装

1.概念

广义的封装：函数和类，模块，本身就是封装的体现

狭义的封装：一个类中某些属性，不希望被外界直接访问，解决办法：将这个属性作为私有的，然后暴露给外界一个访问的方法即可

封装的本质：属性私有化的过程

封装的好处：提高了数据的复用性和安全性

举例：插排

2.属性私有化

    如果想让类内部属性不被外界直接访问，可以在这个属性的前面加两个下划线__，在Python中，如果一个属性的前面出现__，就表示这个属性只能在当前类中被直接访问，这个变量就被称为私有变量set
    # get/set方法
    def setAge(self, age):
      self.__age = age
    def getAge(self):
      return self.__age
    # 私有化好处：可以进行一定程度上数据的过滤，而这个过滤的操作不需要用户知道
    
    __age	# __是代表私有的private
    _score	# _是代表受保护的protected，只能再本类以及子类中访问，访问的时候可以直接访问，但是以后看到类似的变量表示：虽然我可以直接被外界访问，但是请把其视为私有变量，不要直接访问
    
    # __name__	__slots__	属于特殊变量，将不再属于私有变量，将属于内置变量【系统变量】，自己定义变量最好避免这种写法

3.@Property装饰器

    # 使用@property装饰器实现类似get/set的操作
    # name属性的
    # 此函数相当于之前的get函数，函数名可以随意些，但是，一般情况下，命名为变量的名字
    @property
    def name(self):
      return self.__name
    # 此时访问就直接访问函数名
    print(a1.name)	#相当于a1.getName()
    # @property装饰器的作用：将函数属性化
    # xxx.setter,xxx与get函数名需一致
    @name.setter
    def name(self, name):
      self.__name = name
    a1.name = "旺财"	#相当于a1.setName()
    
    # 注：@property装饰器在使用的过程中，本身又创建了一个新的装饰器@xxx.setter,负责给私有成员变量赋值

4.成员函数私有化

事实上，若果对一个函数的名字前面加__，声明该方法为私有方法，只能在本类中被调用

    # 调用格式：self.私有函数名（），在当前类中也不能直接通过函数名调用

三、继承

1.概述

如果两个或者两个以上的类具有相同的属性或者方法，我们就可以抽取出一个类，在抽取出来的类中声明多个类中公共的部分

被抽取出来的类：父类、超类、基类

两个或者两个以上的类：子类、派生类

关系：子类 继承自 父类

继承的好处：

	a.可以简化代码，减少冗余度

	b.提高了代码的可维护性

	c.提高了代码的安全性

	d.是多态的前提

2.单继承

简单来说：一个子类只有一个父类

语法：

父类：

	class 父类类名(object):

		父类类体

子类：

	class 子类类名（父类类名）:

		子类类体

注意：object是Python中所有类的父类【一般情况下，如果一个类没有指明的父类，默认它的父类为object，需要显式的写出来】

    # 子类中使用父类属性：调用父类构造方法
    class Teacher(Person)
      def __init__(self, name, age, work):
        self.work = work
        # 方式一：super(当前类， self).__init__(属性列表)
        super(Teacher,self).__init__(name, age)
        # 方式二：父类名.__init__(属性列表)
        Person.__init__(self, name, age)
        # 方式三： super().__init__(属性列表)
        super().__init__(name, age)
    # 注：子类中不可以访问父类中的私有变量
    # 子类对象可以直接调用父类中的普通的成员方法【私有方法除外】
    # 父类对象不能访问子类中任何的特有数据

总结：

继承的特点：

	a.子类对象可以直接访问父类中未私有化的成员变量

	b.子类对象可以直接调用父类中未私有化的成员方法

	c.父类对象不能访问子类中特有的属性和方法

继承的缺点：

	耦合和内聚被用来描述类与类之间的关系，耦合性越低，内聚性越高，则说明代码质量越高

	在继承关系中，耦合性相对较高【如果修改父类，子类都会被影响】

3.多继承

一个子类可以有多个父类

语法：

class 子类类名(父类1， 父类2……)

    # __slots__ 在继承中
    父类中含有属性的动态限制，不会对子类造成任何影响

4.函数的重写override

主要针对的是具有继承关系的类【子类】

当父类函数的实现部分解决不了子类中的需求时，则需要对函数进行重写

4.1系统函数

    __str__		__repr__
    # 重写系统函数：__str__
    def __str__(self):
      return "name=" + self.name
    # 重写系统函数：__repr__
    def __repr__(self):
      return "lalala"	# 运行程序不会打印在控制台
    # __str__和__repr__本身的作用是相同的，只不过str是给程序员看的，repr是给编译器看的
    # 当两者都被重写之后，使用对象的时候仍然调用__str__

4.2自定义函数

    # 需求：父类中的函数无法满足所有需求，其要在其基础上新增功能
    class SmallAnimal(object):
        def fun(self):
            print("父类中fun")
    
    
    class Cat(SmallAnimal):
    
        #前提：必须是在具有继承关系的类中
        #重写【复写】:函数形式一致，只不过函数的实现部分有所差异
        def fun(self):
            #需求：需要使用父类中的功能，但是在父类功能的基础上添加新的功能
            #在子类函数中调用父类中的函数
            super(Cat,self).fun()
            print("Cat类中的fun")     #【就近原则】
    
    class Dog(SmallAnimal):
        pass
    
    
    c = Cat()
    c.fun()

Day13

一、多态

一种事物的多种表现形式

在Python中，父类的引用指向子类的对象

注意：继承是多态的前提

函数的重写其实就是多态的一种体现

    # 在继承关系中，如果一个实例的数据类型是某个子类，那么同时这个实例的数据类型也是其父类，但是反过来则不成立【多态的体现】

二、获取对象的信息

    import types
    # 1.type()
    print(type(None))		# NoneType
    print(type(123) == int)	# True
    print(type(abs) == types.BuiltinFunctionType)	# 判断是否是内置函数
    print(type(abs) == types.FunctionType)	# 判断是否是自定义函数
    print(type(lambda x:x) == types.LambdaType)	# 判断是否是匿名函数
    print(type(x for x in range(10))) == types.GeneratorType)	# 判断是否是生成器
    
    # 2.isinstance() 判断一个对象是否是某种类型
    print(isinstance(p,Person))
    print(isinstance(123,int))
    print(isinstance([1, 2, 3],(list, tuple)))
    
    # 3.dir():获取一个对象所有的属性和方法，返回值为列表，列表元素为函数名
    # listdir

三、类中属性和方法的分类

1.实例属性和类属性【类属性相当于java中的静态属性，所有实例拥有的共同特性（例如：人两条腿）】

区别：【面试题】

	a.定义的位置不同：类属性直接定义在类中，实例属性定义在构造函数中

	b.访问方式不同：类属性使用类名或者对象直接访问，实例属性使用对象访问

	c.在内存中出现的时机不同：类属性随着类的加载而出现，实例属性随着对象的出现而出现

	d.优先级不同：实例属性的优先级高于类属性



动态添加属性其实添加的是实例属性，只有当前对象拥有

注意：尽量避免将类属性和实例属性重名，因为实例属性会屏蔽掉类属性

	   实例属性随着对象的出现而出现

2.动态添加属性和方法

    __slots__:动态添加属性
    MethodT ype
    # 1.动态添加属性
    p = Person()
    p.height = 100
    # 2.动态添加函数
    def show(self):
      print("show")
    #p.fun = show
    #p.fun(p)
    # 类似于偏函数的用法，使用需要导入 from types import MethodType
    # 通过MethodType在现有函数show的基础上生成了一个新的函数，复制给了fun，此处fun就相当于成员函数的名字
    p.fun = MethodType(show,p)
    p.fun()

3.类方法和静态方法

类方法：在方法前面使用@classmethod装饰器的方法，类方法可以使用类名调用，也可以使用对象调用，但是，一般情况下，使用类名调用

注意：

	a.类方法必须有一个参数，一般写为cls，代表的是当前类

	b.类方法是属于整个类的，而不是某个对象，所以在类方法中禁止出现self

	c.在类方法中，可以直接通过cls调用类方法或者类属性

	d.在类方法中，可通过cls创建对象

静态方法：在方法前面使用@staticmethod装饰器的方法，静态方法可以使用类名调用，也可以使用对象调用，但是，一般情况下，使用类名调用；静态方法无必需参数

成员方法：第一个参数为self，self代表当前对象

【面试题】简述类方法，静态方法，成员方法以及普通方法之间的区别？

4.类的常用属性

    __name__	通过类名访问，得到的结果为类名字符串
    __dict__	通过类名访问，获取类的信息，包括类方法，静态方法，成员方法，以字典的形式返回
    			通过对象访问，获取的是该对象的属性和值，以字典的形式返回
    __bases__    通过类名访问，查看所有的父类	【基类】

四、运算符的重载overload

    print(p1 + p2)	# 底层相当于p1.__add__(p2)
    
    # 运算符重载【与函数重写相似】
    def __add__(self, other):
      return self.num + other.num

五、单例设计模式

1.概念

什么是设计模式？

	总结优化的处理问题的方案

	共23种设计模式（常用的：单例设计模式、工厂设计模式、代理模式、装饰者模式、生产者和消费者设计模式……）

什么是单例设计模式？

	在程序运行过程中，确保某个类只有一个对象【实例】，不管在哪一个模块运行，得到的都是同一个对象

	核心：一个类有且只有一个对象，这个对象需要应用到整个程序中

2.应用场景

实际应用：数据库连接池操作——>程序的多处地方都会用到连接池——>只需要一个连接池即可

3.使用

3.1使用模块

Python中的模块其实就是单例，因为模块在第一次导入时，会生成一个.pyc文件，当第二次导入时，会直接加载这个.pyc文件，而不是再次执行模块，因此，我们只要把相关的函数和数据定义到一个模块中，就可以得到一个单例（直接在模块中实例化一个对象然后导入即可实现单例）

3.2使用new

    #定义一个单例类
    class Singleton(object):
        #类属性，表示当前类的实例
        instance = None   
    
        #运算符重载【类方法】
        def __new__(cls, *args, **kwargs):
            #将类的实例和类属性关联起来
            #如果cls.instance为None，则创建实例，如果不为None的话，则说明已经创建完成，则直接获取
            if not cls.instance:
                cls.instance = super(Singleton,cls).__new__(cls,*args,**kwargs)
    
            return cls.instance
    
    #单例类
    class MyClass(Singleton):
        pass
    
    one = MyClass()
    two = MyClass()
    
    print(one == two)
    print(id(one) == id(two))
    print(one is two)

3.3使用装饰器

    #装饰器
    def singleton(cls):
        #类属性
        instance = {}
    
        #getInstance   currentInstance   defaultInstance
        def getInstance(*args, **kwargs):
            if cls not in instance:
                #添加键值对
                instance[cls] = cls(*args, **kwargs)
            return instance[cls]
    
        return getInstance
    
    @singleton
    class MyClass(object):
        pass
    
    m1 = MyClass()
    m2 = MyClass()
    
    print(m1 == m2)
    print(id(m1) == id(m2))
    print(m1 is m2)

3.4应用于类中【不严谨，不能私有化构造函数】

    class Foo(object):
        #1.声明一个私有变量,表示当前类的实例
        __v = None
    
        #2.给外界提供一个方法，用于返回当前类的对象，静态方法或者类方法
        @classmethod
        def getInstance(cls):
            if cls.__v:
                return  cls.__v
            else:
                cls.__v = Foo()
                return  cls.__v
    
    """f1 = Foo()
    f2 = Foo()
    
    print(f1 == f2)
    """
    
    # 懒汉式
    # 获取单例对象
    f1 = Foo.getInstance()
    f2 = Foo.getInstance()
    
    print(id(f1) == id(f2))
    
    # 弊端；在多线程中使用仍然会出现多个对象【添加多线程】
    # 多线程时可用饿汉式：先在类中直接实例化一个私有对象，然后在公有方法中直接返回这个对象

3.5元类实现

    # 元类实现
    class UpperAttrMetaClass(type):
        # init方法也可以实现
        def __init__(cls, *args, **kwargs):
            cls._instance = None
            super().__init__(*args, **kwargs)
    
        def __call__(cls, *args, **kwargs):
            if not cls._instance:
                cls._instance = super().__call__(*args, **kwargs)
            return cls._instance
    
    
    # 在代码执行到class FOO这里的时候 元类的__new__方法 和 __init__方法其实已经被执行
    class Foo(object, metaclass=UpperAttrMetaClass):
        pass
    
    
    f1 = Foo()
    f2 = Foo()
    print(id(f1))
    print(id(f2))

Day14

一、错误和异常

1.概念

语法错误和异常

2.异常的处理方式

两种方式：捕获异常、抛出异常

注意：在编程语言中，处理异常并不是真正的处理了，而是将错误做了屏蔽，不要影响其他代码的执行【障眼法】

2.1捕获之try-except-else

语法：

try:

	可能出现异常的代码

except 错误表示码 as e:

	语句1

except 错误表示码 as e:

	语句2

else:

	语句

说明：

	a.try块被称为检测区域，用来监测其中的代码是否有异常

	b.如果try中的代码块中没有异常，会直接执行else

	c.如果try中的代码存在异常，则和except语句进行匹配，执行相应的except代码块

	d.如果存在异常，但无可匹配的except，则直接跳出，异常仍然存在，后续内容依然无法执行

	e.else可有可无，根据需求决定

一个except可处理多个异常，将多个异常类型用括号括起来即可

	except (ZeroDivisionError, IndexError) as e:

except后也可什么异常类型都不跟，那样则出现异常就会执行except的代码块	except：

2.2捕获之try-except-finally

语法：

try:

	可能出现异常的代码

except 错误表示码 as e:

	语句1

except 错误表示码 as e:

	语句2

finally:

	语句

说明：和try-except-else的区别

	try块中代码无异常时才会执行else

	而finally中代码块是一定会被执行的，除非执行sys.exit()造成虚拟机宕机

好处：finally块中可以执行关闭文件，释放资源

	else和finally可以同时使用，但else必须在finally之前

3.抛出之raise【相当于java中的throw】

使用raise语句抛出一个指定的异常

raise唯一的一个参数指定了抛出的异常

    a = 0
    b = 1
    if a != 0:
        print(b/a)
    else:
        raise BaseException("分母为0")     # 一般用来抛出自定义异常

4.assert断言

assert（条件表达式），异常描述

好处：对于可能存在的异常，又不确定的情况下，使用断言，方便问题的查找

    def fun(num,divNum):
        #预言成功，则获取结果，预言失败，则打印异常的信息描述
        #换句话说，用来测试表达式，如果其返回值为假，则会触发异常
        #作用:跟try-except的作用类似,只是对可能存在异常的代码给用户一个提示
        #assert expression [, arguments]
    	#assert 表达式 [, 参数]
        assert (divNum != 0),"除数不能为0"
        return  num / divNum
    
    
    #print(fun(10,3))
    print(fun(20,0))

5.自定义异常

当系统的异常函数满足不了实际需求时，就需要自己来定义异常

实现方式：创建一个新的类，继承自Exception

步骤：

	a.书写构造函数，调用父类中的构造函数

	b.重写str函数，打印异常信息

	c.书写成员函数，用来处理自己的异常

    

二、枚举类enum

将枚举类型看做一种标签或者一系列常量的集合，常用来表示某些特定的有限的集合

举例：星期，月份，四季

    from enum import Enum, IntEnum, unique
    
    # enum标准库【Python3.4之后新增的特性】：提供了Enum类, IntEnum类, unique【@unique， 装饰器】
    # Enum:继承Enum类，普通的枚举类
    # IntEnum:继承IntEnum类，限定枚举成员必须为整数类型
    # unique：@unique,作为一个装饰器，限定枚举成员的值不可重复【变量和值均不可重复】
    
    #枚举类
    @unique
    class WEEKDAY(Enum):
        MON = 1
        TUES = 2
        WED = 3
        THUS = 4
        FRI = 5
        
    # ENUM的成员均为单例、常量，不可实例化、不可修改

三、文件读写

1.概述

Python中内置了文件读写的功能

核心：读写文件其实是请求操作系统打开一个文件对象【文件描述符】

2.读文件

步骤：

a.打开文件：open()

b.读取文件内容：read()

c.关闭文件：close()

注意：文件使用完毕之后一定要记得关闭，因为文件对象会占用操作系统的系统资源，并且操作系统在同一时间段内打开文件个数是有限制的

    # 一、打开文件
    f = open(path, "r", encoding = "gbk")
    '''
    open(path,flag[,encoding,errors])
    path:文件路径【绝对，相对】
    flag:打开文件的方式
    	r:只读
    	rb:以二进制格式打开，只读
    	r+：读写
    	w：只写，不存在直接创建
    	wb：以二进制格式写入，若文件已存在则覆盖，不存在则创建
    	a:append,如果一个文件中已经有内容存在，则会将新内容追加到原有内容的后面
    encoding：编码格式
    errors:错误处理
    注意：1.当以r的形式打开文件时：
    	如果文件格式为gbk的，可不加encoding
    	若为utf-8，则必须加
    	 2.二进制格式一般用来处理图片，视频音频
    	 如果文件以rb或者wb的形式打开的话，不能添加encoding，会报错
    	 encode():编码
    	 decode():解码
    '''
    # 二、读取文件
    # 1.读取全部内容
    s = f.read()
    # 2.读取指定字符数【若每行结尾有"\n"符号，也会被认为是字符】
    s = f.read(2)
    # 3.读取整行，不管该行有多少字符，判断依据是换行符
    s = f.readline()
    s = f.readline(3)	#读取一行中的前三个字符
    # 4.将所有内容全部读取出来，返回一个列表，一行为一个元素
    result = f.readlines()
    
    # 三、关闭文件
    f.close()
    
    # 预定义清理行为【自动close文件】
    with open("myfile.txt") as f:
        for line in f:
            print(line)

3.写文件

步骤：

a.打开文件

b.将信息写入缓存

c.刷新文件内部缓冲【提高写入效率】

d.关闭文件

    # 1.打开文件
    f = open(path,"w",encoding="utf-8")
    # 2.写入内容，将内容写入到缓冲区
    f.write("lalala")
    # 3.刷新缓冲区【当写入内容特别多时，会体现的较为明显】加速数据流动，保证缓冲区的流畅
    f.flush()
    # 4.关闭文件
    f.close()
    
    # 预定义清理行为【自动close文件】
    with open(path,"w",encoding="utf-8") as f:
        f.write("lalala")

4.编码和解码

字符串类型和字节类型转换过程

	字符串类型转换为字节类型：编码，encode

	字节类型转换为字符串类型：解码，decode

    str = "今天是个好日子 today is a good day"
    path = "file22.txt"
    
    with open(path,"wb") as f:
        result = str.encode("utf-8")
        print(result)
        f.write(result)
    
    with open(path,"rb") as f1:
        data = f1.read()
        print(data)
        print(type(data))
    
        newData = data.decode("utf-8")
        print(newData)
        print(type(newData))

5.练习：拷贝文件

    import  os
    
    """
    需求：实现文件内容的拷贝
    
    思路：
    源文件：读出来
    目标文件：写入到
    """
    
    def myCopy(srcPath,desPath):
        #1.判断源文件是否存在
        if not os.path.exists(srcPath):
            print("哥们，文件不存在，别拷贝了")
            return
    
        #2.判断源文件是否是文件类型
        if not os.path.isfile(srcPath):
            print("不是文件，无法拷贝")
            return
    
        #3.打开源文件和目标文件
        srcFile = open(srcPath,"rb")
        desFile = open(desPath,"wb")
    
    
        #4.获取源文件的大小
        size = os.path.getsize(srcPath)
    
        while size > 0:
            #读取
            content = srcFile.read(1024)
            #写入
            desFile.write(content)
    
            size -= 1024
    
        #5.关闭文件
        srcFile.close()
        desFile.close()
    
    
    myCopy("file11.txt","file22.txt")

Day14

一、操作csv文件

Comma Separated Values 逗号分隔值

.cvs是一种文本格式，特殊的纯文本文档

csv的读取和写入与普通文件不一样

作用：在不同的程序之间进行数据交互

注意：其中的每个数据以逗号隔开【注意：逗号必须是英文状态的】

在Windows下，csv文件可以通过记事本，excel，notepad++,editplus等打开

    # 读文件
    # 1.打开文件
    csvFile = open(path,"r")
    # 2.读取
    # 注意：将csvFile作为参数用
    reader = csv.reader(csvFile)
    print(reader)   # 可迭代类型
    print(type(reader))  # <class '_csv.reader'>
    
    # 写文件
    # 1.打开文件
    csvFile = open(path,"w",newline="")#默认写入数据的时候每条数据的中间会空一行
    #2.获取可迭代对象
    writer = csv.writer(csvFile)
    #3.获取需要写入内容的长度
    size = len(infoList)
    #4.循环写入数据
    for item in  range(size):
        #按行写入
        writer.writerow(infoList[item])
    #5.关闭文件
    csvFile.close()

二、高阶函数

高阶函数：函数a以函数b作为参数并返回b

1.map()

    """
    map(function, Iterator)
    function：函数
    Iterator：序列(列表)
    功能：将传入的参数依次作用于序列中的每一个元素，并把结果作为新的Iterator返回
    """ 
    list = map(lambda x:x**2, [1, 2, 3, 4])
    # [1, 4, 9, 16]

2.reduce()

    '''
    reduce(函数，[元素1，元素2，元素3……])
    作用：对列表中的元素进行累积
    用函数【有两个参数】先对集合中的元素1和元素2进行操作，得到的结果再和元素三作为参数传给函数，依次类推
    类似于递归
    '''
    from functools import reduce
    reduce(lambda x,y:x+y, [1, 2, 3, 4])	# 15
    reduce(lambda x,y:x * 10 + y, [1, 2, 3, 4])	# 1234

3.filter()过滤

    """
    filter过滤器(函数，列表)
    作用：根据一定的条件筛选列表中的元素
    简单来说：把传入的函数依次作用于列表中的每一个元素，根据返回的是True还是False决定是否保留该元素
    """
    filter(lambda x:x % 2 == 0, [1, 2, 3, 4])

4.sorted()排序

    list2 = sorted(list1)	# 默认升序排序
    sorted(list1,key=abs)	# 按照绝对值排序
    sorted(list1,reverse = True)	# 按照降序排序
    # 可以定义排序规则key = fun即可 fun须有返回值

三、单元测试和文档测试

1.单元测试

作用：为了对某一函数、模块、类进行正确性的校验工作

    # unitTest.mathFun编写代码
    def mySum(x,y):
        return  x + y + 1
    
    def mySub(x,y):
        return  x - y
    
    from unitTest.mathFun import mySum,mySub
    import unittest
    
    # 自定义一个类，继承自unittest.TestCase类
    class Test(unittest.TestCase):
        # 存在的意义：在开始检测和结束检测的时候自动被调用
        def setUp(self):
            print("start")
        def tearDown(self):
            print("end")
    
        # 测试对应的函数
        # 一般情况下，函数名test_需要被测试的函数名
        def test_mySum(self):
            # 使用断言：对函数的结果做一个预判
            self.assertEqual(mySum(1,2),3,"加法有误")
    
        def test_mySub(self):
            self.assertEqual(mySub(2,1),1,"减法有误")
    
    # 当主程序运行的时候，开始进行单元测试
    if __name__ == "__main__":
        unittest.main()

2.文档测试

作用：可以提取注释中的代码执行

需要导入模块doctest  严格按照Python交互模式下的写法

    import doctest
    def ceshi(x):
        """# 这是文档测试的内容
        >>> print(ceshi(2))
        1
        >>> ceshi(3)
        0
        """# End
        if x % 2 == 0:
            return 1
        else:
            return 0
    
    
    if __name__ == "__main__": doctest.testmod(verbose=True)

四、Turtle图形化界面

    import turtle
    # 设置屏幕大小、颜色
    turtle.screensize(800,600,"red")
    # 按照比例设置画面大小
    turtle.setup(width=0.6,height=0.6)
    
    turtle.pencolor("yellow")
    turtle.pensize(10)
    
    # 向着箭头的方向前进100px
    turtle.forward(100)
    
    turtle.speed(0.1)
    turtle.goto(-100,-200)
    #steps表示几边形，数值越大越接近圆，不写就是圆
    turtle.circle(100,steps=10) 
    # 启动窗口【画布】
    turtle.done()

    # 绘制五角星
    import turtle,time
    
    turtle.pensize(10)
    turtle.color("yellow")
    turtle.fillcolor("red")
    turtle.speed(1)
    
    # 开始填充
    turtle.begin_fill()
    
    for i in range(5):
        # 向前移动
        turtle.forward(200)
        # 按照顺时针移动,参数表示移动的角度,left表示逆时针
        turtle.right(144)
        # turtle.left(100)
    
    # 结束填充
    turtle.end_fill()
    
    time.sleep(2)
    
    turtle.penup()
    turtle.goto(-150,-120)
    turtle.color("purple")
    turtle.write("OVER",font=("宋体",50,"italic"))
    
    turtle.done()

Day15

一、破解密码

MD5加密

加密方法其实基本上都是利用的数学上的排列组合

二、正则表达式

1.概念

1.1什么是正则表达式

re

Regular Expression,在代码中简写regex，re

使用单个字符来描述、匹配一系列符合条件的字符串【搜索模式】

用处：

	a.可以用于文本搜索或者替换

	b.可以查询指定的数据

	c.分割比较复杂的字符串

1.2使用场景

用于验证邮箱，手机号格式，密码格式，银行卡验证，身份证号验证

爬虫时，使用正则抓取网络中执行的内容

第三方：Beautiful Soup,Lxml

1.3使用原则

主要是为了处理字符串，效率上远远不如str自带的函数高

2.正则表达式的匹配规则

    ----------匹配单个字符与数字---------
    
    .                匹配除换行符以外的任意字符
    
    0123456789是字符集合，表示匹配方括号中所包含的任意一个字符
    
    [good]           匹配good中任意一个字符
    
    [a-z]            匹配任意小写字母
    
    [A-Z]            匹配任意大写字母
    
    [0-9]            匹配任意数字，类似[0123456789]
    
    [0-9a-zA-Z]      匹配任意的数字和字母
    
    [0-9a-zA-Z_]     匹配任意的数字、字母和下划线
    
    [^good]          匹配除了good这几个字母以外的所有字符，中括号里的^称为脱字符，表示不匹配集合中的字符
    
    [^0-9]           匹配所有的非数字字符
    
    \d               匹配数字，效果同[0-9]
    
    \D               匹配非数字字符，效果同0-9
    
    \w               匹配数字，字母和下划线,效果同[0-9a-zA-Z_]
    
    \W               匹配非数字，字母和下划线，效果同0-9a-zA-Z_
    
    \s               匹配任意的空白符(空格，回车，换行，制表，换页)，效果同[ \r\n\t\f]
    
    \S               匹配任意的非空白符，效果同 \f\n\r\t
    
    
    
    
    
    --------------锚字符(边界字符)-------------
    
    ^     行首匹配，和在[]里的^不是一个意思
    
    $     行尾匹配
    
    \A    匹配字符串开始，它和^的区别是,\A只匹配整个字符串的开头，即使在re.M模式下也不会匹配它行的行首
    
    \Z    匹配字符串结束，它和$的区别是,\Z只匹配整个字符串的结束，即使在re.M模式下也不会匹配它行的行尾
    
    \b    匹配一个单词的边界，也就是值单词和空格间的位置
    
          
    
    \B    匹配非单词边界
    
    
    
    -------------------匹配多个字符------------------------
    
    说明：下方的x、y、z均为假设的普通字符,n、m（非负整数），不是正则表达式的元字符
    
    (xyz)    匹配小括号内的xyz(作为一个整体去匹配)
    
    x?       匹配0个或者1个x
    
    x*       匹配0个或者任意多个x（.* 表示匹配0个或者任意多个字符(换行符除外)）
    
    x+       匹配至少一个x
    
    x{n}     匹配确定的n个x（n是一个非负整数）
    
    x{n,}    匹配至少n个x
    
    x{n,m}   匹配至少n个最多m个x。注意：n <= m
    
    x|y      |表示或，匹配的是x或y
    
    
    
    ---------------特殊-------------------
    
    '''
    
    *?   +?   x?  最小匹配，通常都是尽可能多的匹配，可以使用这种解决贪婪匹配
    
    (?:x)        类似(xyz),但不表示一个组

    # 最简单的正则用法
    import re
    
    str = input("请输入：")
    pattern = re.compile("\d+")
    
    print(pattern.match(str))
    
    # 从控制台输入一串字符串，编写函数，返回字符串中数字的和（输入abcd12ef34   返回46）
    import re
    
    
    def add_num():
        str = input("请输入一串字符串：")
        res = re.findall(r"\d+", str)
        sum = 0
        for i in res:
            sum += int(i)
        print(sum)
    
    
    add_num()
    



Day16

一、网络编程

1.网络编程基础

计算机网络：把分布在不同区域的计算机通过专门的设备使用通信线路连接起来，从而会形成一个庞大的网络系统，不同的计算机之间就可以进行信息的传递

网络编程：在同一个网络中不同机器之间进行通信

2.计算机之间需要通信的条件

三要素：ip地址，端口，协议

2.1ip地址

1>概念

	互联网地址（Internet Protocol Address），是会连设备和互联网之间的标识，在同一个网段中，ip地址是唯一的

	ip地址是数字型的，是一个32位整数，通常将其分为4个8位的二进制，每8位用圆点隔开，并且将8位的二进制转换为0~255之间的十进制，例如：10.0.127.108

2>分类

	形式分类

		ipv4：由4个字节组成，分成4段

		ipv6：由6个字节组成，分为6段

	功能分类：

		A类：保留给政府机构，1.0.0.1~126.255.255.254

		B类：分配给中小型企业，128.0.0.1~191...

		C类：分配给任何有需要的个人，192...~223...

		D类：用于组播【一种数据的传输方式】，224...~239...

		E类：用于实验，240...~255...

		127.0.0.1  回送地址，一般指本机ip，localhost，一般用于测试

总结：ip地址可以唯一的确定网络上的一个通信实体，但是一个通信实体可以有多个应用程序同时提供网络服务，此时还需要端口

2.2端口

1>概念

	数据的发送和接收都需要通过端口初入计算机，端口号是唯一标识通信实体上的应用程序

	注意：同一台机器上不能两个程序占用同一个端口，端口号：0~65535

2>分类

	a.公认端口：0~1023

	b.注册端口：1025~49151

	c.动态端口或者私有端口：1024~65535

3>常用的端口

	mysql：3306

	oracle：1521

	tomcat：8080

	qq：4000

2.3网络协议

网络协议：只要连接到网络的设备，相互之间遵循同一种网络协议，才能够进行数据交互

1.TCP/IP协议

互联网协议：负责两台计算机之间建立可靠的【保证数据安全的到达对方】，可连接【面向连接，三次握手】的通信

2.TCP协议

Transmission Control Protocol，传输控制协议，基于字节的传输层通信协议

特点：

	a.安全的【确保接收方完全正确的获取发送方发送的全部数据】

	b.面向连接的【数据传输必须要建立连接，连接的过程中需要时间】

	c.数据传输效率低

	d.传输的数据大小有限制，一旦建立连接，双方可以通过指定的格式发送数据

面向连接：三次握手

	a.客户端向服务端发送一个请求

	b.服务端收到请求之后，给客户端一个响应

	c.客户端收到服务端的响应之后，回复给服务端一个确认信息

举例：

	客户端-服务端：你好啊，在不

	服务端-客户端：在啊。咋了

	客户端-服务端：好的，那我开始说话了

	【tcp建立完成了】

说明：

	使用tcp来实现数据的发送和接收需要发送方和接收方，但是两个通信实体之间没有明确的客户端和服务端之分，在两个通信实体建立连接之前，必须有一个通信实体做出主动姿态，被称为客户端

Socket通信

Socket：套接字，作用：可以发送和接收数据

Socket必须知道目标计算机的ip地址，端口号，指定协议类型【TCP】

通信的两端都有Socket

注意：

a.同一个端口号，如果被一个socket绑定之后，则其他socket将不能绑定

b.tcp创建的连接是双向通道，谁先发消息谁就是客户端

    #客户端的流程描述
    
    
    #导入模块，socket中内置了数据交互的功能
    import socket
    
    
    #1.创建一个socket的对象
    skt = socket.socket()
    
    #2.客户端打开socket，根据服务器ip地址和端口号试图连接服务器socket
    #注意：此处的ip地址和端口号是目标计算机的
    ip_port = ("10.127.127.1",9996)
    """
    skt.connect(address)
    连接到address处的套接字，一般address的格式为元组（hostname,port），如果连接出错，返回socket.error错误
    """
    skt.connect(ip_port)
    
    #3.客户端向socket写入信息
    """
    skt.sendall(bytes(string),[flag])
    注意：需要将字符串类型转换为字节类型
    将string中的数据发送到套接字，成功返回None，失败则抛出异常
    工作原理：内部递归调用send，直到将所有的内容全部发送出去
    """
    skt.sendall(bytes("我喜欢你",encoding="utf-8"))
    
    
    #4.客户端关闭
    skt.close()

    #服务端的流程描述
    
    import  socket
    
    #1.创建一个socket对象
    server = socket.socket()
    
    #2.绑定ip地址和端口号
    #注意：此处的ip地址和端口号需要和客户端中得保持一致
    ip_port = ("10.0.127.108",9997)
    server.bind(ip_port)
    
    #3.服务端持续监听端口号的请求，随时准备接受客户端的连接
    """
    server.listen(backlog)
    开始监听传入连接，backlog指定在拒接连接之前，可以挂起的最大连接数量
    backlog一般取值5，表示内核已经连接到了请求
    这个值最好不要无限大
    """
    server.listen(5)
    
    print("server waiting.......")
    
    #4.连接
    """
    服务端接收到了客户端发来的请求，开始接收请求
    此时server会进入阻塞状态【accept()函数一直等到客户端返回连接信息】
    #注意：返回conn,address,conn表示新的套接字，可以接收和发送数据，address是连接的客户端的地址
    """
    conn,address = server.accept()
    
    print("连接成功")
    
    #5.服务器读取信息
    """
    conn.recv(size)
    从连接上的客户端套接字中读取数据，数据以字符串形式返回，size表示一次可以接收的数据的大小
    """
    client_data = conn.recv(1024)
    #将字节类型转换为字符串类型
    print(address + "发送来消息")
    print(str(client_data,"utf-8"))
    
    
    #6.服务端关闭
    server.close()

3.UDP协议

User Datagram Protocol，用户数据包协议，提供面向无连接的不可靠的信息传输服务

特点：

	a.不安全【发送方只负责将信息发送出去，数据能不能达到对方，或者到达对方的信息是否正确，都不做任何保证】

	b.无连接的【进行消息发送之前，无需进行发送方和接收方之间的连接】

	c.速度快

	d.大小是有限制的，每个数据包的大小必须限制在64k以内

二、发邮件和发短信

1.发短信

互亿无限

    # !/usr/local/bin/python
    # -*- coding:utf-8 -*-
    import http.client
    import urllib
    
    host = "106.ihuyi.com"
    sms_send_uri = "/webservice/sms.php?method=Submit"
    
    # 用户名是登录用户中心->验证码短信->产品总览->APIID
    account = "C11345804"
    # 密码 查看密码请登录用户中心->验证码短信->产品总览->APIKEY
    password = "735d183ae02189f678c26800ac19b03a"
    
    
    def send_sms(text, mobile):
        params = urllib.parse.urlencode(
            {'account': account, 'password': password, 'content': text, 'mobile': mobile, 'format': 'json'})
        headers = {"Content-type": "application/x-www-form-urlencoded", "Accept": "text/plain"}
        conn = http.client.HTTPConnection(host, port=80, timeout=30)
        conn.request("POST", sms_send_uri, params, headers)
        response = conn.getresponse()
        response_str = response.read()
        conn.close()
        return response_str
    
    
    if __name__ == '__main__':
        mobile = "18501970795"
        text = "您的验证码是：121254。请不要把验证码泄露给其他人。"
    
        print(send_sms(text, mobile))

2.发邮箱

    import smtplib
    from email.mime.text import  MIMEText
    from email.mime.multipart import  MIMEMultipart   #附件
    from email.mime.application import  MIMEApplication
    
    username = "18501970795@163.com"
    password = "yang0122"
    sender = username
    receivers = ",".join(["1490980468@qq.com"])
    
    #创建一个关于附件的对象
    msg = MIMEMultipart()
    msg["From"] = sender
    msg["To"] = receivers
    msg["Subject"] = "带有附件的文本"
    
    #设置文本部分
    text = MIMEText("today is a good day")
    msg.attach(text)
    
    
    #设置附件部分
    file = open("dog.jpg","rb")
    imagepart = MIMEApplication(file.read())
    imagepart.add_header("Content-Disposition","attachment",filename="dog.jpg")
    msg.attach(imagepart)
    
    try:
    
        client = smtplib.SMTP()
        client.connect("smtp.163.com")
        client.login(username,password)
        client.sendmail(sender,receivers,msg.as_string())
    
        client.quit()
    
        print("over")
    
    except BaseException as e:
        print(e)

Day17

一、反射

通过字符串的形式，导入模块，去模块中寻找指定的函数，去对象中操作成员

反射机制：基于字符串的事件驱动

    p = Person("张三",10)
    """
    getattr(object,name,default)   获取某个对象的属性对应的值
    object:指定一一个对象
    name:对应属性的字段名    "name"   "age"
    default:如果指定的字段不存在的话，则指定一个默认值
    """
    value = getattr(p,"name","hello")
    print(value)
    
    #print(p.__age)
    
    
    #_Person__age   类名__私有变量的变量名
    value1 = getattr(p,"_Person__age","yreuyr")
    print(value1)
    
    
    #获取成员方法
    f1 = getattr(p,"show")
    print(f1)  #<bound method Person.show of <__main__.Person object at 0x00000272D79270F0>>
    print(p.show)
    
    p.show()
    f1() #此处的f1就相当于是show
    
    
    #获取类方法
    f2 = getattr(Person,"classFun")
    print(f2)   #<bound method Person.classFun of <class '__main__.Person'>>
    
    Person.classFun()
    f2()
    
    
    #hasattr；判断指定对象中有没有指定的成员
    print(hasattr(p,"show"))
    
    
    #setattr：给指定字段进行赋值
    setattr(p,"name","yangyang")
    print(getattr(p,"name"))
    
    #delattr:删除指定对象中的指定属性
    #del p
    # delattr(p,"name")
    # del p.name

    # 应用在模块中
    import text
    content = input("请输入字段：")
    
    #判断指定的内容是否存在
    res = hasattr(text,content)
    
    if res:
        f = getattr(text,content)   #text:p   content:name
        print(f())	# 执行模块中方法
    else:
        print("该类型不存在")

二、图形界面和游戏开发

GUI是图形用户界面的缩写,图形化的用户界面对使用过计算机的人来说应该都不陌生

Python默认的GUI开发模块是tkinter

基本上使用tkinter来开发GUI应用需要以下5个步骤：

    a.导入tkinter模块中我们需要的东西。
    
    b.创建一个顶层窗口对象并用它来承载整个GUI应用。
    
    c.在顶层窗口对象上添加GUI组件。
    
    d.通过代码将这些GUI组件的功能组织起来。
    
    e.进入主事件循环(main loop)。



    #实现动画效果
    
    #在窗口中绘图
    
    import pygame
    
    def main():
    #必须初始化
    pygame.init()
    #设置窗口尺寸
    screen = pygame.display.set_mode((800,600))
    #设置当前窗口的标题
    pygame.display.set_caption("大球吃小球")
    
    #定义圆心横纵坐标的变量
    x,y = 50,50
    
    running = True
    
    #开启一个事件循环处理发生的事件
    while running:
    #从消息列表中获取事件并对事件作出处理
    list = pygame.event.get()
    for event in list:
    #当事件为退出的时候，则执行退出
    if event.type == pygame.QUIT:
    running = False
    
    # 设置窗口的背景色（RGB：三原色）
    # 三原色的取值范围：0~255，（0,0,0）表示黑色 (25,255,255)白色
    screen.fill((255, 255, 255))
    # 在窗口中绘制圆
    # 屏幕 颜色 圆心位置 半径，（0表示实心圆，1表示空心圆）
    pygame.draw.circle(screen, (255, 0, 0), (x, y), 30, 0)
    # 刷新当前窗口
    pygame.display.flip()
    
    #每隔50毫秒就改变小球的位置
    pygame.time.delay(50)
    
    x += 5
    y += 5
    
    
    if __name__ == "__main__":
    main()




