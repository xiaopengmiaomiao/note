# day02

chr(i)函数显示字符i 的unicode编码值

ord(i)显示unicode编码值i对应的字符

1.字符串几种常见的方法及理解

s.center()方法，顾名思义是将一个字符串居中对齐，它肯定会有两个参数，为了让我们方便，它会设计宽度的大小，以及左右两边需要填充的东西，默认是填充空格

s.count()方法是将一个字串在s中的计数结算出来，肯定第一个参数是需要查找的字符串。还有肯定需要我们可以自行决定在s中那一段来查找，那么后面肯定会有两个参数start,end

s.find()方法，在s中寻找一个字符串，与上面的count方法类似，第一个参数为想要寻找的，第二第三个参数为start,end

s.strip()函数 它可以去掉空白字符，然后再返回结果，那么就肯定有s.lstrip() s.rstrip，来去掉左右的空白字符

s.replace()方法，它的意思很明显，是将里面的老字符串替换为新字符串，那么前两个参数就是old new,当然有时候我们希望替换的个数是我们想要的，所以他的最后一个参数就是个数，替换到多少就不替换了。

s.upper() s.lower()都是将s.中的英文字符替换为大小写，只替换英文字符

s.title()因为英语里的标题都是首字符大写，所以他就将一个字符串中的单词首字母大写，和英文标题一样

字符串中肯定有方法来判断字符串是否全为字母，数字，大写，小写。可以自己去查

3.格式化字符串

格式化字符串包括%d,%s，它们的意思就相当于在一个字符串中占了一个位置,%s %d不需要加'' 然后通过后面加%(内容)来赋值，就是通过后面加% 和一个元组

格式化字符还有一个重要的意义就是它可以将数据进行转化，比如%s 是将后面的对象转化为str()，%c就相当于将后面的unicode整数转化为相应的字符 就相当于执行了函数chr()

当然还有%o 转化为八进制，%x转化为十六进制小写，%X转化为十六进制大写 %e %E会转化为指数形式 只是表示有e 和E区别 %f %F都会转为为十进制浮点型，%g和%G是自动转为（也就是看情况)他将f和e结合，看情况是转化为浮点数还是指数形式,g和G也就是后面的表示e和E区别 浮点数表示无区别 真的是将二者完美结合

犯的错误

1.判断一个字符串中有多少个空字符

我的想法是用if 和+=1的方法 但其实用count方法计数就行了，需要对方法形成一定的理解才能运用到实际中

