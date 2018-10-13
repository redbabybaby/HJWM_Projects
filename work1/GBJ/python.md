## Python基础：

### 数据类型及变量

Python的整数没有大小限制，而某些语言的整数根据其存储长度是有大小限制的，且整数一定是精确的
Python的浮点数也没有大小限制，但是超出一定范围就直接表示为inf（无限大）

### 字符串和编码

Python 3的字符串使用Unicode，直接支持多语言
当str和bytes互相转换时，需要指定编码。最常用的编码是UTF-8
格式化字符串的时候，可以用Python的交互式环境测试，方便快捷。

### 使用list和tuple

list和tuple是Python内置的有序集合，一个可变，一个不可变，可嵌套使用，注意变与不变是指针的概念

### 条件判断

条件判断可以让计算机自己做选择，Python的if...elif...else很灵活。缩进的方式很好用，省略冗余操作

### 循环

循环是让计算机做重复任务的有效的方法。break语句可以在循环过程中直接退出循环，而continue语句可以提前结束本轮循环

### 使用dict和set

dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储
set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key，set可以看成数学意义上的无序和无重复元素的集合

## 函数

### 调用函数

调用Python的函数，需要根据函数定义，传入正确的参数

### 定义函数

函数体内部可以用return随时返回函数结果；
函数执行完毕也没有return语句时，自动return None。
函数可以同时返回多个值，但其实这只是一种假象，Python函数返回的仍然是单一值，其实就是一个tuple，但是，在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。

### 函数的参数

在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数。

### 递归函数

使用递归函数的优点是逻辑简单清晰，缺点是过深的调用会导致栈溢出
针对尾递归优化的语言可以通过尾递归防止栈溢出。尾递归事实上和循环是等价的，没有循环语句的编程语言只能通过尾递归实现循环
Python标准的解释器没有针对尾递归做优化，任何递归函数都存在栈溢出的问题

## 高级特性

### 切片

有了切片操作，很多地方循环就不再需要了。Python的切片非常灵活，一行代码就可以实现很多行循环才能完成的操作

### 迭代

任何可迭代对象都可以作用于for循环，包括我们自定义的数据类型，只要符合迭代条件，就可以使用for循环

### 列表生成式

运用列表生成式，可以快速生成list，可以通过一个list推导出另一个list

### 生产器

在for循环的过程中不断计算出下一个元素，并在适当的条件结束for循环。对于函数改成的generator来说，遇到return语句或者执行到函数体最后一行语句，就是结束generator的指令，for循环随之结束。
在Python中，可以简单地把列表生成式改成generator，也可以通过函数实现复杂逻辑的generator

### 迭代器

可以使用isinstance()判断一个对象是否是Iterable对象
可以使用isinstance()判断一个对象是否是Iterator对象
生成器都是Iterator对象，但list、dict、str虽然是Iterable，却不是Iterator。
把list、dict、str等Iterable变成Iterator可以使用iter()函数
凡是可作用于for循环的对象都是Iterable类型 	
凡是可作用于next()函数的对象都是Iterator类型，它们表示一个惰性计算的序列

## 函数式编程

### 高阶函数

把函数作为参数传入，这样的函数称为高阶函数，函数式编程就是指这种高度抽象的编程范式。

#### map/reduce

map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回
reduce把结果继续和序列的下一个元素做累积计算

#### filter

filter()的作用是从一个序列中筛出符合条件的元素。由于filter()使用了惰性计算，所以只有在取filter()结果的时候，才会真正筛选并每次返回下一个筛出的元素

#### sorted

sorted()排序的关键在于实现一个映射函数
还可以接收一个key函数来实现自定义的排序

### 返回函数

### 匿名函数

### 装饰器

### 偏函数

