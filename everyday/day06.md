# day06

1.当使用if语句时，判断是不是为空什么，一点要想到，True,not True,False,not False组合，因为python中几乎所有都是表达式，都能表示真假，这样就会方便很多

2.注意得是列表的reverse方法是直接改变列表，和append等一样，它不会返回什么。我用print(a.reverse())返回的就是None。a=a.reverse() 也不是让a 翻转过来，而是把列表a变成了None 直接和append一样调用就行了，改变后再输出

3.split()方法是将字符串里得任一字符作为分隔符，分出多个对象，然后将它们组合成一个列表 后面可接参数，如果参数为空，肯定就是默认字符串中的空白字符，不仅仅是空格，是空白字符

   join()方法是将可迭代对象（不仅仅是列表)中的**字符串**（也就是相当于用for迭代出来的每个对象必须是字符串形式)，用一个字符或字符串来连接起来，形成一个字符串    ' '.join

在字符串中\\ \ 表示的是一个\ 它和\d 都一样

4.很重要

```python
>>> L=[1,2]
>>> a=[3,4,L] 
>>> b=a.copy()#浅拷贝
>>> a[2][0]=3.14
>>> a
[3, 4, [3.14, 2]]
>>> b
[3, 4, [3.14, 2]]
>>> L
[3.14, 2]
>>> id(a)
140278076392520
>>> id(b)
140278076392328
>>> id(a[0])
10914432
>>> id(b[0])
10914432
```

列表中每个a[0],a[1]等都是索引变量，它会绑定对象，而地址是存储对象的，实际上那个a=[3,4,L],这个列表的结构是a这个变量绑定这个列表结构对象，然后列表里面有a[0],a[1],a[2]三个变量，分别绑定了对象3，4，和L。

b=a.copy()是一个浅拷贝，它只是拷贝了列表的第一层结构，第一层结构也就是列表的框架和三个变量a[0],a[1],a[2],而这三个变量指向的还是那三个对象（变量如指针，指向的是对象的id)

a[2]【0】=3.14就是将指向的L列表改变了，这样的话a,b对应的都会改变。正是由于列表是可变对象，所以在复制一个结构的时候，如果这个结构里面有列表等可变对象，那么一定不能使用浅拷贝，对于不可变对象可以，反正只要赋值变化，就会创建新的对象，原来那个地址绑定的不可变对象是无论如何都不会发生变化的。

深层拷贝也就是将所有的变量还有需要绑定的所有对象也都拷贝了一份，变量再重新指向这些对象

深拷贝：

import copy

b=copy.deepcopy(a)

值得思考的是 深拷贝只对可变对象进行复制，这就刚好为上面的问题提出了解决的方案，对于不可变的对象，没有必要去进行拷贝，因为id对应的值不变

5.列表推导式的嵌套，每层的结构都是[值 for i in 可迭代对象 if..]，直接第二层就是接在第一层的后面。形成嵌套

犯的错误：我错认为列表以及字符串中的首个元素，对象的id就是整个列表的id，实际上，存储地址的id是他的首个字节，而非首个对象或元素



