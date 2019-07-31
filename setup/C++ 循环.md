<span id = "jump"></span>
# C++ 循环
标签（空格分隔）： C++


----------
有的时候，可能需要多次执行同一块代码。一般情况下，语句是顺序执行的：函数中的第一个语句先执行，接着是第二个语句，依此类推。

编程语言提供了允许更为复杂的执行路径的多种控制结构。

循环语句允许我们多次执行一个语句或语句组，下面是大多数编程语言中循环语句的一般形式：
![循环语句一般形式][1]


----------
## 循环类型 ##
C++ 编程语言提供了以下几种循环类型。点击链接查看每个类型的细节。
循环类型|	描述
--|:--
[while循环](#jumpwhile)| 	当给定条件为真时，重复语句或语句组。它会在执行循环主体之前测试条件。
[for循环](#jumpfor) |	多次执行一个语句序列，简化管理循环变量的代码。
[do...while循环](#jumpdo...while) |	除了它是在循环主体结尾测试条件外，其他与 while 语句类似。
[嵌套循环](#jumpmore) |	您可以在 while、for 或 do..while 循环内使用一个或多个循环。


----------
## 循环控制语句 ##
循环控制语句更改执行的正常序列。当执行离开一个范围时，所有在该范围中创建的自动对象都会被销毁。

C++ 提供了下列的控制语句。点击链接查看每个语句的细节。

控制语句|	描述
--|:--
[break语句](#jumpbreak) |	终止 loop 或 switch 语句，程序流将继续执行紧接着 loop 或 switch 的下一条语句。
[continue语句](#jumpcontinue) |	引起循环跳过主体的剩余部分，立即重新开始测试条件。
[goto语句](#jumpgoto) |	将控制转移到被标记的语句。但是不建议在程序中使用 goto 语句。


----------
## 无限循环 ##
如果条件永远不为假，则循环将变成无限循环。for 循环在传统意义上可用于实现无限循环。由于构成循环的三个表达式中任何一个都不是必需的，您可以将某些条件表达式留空来构成一个无限循环。
```
#include <iostream>
using namespace std;
 
int main ()
{
 
   for( ; ; )
   {
      printf("This loop will run forever.\n");
   }
 
   return 0;
}
```
当条件表达式不存在时，它被假设为真。您也可以设置一个初始值和增量表达式，但是一般情况下，C++ 程序员偏向于使用 for(;;) 结构来表示一个无限循环。

**注意：**您可以按 Ctrl + C 键终止一个无限循环。


<span id = "jumpwhile"></span>
# C++ while 循环 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)

只要给定的条件为真，while 循环语句会重复执行一个目标语句。


----------
## 语法 ##
C++ 中 while 循环的语法：
```
while(condition)
{
   statement(s);
}
```
在这里，**statement(s)** 可以是一个单独的语句，也可以是几个语句组成的代码块。**condition** 可以是任意的表达式，当为任意非零值时都为真。当条件为真时执行循环。

当条件为假时，程序流将继续执行紧接着循环的下一条语句。


----------
## 流程图 ##
![C++ 中的 while 循环][2]
在这里，while 循环的关键点是循环可能一次都不会执行。当条件被测试且结果为假时，会跳过循环主体，直接执行紧接着 while 循环的下一条语句。


----------
## 实例 ##
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // while 循环执行
   while( a < 20 )
   {
       cout << "a 的值：" << a << endl;
       a++;
   }
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 15
    a 的值： 16
    a 的值： 17
    a 的值： 18
    a 的值： 19

[<i class="icon-arrow-left"></i>C++ 循环](#jump)


<span id = "jumpfor"></span>
# C++ for 循环 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
for 循环允许您编写一个执行特定次数的循环的重复控制结构。


----------
## 语法 ##
C++ 中 for 循环的语法：
```
for ( init; condition; increment )
{
   statement(s);
}
```
下面是 for 循环的控制流：

 1. init 会首先被执行，且只会执行一次。这一步允许您声明并初始化任何循环控制变量。您也可以不在这里写任何语句，只要有一个分号出现即可。
 2. 接下来，会判断 condition。如果为真，则执行循环主体。如果为假，则不执行循环主体，且控制流会跳转到紧接着 for
 3. 循环的下一条语句。 在执行完 for 循环主体后，控制流会跳回上面的 increment语句。该语句允许您更新循环控制变量。该语句可以留空，只要在条件后有一个分号出现即可。
 4. 条件再次被判断。如果为真，则执行循环，这个过程会不断重复（循环主体，然后增加步值，再然后重新判断条件）。在条件变为假实例时，for循环终止。


----------
## 流程图 ##
![C++ 中的 for 循环][3]
****
```
#include <iostream>
using namespace std;
 
int main ()
{
   // for 循环执行
   for( int a = 10; a < 20; a = a + 1 )
   {
       cout << "a 的值：" << a << endl;
   }
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 15
    a 的值： 16
    a 的值： 17
    a 的值： 18
    a 的值： 19

**基于范围的for循环(C++11)**
for 语句允许简单的范围迭代：
```
int my_array[5] = {1, 2, 3, 4, 5};
// 每个数组元素乘于 2
for (int &x : my_array)
{
    x *= 2;
    cout << x << endl;  
}
// auto 类型也是 C++11 新标准中的，用来自动获取变量的类型
for (auto &x : my_array) {
    x *= 2;
    cout << x << endl;  
}
```
上面for述句的第一部分定义被用来做范围迭代的变量，就像被声明在一般for循环的变量一样，其作用域仅只于循环的范围。而在":"之后的第二区块，代表将被迭代的范围。
```
#include<iostream>  
#include<string>  
#include<cctype>  
using namespace std;  
  
int main()  
{  
    string str("some string");  
    // range for 语句  
    for(auto &c : str)  
    {  
        c = toupper(c);  
    }  
    cout << str << endl;  
    return 0;  
}
```
上面的程序使用Range for语句遍历一个字符串，并将所有字符全部变为大写，然后输出结果为：

    SOME STRING


[<i class="icon-arrow-left"></i>C++ 循环](#jump)

<span id = "jumpdo...while"></span>
# C++ do...while循环 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
不像 **for** 和 **while** 循环，它们是在循环头部测试循环条件。**do...while** 循环是在循环的尾部检查它的条件。

do...while 循环与 while 循环类似，但是 do...while 循环会确保至少执行一次循环。


----------
## 语法 ##
C++ 中 do...while 循环的语法：
```
do
{
   statement(s);

}while( condition );
```
请注意，条件表达式出现在循环的尾部，所以循环中的 statement(s) 会在条件被测试之前至少执行一次。

如果条件为真，控制流会跳转回上面的 do，然后重新执行循环中的 statement(s)。这个过程会不断重复，直到给定条件变为假为止。


----------
## 流程图 ##
![C++ 中的 do...while 循环][4]


**实例**
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // do 循环执行
   do
   {
       cout << "a 的值：" << a << endl;
       a = a + 1;
   }while( a < 20 );
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 15
    a 的值： 16
    a 的值： 17
    a 的值： 18
    a 的值： 19
    
[<i class="icon-arrow-left"></i>C++ 循环](#jump)


<span id = "jumpmore"></span>
# C++ 嵌套循环 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
一个循环内可以嵌套另一个循环。C++ 允许至少 256 个嵌套层次。


----------
## 语法 ##


C++ 中 **嵌套 for 循环** 语句的语法：
```
for ( init; condition; increment )
{
   for ( init; condition; increment )
   {
      statement(s);
   }
   statement(s); // 可以放置更多的语句
}
```
C++ 中 **嵌套 while 循环** 语句的语法：
```
while(condition)
{
   while(condition)
   {
      statement(s);
   }
   statement(s); // 可以放置更多的语句
}
```
C++ 中 **嵌套 do...while 循环** 语句的语法：
```
do
{
   statement(s); // 可以放置更多的语句
   do
   {
      statement(s);
   }while( condition );
 
}while( condition );
```
关于嵌套循环有一点值得注意，您可以在任何类型的循环内嵌套其他任何类型的循环。比如，一个 for 循环可以嵌套在一个 while 循环内，反之亦然。


----------
## 实例 ##


下面的程序使用了一个嵌套的 for 循环来查找 2 到 100 中的质数：
```
#include <iostream>
using namespace std;
 
int main ()
{
    int i, j;
    for(i=2; i<100; i++) {
        for(j=2; j <= (i/j); j++) {
            if(!(i%j)) {
                break; // 如果找到，则不是质数
            }
        }
        if(j > (i/j)) {
            cout << i << " 是质数\n";
        }
    }
    return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    2 是质数
    3 是质数
    5 是质数
    7 是质数
    11 是质数
    13 是质数
    17 是质数
    19 是质数
    23 是质数
    29 是质数
    31 是质数
    37 是质数
    41 是质数
    43 是质数
    47 是质数
    53 是质数
    59 是质数
    61 是质数
    67 是质数
    71 是质数
    73 是质数
    79 是质数
    83 是质数
    89 是质数
    97 是质数
    
[<i class="icon-arrow-left"></i>C++ 循环](#jump)



<span id = "jumpbreak"></span>
# C++ break语句 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
C++ 中 break 语句有以下两种用法：

 1. 当 break语句出现在一个循环内时，循环会立即终止，且程序流将继续执行紧接着循环的下一条语句。 
 2. 它可用于终止switch语句中的一个case。

如果您使用的是嵌套循环（即一个循环内嵌套另一个循环），break 语句会停止执行最内层的循环，然后开始执行该块之后的下一行代码。


----------
## 语法 ##


C++ 中 break 语句的语法：

```
break;
```

----------
## 流程图 ##
![C++ break 语句][5]


**实例**
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // do 循环执行
   do
   {
       cout << "a 的值：" << a << endl;
       a = a + 1;
       if( a > 15)
       {
          // 终止循环
          break;
       }
   }while( a < 20 );
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 15
    
[<i class="icon-arrow-left"></i>C++ 循环](#jump)



<span id = "jumpcontinue"></span>
# C++ continue语句 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
C++ 中的 continue 语句有点像 break 语句。但它不是强迫终止，continue 会跳过当前循环中的代码，强迫开始下一次循环。

对于 for 循环，continue 语句会导致执行条件测试和循环增量部分。对于 while 和 do...while 循环，continue 语句会导致程序控制回到条件测试上。


----------
## 语法 ##


C++ 中 continue 语句的语法：

```
continue;
```


----------
## 流程图 ##
![C++ continue 语句][6]

**实例**
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // do 循环执行
   do
   {
       if( a == 15)
       {
          // 跳过迭代
          a = a + 1;
          continue;
       }
       cout << "a 的值：" << a << endl;
       a = a + 1;
   }while( a < 20 );
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 16
    a 的值： 17
    a 的值： 18
    a 的值： 19
    
[<i class="icon-arrow-left"></i>C++ 循环](#jump)


<span id = "jumpgoto"></span>
# C++ goto语句 #
[<i class="icon-arrow-left"></i>C++ 循环](#jump)
goto 语句允许把控制无条件转移到同一函数内的被标记的语句。

**注意：**在任何编程语言中，都不建议使用 goto 语句。因为它使得程序的控制流难以跟踪，使程序难以理解和难以修改。任何使用 goto 语句的程序可以改写成不需要使用 goto 语句的写法。


----------
## 语法 ##


C++ 中 goto 语句的语法：
```
goto label;
..
.
label: statement;
```
在这里，**label** 是识别被标记语句的标识符，可以是任何除 C++ 关键字以外的纯文本。标记语句可以是任何语句，放置在标识符和冒号（:）后边。


----------
## 流程图
![C++ goto 语句][7] ##


**实例**
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // do 循环执行
   LOOP:do
   {
       if( a == 15)
       {
          // 跳过迭代
          a = a + 1;
          goto LOOP;
       }
       cout << "a 的值：" << a << endl;
       a = a + 1;
   }while( a < 20 );
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a 的值： 10
    a 的值： 11
    a 的值： 12
    a 的值： 13
    a 的值： 14
    a 的值： 16
    a 的值： 17
    a 的值： 18
    a 的值： 19

goto 语句一个很好的作用是退出深嵌套例程。例如，请看下面的代码片段：
```
for(...) {
   for(...) {
      while(...) {
         if(...) goto stop;
         .
         .
         .
      }
   }
}
stop:
cout << "Error in program.\n";
```
消除 **goto** 会导致一些额外的测试被执行。一个简单的 **break** 语句在这里不会起到作用，因为它只会使程序退出最内层循环。
    
[<i class="icon-arrow-left"></i>C++ 循环](#jump)


  [1]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_while_loop.png
  [2]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_while_loop.png
  [3]: https://www.runoob.com/wp-content/uploads/2015/01/cpp_for_loop.png
  [4]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_do_while_loop.jpg
  [5]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_break_statement.jpg
  [6]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_continue_statement.jpg
  [7]: https://www.runoob.com/wp-content/uploads/2014/09/cpp_goto_statement.jpg