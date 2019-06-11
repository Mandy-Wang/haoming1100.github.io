
# C++复习

### 第一章

- 什么是面向对象

    > 面向对象是一种思想，是基于面向过程而言的，就是说面向对象是将功能等通过对象来实现，将功能封装进对象之中，让对象去实现具体的细节；这种思想是将数据作为第一位，而方法或者说是算法作为其次，这是对数据一种优化，操作起来更加的方便，简化了过程。
    >
    > 面向对象有三大特征：封装性、继承性、多态性，
    >
    > - 封装性：隐藏了对象的属性和实现细节，仅对外提供公共的访问方式，这样就隔离了具体的变化，便于使用，提高了复用性和安全性。
    > - 继承性：就是两种事物间存在着一定的所属关系，那么继承的类就可以从被继承的类中获得一些属性和方法；这就提高了代码的复用性。继承是作为多态的前提的。
    > - 多态是说父类或接口的引用指向了子类对象，这就提高了程序的扩展性，也就是说只要实现或继承了同一个接口或类，那么就可以使用父类中相应的方法，提高程序扩展性，但是多态有一点不好之处在于：父类引用不能访问子类中的成员。
    >
    > ------
    >
    >  比如说你要去饭店吃饭，你只需要饭店，找到饭店的服务员，跟她说你要吃什么，然后就会给你做出来让你吃，你并不需要知道这个饭是怎么错做的，你只需要面向这个服务员，告诉他你要吃什么，然后他也只需要面向你吃完收到钱就好，不需要知道你怎么对这个饭进行吃。这就是面向对象。

- ### 数制转换

    - **十进制 → 二进制**

        > 除2取余法，即每次将整数部分除以2，余数为该位权上的数，而商继续除以2，余数又为上一个位权上的数，这个步骤一直持续下去，直到商为0为止，最后读数时候，从最后一个余数读起，一直到最前面的一个余数。

    ![](https://images0.cnblogs.com/blog/48305/201501/191446012199718.png)

    

    - **十进制 → 八进制**

        > 除8取余法，即每次将整数部分除以8，余数为该位权上的数，而商继续除以8，余数又为上一个位权上的数，这个步骤一直持续下去，直到商为0为止，最后读数时候，从最后一个余数起，一直到最前面的一个余数

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446027976234.png>)

    - **十进制 → 十六进制**

        > 除16取余法，即每次将整数部分除以16，余数为该位权上的数，而商继续除以16，余数又为上一个位权上的数，这个步骤一直持续下去，直到商为0为止，最后读数时候，从最后一个余数起，一直到最前面的一个余数

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446073607794.png>)

        ------

    - **二进制 → 八进制**

        > 三合一法，即从二进制的小数点为分界点，向左（向右）每三位取成一位，接着将这三位二进制按权相加，然后，按顺序进行排列，小数点的位置不变，得到的数字就是我们所求的八进制数。如果向左（向右）取三位后，取到最高（最低）位时候，如果无法凑足三位，可以在小数点最左边（最右边），即整数的最高位（最低位）添0，凑足三位。

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446138756684.png>)

    - **八进制 → 二进制**

        > 取一分三法，即将一位八进制数分解成三位二进制数，用三位二进制按权相加去凑这位八进制数，小数点位置照旧。

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446152665143.png>)

        

    - **二进制 → 十六进制**

          

        > 取四合一法，即从二进制的小数点为分界点，向左（向右）每四位取成一位，接着将这四位二进制按权相加，然后，按顺序进行排列，小数点的位置不变，得到的数字就是我们所求的十六进制数。如果向左（向右）取四位后，取到最高（最低）位时候，如果无法凑足四位，可以在小数点最左边（最右边），即整数的最高位（最低位）添0，凑足四位。

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446167506929.png>)

    - **十六进制 → 二进制**

        > 取一分四法，即将一位十六进制数分解成四位二进制数，用四位二进制按权相加去凑这位十六进制数，小数点位置照旧。

        ![](<https://images0.cnblogs.com/blog/48305/201501/191446183444917.png>)

- C ++ 相较于 C 的特点及演化过程

    > - C++ 几乎是 C 的超集，只有少量功能 C++ 不支持。
    > - 与C++相比，C具备编译速度快、容易学习、显式描述程序细节、较少更新标准（后两者也可同时视为缺点）等优点。
    > - 在语言层面上，C++包含绝大部分C语言的功能（例外之一，C++没有C99的[变长数组VLA]()），且提供OOP和GP的特性。但其实用C也可实现OOP思想，亦可利用宏去实现某程度的GP，只不过C++的语法能较简洁、自动地实现OOP/GP。
    > - C++在语言层面上提供了OOP/GP语法、更严格的类型检查系统、大量额外的语言特性(如异常、[RTTI](http://en.wikipedia.org/wiki/RTTI)等)，并且C++标准库也较丰富。
    > - C 语言的API通常比 C++ 简洁，能较容易供其他语言程序调用。因此，一些 C++ 库会提供 C 的 API 封装，同时也可供 C 程序调用。相反，有时候也会把C的API封装成 C++ 形式，以支持 RAII 和其他C++ 库整合

    > 演化过程
    >
    > - 在31年前(1979年)，一名刚获得博士学位的研究员，为了开发一个软件项目发明了一门新编程语言，该研究员名为[Bjarne Stroustrup](http://www.stroustrup.com/)，该门语言则命名为——C with classes，四年后改称为C++。
    > - C++语言发展大概可以分为三个阶段
    >     - 从80年代到1995年。这一阶段C++语言基本上是传统类型上的面向对象语言，并且凭借着接近C语言的效率，在工业界使用的开发语言中占据了相当大份额；
    >     - 从1995年到2000年，这一阶段由于标准模板库(STL)和后来的Boost等程序库的出现，泛型程序设计在C++中占据了越来越多的比重性。当然，同时由于Java、C#等语言出现和硬件价格的大规模下降，C++受到了一定的冲击；
    >     - 从2000年至今，由于以Loki、MPL等程序库为代表的产生式编程和模板元编程的出现，C++出现了发展历史上又一个新的高峰，这些新技术的出现以及和原有技术的融合，使C++已经成为当今主流程序设计语言中最复杂的一员。

### 第二章 C++ 简单程序设计

- 关键字与标识符的定义及规则

    > 标识符: 
    >
    > 用来标识变量、函数、类、模块，或任何其他用户自定义项目的名称。一个标识符以字母 A-Z 或 a-z 或下划线 _ 开始，后跟零个或多个字母、下划线和数字（0-9）。
    >
    > C++ 标识符内不允许出现标点字符，比如 @、& 和 %。C++ 是区分大小写的编程语言。因此，在 C++ 中，**Manpower** 和 **manpower** 是两个不同的标识符。

    > 关键字
    >
    > | asm          | else      | new              | this     |
    > | ------------ | --------- | ---------------- | -------- |
    > | auto         | enum      | operator         | throw    |
    > | bool         | explicit  | private          | true     |
    > | break        | export    | protected        | try      |
    > | case         | extern    | public           | typedef  |
    > | catch        | false     | register         | typeid   |
    > | char         | float     | reinterpret_cast | typename |
    > | class        | for       | return           | union    |
    > | const        | friend    | short            | unsigned |
    > | const_cast   | goto      | signed           | using    |
    > | continue     | if        | sizeof           | virtual  |
    > | default      | inline    | static           | void     |
    > | delete       | int       | static_cast      | volatile |
    > | do           | long      | struct           | wchar_t  |
    > | double       | mutable   | switch           | while    |
    > | dynamic_cast | namespace | template         |          |

- 变量与常量

    > 变量其实只不过是程序可操作的存储区的名称。C++ 中每个变量都有指定的类型，类型决定了变量存储的大小和布局，该范围内的值都可以存储在内存中，运算符可应用于变量上。
    >
    > 变量的名称可以由字母、数字和下划线字符组成。它必须以字母或下划线开头。大写字母和小写字母是不同的。
    >
    > 作用域是程序的一个区域，一般来说有三个地方可以定义变量：
    >
    > - 在函数或一个代码块内部声明的变量，称为局部变量。
    > - 在函数参数的定义中声明的变量，称为形式参数。
    > - 在所有函数外部声明的变量，称为全局变量。

    > 常量是固定值，在程序执行期间不会改变。这些固定的值，又叫做**字面量**。
    >
    > 常量可以是任何的基本数据类型，可分为整型数字、浮点数字、字符、字符串和布尔值。
    >
    > 常量就像是常规的变量，只不过常量的值在定义后不能进行修改。

- 算术表达式及其相关语句

    > - 算术运算符
    >
    >  假设变量 A 的值为 10，变量 B 的值为 20，则：
    >
    > | 运算符 | 描述                                                         | 实例             |
    > | :----- | :----------------------------------------------------------- | :--------------- |
    > | +      | 把两个操作数相加                                             | A + B 将得到 30  |
    > | -      | 从第一个操作数中减去第二个操作数                             | A - B 将得到 -10 |
    > | *      | 把两个操作数相乘                                             | A * B 将得到 200 |
    > | /      | 分子除以分母                                                 | B / A 将得到 2   |
    > | %      | 取模运算符，整除后的余数                                     | B % A 将得到 0   |
    > | ++     | [自增运算符](https://www.runoob.com/cplusplus/cpp-increment-decrement-operators.html)，整数值增加 1 | A++ 将得到 11    |
    > | -–     | [自减运算符](https://www.runoob.com/cplusplus/cpp-increment-decrement-operators.html)，整数值减少 1 | A-– 将得到 9     |
    >
    > - 关系运算符
    >
    >  假设变量 A 的值为 10，变量 B 的值为 20，则：
    >
    > | 运算符 | 描述                                                         | 实例              |
    > | :----- | :----------------------------------------------------------- | :---------------- |
    > | ==     | 检查两个操作数的值是否相等，如果相等则条件为真。             | (A == B) 不为真。 |
    > | !=     | 检查两个操作数的值是否相等，如果不相等则条件为真。           | (A != B) 为真。   |
    > | >      | 检查左操作数的值是否大于右操作数的值，如果是则条件为真。     | (A > B) 不为真。  |
    > | <      | 检查左操作数的值是否小于右操作数的值，如果是则条件为真。     | (A < B) 为真。    |
    > | >=     | 检查左操作数的值是否大于或等于右操作数的值，如果是则条件为真。 | (A >= B) 不为真。 |
    > | <=     | 检查左操作数的值是否小于或等于右操作数的值，如果是则条件为真。 | (A <= B) 为真。   |
    >
    > - 逻辑运算符
    >
    >  假设变量 A 的值为 1，变量 B 的值为 0，则：
    >
    > | 运算符 | 描述                                                         | 实例              |
    > | :----- | :----------------------------------------------------------- | :---------------- |
    > | &&     | 称为逻辑与运算符。如果两个操作数都非零，则条件为真。         | (A && B) 为假。   |
    > | \|\|   | 称为逻辑或运算符。如果两个操作数中有任意一个非零，则条件为真。 | (A \|\| B) 为真。 |
    > | !      | 称为逻辑非运算符。用来逆转操作数的逻辑状态。如果条件为真则逻辑非运算符将使其为假。 | !(A && B) 为真。  |
    >
    > - 位运算符
    >
    > | p    | q    | p & q | p \| q | p ^ q |
    > | :--- | :--- | :---- | :----- | :---- |
    > | 0    | 0    | 0     | 0      | 0     |
    > | 0    | 1    | 0     | 1      | 1     |
    > | 1    | 1    | 1     | 1      | 0     |
    > | 1    | 0    | 0     | 1      | 1     |
    >
    >  假设如果 A = 60，且 B = 13，现在以二进制格式表示，它们如下所示：
    >
    >  A = 0011 1100
    >
    >  B = 0000 1101
    >
    >  \--–-–-–-–-–-–-–-–
    >
    >  A&B = 0000 1100
    >
    >  A|B = 0011 1101
    >
    >  A^B = 0011 0001
    >
    >  ~A  = 1100 0011
    >
    >  假设变量 A 的值为 60，变量 B 的值为 13，则：
    >
    > | 运算符 | 描述                                                         | 实例                                                         |
    > | :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
    > | &      | 如果同时存在于两个操作数中，二进制 AND 运算符复制一位到结果中。 | (A & B) 将得到 12，即为 0000 1100                            |
    > | \|     | 如果存在于任一操作数中，二进制 OR 运算符复制一位到结果中。   | (A \| B) 将得到 61，即为 0011 1101                           |
    > | ^      | 如果存在于其中一个操作数中但不同时存在于两个操作数中，二进制异或运算符复制一位到结果中。 | (A ^ B) 将得到 49，即为 0011 0001                            |
    > | ~      | 二进制补码运算符是一元运算符，具有“翻转”位效果，即0变成1，1变成0。 | (~A ) 将得到 -61，即为 1100 0011，一个有符号二进制数的补码形式。 |
    > | <<     | 二进制左移运算符。左操作数的值向左移动右操作数指定的位数。   | A << 2 将得到 240，即为 1111 0000                            |
    > | >>     | 二进制右移运算符。左操作数的值向右移动右操作数指定的位数。   | A >> 2 将得到 15，即为 0000 1111                             |
    >
    > - 赋值运算符
    >
    > | 运算符 | 描述                                                         | 实例                            |
    > | :----- | :----------------------------------------------------------- | :------------------------------ |
    > | =      | 简单的赋值运算符，把右边操作数的值赋给左边操作数             | C = A + B 将把 A + B 的值赋给 C |
    > | +=     | 加且赋值运算符，把右边操作数加上左边操作数的结果赋值给左边操作数 | C += A 相当于 C = C + A         |
    > | -=     | 减且赋值运算符，把左边操作数减去右边操作数的结果赋值给左边操作数 | C -= A 相当于 C = C - A         |
    > | *=     | 乘且赋值运算符，把右边操作数乘以左边操作数的结果赋值给左边操作数 | C *= A 相当于 C = C * A         |
    > | /=     | 除且赋值运算符，把左边操作数除以右边操作数的结果赋值给左边操作数 | C /= A 相当于 C = C / A         |
    > | %=     | 求模且赋值运算符，求两个操作数的模赋值给左边操作数           | C %= A 相当于 C = C % A         |
    > | <<=    | 左移且赋值运算符                                             | C <<= 2 等同于 C = C << 2       |
    > | >>=    | 右移且赋值运算符                                             | C >>= 2 等同于 C = C >> 2       |
    > | &=     | 按位与且赋值运算符                                           | C &= 2 等同于 C = C & 2         |
    > | ^=     | 按位异或且赋值运算符                                         | C ^= 2 等同于 C = C ^ 2         |
    > | \|=    | 按位或且赋值运算符                                           | C \|= 2 等同于 C = C \| 2       |
    >
    > - 杂项运算符
    >
    > | 运算符               | 描述                                                         |
    > | :------------------- | :----------------------------------------------------------- |
    > | sizeof               | [sizeof 运算符]()返回变量的大小。例如，sizeof(a) 将返回 4，其中 a 是整数。 |
    > | Condition ? X : Y    | [条件运算符]()。如果 Condition 为真 ? 则值为 X : 否则值为 Y。 |
    > | ,                    | [逗号运算符]()会顺序执行一系列运算。整个逗号表达式的值是以逗号分隔的列表中的最后一个表达式的值。 |
    > | .（点）和 ->（箭头） | [成员运算符]()用于引用类、结构和共用体的成员。               |
    > | Cast                 | [强制转换运算符]()把一种数据类型转换为另一种数据类型。例如，int(2.2000) 将返回 2。 |
    > | &                    | [指针运算符 &]() 返回变量的地址。例如 &a; 将给出变量的实际地址。 |
    > | *                    | [指针运算符 *]() 指向一个变量。例如，*var; 将指向变量 var。  |

- 程序结构 sizeof() 的应用

    > **sizeof** 是一个关键字，它是一个编译时运算符，用于判断变量或数据类型的字节大小。
    >
    > sizeof 运算符可用于获取类、结构、共用体和其他用户自定义数据类型的大小。
    >
    > ```c++
    > sizeof (data type)
    > ```
    >
    > ```c++
    > #include <iostream>
    > using namespace std;
    > 
    > int main()
    > {
    > cout << "Size of char : " << sizeof(char) << endl;
    > cout << "Size of int : " << sizeof(int) << endl;
    > cout << "Size of short int : " << sizeof(short int) << endl;
    > cout << "Size of long int : " << sizeof(long int) << endl;
    > cout << "Size of float : " << sizeof(float) << endl;
    > cout << "Size of double : " << sizeof(double) << endl;
    > cout << "Size of wchar_t : " << sizeof(wchar_t) << endl;
    > return 0;
    > }
    > 
    > ```

    > ```c++
    > Size of char : 1
    > Size of int : 4
    > Size of short int : 2
    > Size of long int : 4
    > Size of float : 4
    > Size of double : 8
    > Size of wchar_t : 4
    > ```

    

### 第三章 函数

- #### 函数的应用

    > 函数是一组一起执行一个任务的语句。每个 C++ 程序都至少有一个函数，即主函数 **main()** ，所有简单的程序都可以定义其他额外的函数。

    C++ 中的函数定义的一般形式如下：

    ```c++
    return_type function_name( parameter list ){
       body of the function
    }
    ```

    <font color=red>函数**声明**会告诉编译器函数名称及如何调用函数。函数的实际主体可以单独定义。</font>

    ```c++
    int max(int num1, int num2);
    ```

    ```c++
    #include <iostream>
    using namespace std;
     
    // 函数声明
    int max(int num1, int num2);
     
    int main ()
    {
       // 局部变量声明
       int a = 100;
       int b = 200;
       int ret;
     
       // 调用函数来获取最大值
       ret = max(a, b);
     
       cout << "Max value is : " << ret << endl;
     
       return 0;
    }
     
    // 函数返回两个数中较大的那个数
    int max(int num1, int num2) 
    {
       // 局部变量声明
       int result;
     
       if (num1 > num2)
          result = num1;
       else
          result = num2;
     
       return result; 
    }
    ```

    - 参数：

    |     类型     |                             描述                             |
    | :----------: | :----------------------------------------------------------: |
    | [传值调用]() | 该方法把参数的实际值复制给函数的形式参数。在这种情况下，修改函数内的形式参数对实际参数没有影响。 |
    | [指针调用]() | 该方法把参数的地址复制给形式参数。在函数内，该地址用于访问调用中要用到的实际参数。这意味着，修改形式参数会影响实际参数。 |
    | [引用调用]() | 该方法把参数的引用复制给形式参数。在函数内，该引用用于访问调用中要用到的实际参数。这意味着，修改形式参数会影响实际参数。 |

    

- #### 递归函数

    **在调用一个函数的过程中又出现直接或间接地调用该函数本身，称为函数的递归(recursive)调用**

    ```c++
    int test(int x)
    {
        x ++;
        if (x > 0 && x <= 10) {
           int y;
        	y = test(x);
        	return(2*y);
        }
        return 0;
    }
    ```

    递归函数必须有退出条件

- #### 内联函数

    > C++ **内联函数**是通常与类一起使用。如果一个函数是内联的，那么在编译时，编译器会把该函数的代码副本放置在每个调用该函数的地方。
    >
    > 对内联函数进行任何修改，都需要重新编译函数的所有客户端，因为编译器需要重新更换一次所有的代码，否则将会继续使用旧的函数。
    >
    > 如果想把一个函数定义为内联函数，则需要在函数名前面放置关键字 **inline**，在调用函数之前需要对函数进行定义。如果已定义的函数多于一行，编译器会忽略 inline 限定符。

    <font color= red>在类定义中的定义的函数都是内联函数，即使没有使用 **inline** 说明符。</font>

    > Tip： 只有当函数只有 10 行甚至更少时才将其定义为内联函数.
    >
    > - 定义: 当函数被声明为内联函数之后, 编译器会将其内联展开, 而不是按通常的函数调用机制进行调用.
    > - 优点: 当函数体比较小的时候, 内联该函数可以令目标代码更加高效. 对于存取函数以及其它函数体比较短, 性能关键的函数, 鼓励使用内联.
    > - 缺点: 滥用内联将导致程序变慢. 内联可能使目标代码量或增或减, 这取决于内联函数的大小. 内联非常短小的存取函数通常会减少代码大小, 但内联一个相当大的函数将戏剧性的增加代码大小. 现代处理器由于更好的利用了指令缓存, 小巧的代码往往执行更快。

    ```c++
    #include <iostream>
     
    using namespace std;
    // 这里使用inline 因为不是在类中
    inline int Max(int x, int y)
    {
       return (x > y)? x : y;
    }
    
    // 程序的主函数
    int main( )
    {
    
       cout << "Max (20,10): " << Max(20,10) << endl;
       cout << "Max (0,200): " << Max(0,200) << endl;
       cout << "Max (100,1010): " << Max(100,1010) << endl;
       return 0;
    }
    ```

    

- 函数参数

    C++函数参数传递有以下三种方式：

    - **值传递 **：  利用值传递方式，实际上是把实参的内容复制到形参中，实参和形参是存放在两个不同的内存空间中。在函数体内对形参的一切修改对实参都没有影响

        ```c++
        #include<iostream>
        #include<algorithm>
        using namespace std;
         
        class Node{
        public:
        	Node(){}
        private:
        	int value;
        };
         
        //形参是内置数据类型
        void Fun(int a){
        	cout<<"形参a的地址 = "<<&a<<endl;
        }
         
        //形参是类的对象
        void Fun(Node node){
        	cout<<"形参node的地址 = "<<&node<<endl;
        }
         
        int main(){
        	//内置数据类型
        	int a = 10;
        	cout<<"实参a的地址 = "<<&a<<endl;
        	Fun(a);
        	//数据类型是类
        	Node node;
        	cout<<"实参node的地址 = "<<&node<<endl;
        	Fun(node);
        	return 0;
        }
        ```

        

    - **指针传递（地址传递)**

        - 当进行指针传递的时候，形参是指针变量，实参是一个变量的地址或者是指针变量，调用函数的时候，形参指向实参的地址。
        - 指针传递中，函数体内可以通过形参指针改变实参地址空间的内容。

    ```c++
    //指针传递
    void swap(int *a, int *b){
    	cout<<"形参指针a的地址 = "<<a<<endl;
    	cout<<"形参指针b的地址 = "<<b<<endl;
        int tmp = *a;
    	*a = *b;
    	*b = tmp;
    }
     
    int main(){
    	int a = 5;
    	int b = 10;
    	cout<<"实参变量a的地址 = "<<&a<<endl;
    	cout<<"实参变量b的地址 = "<<&b<<endl;
    	cout<<"实参变量a的值 = "<<a<<endl;
    	cout<<"实参变量b的值 = "<<b<<endl;
    	//调用函数，指针传递方式
    	swap(&a, &b);
    	cout<<"实参变量a的值 = "<<a<<endl;
    	cout<<"实参变量b的值 = "<<b<<endl;
    	getchar();
    	return 0;
    }
    ```

    ```c++
    实参变量a的地址 = 010FF8A4
    实参变量b的地址 = 010FF898
    实参变量a的值 = 5
    实参变量b的值 = 10
    形参指针a的地址 = 010FF8A4
    形参指针b的地址 = 010FF898
    实参变量a的值 = 10
    实参变量b的值 = 5
    ```

    

    - **引用传递**
        - 引用实际上是某一个变量的别名，和这个变量具有相同的内存空间。 
        - 实参把变量传递给形参引用，相当于形参是实参变量的别名，对形参的修改都是直接修改实参

    ```c++
    //引用传递
    void Fun(int &a){
    	cout<<"形参引用a的地址 = "<<&a<<endl;
    	a = 100; //对形参引用进行修改
    }
     
    int main(){
    	int a = 10;
    	cout<<"实参a的地址 = "<<&a<<endl;
    	cout<<"实参a的值 = "<<a<<endl;
    	Fun(a);
    	cout<<"实参a的值 = "<<a<<endl;
    	getchar();
    	return 0;
    }
    ```

    ```c++
    实参a的地址 = 00AFF700
    实参a的值 = 10
    形参引用a的地址 = 00AFF700
    实参a的值 = 100
    ```

    

### 第四章 类与对象

#### 构造函数

> 类的**构造函数**是类的一种特殊的成员函数，它会在每次创建类的新对象时执行。
>
> 构造函数的名称与类的名称是完全相同的，并且不会返回任何类型，也不会返回 void。构造函数可用于为某些成员变量设置初始值。
>
> 构造函数分为无参和有参

##### 无参构造函数

```c++
#include <iostream>
using namespace std;

class Time
{
public :
    //无参构造函数
    Time()
    {
        hour = 0;
        minute = 0;
        sec = 0;
    }
    void showtime();
private:
    int hour;
    int minute;
    int sec;
};
void Time::showtime()
{
    cout<<"hour:"<<hour<<"min:"<<minute<<"sec:"<<sec<<endl;
}
 int main()
 {
 Time time;// 构造函数初始化
 time.showtime();
 getchar();
 return 0; 
 }

```

**构造函数除了可以定义在类内，还可以定义在类外，注意要先在类内声明**

```c++
#include <iostream>
using namespace std;

class Time
{
public :
    Time();
    void showtime();
private:
    int hour;
    int minute;
    int sec;
};
void Time::showtime()
{
    cout<<"hour:"<<hour<<endl<<"min:"<<minute<<endl<<"sec:"<<sec<<endl;
}
//定义在类外的构造函数
Time::Time()
{
    hour = 0;
    minute = 0;
    sec = 0;
}
 int main()
 {
 Time time;
 time.showtime();
 getchar();
 return 0;
 }

```

------

##### 有参构造函数

```c++
#include <iostream>
using namespace std;

class Time
{
public :
    Time(int,int,int);
    void showtime();
private:
    int hour;
    int minute;
    int sec;
};
void Time::showtime()
{
    cout<<"hour:"<<hour<<endl<<"min:"<<minute<<endl<<"sec:"<<sec<<endl;
}
Time::Time(int h,int m,int s)
{
    hour = h;
    minute = m;
    sec = s;
}
 int main()
 {
 Time time(1,2,3);
 time.showtime();
 getchar();
 return 0;
 }

```

##### 构造函数的重载

在一个类中可以定义多个构造函数，以便为对象提供不同的初始化方法，供用户选择。这些构造函数具有相同的名字，而参数的个数或参数的类型不同。这称为构造函数的重载。

```c++
#include <iostream>
using namespace std;

class Time
{
public :
    Time();
    Time(int,int,int);//重载
    void showtime();
private:
    int hour;
    int minute;
    int sec;
};
void Time::showtime()
{
    cout<<"hour:"<<hour<<endl<<"min:"<<minute<<endl<<"sec:"<<sec<<endl;
}
Time::Time()
{
    hour = 0;
    minute = 0;
    sec = 0;
}
Time::Time(int h,int m,int s)
{
    hour = h;
    minute = m;
    sec = s;
}
 int main()
 {
 Time time1(1,2,3);
 time1.showtime();
 Time  time2;
 time2.showtime();
 getchar();
 return 0;
 }

```

##### 构造函数的默认值

构造函数中参数的值既可以通过实参传递，也可以指定某些值的默认值，即如果用户不指定实参值，编译系统就使用默认值。

```c++
#include <iostream>
using namespace std;

class Time
{
public :
    Time(int h =2,int m=2,int s=2);
    void showtime();
private:
    int hour;
    int minute;
    int sec;
};
void Time::showtime()
{
    cout<<"hour:"<<hour<<endl<<"min:"<<minute<<endl<<"sec:"<<sec<<endl;
}
Time::Time(int h,int m,int s)
{
    hour = h;
    minute = m;
    sec = s;
}
 int main()
 {
 Time time1(1,2,3);
 time1.showtime();
 getchar();
 return 0;
 }

```





#### 复制构造函数 （拷贝构造函数）

​	**拷贝构造函数**是一种特殊的构造函数，它在创建对象时，是使用同一类中之前创建的对象来初始化新创建的对象。拷贝构造函数通常用于：

- 通过使用另一个同类型的对象来初始化新创建的对象。
- 复制对象把它作为参数传递给函数。
- 复制对象，并从函数返回这个对象。

如果在类中没有定义拷贝构造函数，编译器会自行定义一个。如果类带有指针变量，并有动态内存分配，则它必须有一个拷贝构造函数。拷贝构造函数的最常见形式如下：

```c++
classname (const classname &obj) {
   // 构造函数的主体
}
```

```c++
#include <iostream>
 
using namespace std;
 
class Line
{
   public:
      int getLength( void );
      Line( int len );             // 简单的构造函数
      Line( const Line &obj);      // 拷贝构造函数
      ~Line();                     // 析构函数
 
   private:
      int *ptr;
};
 //简单的构造函数
// 成员函数定义，包括构造函数
Line::Line(int len)
{
    cout << "调用构造函数" << endl;
    // 为指针分配内存
    ptr = new int;
    *ptr = len;
}
 //拷贝构造函数
Line::Line(const Line &obj)
{
    cout << "调用拷贝构造函数并为指针 ptr 分配内存" << endl;
    ptr = new int;
    *ptr = *obj.ptr; // 拷贝值
}
 //析构函数
Line::~Line(void)
{
    cout << "释放内存" << endl;
    delete ptr;
}
int Line::getLength( void )
{
    return *ptr;
}
 
void display(Line obj)
{
   cout << "line 大小 : " << obj.getLength() <<endl;
}
 
// 程序的主函数
int main( )
{
   Line line(10);
 
   display(line);
 
   return 0;
}
```



#### 析构函数

类的**析构函数**是类的一种特殊的成员函数，它会在每次删除所创建的对象时执行。

析构函数的名称与类的名称是完全相同的，只是在前面加了个波浪号（~）作为前缀，它不会返回任何值，也不能带有任何参数。析构函数有助于在跳出程序（比如关闭文件、释放内存等）前释放资源。

```c++
#include <iostream>
 
using namespace std;
 
class Line
{
   public:
      void setLength( double len );
      double getLength( void );
      Line();   // 这是构造函数声明
      ~Line();  // 这是析构函数声明
 
   private:
      double length;
};
 
// 成员函数定义，包括构造函数
Line::Line(void)
{
    cout << "Object is being created" << endl;
}
Line::~Line(void)
{
    cout << "Object is being deleted" << endl;
}
 
void Line::setLength( double len )
{
    length = len;
}
 
double Line::getLength( void )
{
    return length;
}
// 程序的主函数
int main( )
{
   Line line;
 
   // 设置长度
   line.setLength(6.0); 
   cout << "Length of line : " << line.getLength() <<endl;
 
   return 0;
}
```

输出

```c++
Object is being created
Length of line : 6
Object is being deleted
```



### 第五章 数据的共享与保护

#### 作用域

> 作用域是程序的一个区域，一般来说有三个地方可以定义变量：
>
> - 在函数或一个代码块内部声明的变量，称为局部变量。
> - 在函数参数的定义中声明的变量，称为形式参数。
> - 在所有函数外部声明的变量，称为全局变量。
>
>  当局部变量被定义时，系统不会对其初始化，您必须自行对其初始化。定义全局变量时，系统会自动初始化为下列值：
>
> | 数据类型 | 初始化默认值 |
> | :------- | :----------- |
> | int      | 0            |
> | char     | ‘\0’         |
> | float    | 0            |
> | double   | 0            |
> | pointer  | NULL         |

#### 对象生存期

```c++
#include <iostream>
#include <string.h>
using namespace std;
class A {
  char string[50];
public :
  A(char * st);
  ~A( );
};

A::A(char * st)
{ 
   strcpy(string, st);
   cout << string << "被创建时调用构造函数 ! " << endl;
}
A::~A( )
{  
    cout << string << 
    "被撤消时调用析构函数 ! " << endl;
}


void fun( )
{ 
    cout << "在fun( )函数体内 : \n" << endl; 
    A FunObj("fun( )函数体内的自动对象FunObj");
              
    static A InStaObj("内部静态对象InStaObj");
}

int main( )
{ 
    A MainObj("主函数体内的自动对象MainObj");
    cout<<"主函数体内，调用fun()函数前: \n";
    fun( );
    cout << "\n主函数体内，调用fun()函数后:\n";
    return 0;
}

static A ExStaObj("外部静态对象ExStaObj");
A GblObj("外部对象GblObj"); 
```

说明：

- 类A，含构造函数和析构函数
- 普通函数fun，函数体里新建了类A的局部自动对象`FunObj`和局部静态对象`InStaObj`
- main方法新建了类A的局部自动对象`MainObj`,调用`fun`方法
- 外面新建了A的的外部静态对象`ExStaObj`和外部对象`GblObj`



输出

```c++
外部静态对象ExStaObj被创建时调用构造函数 ! 
外部对象GblObj被创建时调用构造函数 ! 
主函数体内的自动对象MainObj被创建时调用构造函数 ! 
主函数体内，调用fun()函数前: 
在fun( )函数体内 : 

fun( )函数体内的自动对象FunObj被创建时调用构造函数 ! 
内部静态对象InStaObj被创建时调用构造函数 ! 
fun( )函数体内的自动对象FunObj被撤消时调用析构函数 ! 

主函数体内，调用fun()函数后:
主函数体内的自动对象MainObj被撤消时调用析构函数 ! 
内部静态对象InStaObj被撤消时调用析构函数 ! 
外部对象GblObj被撤消时调用析构函数 ! 
外部静态对象ExStaObj被撤消时调用析构函数 ! 
```

若将`A GblObj("外部对象GblObj"); `写在`static A ExStaObj("外部静态对象ExStaObj");`前面，则输出时两者顺序也颠倒。

- 创建顺序
    外部静态对象or外部对象优先于main函数
- 销毁顺序
    和创建顺序相反，**注意**静态对象会在main函数执行完才会销毁

 内存的三种分配方式

- 从静态存储区分配：此时的内存在程序编译的时候已经分配好，并且在程序的整个运行期间都存在。全局变量，static变量等在此存储
- 在栈区分配：相关代码执行时创建，执行结束时被自动释放。局部变量在此存储。栈内存分配运算内置于处理器的指令集中，效率高，但容量有限
- 在堆区分配：动态分配内存。用new/malloc时开辟，delete/free时释放。生存期由用户指定，灵活。但有内存泄露等问题

#### 友元的特点

> 类的友元函数是定义在类外部，但有权访问类的所有私有（private）成员和保护（protected）成员。尽管友元函数的原型有在类的定义中出现过，但是友元函数并不是成员函数。
>
> 友元可以是一个函数，该函数被称为友元函数；友元也可以是一个类，该类被称为友元类，在这种情况下，整个类及其所有成员都是友元。
>
> 如果要声明函数为一个类的友元，需要在类定义中该函数原型前使用关键字 **friend**，

```c++
class Box
{
   double width;
public:
   double length;
   friend void printWidth( Box box );
   void setWidth( double wid );
};
```

声明类 ClassTwo 的所有成员函数作为类 ClassOne 的友元，需要在类 ClassOne 的定义中放置如下声明

```c++
friend class ClassTwo;
```

```c++
#include <iostream>
 
using namespace std;
 
class Box
{
   double width;
public:
   friend void printWidth( Box box );
   void setWidth( double wid );
};

// 成员函数定义
void Box::setWidth( double wid )
{
    width = wid;
}

// 请注意：printWidth() 不是任何类的成员函数
void printWidth( Box box )
{
   /* 因为 printWidth() 是 Box 的友元，它可以直接访问该类的任何成员 */
   cout << "Width of box : " << box.width <<endl;
}
 
// 程序的主函数
int main( )
{
   Box box;
 
   // 使用成员函数设置宽度
   box.setWidth(10.0);
   
   // 使用友元函数输出宽度
   printWidth( box );
 
   return 0;
}
```

输出

```c++
Width of box : 10
```

> 因为友元函数没有this指针，则参数要有三种情况： 
>
> 要访问非static成员时，需要对象做参数；
>
> 要访问static成员或全局变量时，则不需要对象做参数；
>
> 如果做参数的对象是全局对象，则不需要对象做参数.
>
> 可以直接调用友元函数，不需要通过对象或指针

### 第六章 数组、指针与字符串

#### 数组

> C++ 支持**数组**数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量。
>
> 数组的声明并不是声明一个个单独的变量，比如 number0、number1、..…、number99，而是声明一个数组变量，比如 numbers，然后使用 numbers[0]、numbers[1]、..…、numbers[99] 来代表一个个单独的变量。数组中的特定元素可以通过索引访问。
>
> 所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。

> ```c++
> type arrayName [ arraySize ];//数组的声明
> ```

```c++
double balance[10];
double balance[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};
balance[4] = 50.0;//设置值
double salary = balance[9]; // 访问
```



#### 指针

> 每一个变量都有一个内存位置，每一个内存位置都定义了可使用连字号（&）运算符访问的地址，它表示了在内存中的一个地址。

```c++
#include <iostream>
 
using namespace std;
 
int main ()
{
   int  var1;
   char var2[10];
 
   cout << "var1 变量的地址： ";
   cout << &var1 << endl;
 
   cout << "var2 变量的地址： ";
   cout << &var2 << endl;
 
   return 0;
}
```

输出

```c++
var1 变量的地址： 0xbfebd5c0
var2 变量的地址： 0xbfebd5b6
```

> **指针**是一个变量，其值为另一个变量的地址，即，内存位置的直接地址。就像其他变量或常量一样，您必须在使用指针存储其他变量地址之前，对其进行声明。
>
> ```c++
> type *var-name;
> 
> int    *ip;    /* 一个整型的指针 */
> double *dp;    /* 一个 double 型的指针 */
> float  *fp;    /* 一个浮点型的指针 */
> char   *ch;    /* 一个字符型的指针 */
> ```



用指针时会频繁进行以下几个操作：定义一个指针变量、把变量地址赋值给指针、访问指针变量中可用地址的值。这些是通过使用一元运算符 *****来返回位于操作数所指定地址的变量的值。

```c++
#include <iostream>
 
using namespace std;
 
int main ()
{
   int  var = 20;   // 实际变量的声明
   int  *ip;        // 指针变量的声明
 
   ip = &var;       // 在指针变量中存储 var 的地址
 
   cout << "Value of var variable: ";
   cout << var << endl;
 
   // 输出在指针变量中存储的地址
   cout << "Address stored in ip variable: ";
   cout << ip << endl;
 
   // 访问指针中地址的值
   cout << "Value of *ip variable: ";
   cout << *ip << endl;
 
   return 0;
}
```

```
Value of var variable: 20
Address stored in ip variable: 0xbfc601ac
Value of *ip variable: 20
```



#### this 指针

> 在 C++ 中，每一个对象都能通过 **this** 指针来访问自己的地址。**this** 指针是所有成员函数的隐含参数。因此，在成员函数内部，它可以用来指向调用对象。
>
> 友元函数没有 **this** 指针，因为友元不是类的成员。只有成员函数才有 **this** 指针。

```c++
#include <iostream>
 
using namespace std;
 
class Box
{
   public:
      // 构造函数定义
      Box(double l=2.0, double b=2.0, double h=2.0)
      {
         cout <<"Constructor called." << endl;
         length = l;
         breadth = b;
         height = h;
      }
      double Volume()
      {
         return length * breadth * height;
      }
      int compare(Box box)
      {
         return this->Volume() > box.Volume();
      }
   private:
      double length;     // Length of a box
      double breadth;    // Breadth of a box
      double height;     // Height of a box
};
 
int main(void)
{
   Box Box1(3.3, 1.2, 1.5);    // Declare box1
   Box Box2(8.5, 6.0, 2.0);    // Declare box2
 
   if(Box1.compare(Box2))
   {
      cout << "Box2 is smaller than Box1" <<endl;
   }
   else
   {
      cout << "Box2 is equal to or larger than Box1" <<endl;
   }
   return 0;
}
```

输出

```
Constructor called.
Constructor called.
Box2 is equal to or larger than Box1
```



#### 指针数组与数组指针的概念辨析

> 指针数组：array of pointers，即用于存储指针的数组，也就是数组元素都是指针
>
> 数组指针：a pointer to an array，即指向数组的指针

```c++
int* a[4]     指针数组     

              表示：数组a中的元素都为int型指针    

              元素表示：*a[i]   *(a[i])是一样的，因为[]优先级高于*

int (*a)[4]   数组指针     

              表示：指向数组a的指针

              元素表示：(*a)[i]  
```

在实际应用中，对于指针数组，我们经常这样使用：

```c++
typedef` `int``* pInt;
pInt a[4];
```

```c++
#include <iostream>
 
using namespace std;
 
int main()
{
int c[4]={1,2,3,4};
int *a[4]; //指针数组
int (*b)[4]; //数组指针
b=&c;
//将数组c中元素赋给数组a
for(int i=0;i<4;i++)
{
a[i]=&c[i];
}
//输出看下结果
cout<<*a[1]<<endl; //输出2就对
cout<<(*b)[2]<<endl; //输出3就对
return 0;
}
```

> 定义了数组指针，该指针指向这个数组的首地址，必须给指针指定一个地址，容易犯的错得就是，不给b地址，直接用 (b)[i]=c[i] 给数组 b 中元素赋值，这时数组指针不知道指向哪里，调试时可能没错，但运行时肯定出现问题，使用指针时要注意这个问题。但为什么 a 就不用给他地址呢，a 的元素是指针，实际上 for 循环内已经给数组 a 中元素指定地址了。但若在 for 循环内写 a[i]=c[i]，这同样会出问题。总之一句话，定义了指针一定要知道指针指向哪里，不然要悲剧。



#### 数组与指针的关系

> 数组和指针是两种不同的类型，数组具有确定数量的元素，而指针只是一个标量值。数组可以在某些情况下转换为指针，当数组名在表达式中使用时，编译器会把数组名转换为一个指针常量，是数组中的第一个元素的地址，类型就是数组元素的地址类型，如：
> int a[5]={0,1,2,3,4}; 
> 数组名a若出现在表达式中，如int *p=a;那么它就转换为第一个元素的地址，等价于int *p=&a[0]；
> 再来一个：
> int aa[2][5]={0,1,2,3,4,  5,6,7,8,9};
> 数组名aa若出现在表达式中，如int (*p)[5]=aa;那么它就转换为第一个元素的地址，等价于int (*p)[5]=&aa[0]; 
> 但是int (*p)[5]=aa[0]; 这个就不对了，根据规则我们推一下就很明了了，aa[0]的类型是int [5]，是一个元素数量为5的整型数组，就算转化，那么转化成的是数组（int [5]）中第一个元素的地址&aa[0][0]，类型是 int *。所以，要么是int (*p)[5]=aa;要么是int (*p)[5]=&aa[0];
> 只有在两种场合下，数组名并不用指针常量来表示-–就是当数组名作为sizeof操作符或单目操作符&的操作数时，sizeof返回整个数组的长度，使用的是它的类型信息，而不是地址信息，不是指向数组的指针的长度。取一个数组名的地址所产生的是一个指向数组的指针，而不是指向某个指针常量值的指针。
>
> 如对数组a，&a表示的是指向数组a的指针，类型是int (*) [5]，所以int *p=&a;是不对的，因为右边是一个整形数组的指针int (*)[5]，而p是一个整形指针int *；



#### 字符串长度与数组长度的关系

> strlen(str)和str.length()和str.size()都可以用来求字符串的长度 
>
> tr.length()和str.size()是用于求string类对象的成员函数 
> strlen(str) 是用于求字符串数组的长度，其参数是char*

#### 指针存储的内容

> 指针的值是一个地址，通过间接寻址运算符*来区分地址与指针所指地址保存的值区分开。 
> 一个变量的地址称为该变量的指针。 
> 如果有一个变量是用来专门存放另一变量地址（即指针）的，则称它为指针变量。
>
> int p,i; 
> p = &i; 
> p的值是i的地址，p的值为i的值。 
> 指针的两个属性：内容和位置。 
> 其中位置可以存储在另一个变量中，这样便成为了指向指针的指针。 



### 第七章 继承与派生

#### 类的继承与派生

> 一个新类从已有的类那里获得已有的特性，这种现象称为类的继承。同样也可以说成已有的类派生出来了新的类。类A继承自类B也就是类B派生了类A。所以继承和派生的关系就像小学时把字句和被字句的造句一样。有了继承与派生后，就有了父类/基类与子类/派生类，C++中将类B称为父类/基类，将类A称为子类/派生类。

**派生类的声明：**

```c++
#include <iostream>

using namespace std;

class Student   //基类的声明
{
public:
    Student()
    {
        num = 1;
        name = 'Z';
        sex = 'm';
    }
    void myshow()
    {
        cout<<"num:"<<num<<endl<<"name:"<<name<<endl<<"sex:"<<sex<<endl;
    }
private:
    int num;
    char name;
    char sex;
};
class Student1:public Student //派生类的声明
{
public:
    Student1()
    {
      age = 16;
    }
    void myshow1()
    {
      myshow();
      cout<<"age:"<<age<<endl;
    }
private:
    int age;
};
int main()
{
    Student stu;
    stu.myshow();
    Student1 stu1;
    stu1.myshow1();
    getchar();
    return 0;
}

```

```c++
num:1 
name:Z 
sex:m 
age:16 
num:1 
name:Z 
sex:m
```

> - 类的继承以class Student1:public Student{} 的形式，Student是基类，Student1是派生类，继承方式为public（公用继承）。 
>
> - 派生类需要把基类的全部成员（不包括构造函数与析构函数）接收过来，不能只接受一部分。 
>
> - 类的继承方式包括：public（公用继承），private（私有继承），protected（受保护的），而不同的继承方式将影响派生类成员的访问属性。

#### 不同继承方式

- 公有继承

> 如果采用公用继承，基类中的访问属性在派生类中保持不变，即： 
> 基类中的私有属性——派生类中私有属性 
> 基类中的共用属性——派生类中共用属性 
> 基类中的受保护属性——派生类中受保护属性

```c++
class Student   //基类的声明
{
public:
    Student()
    {
        num = 1;
        name = 'Z';
        sex = 'm';
    }
    void myshow()
    {
        cout<<"num:"<<num<<endl<<"name:"<<name<<endl<<"sex:"<<sex<<endl;
    }
private:
    int num;
    char name;
    char sex;
};
class Student1:public Student //派生类的声明
{
public:
    Student1()
    {
      age = 16;
    }
    void myshow1()
    {
      myshow();
      cout<<"age:"<<age<<endl;
    }
private:
    int age;
};

```

在这个例子中，派生类Student1中的私有成员为：

```
	int num;
    char name;
    char sex;
    int age;
```

共有成员为：

```
 	myshow();
    myshow1();
```

- 私有继承

> 如果采用私有继承，基类中的访问属性在派生类中发生如下变化，即： 
> 基类中的私有属性——派生类中不可访问 
> 基类中的共用属性——派生类中私有属性 
> 基类中的受保护属性——派生类中私有属性

```c++
class Student   //基类的声明
{
public:
    Student()
    {
        num = 1;
        name = 'Z';
        sex = 'm';
    }
    void myshow()
    {
        cout<<"num:"<<num<<endl<<"name:"<<name<<endl<<"sex:"<<sex<<endl;
    }
private:
    int num;
    char name;
    char sex;
};
class Student1:private Student //派生类的声明
{
public:
    Student1()
    {
      age = 16;
    }
    void myshow1()
    {
      myshow();
      cout<<"age:"<<age<<endl;
    }
private:
    int age;
};

```

在这个例子中，派生类Student1中的私有成员为：

```
	int age;//子类新增
    myshow();//继承自父类
```

共有成员为：

```
myshow1(); //子类新增
```

子类不可访问：

```
    int num;
    char name;
    char sex;
```



- 保护继承

> 受保护的成员不能被类外访问，这一点类似私有成员，可以认为保护尘缘对类的用户来说是私有的。但是有一点与私有成员不同：受保护成员可以被派生类的成员函数引用。
>
> 如果采用保护继承，基类中的访问属性在派生类中发生如下变化，即： 
> 基类中的私有属性——派生类中不可访问 
> 基类中的共用属性——派生类中受保护属性 
>
> 基类中的受保护属性——派生类中受保护属性

```c++
class Student
{
public:
    Student()
    {
        num = 1;
        name = 'Z';
        sex = 'm';
    }
 protected:
    void myshow()
    {
        cout<<"num:"<<num<<endl<<"name:"<<name<<endl<<"sex:"<<sex<<endl;
    }
private:
    int num;
    char name;
    char sex;
};
class Student1:protected Student
{
public:
    Student1()
    {
        age = 16;
    }
    void myshow1()
    {
        cout<<"age:"<<age<<endl;
    }
private:
    int age;
};

```

在这个例子中，派生类Student1中的私有成员为：

```
int age;
```

共有成员为：

```
myshow1(); 
```

受保护成员为：

```
myshow(); 
```

子类不可访问：

```
    int num;
    char name;
    char sex;
```



### 第八章 多态性

#### 多态概念

**多态**按字面的意思就是多种形态。当类之间存在层次结构，并且类之间是通过继承关联时，就会用到多态。

C++ 多态意味着调用成员函数时，会根据调用函数的对象的类型来执行不同的函数。

基类 Shape 被派生为两个类，如下:

```c++
#include <iostream> 
using namespace std;
 
class Shape {
   protected:
      int width, height;
   public:
      Shape( int a=0, int b=0)
      {
         width = a;
         height = b;
      }
      int area()
      {
         cout << "Parent class area :" <<endl;
         return 0;
      }
};
class Rectangle: public Shape{
   public:
      Rectangle( int a=0, int b=0):Shape(a, b) { }
      int area ()
      { 
         cout << "Rectangle class area :" <<endl;
         return (width * height); 
      }
};
class Triangle: public Shape{
   public:
      Triangle( int a=0, int b=0):Shape(a, b) { }
      int area ()
      { 
         cout << "Triangle class area :" <<endl;
         return (width * height / 2); 
      }
};
// 程序的主函数
int main( )
{
   Shape *shape;
   Rectangle rec(10,7);
   Triangle  tri(10,5);
 
   // 存储矩形的地址
   shape = &rec;
   // 调用矩形的求面积函数 area
   shape->area();
 
   // 存储三角形的地址
   shape = &tri;
   // 调用三角形的求面积函数 area
   shape->area();
   
   return 0;
}
```

输出

```
Parent class area
Parent class area
```

导致错误输出的原因是，调用函数 area() 被编译器设置为基类中的版本，这就是所谓的**静态多态**，或**静态链接** - 函数调用在程序执行前就准备好了。有时候这也被称为**早绑定**，因为 area() 函数在程序编译期间就已经设置好了。

但现在，让我们对程序稍作修改，在 Shape 类中，area() 的声明前放置关键字 **virtual**，如下所示：

```c++
class Shape {
   protected:
      int width, height;
   public:
      Shape( int a=0, int b=0)
      {
         width = a;
         height = b;
      }
      virtual int area()
      {
         cout << "Parent class area :" <<endl;
         return 0;
      }
};
```

修改后，当编译和执行前面的实例代码时，它会产生以下结果：

```
Rectangle class area
Triangle class area
```

此时，编译器看的是指针的内容，而不是它的类型。因此，由于 tri 和 rec 类的对象的地址存储在 *shape 中，所以会调用各自的 area() 函数。

正如您所看到的，每个子类都有一个函数 area() 的独立实现。这就是**多态**的一般使用方式。有了多态，您可以有多个不同的类，都带有同一个名称但具有不同实现的函数，函数的参数甚至可以是相同的。

**虚函数** 是在基类中使用关键字 **virtual** 声明的函数。在派生类中重新定义基类中定义的虚函数时，会告诉编译器不要静态链接到该函数。

我们想要的是在程序中任意点可以根据所调用的对象类型来选择调用的函数，这种操作被称为**动态链接**，或**后期绑定**。

------

#### 运算符重载 和函数重载

> C++ 允许在同一作用域中的某个**函数**和**运算符**指定多个定义，分别称为**函数重载**和**运算符重载**。
>
> 重载声明是指一个与之前已经在该作用域内声明过的函数或方法具有相同名称的声明，但是它们的参数列表和定义（实现）不相同。
>
> 当您调用一个**重载函数**或**重载运算符**时，编译器通过把您所使用的参数类型与定义中的参数类型进行比较，决定选用最合适的定义。选择最合适的重载函数或重载运算符的过程，称为**重载决策**。

##### 运算符重载

> 您可以重定义或重载大部分 C++ 内置的运算符。这样，您就能使用自定义类型的运算符。
>
> 重载的运算符是带有特殊名称的函数，函数名是由关键字 operator 和其后要重载的运算符符号构成的。与其他函数一样，重载运算符有一个返回类型和一个参数列表。

```c++
Box operator+(const Box&);
```

声明加法运算符用于把两个 Box 对象相加，返回最终的 Box 对象。大多数的重载运算符可被定义为普通的非成员函数或者被定义为类成员函数。如果我们定义上面的函数为类的非成员函数，那么我们需要为每次操作传递两个参数，如下所示：

```c++
Box operator+(const Box&, const Box&);
```

```c++
#include <iostream>
using namespace std;
 
class Box
{
   public:
 
      double getVolume(void)
      {
         return length * breadth * height;
      }
      void setLength( double len )
      {
          length = len;
      }
 
      void setBreadth( double bre )
      {
          breadth = bre;
      }
 
      void setHeight( double hei )
      {
          height = hei;
      }
      // 重载 + 运算符，用于把两个 Box 对象相加
      Box operator+(const Box& b)
      {
         Box box;
         box.length = this->length + b.length;
         box.breadth = this->breadth + b.breadth;
         box.height = this->height + b.height;
         return box;
      }
   private:
      double length;      // 长度
      double breadth;     // 宽度
      double height;      // 高度
};
// 程序的主函数
int main( )
{
   Box Box1;                // 声明 Box1，类型为 Box
   Box Box2;                // 声明 Box2，类型为 Box
   Box Box3;                // 声明 Box3，类型为 Box
   double volume = 0.0;     // 把体积存储在该变量中
 
   // Box1 详述
   Box1.setLength(6.0); 
   Box1.setBreadth(7.0); 
   Box1.setHeight(5.0);
 
   // Box2 详述
   Box2.setLength(12.0); 
   Box2.setBreadth(13.0); 
   Box2.setHeight(10.0);
 
   // Box1 的体积
   volume = Box1.getVolume();
   cout << "Volume of Box1 : " << volume <<endl;
 
   // Box2 的体积
   volume = Box2.getVolume();
   cout << "Volume of Box2 : " << volume <<endl;
 
   // 把两个对象相加，得到 Box3
   Box3 = Box1 + Box2;
 
   // Box3 的体积
   volume = Box3.getVolume();
   cout << "Volume of Box3 : " << volume <<endl;
 
   return 0;
}
```

输出

```
Volume of Box1 : 210
Volume of Box2 : 1560
Volume of Box3 : 5400
```

下面是可重载的运算符列表：

| 双目算术运算符 | + (加)，-(减)，*(乘)，/(除)，% (取模)                        |
| -------------- | ------------------------------------------------------------ |
| 关系运算符     | ==(等于)，!= (不等于)，< (小于)，> (大于>，<=(小于等于)，>=(大于等于) |
| 逻辑运算符     | \|\|(逻辑或)，&&(逻辑与)，!(逻辑非)                          |
| 单目运算符     | + (正)，-(负)，*(指针)，&(取地址)                            |
| 自增自减运算符 | ++(自增)，-–(自减)                                           |
| 位运算符       | \| (按位或)，& (按位与)，~(按位取反)，^(按位异或),，<< (左移)，>>(右移) |
| 赋值运算符     | =, +=, -=, *=, /= , % = , &=, \|=, ^=, <<=, >>=              |
| 空间申请与释放 | new, delete, new[ ] , delete[]                               |
| 其他运算符     | **()**(函数调用)，**->**(成员访问)，**,**(逗号)，**[]**(下标) |

下面是不可重载的运算符列表：

- **.**：成员访问运算符

- **.\***, **->\***：成员指针访问运算符

- **::**：域运算符

- **sizeof**：长度运算符

- **?:**：条件运算符

- **#**： 预处理符号

    ------

##### 函数重载

> 在同一个作用域内，可以声明几个功能类似的同名函数，但是这些同名函数的形式参数（指参数的个数、类型或者顺序）必须不同。您不能仅通过返回类型的不同来重载函数。
>
> 下面的实例中，同名函数 **print()** 被用于输出不同的数据类型：

```c++
#include <iostream>
using namespace std;
 
class printData
{
   public:
      void print(int i) {
        cout << "整数为: " << i << endl;
      }
 
      void print(double  f) {
        cout << "浮点数为: " << f << endl;
      }
 
      void print(char c[]) {
        cout << "字符串为: " << c << endl;
      }
};
 
int main(void)
{
   printData pd;
 
   // 输出整数
   pd.print(5);
   // 输出浮点数
   pd.print(500.263);
   // 输出字符串
   char c[] = "Hello C++";
   pd.print(c);
 
   return 0;
}
```

输出

```
整数为: 5
浮点数为: 500.263
字符串为: Hello C++
```



#### 二义性问题及其解决方案

> - 在继承时，基类之间、或基类与派生类之间发生成员同名时，将出现对成员访问的不确定性——同名二义性。
>
> - 当派生类从多个基类派生，而这些基类又从同一个基类派生，则在访问此共同基类中的成员时，将产生另一种不确定性——路径二义性。

##### 同名二义性

同名隐藏规则——解决同名二义的方法

```
 当派生类与基类有同名成员时,派生类中的成员将屏蔽基类中的同名成员。

 若未特别指明，则通过派生类对象使用的都是派生类中的同名成员;

 如要通过派生类对象访问基类中被屏蔽的同名成员，应使用基类名限定(::)。
```

```c++
//多继承同名隐藏举例
#include <iostream>
using namespace std;
class B1//声明基类B1
{ 
public:
	int nV;
	void fun() {cout<<"Member of B1"<<endl;}
};
class B2//声明基类B2
{ 
public:
	int nV;
	void fun() {cout<<"Member of B2"<<endl;}
};
class D1: public B1, public B2
{ 
public:
	int nV;//同名数据成员
	void fun(){cout<<"Member of D1"<<endl;} //同名函数成员
};
 
 
void main()
{
	D1 d1;
	//用“对象名.成员名”访问子类成员。
	d1.nV=1;
	d1.fun();
	//加“作用域分辨符标识”, 可访问基类被屏蔽的成员
	d1.B1::nV=2;
	d1.B1::fun();
	d1.B2::nV=3;
	d1.B2::fun();
}

```

<font color = red>解决办法</font>

```
解决方法一：用类名来限定c1.A::f() 或c1.B::f()

解决方法二：同名覆盖，再造接口在C 中再声明一个同名成员函数f()，该函数根据需要调用A::f() 或B::f()
```

##### 路径二义性

```
为了解决路径二义性问题，引入虚基类。

–用于有共同基类的多继承场合(多层共祖)

声明
–以virtual修饰说明共同的直接基类
例：class B1: virtual public B
作用
–用来解决多继承时可能发生的对同一基类继承多次和多层而产生的二义性问题.
–为最远的派生类提供唯一的基类成员，而不重复产生个副本。
注意：

在第一级继承时就要将共同基类设计为虚基类。

虚基类举例
class B { public: int b;};
class B1 : virtual public B { private: int b1;};
class B2 : virtualpublic B { private: int b2;};
class C: public B1, public B2{ private: float d;};
在子类对象中，最远基类成分是唯一的。于是下面的访问是正确的：
C cobj;
cobj.b;

```

<font color=red>解决办法</font>

使用最远基类成员原则

```c++
//使用最远基类成员原则
#include <iostream>
using namespace std;
class B0//声明基类B0
{ 
public://外部接口
	int nV;
	void fun(){cout<<"Member of B0"<<endl;}
};
class B1: virtual public B0 //B0为虚基类，派生B1类
{ 
	public://新增外部接口
	int nV1;
};
class B2: virtual public B0 //B0为虚基类，派生B2类
{ 
	public://新增外部接口
	int nV2;
};
 
class D1: public B1, public B2//派生类D1声明
{
	public://新增外部接口
	int nVd;
	void fund(){cout<<"Member of D1"<<endl;}
};
void main()//程序主函数
{
	D1 d1;//声明D1类对象d1
	d1.nV=2;//使用最远基类成员
	d1.fun();

}
```

输出

```
Member of B0
Press any key to continue
```

> 有虚基类时的构造函数的调用次序：
>
> 无论虚基类与产生对象的派生类相隔多远，首先调用虚基类的构造函数；
>
> 然后按继承次序调用直接基类的构造函数；
>
> 如果有包含的对象，再按声明次序调用所包含对象类的构造函数；
>
> 最后才是普通类型数据成员的初始化。

有虚基类时的构造函数举例

```c++
//有虚基类时的构造函数举例
#include <iostream>
using namespace std;
class B0//声明基类B0
{ 
	public://外部接口
	B0(int n){ nV=n;cout<<"B0's constructor called \n";}
	int nV;
	void fun(){cout<<"Member of B0"<<endl;}
};
class B1: virtual public B0
{ 
public:
	B1(int a) : B0(a) {cout<<"B1's constructor called \n";}
	int nV1;
};
class B2: virtual public B0
{ 
public:
	B2(int b) : B0(b) {cout<<"B2's constructor called \n";}
	int nV2;
};
class D1: public B1, public B2
{
public:
	D1(int c) : B0(c), B1(c), B2(c),b1(c),b2(c) {cout<<"D1's constructor called \n"; }
	int nVd;
	void fund(){cout<<"Member of D1"<<endl;}
private:
	B1 b1;
	B2 b2;
};
void main()
{
	D1 d1(1);
	d1.nV=2;
	d1.fun();

}
```

输出

```
B0's constructor called
B1's constructor called
B2's constructor called
B0's constructor called
B1's constructor called
B0's constructor called
B2's constructor called
D1's constructor called
Member of B0
Press any key to continue

```

##### 总结

> 凡是编译器访问或调用时有多于一项的合法选择，这种会让编译器举棋不定的代码叫具二义性的代码。

> 发生场合
>
> - 带默认形参值的函数与同名的重载函数相遇时；
> - 继承时的同名二义；
> - 多层共祖的路径二义；
> - 形实结合时的类型兼容；
> - 用户自定义类型的转换时。

### 第十一章 流类库与输入输出

到目前为止，我们已经使用了 **iostream** 标准库，它提供了 **cin** 和 **cout** 方法分别用于从标准输入读取流和向标准输出写入流。

#### iostream

iostream头文件中4种流对象

| **对象** | **含义**   | **对应设备** | **对应的类**       | **c语言中相应的标准文件** |
| -------- | ---------- | ------------ | ------------------ | ------------------------- |
| cin      | 标准输入流 | 键盘         | istream_withassign | stdin                     |
| cout     | 标准输出流 | 屏幕         | ostream_withassign | stdout                    |
| cerr     | 标准错误流 | 屏幕         | ostream_withassign | stderr                    |
| clog     | 标准错误流 | 屏幕         | ostream_withassign | stderr                    |

##### 标准输入流 cin

> cin.get()                 //读入一个字符并返回它的值
> cin.get(一个参数)  /**/**读入一个字符并把它存储在ch
> cin.get(两个参数)  //可以读取字符串
> cin.get(三个参数)  //可以读字符串
> cin.getline()
> cin.ignore()           //读取字符并忽略指定字符
> cin.peek()            //检查下一个输入的字符，不会把字符从流中移除
> cin.putback()       //返回一个字符给一个流

> 1、使用cin，从流中读出的字符，流中就没有这字符了，再次读取时只能读取剩下的
> 2、缓冲去只有在遇到EOF、手动敲回车、流（缓存区）满时，才将流中的字符全部读出（即清空缓存区）

```c++
#include <iostream>
using namespace std;
 
int main()
{
	char ch1;
	int look;
	char str1[11] = {0};
	char str2[11] = {0};
	char str3[100] = {0};
	
	//从流中取一个字符，然后在放进去
	ch1 = cin.get();
	cin.putback(ch1);
 
	//判断流中的第一个字符是不是放进去的那个字符
	look = cin.peek();
	if(look == (int)ch1)
	{
		cout<<"cin.peek()放进去的字符在第一个位置"<<endl;
	}
	else
	{
		cout<<"cin.peek()放进去的字符不是在第一个位置"<<endl;
	}
 
	//从流中读取10个字符
	cin.get(str1,11);
 
	//从流中忽略5个字符，再读取10个字符
	cin.ignore(5);
	cin.get(str2,11,EOF);
 
	//最后读取剩下的字符，最后输出读到的所有字符
	cin.getline(str3,100);
 
	//输出读到的数据
	cout<<"第一个字符"<<ch1<<endl;
	cout<<"第一组 字符串："<<str1<<endl;
	cout<<"第二组 字符串："<<str2<<endl;
	cout<<"剩下的字符串："<<str3<<endl;
 
	system("pause");
	return 0;
}
```

输出

```
0123456789abcde9876543210zzzzzzzzzzxxxxxxxxxxxxxyyyyyyyyyyyy
cin.peek()放进去的字符在第一个位置
第一个字符0
第一组 字符串：0123456789
第二组 字符串：9876543210
剩下的字符串：zzzzzzzzzzxxxxxxxxxxxxxyyyyyyyyyyyy
```

------

##### 标准输出流 cout

预定义的对象 **cout** 是 **iostream** 类的一个实例。cout 对象"连接"到标准输出设备，通常是显示屏。**cout** 是与流插入运算符 << 结合使用的

> cout.flush()      //清空缓冲区
> cout.put()        //把字符写入流中
> cout.write()      //将字符串写入当前输出流中

```c++
#include <iostream>
 
using namespace std;
 
int main( )
{
   char str[] = "Hello C++";
 
   cout << "Value of str is : " << str << endl;
}
```

```c++
#include <iostream>
#include <iomanip>
using namespace std;
int main()
{
    cout<<setiosflags(ios::left|ios::showpoint);  // 设左对齐，以一般实数方式显示
    cout.precision(5);       // 设置除小数点外有五位有效数字 
    cout<<123.456789<<endl;
    cout.width(10);          // 设置显示域宽10 
    cout.fill('*');          // 在显示区域空白处用*填充
    cout<<resetiosflags(ios::left);  // 清除状态左对齐
    cout<<setiosflags(ios::right);   // 设置右对齐
    cout<<123.456789<<endl;
    cout<<setiosflags(ios::left|ios::fixed);    // 设左对齐，以固定小数位显示
    cout.precision(3);    // 设置实数显示三位小数
    cout<<999.123456<<endl; 
    cout<<resetiosflags(ios::left|ios::fixed);  //清除状态左对齐和定点格式
    cout<<setiosflags(ios::left|ios::scientific);    //设置左对齐，以科学技术法显示 
    cout.precision(3);   //设置保留三位小数
    cout<<123.45678<<endl;
    return 0; 
}
```

```
123.46
****123.46
999.123
1.235e+02
```

其中 cout.setf 跟 setiosflags 一样，cout.precision 跟 setprecision 一样，cout.unsetf 跟 resetiosflags 一样。

```
setiosflags(ios::fixed) 固定的浮点显示 
setiosflags(ios::scientific) 指数表示 
setiosflags(ios::left) 左对齐 
setiosflags(ios::right) 右对齐 
setiosflags(ios::skipws 忽略前导空白 
setiosflags(ios::uppercase) 16进制数大写输出 
setiosflags(ios::lowercase) 16进制小写输出 
setiosflags(ios::showpoint) 强制显示小数点 
setiosflags(ios::showpos) 强制显示符号 
```

cout.setf 常见的标志：

| 标志       | 功能                                                        |
| :--------- | :---------------------------------------------------------- |
| boolalpha  | 可以使用单词”true”和”false”进行输入/输出的布尔值.           |
| oct        | 用八进制格式显示数值.                                       |
| dec        | 用十进制格式显示数值.                                       |
| hex        | 用十六进制格式显示数值.                                     |
| left       | 输出调整为左对齐.                                           |
| right      | 输出调整为右对齐.                                           |
| scientific | 用科学记数法显示浮点数.                                     |
| fixed      | 用正常的记数方法显示浮点数(与科学计数法相对应).             |
| showbase   | 输出时显示所有数值的基数.                                   |
| showpoint  | 显示小数点和额外的零，即使不需要.                           |
| showpos    | 在非负数值前面显示”＋（正号）”.                             |
| skipws     | 当从一个流进行读取时，跳过空白字符(spaces, tabs, newlines). |
| unitbuf    | 在每次插入以后，清空缓冲区.                                 |
| internal   | 将填充字符回到符号和数值之间.                               |
| uppercase  | 以大写的形式显示科学记数法中的”e”和十六进制格式的”x”.       |

------

##### 标准错误流（cerr）

> 预定义的对象 **cerr** 是 **iostream** 类的一个实例。cerr 对象附属到标准错误设备，通常也是显示屏，但是 **cerr** 对象是非缓冲的，且每个流插入到 cerr 都会立即输出。
>
> **cerr** 也是与流插入运算符 << 结合使用的

```c++
#include <iostream>
 
using namespace std;
 
int main( )
{
   char str[] = "Unable to read....";
 
   cerr << "Error message : " << str << endl;
}
```

输出

```
Error message : Unable to read....
```

##### 标准日志流（clog）

> 预定义的对象 **clog** 是 **iostream** 类的一个实例。clog 对象附属到标准错误设备，通常也是显示屏，但是 **clog** 对象是缓冲的。这意味着每个流插入到 clog 都会先存储在缓冲在，直到缓冲填满或者缓冲区刷新时才会输出。
>
> **clog** 也是与流插入运算符 << 结合使用的

```c++
#include <iostream>
 
using namespace std;
 
int main( )
{
   char str[] = "Unable to read....";
 
   clog << "Error message : " << str << endl;
}
```

输出

```
Error message : Unable to read....
```

------

iostream 中定义的操作符：

| 操作符      | 描述                       | 输入 | 输出 |
| :---------- | :------------------------- | :--- | :--- |
| boolalpha   | 启用boolalpha标志          | √    | √    |
| dec         | 启用dec标志                | √    | √    |
| endl        | 输出换行标示，并清空缓冲区 |      | √    |
| ends        | 输出空字符                 |      | √    |
| fixed       | 启用fixed标志              |      | √    |
| flush       | 清空流                     |      | √    |
| hex         | 启用 hex 标志              | √    | √    |
| internal    | 启用 internal 标志         |      | √    |
| left        | 启用 left 标志             |      | √    |
| noboolalpha | 关闭boolalpha 标志         | √    | √    |
| noshowbase  | 关闭showbase 标志          |      | √    |
| noshowpoint | 关闭showpoint 标志         |      | √    |
| noshowpos   | 关闭showpos 标志           |      | √    |
| noskipws    | 关闭skipws 标志            | √    |      |
| nounitbuf   | 关闭unitbuf 标志           |      | √    |
| nouppercase | 关闭uppercase 标志         |      | √    |
| oct         | 启用 oct 标志              | √    | √    |
| right       | 启用 right 标志            |      | √    |
| scientific  | 启用 scientific 标志       |      | √    |
| showbase    | 启用 showbase 标志         |      | √    |
| showpoint   | 启用 showpoint 标志        |      | √    |
| showpos     | 启用 showpos 标志          |      | √    |
| skipws      | 启用 skipws 标志           | √    |      |
| unitbuf     | 启用 unitbuf 标志          |      | √    |
| uppercase   | 启用 uppercase 标志        |      | √    |
| ws          | 跳过所有前导空白字符       | √    |      |

| 操作符                | 描述                     | 输入 | 输出 |
| :-------------------- | :----------------------- | :--- | :--- |
| resetiosflags(long f) | 关闭被指定为f的标志      | √    | √    |
| setbase(int base)     | 设置数值的基本数为base   |      | √    |
| setfill(int ch)       | 设置填充字符为ch         |      | √    |
| setiosflags(long f)   | 启用指定为f的标志        | √    | √    |
| setprecision(int p)   | 设置数值的精度(四舍五入) |      | √    |
| setw(int w)           | 设置域宽度为w            |      | √    |

#### fstream

从文件读取流和向文件写入流需要用到 C++ 中另一个标准库 **fstream**，它定义了三个新的数据类型：

| 数据类型 | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| ofstream | 该数据类型表示输出文件流，用于创建文件并向文件写入信息。     |
| ifstream | 该数据类型表示输入文件流，用于从文件读取信息。               |
| fstream  | 该数据类型通常表示文件流，且同时具有 ofstream 和 ifstream 两种功能，这意味着它可以创建文件，向文件写入信息，从文件读取信息。 |

要在 C++ 中进行文件处理，必须在 C++ 源代码文件中包含头文件 <iostream> 和 <fstream>。

##### 打开文件

在从文件读取信息或者向文件写入信息之前，必须先打开文件。**ofstream** 和 **fstream** 对象都可以用来打开文件进行写操作，如果只需要打开文件进行读操作，则使用 **ifstream** 对象。

下面是 open() 函数的标准语法，open() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。

```
void open(const char *filename, ios::openmode mode);
```

在这里，**open()** 成员函数的第一参数指定要打开的文件的名称和位置，第二个参数定义文件被打开的模式。

| 模式标志   | 描述                                                         |
| :--------- | :----------------------------------------------------------- |
| ios::app   | 追加模式。所有写入都追加到文件末尾。                         |
| ios::ate   | 文件打开后定位到文件末尾。                                   |
| ios::in    | 打开文件用于读取。                                           |
| ios::out   | 打开文件用于写入。                                           |
| ios::trunc | 如果该文件已经存在，其内容将在打开文件之前被截断，即把文件长度设为 0。 |

您可以把以上两种或两种以上的模式结合使用。例如，如果您想要以写入模式打开文件，并希望截断文件，以防文件已存在，那么您可以使用下面的语法：

```
ofstream outfile;
outfile.open("file.dat", ios::out | ios::trunc );
```

类似地，您如果想要打开一个文件用于读写，可以使用下面的语法：

```c++
ifstream  afile;
afile.open("file.dat", ios::out | ios::in );
```



------

##### 关闭文件

当 C++ 程序终止时，它会自动关闭刷新所有流，释放所有分配的内存，并关闭所有打开的文件。但程序员应该养成一个好习惯，在程序终止前关闭所有打开的文件。

下面是 close() 函数的标准语法，close() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。

```c++
void close();
```



------

##### 写入文件

在 C++ 编程中，我们使用流插入运算符（ << ）向文件写入信息，就像使用该运算符输出信息到屏幕上一样。唯一不同的是，在这里您使用的是 **ofstream** 或 **fstream** 对象，而不是 **cout** 对象。



------

##### 读取文件

在 C++ 编程中，我们使用流提取运算符（ >> ）从文件读取信息，就像使用该运算符从键盘输入信息一样。唯一不同的是，在这里您使用的是 **ifstream** 或 **fstream** 对象，而不是 **cin** 对象。



------

##### 读取 & 写入

```c++
#include <fstream>
#include <iostream>
using namespace std;
 
int main ()
{
    
   char data[100];
 
   // 以写模式打开文件
   ofstream outfile;
   outfile.open("afile.dat");
 
   cout << "Writing to the file" << endl;
   cout << "Enter your name: "; 
   cin.getline(data, 100);
 
   // 向文件写入用户输入的数据
   outfile << data << endl;
 
   cout << "Enter your age: "; 
   cin >> data;
   cin.ignore();
   
   // 再次向文件写入用户输入的数据
   outfile << data << endl;
 
   // 关闭打开的文件
   outfile.close();
 
   // 以读模式打开文件
   ifstream infile; 
   infile.open("afile.dat"); 
 
   cout << "Reading from the file" << endl; 
   infile >> data; 
 
   // 在屏幕上写入数据
   cout << data << endl;
   
   // 再次从文件读取数据，并显示它
   infile >> data; 
   cout << data << endl; 
 
   // 关闭打开的文件
   infile.close();
 
   return 0;
}
```

输出

```
$./a.out
Writing to the file
Enter your name: Zara
Enter your age: 9
Reading from the file
Zara
9
```

上面的实例中使用了 cin 对象的附加函数，比如 getline()函数从外部读取一行，ignore() 函数会忽略掉之前读语句留下的多余字符。



### 第十二章 异常处理

> 异常是程序在执行期间产生的问题。C++ 异常是指在程序运行时发生的特殊情况，比如尝试除以零的操作。
>
> 异常提供了一种转移程序控制权的方式。C++ 异常处理涉及到三个关键字：**try、catch、throw**。
>
> - **throw:** 当问题出现时，程序会抛出一个异常。这是通过使用 **throw** 关键字来完成的。
> - **catch:** 在您想要处理问题的地方，通过异常处理程序捕获异常。**catch** 关键字用于捕获异常。
> - **try:** **try** 块中的代码标识将被激活的特定异常。它后面通常跟着一个或多个 catch 块。
>
> 如果有一个块抛出一个异常，捕获异常的方法会使用 **try** 和 **catch** 关键字。try 块中放置可能抛出异常的代码，try 块中的代码被称为保护代码。

```c++
try
{
   // 保护代码
}catch( ExceptionName e1 )
{
   // catch 块
}catch( ExceptionName e2 )
{
   // catch 块
}catch( ExceptionName eN )
{
   // catch 块
}
```

#### 抛出异常

可以使用 **throw** 语句在代码块中的任何地方抛出异常。throw 语句的操作数可以是任意的表达式，表达式的结果的类型决定了抛出的异常的类型。

```c++
double division(int a, int b)
{
   if( b == 0 )
   {
      throw "Division by zero condition!";
   }
   return (a/b);
}
```

#### 捕获异常

> **catch** 块跟在 **try** 块后面，用于捕获异常。您可以指定想要捕捉的异常类型，这是由 catch 关键字后的括号内的异常声明决定的。

```c++
try
{
   // 保护代码
}catch( ExceptionName e )
{
  // 处理 ExceptionName 异常的代码
}
```

```c++
#include <iostream>
using namespace std;
 
double division(int a, int b)
{
   if( b == 0 )
   {
      throw "Division by zero condition!";
   }
   return (a/b);
}
 
int main ()
{
   int x = 50;
   int y = 0;
   double z = 0;
 
   try {
     z = division(x, y);
     cout << z << endl;
   }catch (const char* msg) {
     cerr << msg << endl;
   }
 
   return 0;
}
```

输出

```
Division by zero condition!
```



### 重点

- 生存期与作用域
- 静态数据成员
- 封装、继承、对象、类、多态等面向对象的概念
- 递归调用及其时间和空间复杂度、内联函数、构造函数、析构函数、友元函数
- 数组与指针的关系、指针的主要特征、公有继承、私有继承和保护继承



