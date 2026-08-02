# **<mark>python基础题</mark>**

## **<mark>第一题</mark>**

编写一个程序，找到2000年至3200年（包括在内）中所有可被7整除但不能被5整除的所有数字，得到的数字按逗号分隔，打印在一行上。

```
for i in range(2000,3201):
    if i%7==0 and i%5!=0:
        print(i,end=",")
```

## **<mark>第二题</mark>**

编写一个可以计算给定数阶乘的程序，结果以逗号分隔，打印在一行上；

```
l = map(int, input("请输入数字").split())
def function(x):
    if x < 2:
        return 1
    else:
        return x * function(x-1)
result = []
for i in l:
    result.append(str(function(i)))
print(",".join(result))  
#此程序可以一次输入多个数字并计算其阶乘
```

## **<mark>第三题</mark>**

使用给定的整数n，编写程序生成一个包含（i，ixi）的字典，该字典包含从1到n之间的整数（两者都包含），然后打印字典。假设向程序提供以下输入:8 则输出为:{1:1，2:4，3:9，4:16，5:25，6:36，,7:49，8:64}

```
l={}
n=int(input("请输入数字："))
for i in range(1,n+1):
    l.update({i:i*i})
print(l)
```

## **<mark>第四题</mark>**

编写一个程序，该程序接收控制台以逗号分隔的数字序列，并生成包含每个数字的列表和元组，假设，向程序提供以下输入：34岁,67年,55岁,33岁,12日,98年;则输出为:['34'，'67'，'55'，'33'，'12'，'98] ('34'，'67'，'55'，'33'，'12'，'98')

```
import re
l=input("")
res=re.findall(r"\d+",l)
print(res,end="")
print(tuple(res))
```

## **<mark>第五题</mark>**

定义一个至少有两个方法的类：一、getString：从控制台输入获取字符串；二、

printString：将获取的字符串中的小写字母转为大写字母，并打印整个字符串，并写出简单的测试函数来测试类方法。

```
class Function:

    def getString(self):
        self.l = input("enter string:")  #使用实例属性

    def printString(self):
        print(self.l.upper())
a = Function()
a.getString()
a.printString()  
```

## **<mark>第六题</mark>**

编写一个程序，根据给定的公式计算并打印值：

$$
Q=\sqrt{\frac{2 \cdot C \cdot D}{H}}
$$

其中，假设C=50。H=30。D是一个变量，它的值应该以逗号分隔的序列输入到程序中。例：程序的输入序列为（以逗号分隔）：100，150，180；则程序输出为：18，22，24；

```
l = map(int, input("请输入数字").split(","))
c=50
h=30
result = []
for d in l:
    result.append(str(int(((2*c*d)/h)**0.5)))
print(",".join(result))
```

## **<mark>第七题</mark>**

编写一个程序，X，Y作为输入，生成一个二维数组，数组的第i行和第j列的元素值应该是i×j。注意：i=0,1..X-1;j=0，1，Y-1。假设，程序输入3,5；则程序输出为：[[0,0,0,0,0],[0,1,2,3,4],[0,2,4,6,8]]；

```
l = map(int, input("请分别输入x和y值").split(","))
x = next(l)
y = next(l)
a = []
for i in range(x):
    row = []
    for j in range(y):
        row.append(i*j)
    a.append(row)
print(a)
```

## **<mark>第八题</mark>**

编写一个程序，以逗号分隔的单词序列作为输入，按照字母顺序对每个单词进行排序，并通过逗号分隔的序列来打印单词。假设向程序输入：without,hello,bag,world；则输出为：bag,hello,without,world;

```
l = input("请输入字符串").split(",")
print(",".join(sorted(l))) 
```

## **<mark>第九题</mark>**

编写一个程序，接收一行序列作为输入，并在将句子中的所有字符大写后打印行。

```
l = input("请输入字符串")
print(l.upper())
```

## **<mark>第十题</mark>**

编写一个程序，以一系列空格分隔的单词作为输入，并在删除所有重复的单词后，按字母顺序排序后打印这些单词。假设向程序输入:hello world and practice makes perfect and hello world again 则J输出为:again and hello makes perfect practice world

```
l=set(input("请输入序列：").split(" "))
print(" ".join(sorted(l)))
```

## **<mark>第十一题</mark>**

编写一个程序，接收一系列以逗号分隔的4位二进制数作为输入，然后检查它们是否可被5整除，可被5整除的数字将以逗号分隔的顺序打印。例：0100,0011,1010,1001那么输出应该是：1010

```
l=input("请输入二进制序列：").split(",")
l1=[]
for i in l:
    if int(i,2)%5==0:
        l1.append(i)
print(",".join(l1))
```

## **<mark>第十二题</mark>**

编写一个程序，找到1000到3000之间并且所有位数均为偶数的所有数字，比如2000，2002等；获得的数字都以逗号分隔的顺序，打印在一行上。

```
l=[]
for i in range(1000,3001):
    if i%2==0 and int(i/10)%2==0 and int(i/100)%2==0 and int(i/1000)%2==0:
        l.append(str(i))
print(",".join(l))
```

## **<mark>第十三题</mark>**

编写一个接受句子并计算字母和数字的程序。假设程序输入：Helloworld！123则输出应该是：字母10数字3

```
import re
l=input("请输入字符串：")
character = len(re.findall("[a-zA-Z]", l))
number = len(re.findall(r"\d", l))
print(f"字母{character} 数字{number}")
```

## **<mark>第十四题</mark>**

编写一个接收句子的程序，并计算大写字母和小写字母的数量。假设为程序提供了以下输入：Hello world！则输出应该是：UPPER CASE 1;LOWER CASE9

```
import re
l=input("请输入字符串：")
uppercase = len(re.findall("[A-Z]", l))
lowercase = len(re.findall("[a-z]", l))
print(f"UPPER CASE {uppercase};LOWER CASE {lowercase}")
```

## **<mark>第十五题</mark>**

编写一个程序，计算a+aa+aaa+aaaa的值，给定的数字作为a的值。假设为程序提供了以下输入：9；输出应该是：11106

```
str=input("请输入数字：")
print(int(str)+int(str*2)+int(str*3)+int(str*4))
```

## **<mark>第十六题</mark>**

使用列表推导输出列表中的每个奇数，该列表由一系列逗号分隔的数字输入。

```
nums = [int(i) for i in input("请输入数字串：").split(",") if int(i) % 2 != 0]
print(nums)
```

## **<mark>第十七题</mark>**

您需要编写一个程序，按升序对（名称，年龄，高度）元组进行排序，其中name是字符串，age和height是数字，元组由控制台输入。
排序标准是：
1：根据名称排序：
2：然后根据年龄排序；
3：然后按分数排序。
优先级是name>age>height。
如果给出以下元组作为程序的输入：
Tom,19,80;John,20,90;Jony,17,91; Jony,17,93; Json,21,85

```
people = input().split(";")
#此时people=['Tom,19,80','John,20,90','Jony,17,91','Jony,17,93','Json,21,85']
people = [
    (name, int(age), int(height))
    for name, age, height in (p.split(",") for p in people)
]
#后面的生成器会依次产生
#['Tom','19','80']
# ['John','20','90']
# ['Jony','17','91']......
#最后元组解包，经过循环后
# people = [
#     ('Tom',19,80),
#     ('John',20,90),
#     ('Jony',17,91)
#     ........
# ]
people.sort(key=lambda x:(x[0],x[1],x[2]))  #排序
print(people)
```

## **<mark>第十八题(较难)</mark>**

使用生成器定义一个类，该生成器可以在给定范围0和n之间迭代可被7整除的数字。

```
class Number:
    def __init__(self, n):
        self.n = n
        self.x = 0

    def __iter__(self):
        return self

    def __next__(self):
        while self.x <= self.n:
            result = self.x
            self.x += 1

            if result % 7 == 0:
                return result

        raise StopIteration

l = Number(int(input()))
print(type(l))
print(",".join(map(str,l)))
```

## **<mark>第十九题</mark>**

问题：编写一个程序，来计算每个单词出现的频率，按字母顺序对键进行排序后输出。
假设程序输入：
New to Python or choosing between Python 2 and Python 3? Read Python 2 or Python 3.
则输出应该是：
2:2
3.:1
3?:1
New:1
Python:5
Read:1
and:1
between:1
choosing:l
or:2
to:1

```
d=input().split(" ")
c=list(set(d))
c.sort()
for i in c:
    print(f"{i}:{d.count(i)}")
```

## **<mark>第二十题</mark>**

问题：写一个可以计算数字平方值的方法。
提示：使用**运算符

```
a=int(input("请输入数字："))
print((lambda x:x**2)(a))
```

## **<mark>第二十一题</mark>**

问题：Python有许多内置函数，如果不知道如何使用它，可以在线阅读文档或查找一些书籍。请编写一个程序来打印一些Python内置函数文档，例如abs()，int()
提示：内置文档方法是doc:

```
def abs(x):
    if x > 0:
        return x
    else:
        return -x
x=int(input("请输入数字:"))
print(abs(x)) 
```

## **<mark>第二十二题</mark>**

问题：定义一个类，它具有类参数并具有相同的实例参数。
提示：定义一个实例参数，需要在init方法中添加它。您可以使用构造参数初始化对象，也可以稍后设置该值

```
class Student:
    # 类参数（类属性）
    name = "学生"

    def __init__(self, name):
        # 实例参数（实例属性）
        self.name = name
# 创建对象
s1 = Student("张三")
s2 = Student("李四")

print(Student.name)  # 访问类参数
print(s1.name)       # 访问实例参数
print(s2.name)
```

## **<mark>第二十三题</mark>**

问题：定义一个可以计算两个数之和的函数。
提示：定义一个带有两个数字作为参数的函数。可以在函数中计算和并返回值。

```
def sum(a,b):
    return a+b
l=input("请分别输入两个数字").split(" ")
print(f"两数之和为：{sum(int(l[0]),int(l[1]))}")
```

## **<mark>第二十四题</mark>**

问题：定义一个可以将整数转换为字符串并在控制台中打印的函数。
提示：使用str()将数字转换为字符串。

```
def func(n):
    print(str(n))
```

## **<mark>第二十五题</mark>**

问题：定义一个函数，它可以接收两个字符串形式的整数并计算它们的和，然后在控制台中输出。
提示：使用int()将字符串转换为整数。

```
def func(a,b):
    print(int(a)+int(b))
func("3","4")
```

## **<mark>第二十六题 </mark>**

定义一个函数，它可以接受两个字符串作为输入，并将它们连接起来，然后在控制台中输出。
提示：使用+连接字符串

```
def func(a,b):
    print(a+b)
func("3","4")
```

## <mark>**第二十七题**</mark>

定义一个函数，它可以接受两个字符串作为输入，并在控制台中以最大长度打印字符串。如果两个字符串长度相同，则函数应逐行打印所有字符串。
提示：使用1en()函数获取字符串的长度。

```
def func(a,b):
    if len(a)>len(b):
        print(a)
    if len(a)<len(b):
        print(b)
    if len(a)==len(b):
        print(a)
        print(b)
func("asldfj","123146448")
```

## **<mark>第二十八题</mark>**

问题：定义一个函数，它可以接受一个整数作为输入，如果这个数字是偶数，则输出“它是偶数”，否则输出“它是奇数”。
提示：使用%运算符检查一个数字是偶数还是奇数。

```
def func(n):
    if n % 2 == 0:
        print("它是偶数")
    else:
        print("它是奇数")
func(int(input("请输入数字：")))
```

## **<mark>第二十九题</mark>**

问题：定义一个函数，它可以打印一个字典，其中键是1到3之间的数字（包括在内），值是键的平方。
提示：使用dict[key]=value模式将条目放入字典中。
使用**运算符得到一个数字的幂。

```
def func():
    l={}
    for i in range(1,4):
      l.update({i:i**2})
    print(l)
func()
```

## **<mark>第三十题</mark>**

问题：定义一个函数，它可以打印一个字典，其中键是1到20之间的数字（包括在内），值是键的平方。
提示：使用dict[key]=value模式将条目放入字典中。使用\*\*操作符获取\*一个数的幂。对循环使用range()。

```
def func():
    l={}
    for i in range(1,21):
      l.update({i:i**2})
    print(l)
func()
```

## **<mark>第三十一题</mark>**

问题：定义一个函数，它可以生成一个字典，其中键是1到20之间的数字（包括在内），值是键的平方。函数只输出值即可。
提示：使用dict[key]=value模式将条目放入字典中。使用\*\*操作符获取*一个数的幂。对于循环使用range()。使用keys()迭代字典中的键。我们还可以使用item()来获取键/值对。

```
def func():
    l={}
    for i in range(1,21):
      l.update({i:i**2})
    print(l.values())
func()
```

## **<mark>第三十二题</mark>**

问题：定义一个函数，它可以生成一个字典，其中键是1到20之间的数字（包括在内），值是键的平方。函数只打印键即可。
提示：使用dict[key]=value模式将条目放入字典中。使用\*\*操作符获取*一个数的幂。对于循环使用range()。使用keys()迭代字典中的键。我们还可以使用item()来获取键/值对。

```
def func():
    l={}
    for i in range(1,21):
      l.update({i:i**2})
    print(l.keys())
func()
```

## **<mark>第三十三题</mark>**

问题：定义一个函数，它可以生成和打印一个列表，其中的值是1到20之间的数的平方（包括这两个数）。
提示：使用**运算符得到一个数字的幂，对于循环使用range()，使用list.append()向列表中添加值。

```
def func():
    l=[]
    for i in range(1,21):
        l.append(i**2)
    print(l)
func()
```

## **<mark>第三十四题</mark>**

问题：定义一个函数，它可以生成一个列表，其中的值是1到20之间的数的平方（包括这两个数），然后函数需要打印列表中的前5个元素。
提示：使用**运算符得到一个数字的幂。对循环使用range()，使用list.append()向列表中添加值，使用[n1：n2]对列表进行切片：

```
def func():
    l=[]
    for i in range(1,21):
        l.append(i**2)
    print(l[0:5])
func()
```

## **<mark>第三十五题</mark>**

问题：定义一个函数，它可以生成一个列表，其中的值是1到20之间的数的平方（包括这两个数），然后函数需要打印列表中的最后5个元素。
提示：使用**运算符得到一个数字的幂。对循环使用range()，使用list.append()向列表中添加值，使用[n1：n2]对列表进行切片：

```
def func():
    l=[]
    for i in range(1,21):
        l.append(i**2)
    print(l[-5:])
func()
```

## **<mark>第三十六题</mark>**

问题：定义一个函数，它可以生成一个列表，其中的值是1到20之间的数的平方（包括这两个数）。然后，该函数需要打印列表中除前5个元素外的所有值。
提示：使用**运算符得到一个数字的幕。对循环使用range()。使用list.append()向列表中添加值。使用[n1：n2]对列表进行切片：

```
def func():
    l=[]
    for i in range(1,21):
        l.append(i**2)
    print(l[5:])
func()
```

## **<mark>第三十七题</mark>**

问题：定义一个函数，它可以生成并打印一个元组，其中的值是1到20之间的数的平方（包括这两个数）。
提示：使用**运算符得到一个数字的幂。对循环使用range()。使用list.append()向列表中添加值。使用tuple()从列表中获取一个元组。

```
def func():
    a=()
    l=list(a)
    for i in range(1,21):
        l.append(i**2)
    print(tuple(l))
func()
```

## **<mark>第三十八题</mark>**

问题：对于给定的元组（1，2，3，4，5，6，7，8，9，10），编写一个程序，在一行中输出前半部分值，在一行中输出后半部分值。
提示：使用[n1：n2]表示法从元组中获取切片。

```
b=map(int,input().split(","))
a=tuple(b)
print(a[:len(a)//2])
print(a[len(a)//2:])
```

## **<mark>第三十九题</mark>**

问题：编写程序生成并输出另一个元组，其值是给定元组（1，2，3，4，5，6，7，8，9，10）中的偶数。
提示：使用“for”来迭代元组，使用tuple从列表中生成一个tuple。

```
a=(1,2,3,4,5,6,7,8,9,10)
c=[]
for i in a:
    if i%2==0:
        c.append(i)
print(tuple(c))
```

## **<mark>第四十题</mark>**

问题：写一个程序，接受一个字符串作为输入，如果字符串是“yes”或“YES”或“Yes”，打印“Yes”，否则打印“No”
提示：使用if语句判断条件。

```
l=input()
if l=="yes" or l=="Yes" or l=="YES":
    print("Yes")
else:
    print("No")
```

## **<mark>第四十一题</mark>**

问题：编写一个程序，可以使用过滤函数过滤列表中的偶数。列表是：[1,2,3,4,5,6,7,8,9，10]。
提示：使用filter()过滤列表中的一些元素。使用1ambda定义匿名函数。

```
l=[1,2,3,4,5,6,7,8,9,10]
a=lambda x:x%2!=0
b=filter(a,l)
print(list(b))
```

## **<mark>第四十二题</mark>**

问题：编写一个程序，可以使用map()构造一个列表，其中的元素是[1,2,3,4,5,6,7,8,9,10]中元素的平方。
提示：使用map生成列表。使用lambda定义匿名函数

```
l=[1,2,3,4,5,6,7,8,9,10]
a=map(lambda x:x**2,l)
print(list(a))
```

## **<mark>第四十三题</mark>**

问题：编写一个程序，它可以使用map()和filter()生成一个列表，共中的元素是[1,2,3,4,5,6,7,8,9,10]中的偶数的平方。
提示：使用map()生成列表。使用filter()来过滤列表中的元素。使用lambda定义匿名函数。

```
l=[1,2,3,4,5,6,7,8,9,10]
a=filter(lambda x:x%2==0,l)
b=map(lambda x:x**2,a)
print(list(b))
```

## **<mark>第四十四题</mark>**

问题：编写一个程序，它可以使用map()生成一个列表，其中的元素是1到20之间的数的平方（包括两个数）。
提示：使用map()生成列表。使用1ambda定义匿名函数。

```
a=map(lambda x:x**2,range(1,21))
print(list(a))
```

## **<mark>第四十五题</mark>**

问题：定义一个名为American的类，它有一个名为printNationality的静态方法。
提示：使用@staticmethod装饰器来定义类的静态方法。

```
class American:
    @staticmethod
    def printNationality():
        print("Nationality")
American.printNationality()
```

## **<mark>第四十六题</mark>**

问题：定义一个名为American的类及其子类NewYorker。
提示：使用类子类（ParentClass)来定义子类。

```
class American:
    @staticmethod
    def printNationality():
        print("Nationality")
American.printNationality()
class NewYork(American):
    pass
NewYork.printNationality()
```

## **<mark>第四十七题</mark>**

问题：定义一个名为Circle的类，可以用半径来构造。Circle类有一个可以计算面积的方法。

```
import math
class Circle:
    def __init__(self,r):
        self.radius=r
    def area(self):
        return math.pi*self.radius**2
l=Circle(3)
print(l.area())
```

## **<mark>第四十八题</mark>**

定义一个名为Rectangle的类，它可以由长度和宽度构造。矩形类有一个方法可以计算面积。

```
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    def area(self):
        return self.width * self.height
rectangle = Rectangle(100, 100)
print(rectangle.area()) 
```

## **<mark>第四十九题</mark>**

定义一个名为Shape的类及其子类square。Square类有一个init函数，它以长度作为参数。这两个类都有一个area函数，可以打印形状的区域，形状的区域默认为0。

```
class Shape: 
    def area(self):
        print(0)
class Square(Shape):
    def __init__(self, length):
        self.length = length
    def area(self):
        print(0)
```

## **<mark>第五十题</mark>**

请引发RuntimeError异常。

```
raise RuntimeError('this is a runtime error')
```

## **<mark>第五十一题</mark>**

问题：编写一个函数来计算5/0，并使用try/except来捕获异常。

```
def func(a,b):
    return a/b
try:
    func(5,0)
except ZeroDivisionError:
    print("计算错误") 
```

## **<mark>第五十二题</mark>**

定义一个自定义异常类，它将字符串消息作为属性。

```
class MyError(Exception):
    def __init__(self, message):
        self.message = message
    def __str__(self):
        return self.message
try:
    raise MyError("这是一个自定义异常")
except MyError as e:
    print(e.message)
    print(e) 
    #当你使用 print(对象) 时，Python 会自动调用这个对象的 __str__() 方法，
    把对象转换成字符串后再输出。
```

## **<mark>第五十三题</mark>**

问题：假设我们有一些’username@companyname.com’格式的电子邮件地址，请编写程序打印给定电子邮件地址的用户名，用户名和公司名都只由字母组成。
示例：如果下面的电子邮件地址作为程序的输入：john@google.com.
那么，程序的输出应该是：john
在向问题提供输入数据的情况下，应该假定它是控制台输入。

```
import re
l=input("请输入电子邮件地址：")
res=re.match(r"\w+",l)
print(res.group())
```

## **<mark>第五十四题</mark>**

问题：假设我们有一些“username@companyname.com”格式的电子邮件地址，请编写程序打印给定的电子邮件地址的公司名称：用户名和公司名都只由字母组成。
示例：如果下面的电子邮件地址作为程序的输入：john@google.com
那么，程序的输出应该是：google
在向问题提供输入数据的情况下，应该假定它是控制台输入。

```
import re

l=input("请输入电子邮件地址：")
res=re.match(r"(\w+)@(\w+).com",l)
print(res.group(0))
#有多个分组时，用group(n)来定位分组，n从1开始
```

## **<mark>第五十五题</mark>**

问题：编写一个程序，接收一个由空格分隔的单词序列作为输入，打印只由数字组成的单词。
示例：如果下面的单词作为程序的输入：2 cats and 3 dogs;
那么，程序的输出应该是：['2','3']
在向问题提供输入数据的情况下，应该假定它是控制台输入。

```
import re

l=input("请输入单词序列：")
res=re.findall(r"\d+",l)
print(res)
```

## **<mark>第五十六题</mark>**

问题：打印unicode字符串“helloworld”。

```
l="hello world"
print(l)
#Python 3 的字符串默认就是 Unicode 字符串。
```

## **<mark>第五十七题</mark>**

问题：python中的解码与编码；

```
l="hello world"
a=l.encode("utf8")
print(a)
print(a.decode("utf8"))
```

## **<mark>第五十八题</mark>**

问题：编写一个特殊注释来表明Python源代码文件是unicode格式的。

```
# -*- coding: utf-8 -*-
```

## **<mark>第五十九题</mark>**

问题：写一个程序来计算1/2+2/3+3/4+......+n/（n+1)。
示例：如果下面的n作为程序的输入：5；
那么，程序的输出应该是：3.55

```
n=int(input("Enter a number:"))
sum=0
for i in range(1,n+1):
    sum=sum+i/(i+1)
print(sum)
```

## **<mark>第六十题</mark>**

问题：编写程序计算：当n>0和F（0）=1时，F（n）=F（n-1）+100通过控制台输入一个给定的n（n>0）。
示例：如果下面的n作为程序的输入：5，
那么，程序的输出应该是：501；

```
x = int(input("Enter a number:"))
def F(n):
    if n == 0:
        return 1
    else:
        return F(n-1) + 100
print(F(x))
```

## **<mark>第六十一题</mark>**

问题：斐波那契数列的计算公式如下：如果n=0，f（n）=0：如果n=1，f（n）=1：如果n>1，f（n）=f（n-1）+f（n-2）：请编写一个程序，在控制台输入给定n的情况下计
算f(n)的值。
示例：如果下面的n作为程序的输入：7；
那么，程序的输出应该是：13:

```
x = int(input("Enter a number:"))
def F(n):
    if n == 0:
        return 0
    elif n==1:
        return  1
    else:
        return F(n-1)+F(n-2)
print(F(x))
```

## **<mark>第六十二题</mark>**

问题：请使用generator编写一个程序，当n由控制台输入时，以逗号分隔的形式输出0和n之间的偶数；
示例：如果下面的n作为程序的输入10；
那么，程序的输出应该是：0,2,4,6,8,10:

```
n=int(input("Enter a number:"))
def func():
    for i in range(0,n+1):
        if i%2==0:
            yield i
l=[]
for i in func():
    l.append(str(i))
print(",".join(l))
```

## **<mark>第六十三题</mark>**

问题：请编写一个生成器程序，以逗号分隔的形式输出0到n之间可以被5和7整除的数字，而n是通过控制台输入的。
示例：如果下面的n作为程序的输入：100；
那么，程序的输出应该是：0，35，70：

```
#方法一
n=int(input("Enter a number:"))
l=(x for x in range(n+1) if x%5==0 and x%7==0 )
a=map(str,l)
print(",".join(list(a)))  
#方法二
n=int(input("Enter a number:"))
def func():
    for i in range(0,n+1):
        if i%5==0 and i%7==0:
            yield i
l=[]
for i in func():
    l.append(str(i))
print(",".join(l))
```

## **<mark>第六十四题</mark>**

问题：请写assert语句来验证列表[2，4，6，8]中的每个数字都是偶数。
提示：使用“断言表达式”进行断言。

```
l=[2,4,6,8]
for i in l:
    assert i%2==0
```

## **<mark>第六十五题</mark>**

问题：请编写一个程序，从控制台接收基本数学表达式，并输出计算结果。
示例：如果下面的字符串作为程序的输入：35+3：
那么，程序的输出应该是：38；

```
#傻逼做法
import re
l=input()
res=re.match(r"(\d+)(.)(\d+)",l)
a=int(res.group(1))
b=int(res.group(3))
if res.group(2)=="+":
    print(a+b)
elif res.group(2)=="-":
    print(a-b)
elif res.group(2)=="*":
    print(a*b)
else:
    try:
        print(a/b)
    except ZeroDivisionError:
        print("计算出错")
#正确做法
print(eval(input()))
```

## **<mark>第六十六题</mark>**

问题：随机生成1，100内的一个整数；

```
import random
print(random.randint(1,1000))
```

## **<mark>第六十七题</mark>**

问题：生成一个值在10到100之间的随机浮点数

```
import random
print(random.uniform(10,1000))
```

## **<mark>第六十八题</mark>**

问题：请编写一个程序输出0和10之间的随机偶数使用随机模块和列表理解。

```
#方法一
import random 
print(random.randrange(0,10,2))  
#方法二
import random
print(random.choice([i for i in range(11) if i%2==0]))
```

## **<mark>第六十九题</mark>**

问题：请编写一个程序输出一个随机数，它可以被5和7整除，在0和100之间，使用随机模块和列表理解。

```
import random
print(random.choice([i for i in range(101) if i%5==0 and i%7==0]))
```

## **<mark>第七十题</mark>**

问题：请编写一个程序生成一个包含100到200之间的5个随机数的列表。

```
import random
print(random.sample(range(100,201), 5))
```

## **<mark>第七十一题</mark>**

问题：请编写一个程序随机生成一个列表，其中包含100到200之间的5个偶数。

```
import random
print(random.sample([x for x in range(100,201) if x%2==0], 5))
```

## **<mark>第七十二题</mark>**

问题：请编写一个程序，随机生成一个列表，从1到1000（含1000），有5个数字，可以被5和7整除。

```
import random
print(random.sample([x for x in range(1,1001) if x%5==0 and x%7==0], 5))
```

## **<mark>第七十三题</mark>**

问题：请写一个程序来随机打印一个7到15之间的整数（包括15）。

```
import random
print(random.randrange(7,16)) 
```

## **<mark>第七十四题</mark>**

问题：请编写一个程序来压缩和解压字符串“hello world!hello world!hello world!”。

```
import zlib
text = "hello world!hello world!hello world!"

# 1. 字符串转bytes
data = text.encode("utf-8")

# 2. 压缩
compressed = zlib.compress(data)

# 3. 解压
result = zlib.decompress(compressed)

# 4. bytes转字符串
text2 = result.decode("utf-8")

print(text2)  #你好，Python
```

## **<mark>第七十五题</mark>**

问题：请编写一个程序打印100次“1+1”执行的运行时间。

```
import timeit
t=timeit.timeit( "for x in range(100):1+1",
    number=1)
print(t)
```

## **<mark>第七十六题</mark>**

问题：请编写一个程序洗牌和打印列表[3，6，7，8]。

```
import random

l=[3,6,7,8]
random.shuffle(l)
print(l)
```

## <mark>第七十七题</mark>

问题：请编写一个程序，生成主语在[“I”，“You”]，动词在[“Play”，“Love”]中，对象在[“Hockey”，“Footbal1"]中的所有句子

```
import random

l1=["I","You"]
l2=["Play","Love"]
l3=["Hockey","Football"]
for i in l1:
    for j in l2:
        for k in l3:
            l=[i,j,k]
            print(" ".join(l))
```

## **<mark>第七十八题</mark>**

问题：请写一个程序打印列表，删除后删除偶数[5,6,77,45,22,12,24]。

```
l=[5,6,77,45,22,12,24]
l=[i for i in l if i%2!=0]
print(l)
```

## **<mark>第七十九题</mark>**

问题：使用列表理解，请编写程序，删除[12，24，35，70，88，120，155]中可被5和7整除的删除数后，打印列表。

```
l=[12,24,35,70,88,120,155]
l=[i for i in l if i%5!=0 or i%7!=0]
print(l)
```

## **<mark>第八十题</mark>**

问题：使用列表理解法，请编写一个程序，去掉[12，24，35，70，88，120，155]中的第0，2，4，6位置上的元素后打印列表

```
l=[12,24,35,70,88,120,155]
l=[l[x] for x in range(len(l)) if x%2!=0]
print(l)
```

## **<mark>第八十一题</mark>**

问题：使用列表理解，编写一个程序生成一个358三维数组，每个元素为0。

```
import numpy as np
a=np.zeros((3,5,8))
print(a)
```

## **<mark>第八十二题</mark>**

问题：利用列表理解，请编写一个程序，去掉[12，24，35，70，88，120，155]中的第0，第4，第5个数字后，将列表打印出来。

```
li=[12,24,35,70,88,120,155]
li=[x for (i,x) in enumerate(li) if i not in [0,4,5]]
print(li) 
```

## **<mark>第八十三题</mark>**

问题：通过使用列表理解，请编写一个程序，在[12，24，35，24，88，120，155]中删除值24后打印列表

```
li=[12,24,35,24,88,120,155]
li=[x for (i,x) in enumerate(li) if x not in [24]]
print(li)
```

## **<mark>第八十四题</mark>**

问题：对于两个己知列表[1,3,6,78,35,55]和[12,24,35,24,88,120，155]编写一个程序来生成一个元素为上述两个列表交集的链表。

```
l1=[1,3,6,78,35,55]
l2=[12,24,35,24,88,120,155]
li=[x for (i,x) in enumerate(l1) if x in l2]
print(li) 
```

## **<mark>第八十五题</mark>**

问题：对于给定的列表[12,24,35,24,88,120,155,88,120,155]，编写一个程序来打印这个列表---删除所有重复的值与原始顺序保留

```
l1=[12,24,35,24,88,120,155,88,120,155]
l=[x for (i,x) in enumerate(l1) if x not in l1[:i]]
print(l)
```

## **<mark>第八十六题</mark>**

问题：定义一个类Person和它的两个子类：Male和Female。所有的类都有一个方法"getGender"，它可以打印“Male”为男性类，“Female”为女性类。

```
class Person:
    @staticmethod
    def getGender():
        pass
class Male(Person):
    @staticmethod
    def getGender():
        print("Male")
class Female(Person):
    @staticmethod
    def getGender():
        print("Female")
Male.getGender()
Female.getGender()
```

## **<mark>第八十七题</mark>**

问题：请编写一个程序，计算并打印由控制台输入的字符串中的每个字符的数量。
示例：如果下面的字符串作为程序的输入：abcdefgab：
那么，程序的输出应该是：a,2 c,2 b,2 e,1 d,1 g,1 f,1;

```
#法一
l=list(input("请输入字符串："))
li=list(dict.fromkeys(l))
for i in li:
    print(f"{i},{l.count(i)}",end=" ")
#法二
dic={}
s=input()
for ch in s:
    dic[ch]=dic.get(ch,0)+1
print(" ".join(['%s,%s'%(k,v)for k,v in dic.items()]))  
```

## **<mark>第八十八题</mark>**

问题：x=[“11”，“uu”，’kk’，'hh']，y=[1，2，3,4,5,6]，对两个列名进行数据对齐，一个键，一个值的对齐形式。

```
x=['11','uu','kk','hh']
y=[1,2,3,4,5,6]
print(list(zip(x,y)))
```

## **<mark>第八十九题</mark>**

问题：请编写一个程序，从控制台接收一个字符串，并以相反的顺序打印出来。
示例：如果下面的字符串作为程序的输入：rise to vote sir；
那么，程序的输出应该是:ris etov ot esir;

```
#法一
l=list(input()) 
l.reverse()
print("".join(l))  
#法二
s = input()
print(s[::-1])
```

## **<mark>第九十题</mark>**

问题：请编写一个程序，从控制台接收一个字符串，并打印具有偶数索引的字符：
示例：如果下面的字符串作为程序的输入：H1e21314o5w6o7r819d
那么，程序的输出应该是：Helloworld；

```
#法一
l=input()
x=0
for i in l:
    if x%2==0:
        print(i,end="") 
    x=x+1
法二
s = input()
print(s[::2])
```

## **<mark>第九十一题</mark>**

问题：请写一个程序，打印[1，2，3]的所有排列：

```
from itertools import permutations
l = [1, 2, 3]
for x in permutations(l):
    print(list(x))
```

## **<mark>第九十二题</mark>**

问题：写一个程序来解决一个中国古代的经典难题：我们数农场里的鸡和兔子中有35个头和94条腿。我们有多少只兔子和多少只鸡？

```
for i in range(0,35):
    for j in range(0,35):
        if i+j==35 and 4*i+2*j==94:
            print(f"兔子数量为：{i}，鸡数量为：{j}")
```

## **<mark>第九十三题</mark>**

给定一个字符，用它构造一个底边长5个字符，高3个字符的等腰字符三角形。

```
a=input("Enter a character :")
print(f"  {a}")
print(f" {a*3}")
print(f"{a*5}") 
```

## **<mark>第九十四题</mark>**

己知一个字符串为“hello_world_yoyo”，如何得到一个队列[“hello”，”world”，”yoyo”］？

```
a="hello_world_yoyo"
print(a.split("_"))
```

## **<mark>第九十五题</mark>**

Python如何打印99乘法表？

```
i=1
while i<=9:
    j=1
    while j<=i:
        print(f"{i}*{j}={i*j}",end=" ")
        j=j+1
    print()
    i=i+1
```

## **<mark>第九十六题</mark>**

输入一个姓名，判断是否姓王。

```
l=input()
print(l[0]=="王")  
```

## **<mark>第九十七题</mark>**

统计字符串“Hello，welcome to my world.”中字母w出现的次数。

```
l=input()
print(l.count('w'))
```

## **<mark>第九十八题</mark>**

把列表a=[1，-6，2，-5，9，4，20，-3]中的数字绝对值。

```
a=[1,-6,2,-5,9,4,20,-3]
print(list(map(abs,a)))
```
