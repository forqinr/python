1.转义字符
  - `\n`
  - `\t`
  - `\\`
  
2.多行显示
  - ‘使用`r'...'`形式‘
  - 使用三个单引号
  
3.Unicode支持
  - python只支持ASCII码
  - 如果要使用unicode码，需要在字符串前加u指明。如：`u'中文'`
  - u和r可以关联使用，表示字符串中的换行等
  - 如果中文字符串在Python环境下遇到 UnicodeDecodeError，这是因为.py文件保存的格式有问题。可以在第一行添加注释
    `# -*- coding: utf-8 -*-`
	目的是告诉Python解释器，用UTF-8编码读取源代码。然后用Notepad++ 另存为... 并选择UTF-8格式保存。

4.布尔运算
  - 布尔值有True，False两种
  - 逻辑运算符是and，or，not
  - 在Python中，布尔类型还可以与其他数据类型做 and、or和not运算。Python把0、空字符串''和None看成 False，其他数值和非空字符串都看成 True
  - python中的布尔计算遵循短路原则。第一个值能决定表达式的值时，就不再计算后一个表达式。
    `a = 'python'
     print 'hello,', a or 'world'
	 # hello,python

     b = ''
     print 'hello,', b or 'world'
	 #hello,world`
	 
5.list
  - 内置数据类型
  - 因为是动态语言，所以list中的数据类型不用是一种
  - list可以赋值给一个对象
  - 直接用方括号阔住即完成了申明和赋值
  - 元素引用同java的数组，直接用方括号内一个下标索引值即可
  - 下标从0开始索引
  - 越界会报错IndexError
  - python的-1表示列表的最后一个元素，即array.length-1。这个和redis里获取列表的最后一个元素是一样的语法。`list[list.length-1]`同`list[-1]`
  - python中，可以倒序索引列表。-1表示最后一个，-2表示倒数第二个，以此类推。注意不要下标越界。
  - 向列表最后插入一个元素，用`append(element)`方法。如果想向指定的位置插入元素，用`insert(index,element)`
  - 删除最后一个元素`L.pop()`，删除指定位置的元素`L.pop(index)`。删除后，会返回被删除的元素
  - python交换对象不需要中间变量。如交换list的两个元素的位置，只需要`L[0],L[2]=L[2],L[0]`
  
5.tuple
  - tuple一旦创建完毕，就不能修改了
  - tuple（元组）创建使用小括号表示有序序列
  - tuple的引用不能变，里面的元素也不能变。没有append，pop等方法。
  - 正是因为用()定义单元素的tuple有歧义，所以 Python 规定，单元素 tuple 要多加一个逗号“,”，这样就避免了歧义。
  - `t = (1,)`
  - 如果tuple指向一个可变的元素，如list，list内的元素还是可以变得，只是tuple对list对象的指向没变而已。这就造成了一个内容可变的假象。
  - `t = ('a', 'b', ['A', 'B'])`，这种元组，A和B是可以变的
  - 想让元组内的内容也不变，就使用不可变的元素。如用元组中的元组对象替换list对象。