# c语言编程



## 前言



## 框架



```c
#include "stdio.h"
int main()
{

    return 0;
}
```
任何c语言编写的程序都不能少的框架。

****



## 输出函数



可以理解为数学上的函数，既一种映射关系，但细节有所不同。

**"printf"**是一个函数，功能是可以输出**字符串**，格式为『**ptintf("……\n");**』。

例如经典的『Hello，world！』程序：

```c
#include "stdio.h"
int main()
{
    printf("Hello,world!\n"); // \n的作用是换行
    return 0;
}
```

运行结果如下：

![截屏2021-07-06 下午4.02.09](/Users/icarus/Desktop/截屏2021-07-06 下午4.02.09.png)

**「printf」**不仅可以输出字符串，还可以输出**变量**的值，但需要对变量进行格式化。

****



## 变量与常量



计算机进行计算，那么参与计算的就是数字，在c语言中参与计算的数字称为量，量分为变量与常量。对于量的表达，日常生活使用十进制，因为便于人脑计算，计算机内部使用二进制，因为便于计算机计算，而计算机表达时，由于**字节 (byte)**在计算机内部出现的频率较高，如果可以使用一种简洁的方式将它的内在含义准确表达出来，将会给我们带来很多方便，于是常常使用十六进制表达。但不管哪种计数方式，所记录的数本身是不变的。



### 常量



顾名思义，不变的量，这种量一旦被初始化赋值后，就无法再改变。



### 变量



顾名思义，可以改变的量，这种量被定义出来之后，可以随便赋值来改变其大小。

定义方式：

```c
int i;
int j = 1;
char k;
float h = 1.2;
double g = 2.0;
```

以上「i」等为变量本身，前面「int」等是定义变量的种类，比如int为整型变量，其值只能是整数，而double是**双精度浮点数**，可以表示小数。

不同的变量类型具有不同的值的类型和值的范围。

字符型变量：

用于存放字符常量，一个字符变量只能存放一个字符常量，类型说明符是char。

```c
#include<stdio.h>
int main()
{
			char x,y,z;
			x = 'b';
			y = 'o';
			z = 'y';
			printf("%c%c%c\n",x,y,z);
return 0;
}
```

程序运行结果是『boy』。

字符变量的字面量与其存放的字符常量无关，可类比于整型变量。

字符变量也可以储存整型数据，有通用性，输入输出时将『%c』改成『%d』即可。



## 变量的输出与输入



前文已述，printf函数可以输出字符串，并且可以输出变量的值，下例：

```c
#include "stdio.h"
int main()
{
    int i = 1;
    printf("i = %d\n",i);
    i = 2;
    printf("赋值之后，i = %d\n",i);
    return 0;
}
```

运行结果如下：

![截屏2021-07-06 下午4.29.45](/Users/icarus/Desktop/截屏2021-07-06 下午4.29.45.png)

注意到printf输出变量的值时候，双引号内有一个「%d」，这既是前文所说的对变量进行格式化。「%d」表示输出的变量是整数。

|      变量类型      | 格式化符号 |
| :----------------: | :--------: |
|        int         |     %d     |
|      unsigned      |     %u     |
|     long long      |    %ld     |
| unsigned long long |    %lu     |
|       float        |     %f     |
|       double       |    %lf     |

输出时可以用科学计数法，格式化符号要用「%e」。

```c
printf("%.nf",sum);
```

此行代码可以保留n位小数。

以下是转义字符：

|符号|英文|含义|
| :---------: | :--: | :--: |
|\b|backspace|回退一格|
|\t|tab|下一个制表位|
|\n|new line|换行|
|\r|return|回车|
|\f|f|换页|



## 浮点数



数学中，数轴上的数是连续的，任意不同的两点之间，可以找出无穷多个数，但这在计算机中难以实现，因此浮点数就出现了。

浮点数用来表示整数之间的小数，但其精确度并不是无限的，表达能力也不是无限的，因此随便写一个小数，可能计算机无法表达出来。



## 运算



**运算符：**

|   数学中    |  加  |  减  |  乘  |  除  | 求余数 |
| :---------: | :--: | :--: | :--: | :--: | :----: |
| **c语言中** |  +   |  -   |  *   |  /   |   %    |

**关系运算符：**

| 关系 | 相等 | 不相等 | 大于 | 大于或等于 | 小于 | 小于或等于 |
| :--: | :--: | :----: | :--: | :--------: | :--: | :--------: |
| 符号 |  ==  |   !=   |  >   |     >=     |  <   |     <=     |

关系运算符的计算结果只有0和1。

**特殊运算符：**

**「count ++」**与**「++ count」**都有变量加一的意思，但`a = count ++; `表示先将count的值赋给a，然后count加一，而`a = ++count;`表示先将count加一，然后加完后的值赋给a，因此这两种最终count都会加一，但是a的值相差1。

**「count --」**与**「-- count」**同理。

**「,」**是逗号运算符，一般只有一个作用，就是if语句中添加多个条件。

**条件运算符：**

**count = (** *<#condition#>* **)?**  *<#yes#>* **:** *<#no#>* **;**

相当于一个if语句。

不建议嵌套使用，会很难读。

**逻辑运算符：**

|逻辑|与|或|非|
| :--: | :--: | :----: | :--: |
|**符号**|&&|\|\||!|
逻辑运算符的运算结果是1或0。



## 几种语句



1. **if判断**

   ```c
     if (<#condition#>) {
           <#statements#>
       }
   ```

   用以判断，并作出条件成立时的动作。

   ```c
       if (<#condition#>) {
           <#statements#>
       }
       else if (#condition#) {
           <#statements#>
       }
   		else if (#condition#) {
           <#statements#>
       }
   		……
       else {
           <#statements#>
       }
   ```

   可以加上else，做出条件不成立时的动作。

   else总是与最近的if匹配。

2. **while循环**

   ```c
       while (<#condition#>) {
           <#statements#>
       }
   ```

   条件成立时，循环一直进行，直到条件不成立。

3. **dowhile循环**

   ```c
       do {
           <#statements#>
       } while (<#condition#>);
   ```

   条件成立时，循环一直进行，直到条件不成立。与while循环的差别在于，dowhile是先做一步，然后判断条件，而while是先判断条件，再循环。while可能一次循环都不做，如果条件一开始就不满足。

4. **switch判断**

   ```c
       switch (<#expression#>) {
           case <#constant#>:
               <#statements#>
               break;
        		case <#constant#>:
               <#statements#>
               break;
           ......
           default:
               break;
       }
   ```

   switch是一个判断，其中expression是一个常量表达式，必须是一个整型或枚举类型。这种语句的实质是在switch后写一个表达式，程序会计算这个表达式的值，然后一次与各个case的值比较，相等时执行该case后的动作。

   case的数量无限，每一个后面要跟一个比较的值和冒号。

   作比较的变量必须是同一个类型。

   所有case都不真时，执行default后的动作，因此default也可以没有。

   例：

   ```c
   #include <stdio.h>
   int main(){
       int a;
       printf("Input integer number:");
       scanf("%d",&a);
       switch(a){
           case 1: printf("Monday\n"); break;
           case 2: printf("Tuesday\n"); break;
           case 3: printf("Wednesday\n"); break;
           case 4: printf("Thursday\n"); break;
           case 5: printf("Friday\n"); break;
           case 6: printf("Saturday\n"); break;
           case 7: printf("Sunday\n"); break;
           default:printf("error\n"); break;
       }
       return 0;
   }
   ```

   

5. **for循环**

   ```c
       for (<#initialization#>; <#condition#>; <#increment#>) {
           <#statements#>
       }
   ```

   for循环适用于确定循环次数的循环，比如『遍历』。

   小括号内是三个部分，用『；』隔开，分别是**初始化**、**循环进行的条件**和**每轮循环都要做的动作**。   
   
   

## 杂项



**Inf => 无穷**

**-inf => 负无穷**

**nan => 无效的数字**

**fabs(#expression#) => 绝对值**

break => 结束循环，也即跳出循环

continue => 跳过本轮循环



## 函数与自定义函数



C语言开头`#include <stdio.h>`的含义是包含一个名为stdio.h的函数库，然后就可以调用这个库里的函数，前文所用到的printf与scanf函数都是这个库里的函数。

在实际操作中，我们常常会遇到重复的运算过程，我们可以复制这段代码来完成重复的动作，但是代码复制是程序质量不良的表现，因为维护时可能需要修改太多的地方。

可以通过自定义函数的方式来解决这一问题：

```c
		<#type#> (<#type#>,<#type#>,……){
				<#statement#>
				return 0; //取决于函数类型，也有形如：return;
		}
```

- 一个函数可以有多个return，也可以一个都没有。但不建议多个return，为了便于修改。

- 每个函数都有自己的变量空间，既｛｝（块）之中，这是相互独立的。本地变量又称局部变量，因为变量受到所在块的限制。块内与块外同名，则块内优先。

- 调用函数时，永远只能传值给函数，而不能传变量给函数，也就是说传给函数一个变量后，函数会读取变量的值进行运算，但不会改变变量的值。

- 函数的第一行加上分号放在整个程序代码的前面，叫做函数的原型声明，目的是在编译器没有碰到函数之前告诉编译器函数的类型。

  

## 数组



#### 定义



> 变量类型 + 字符 + [变量个数]

数组是一种容器，创建之后，不能更改大小，内部有序，可以出现在赋值号的两边。

数组的下标是从0开始计数的。

可以理解为数学中的数列。



#### 使用



集成初始化很好用：

```c
int a[3] = {1,3,5,};
int a[13] = {[0]=2,[3]=5,6,7,[9]=0,}; //（c99才可以用）
```

* 如果不知道一个数组到底有多少单元，可以用`sizeof(a)/sizeof(a[0])`表示数组中单元的个数，这样更改数组中单元个数时不需要再调别的。

  

#### 多维数组



多维数组实际上就是多维矩阵，脚标随之增多。

初始化：

```c
int a[][5] = {
	{0,1,2,3,4},
	{2,3,4,5,6},
}
```

列数必须给出来，行数编译器自己可以数。



## 指针



#### 地址

每一个变量在计算机中都有以个保存它的地址，变量的值可以变，但它的地址是不变的，可以通过以下代码查看一个变量的地址。

```c
int i = 1;
printf("%d\n",&i);
```

「&」是访问变量的地址；

「*」是访问地址上的变量。

#### 定义

指针是一个变量，但它无法独立着被使用，它必须指向某一个变量，这时，指针变量的值是它所指向变量的地址。

说白了，指针就是地址。

#### 使用

```c
int *p = &i;
```

这时，p是一个指针，指向变量i的地址。因此p的值是i的地址，而i的值可以通过*p来访问（读和写）。

定义时的 * 与访问时的 * 不一样，第一个仅用于区别所定义的是指针变量还是普通变量。

以下是一个实例，使用指针来完成调用函数交换两个变量的值。

```c
#include <stdio.h>
void exchange(int *a,int *b)
{
    int i = *a;
    *a = *b;
    *b = i;
}
int main()
{
    int a = 5;
    int b = 6;
    exc(&a, &b);
    printf("a = %d,b = %d\n",a,b);
    
    return 0;
}
```

这个用法很巧妙，前文已知，函数无法输入变量参数，因此这段代码定义了指针指向变量的地址，函数输入指针变量也即变量的地址，在函数内部通过*加指针访问该变量，进而达到函数修改变量的目的。

另外，指针常用于函数需要返回多个值的时候。

#### 数组是特殊的指针

```c
#include <stdio.h>
int main()
{
    int a[] = {1,2,3,};
    printf("%p\n",a);
    return 0;
}
```

这段代码的运行结果是：

![截屏2021-07-06 下午10.07.45](/Users/icarus/Library/Application Support/typora-user-images/截屏2021-07-06 下午10.07.45.png)

可见数组变量a本身就是一个地址，因此当我们想用一个指针指向数组a时，应写`int *p = a`，不用加「&」。但是数组的单元是变量，故`int *p = &a[0]`，而同时，`a == &a[0]`,`&a[x] == &a[0] + 4x = a + 4x`（当a是int时）。

数组是一个常量指针，因此不能被赋值。

#### 常量指针



```c
int i;
int const *p = &i; // 1
int *const p = &i; // 2
```

对于以上代码，可以看作以下代码：

```c
int i;
int const (*p) = &i; // 1
int *(const p) = &i; // 2
```

1表示指针p指向的地址上的变量不能通过指针修改；

2表示的是p指向的地址不能修改。



```c
const int a[] = {1,2,3,};
```

以上代码表示每个单元都是const，因此在函数参数输入时可以用来保护数组。



#### 指针的地址



```c
int a[];
int *p = a;
```

则`*p = a = a[0], *(p+1) = a[1], *(p+2) = a[2], ……,*(p+n) = a[n]`。



## 申请内存



malloc函数是向内存申请空间，以字节为单位，返回的结果是void *，需要自己转换想要的类型，最后要释放内存。格式如：

`(int *)malloc(n * sizeof(int))`

如果申请失败，会返回0，或者NULL。

****



## 字符串



`Char word[] = {'H','D','e','!'};` n

这样的数组是字符数组，但并不是字符串，因为不能用字符串的方式做计算。

`Char word[] = {'H','D','e','!','\0'};`

后面加个 **\0**，那么word就是一个字符串了。***0 = '\0' != '0'***

**0标志着字符串的结束，但这个0不属于字符串的一部分。**

字符串以数组的形式存在，以数组或指针的形式访问，但更多的还是以指针的形式。

string.h里面有很多处理字符串的函数。

字符串变量：

`char *str = "hello";`

`char word[] = "hello";`

`char line[10] = "hello";`

> "hello" 

编译器会把这种变成一个字符数组放在某处，这个数组的长度是6，因为编译器会在后面加上个0以使其为字符串。

字符串的字面量可以用来初始化字符数组。

```c
#include "stdio.h"
int main()
{
    int i = 0;
    char *s = "hello world";
//    s[0] = 'B';
    char *s2= "hello world";
    char s3[] = {"hello world"};
//    s3[0] = 'b';
    
    printf("&i = %p\n", &i);
    printf("s = %p\n", s);
    printf("s2 = %p\n", s2);
    printf("Here is s[0] = %c\n", s[0]);
    printf("Here is s3[0] = %c\n",s3[0]);
    return 0;
}
```

 以上代码运行结果为：



![image-20210706153645756](/Users/icarus/Library/Application Support/typora-user-images/image-20210706153645756.png)



可见本地变量i与指针s所指的位置相差很远。i变量所在的地址是非常靠后的，而指针所指位置很靠前。靠前的地方是计算机很重要的部分，不允许被修改，比如把`s[0] = 'B';`加上，运行结果为：



![截屏2021-07-06 下午3.33.40](/Users/icarus/Library/Application Support/typora-user-images/截屏2021-07-06 下午3.33.40.png)



程序试图给已经初始化过的字符串s重新赋值，运行报错，『thread』，意思是程序正在试图改写地址为0x100003f7e上的值，对计算机构成威胁，因而没有被允许。    

事实上，对于` char *s = "hello world";`，指针s初始化为指向一个字符串常量，实际上应该是` const char *s = "hello world";`，但是由于历史原因，编译器接受没有const的写法，但试图修改s所指的字符串时，就会产生严重的后果。

而s3是一个数组，里面的字符串是本地变量，可以修改，加上` s3[0] = 'b'`：



![截屏2021-07-06 下午10.44.07](/Users/icarus/Library/Application Support/typora-user-images/截屏2021-07-06 下午10.44.07.png)



**可见定义字符串有两种：指针或数组。**

数组知道字符串的地址，而指针不知道。



char *、int *不一定是字符串，其本意是指向字符的指针，也有可能是指向字符的数组，只有指针所指向的字符数组有结尾的0时，才能说它是字符串。



## 字符串的输入与输出



```c
char *t = "title";
char *s;
s = t;
```

对于以上代码，有两个指针，t和s，首先t指向了字符串『title』，然后对s赋值，结果是s也指向了同一个字符串，而不是新产生一个字符串。



对于printf和scanf，可以用**%s**来输入和输出字符串。

scanf中每一个%s读取到空格或回车为止，这是不安全的，因为不知道到底要读入多少个字符，

因此采用以下代码：

```c
char s[8];
scanf("%7s",s);
```



## 字符串数组

```c
char a[][10];
char *a[];
```

以上两行代码，第一行是指a为一个二维数组，第二行是指a为一个指针数组，数组里的每一个单元都是一个指针，指向某一个字符串。

字符数组中的每一个元素存放一个字符，加上最后面的0，一个长度为n的数组能存放(n-1)个字符。

**不论是字符串数组还是整型数组，多维情况下输入输出全部元素就需要使用多重循环。**





目前为止，提到数组，首先想到数组是一个矩阵，可以用来储存变量或字符变量，全部的输入与输出需要循环，但是对于字符数组有两种输入输出方式：

#### **用格式%c输入与输出单个字符:**

```c
#include <stdio.h>

int main()
{

    int x,i,j;
    char a[][20] = {
        "",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
        "Sunday",
    };
    printf("请输入月份：\n");
    scanf("%d",&x);
    if (x > 0 && x < 8) {
        for (i = x ; i < x + 1; i ++) {
            for (j = 0; j < 20; j ++) {
               printf("%c",a[i][j]);
          }
       }       
    }
    else printf("Error");
    printf("\n");
    return 0;
}
```

#### **用格式%s整体输入与输出:**

```c
#include <stdio.h>

int main()
{

    int x,i,j;
    char a[][20] = {
        "",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
        "Sunday",
    };
    printf("请输入月份：\n");
    scanf("%d",&x);
    if (x > 0 && x < 8) {
        printf("%s",a[x]);
    }
    else printf("Error");
    printf("\n");
    return 0;
}
```

注意，使用%s输入字符时遇到**空格、回车、跳格符**就会结束字符串的输入，因此c语言提供了最适合字符串的输入函数gets()和输出函数puts()。

**gets(#字符数组名#)**功能是从键盘上输入一个字符串，可以包含空格，以回车换行符作为结束的标志。

**puts(#字符数组名或字符串名#)**功能是将字符数组中的字符串输出到屏幕上，并将字符串结束的标志转换成换行符。

另外，%s输出字符串时，需保留一维，编译器会自动将这一维上的字符串全部输入或输出。gets与puts同理。



## 字符数据的输入与输出



#### putchar(参数)

参数可以是数值、字符常量、字符变量及算术或字符的表达式，但最终输出的是字符。

#### getchar()

从键盘上输入一个字符。



## 字符串函数



#### strlen

```c
#include<stdio.h>
#include <string.h>
int main(int argc, char const *argv[])
{   
		char line[] = "hello";
    printf("%lu\n", strlen(line));
    printf("%lu\n", sizeof(line));
    return 0;
}
```

运行结果为：

![截屏2021-07-07 下午5.12.26](/Users/icarus/Library/Application Support/typora-user-images/截屏2021-07-07 下午5.12.26.png)

可见strlen是string length，会返回字符串的长度。



#### strcmp

功能是比较两个字符串的大小，通过返回的值表达比较的结果，0为相等，1为前面的大，-1为后面的大。

string compare 只能比较第一个不相同的字符大小。



#### strcpy

意味string copy，形式是：

```c
char *strcpy(char *restrict dst, const *restrict src);
```

功能是把src的字符串copy到dst里面去。

restrict的意思是src与dst不能重叠。

源在后面，需要拷贝到的地方在前面。

返回dst，目的是函数本身可以再做运算。

一般用法：

```
char *dst = (char)malloc(strlen(src)+1);
strcpy (dst,src):
```



#### strcat

功能是把一个字符串链接到另一个字符串。



#### 另一个版本

```c
char *strncpy(char *restrict dst, const *restrict src,size_t n);
char *strncat(char *restrict s1, const *restrict s2,size_t n);
int strncmp(const char *s1, const char *s2, size_t n);
```

前两个是限制复制的字符串的长度，消除安全问题，既不会越界。

最后一个是比较前n个字符。



#### strchr

用来寻找字符串里的某一个字符。

```c
#include<stdio.h>
#include <string.h>
#include <stdlib.h>

int main(int argc, char const *argv[])
{
    char s[] = "hello,world!";
    char *p = strchr(s,'l');
    printf("%s\n",p);
    char c = *p;
    *p = '\0';
    printf("%c\n",c);
    char *p3 = (void*)malloc(strlen(s)+1);
    strcpy(p3, s);
    printf("%s\n",p3);
    free(p3);
    char *p1 = strchr((p+1), 'l');
    char *p2 = strchr((p1+1), 'l');
    printf("%s\n",p1);
    printf("%s\n",p2);

    return 0;
}
```

运行结果如下：

![截屏2021-07-10 下午3.19.36](/Users/icarus/Desktop/截屏2021-07-10 下午3.19.36.png)

## 枚举



```c
enum type {num_0,num_1,num_2,……,num_n};
```

可以使用大括号里面的名字，其从num_0到num_n代表的就是常量0到n。

比如：

```c
enum colors {red,yellow,green};
// 这里，red == 0, yellow == 1, green == 2都成立。
```

```c
enum type {num_0,num_1,num_2,……,num_n, number of type};
```

这里刚刚好，最后一个number of type正是number of type，是个小套路。



## 数据结构



```c

#include <stdio.h>
struct date {
    int day;
    int month;
    int year;
};
//结构类型声明
//struct date {
//    int day;
//    int month;
//    int year;
//} today;
//这是另一种形式。

int main()
{
    struct date today;
  
    today.day = 25;
    today.month = 3;
    today.year = 2021;
  	today = (struct date){25,3,2021};
  
    printf("今天是%i年%i月%i日。\n",
           today.year,today.month,today.day);
    
    return 0;
}

```

意思是先声明一个数据结构类型，使用时定义一个变量，这个变量就会包含数据结构中的各个变量。

数据结构的结构成员不一定是同一个变量类型，而数组只能是一种。

数据结构可以进行**结构运算**：

给结构变量赋值或结构变量之间进行赋值是一一对应的，前者需要大括号。

结构变量的名字并不是结构变量的地址，因此定义指针时需要加上&。



数据结构可以作为函数参数输入，但是跟数组不同，整个结构是作为参数的值传入了函数，这时候在函数内部新建了一个结构变量，并且复制调用者的结构的值。

也可以返回一个结构。

说白了，数据类型可以在函数中传递。但是函数只能传值。



## 自定义数据类型

typedef可以给数据类型一个别名。

```c
typedef long int64_t;
typedef struct ADate {
	int month;
	int day;
	int year;
} Date;

int64_t i = 100000000000;
Date d = {9, 1, 2005, };

```



## 联合

union

带参数的宏一定要有括号，结尾不能加分号。
