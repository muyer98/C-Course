﻿ <span id = "jump"></span>
# C++ 数组

标签（空格分隔）： C++


----------
C++ 支持数组数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量。

数组的声明并不是声明一个个单独的变量，比如 number0、number1、...、number99，而是声明一个数组变量，比如 numbers，然后使用 numbers&#91;0]、numbers&#91;1]、...、numbers&#91;99] 来代表一个个单独的变量。数组中的特定元素可以通过索引访问。

所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。


----------
## 声明数组 ##


在 C++ 中要声明一个数组，需要指定元素的类型和元素的数量，如下所示：
```
type arrayName [ arraySize ];
```
这叫做一维数组。arraySize 必须是一个大于零的整数常量，type 可以是任意有效的 C++ 数据类型。例如，要声明一个类型为 double 的包含 10 个元素的数组 balance，声明语句如下：
```
double balance[10];
```
现在 balance 是一个可用的数组，可以容纳 10 个类型为 double 的数字。


----------
## 初始化数组 ##


在 C++ 中，您可以逐个初始化数组，也可以使用一个初始化语句，如下所示：
```
double balance[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};
```
大括号 { } 之间的值的数目不能大于我们在数组声明时在方括号 [ ] 中指定的元素数目。

如果您省略掉了数组的大小，数组的大小则为初始化时元素的个数。因此，如果：
```
double balance[] = {1000.0, 2.0, 3.4, 7.0, 50.0};
```
您将创建一个数组，它与前一个实例中所创建的数组是完全相同的。下面是一个为数组中某个元素赋值的实例：
```
balance[4] = 50.0;
```
上述的语句把数组中第五个元素的值赋为 50.0。所有的数组都是以 0 作为它们第一个元素的索引，也被称为基索引，数组的最后一个索引是数组的总大小减去 1。以下是上面所讨论的数组的的图形表示：
![数组表示][1]


----------
## 访问数组元素 ##


数组元素可以通过数组名称加索引进行访问。元素的索引是放在方括号内，跟在数组名称的后边。例如：
```
double salary = balance[9];
```
上面的语句将把数组中第 10 个元素的值赋给 salary 变量。下面的实例使用了上述的三个概念，即，声明数组、数组赋值、访问数组：

```
#include <iostream>
using namespace std;
 
#include <iomanip>
using std::setw;
 
int main ()
{
   int n[ 10 ]; // n 是一个包含 10 个整数的数组
 
   // 初始化数组元素          
   for ( int i = 0; i < 10; i++ )
   {
      n[ i ] = i + 100; // 设置元素 i 为 i + 100
   }
   cout << "Element" << setw( 13 ) << "Value" << endl;
 
   // 输出数组中每个元素的值                     
   for ( int j = 0; j < 10; j++ )
   {
      cout << setw( 7 )<< j << setw( 13 ) << n[ j ] << endl;
   }
 
   return 0;
}
```
上面的程序使用了 setw() 函数来格式化输出。当上面的代码被编译和执行时，它会产生下列结果：

    Element        Value
          0          100
          1          101
          2          102
          3          103
          4          104
          5          105
          6          106
          7          107
          8          108
          9          109


----------
## C++ 中数组详解 ##


在 C++ 中，数组是非常重要的，我们需要了解更多有关数组的细节。下面列出了 C++ 程序员必须清楚的一些与数组相关的重要概念：

概念|	描述
--|:--
[多维数组](#jump1)|	C++ 支持多维数组。多维数组最简单的形式是二维数组。
[指向数组的指针](#jump2)|	您可以通过指定不带索引的数组名称来生成一个指向数组中第一个元素的指针。
[传递数组给函数](#jump3)|	您可以通过指定不带索引的数组名称来给函数传递一个指向数组的指针。
[从函数返回数组](#jump4)|	C++ 允许从函数返回数组。



 <span id = "jump1"></span>
# C++ 多维数组 #
[<i class="icon-arrow-left"></i>C++ 数组](#jump)
C++ 支持多维数组。多维数组声明的一般形式如下：
```
type name[size1][size2]...[sizeN];
```
例如，下面的声明创建了一个三维 5 . 10 . 4 整型数组：
```
int threedim[5][10][4];
```


----------
## 二维数组 ##


多维数组最简单的形式是二维数组。一个二维数组，在本质上，是一个一维数组的列表。声明一个 x 行 y 列的二维整型数组，形式如下：
```
type arrayName [ x ][ y ];
```
其中，type 可以是任意有效的 C++ 数据类型，arrayName 是一个有效的 C++ 标识符。

一个二维数组可以被认为是一个带有 x 行和 y 列的表格。下面是一个二维数组，包含 3 行和 4 列：
![C++ 中的二维数组][2]

因此，数组中的每个元素是使用形式为 a[ i , j ] 的元素名称来标识的，其中 a 是数组名称，i 和 j 是唯一标识 a 中每个元素的下标。


**初始化二维数组**
多维数组可以通过在括号内为每行指定值来进行初始化。下面是一个带有 3 行 4 列的数组。
```
int a[3][4] = {  
 {0, 1, 2, 3} ,   /*  初始化索引号为 0 的行 */
 {4, 5, 6, 7} ,   /*  初始化索引号为 1 的行 */
 {8, 9, 10, 11}   /*  初始化索引号为 2 的行 */
};
```
内部嵌套的括号是可选的，下面的初始化与上面是等同的：
```
int a[3][4] = {0,1,2,3,4,5,6,7,8,9,10,11};
```
**访问二维数组元素**
二维数组中的元素是通过使用下标（即数组的行索引和列索引）来访问的。例如：
```
int val = a[2][3];
```
上面的语句将获取数组中第 3 行第 4 个元素。您可以通过上面的示意图来进行验证。让我们来看看下面的程序，我们将使用嵌套循环来处理二维数组：
```
#include <iostream>
using namespace std;
 
int main ()
{
   // 一个带有 5 行 2 列的数组
   int a[5][2] = { {0,0}, {1,2}, {2,4}, {3,6},{4,8}};
 
   // 输出数组中每个元素的值                      
   for ( int i = 0; i < 5; i++ )
      for ( int j = 0; j < 2; j++ )
      {
         cout << "a[" << i << "][" << j << "]: ";
         cout << a[i][j]<< endl;
      }
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    a[0][0]: 0
    a[0][3]: 0
    a[1][0]: 1
    a[1][4]: 2
    a[2][0]: 2
    a[2][5]: 4
    a[3][0]: 3
    a[3][6]: 6
    a[4][0]: 4
    a[4][7]: 8

如上所述，您可以创建任意维度的数组，但是一般情况下，我们创建的数组是一维数组和二维数组。
    
[<i class="icon-arrow-left"></i>C++ 数组](#jump)

 <span id = "jump2"></span>
# C++  指向数组的指针#
[<i class="icon-arrow-left"></i>C++ 数组](#jump)
您可以先跳过本章，等了解了 C++ 指针的概念之后，再来学习本章的内容。

如果您对 C++ 指针的概念有所了解，那么就可以开始本章的学习。数组名是一个指向数组中第一个元素的常量指针。因此，在下面的声明中：
```
double balance[50];
```
balance 是一个指向 &balance[0] 的指针，即数组 balance 的第一个元素的地址。因此，下面的程序片段把 p 赋值为 balance 的第一个元素的地址：
```
double *p;
double balance[10];

p = balance;
```
使用数组名作为常量指针是合法的，反之亦然。因此，*(balance + 4) 是一种访问 balance[4] 数据的合法方式。

一旦您把第一个元素的地址存储在 p 中，您就可以使用 *p、*(p+1)、*(p+2) 等来访问数组元素。下面的实例演示了上面讨论到的这些概念：

```
#include <iostream>
using namespace std;
 
int main ()
{
   // 带有 5 个元素的双精度浮点型数组
   double balance[5] = {1000.0, 2.0, 3.4, 17.0, 50.0};
   double *p;
 
   p = balance;
 
   // 输出数组中每个元素的值
   cout << "使用指针的数组值 " << endl; 
   for ( int i = 0; i < 5; i++ )
   {
       cout << "*(p + " << i << ") : ";
       cout << *(p + i) << endl;
   }
 
   cout << "使用 balance 作为地址的数组值 " << endl;
   for ( int i = 0; i < 5; i++ )
   {
       cout << "*(balance + " << i << ") : ";
       cout << *(balance + i) << endl;
   }
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    使用指针的数组值
    *(p + 0) : 1000
    *(p + 1) : 2
    *(p + 2) : 3.4
    *(p + 3) : 17
    *(p + 4) : 50
    使用 balance 作为地址的数组值
    *(balance + 0) : 1000
    *(balance + 1) : 2
    *(balance + 2) : 3.4
    *(balance + 3) : 17
    *(balance + 4) : 50

在上面的实例中，p 是一个指向 double 型的指针，这意味着它可以存储一个 double 类型的变量。一旦我们有了 p 中的地址，*p 将给出存储在 p 中相应地址的值，正如上面实例中所演示的。
    
[<i class="icon-arrow-left"></i>C++ 数组](#jump)


 <span id = "jump3"></span>
# C++ 传递数组给函数 #
[<i class="icon-arrow-left"></i>C++ 数组](#jump)
C++ 中您可以通过指定不带索引的数组名来传递一个指向数组的指针。

C++ 传数组给一个函数，数组类型自动转换为指针类型，因而传的实际是地址。

如果您想要在函数中传递一个一维数组作为参数，您必须以下面三种方式来声明函数形式参数，这三种声明方式的结果是一样的，因为每种方式都会告诉编译器将要接收一个整型指针。同样地，您也可以传递一个多维数组作为形式参数。

**方式 1**
形式参数是一个指针：
```
void myFunction(int *param)
{
.
.
.
}
```
**方式 2**
形式参数是一个已定义大小的数组：
```
void myFunction(int param[10])
{
.
.
.
}
```
**方式 3**
形式参数是一个未定义大小的数组：
```
void myFunction(int param[])
{
.
.
.
}
```
**实例**
现在，让我们来看下面这个函数，它把数组作为参数，同时还传递了另一个参数，根据所传的参数，会返回数组中各元素的平均值：
```
double getAverage(int arr[], int size)
{
  int    i, sum = 0;       
  double avg;          
 
  for (i = 0; i < size; ++i)
  {
    sum += arr[i];
   }
 
  avg = double(sum) / size;
 
  return avg;
}
```
现在，让我们调用上面的函数，如下所示：
```
#include <iostream>
using namespace std;
 
// 函数声明
double getAverage(int arr[], int size);
 
int main ()
{
   // 带有 5 个元素的整型数组
   int balance[5] = {1000, 2, 3, 17, 50};
   double avg;
 
   // 传递一个指向数组的指针作为参数
   avg = getAverage( balance, 5 ) ;
 
   // 输出返回值
   cout << "平均值是：" << avg << endl; 
    
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    平均值是： 214.4

您可以看到，就函数而言，数组的长度是无关紧要的，因为 C++ 不会对形式参数执行边界检查。
    
[<i class="icon-arrow-left"></i>C++ 数组](#jump)



 <span id = "jump4"></span>
# C++ 从函数返回数组 #
[<i class="icon-arrow-left"></i>C++ 数组](#jump)
C++ 不允许返回一个完整的数组作为函数的参数。但是，您可以通过指定不带索引的数组名来返回一个指向数组的指针。

如果您想要从函数返回一个一维数组，您必须声明一个返回指针的函数，如下：
```
int * myFunction()
{
.
.
.
}
```
另外，C++ 不支持在函数外返回局部变量的地址，除非定义局部变量为 static 变量。

现在，让我们来看下面的函数，它会生成 10 个随机数，并使用数组来返回它们，具体如下：
```
#include <iostream>
#include <cstdlib>
#include <ctime>
 
using namespace std;
 
// 要生成和返回随机数的函数
int * getRandom( )
{
  static int  r[10];
 
  // 设置种子
  srand( (unsigned)time( NULL ) );
  for (int i = 0; i < 10; ++i)
  {
    r[i] = rand();
    cout << r[i] << endl;
  }
 
  return r;
}
 
// 要调用上面定义函数的主函数
int main ()
{
   // 一个指向整数的指针
   int *p;
 
   p = getRandom();
   for ( int i = 0; i < 10; i++ )
   {
       cout << "*(p + " << i << ") : ";
       cout << *(p + i) << endl;
   }
 
   return 0;
}
```
当上面的代码被编译和执行时，它会产生下列结果：

    624723190
    1468735695
    807113585
    976495677
    613357504
    1377296355
    1530315259
    1778906708
    1820354158
    667126415
    *(p + 0) : 624723190
    *(p + 1) : 1468735695
    *(p + 2) : 807113585
    *(p + 3) : 976495677
    *(p + 4) : 613357504
    *(p + 5) : 1377296355
    *(p + 6) : 1530315259
    *(p + 7) : 1778906708
    *(p + 8) : 1820354158
    *(p + 9) : 667126415
    
[<i class="icon-arrow-left"></i>C++ 数组](#jump)


  [1]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
  [2]: https://www.runoob.com/wp-content/uploads/2014/09/two_dimensional_arrays.jpg
  [3]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
  [4]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
  [5]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
  [6]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
  [7]: https://www.runoob.com/wp-content/uploads/2014/08/array_presentation.jpg
