# Java 基础笔记
## 0.说在最前面的话
该笔记主要对Java的相关基础知识进行一个简单的梳理，并且将基础部分的代码进行简单的书写，该部分主要面对0基础入门的同学，如果你已经完成了Java基础的学习或已经在学校
上过相关的课程，请移步其他部分。
## 1.Helloworld！
### 1.1 输入与输出

```java
//base 1-1
import java.util.Scanner;

public class Hello {
    public static void main(String[] args) {
        //输出
        System.out.println("Hello World!");
        //输入
        Scanner in = new Scanner(System.in);
        System.out.println("echo:" + in.nextLine());
    }
}
```

### 1.2 变量
定义变量的一般形式：<变量类型><变量名称>
```java
// base 1-2
import java.util.Scanner;
public  class  Hello {
    public static  void  main(String[] args) {
        Scanner in = new Scanner(System.in);
        int price = in.nextInt();
        System.out.println("剩余金额：" + (100 - price));
    }
}
```

### 1.3 赋值
使用“ = ”进行赋值操作，将等号后面的值赋给前面的变量。
```java
public  class hello{
    public static void main(String[] args) {
        int p = 9;
    }
}
```

### 1.4 浮点数
```java
public class Hello{
    public static void main(String[] args) {
        double i = 12.0;
    }
}
```
浮点数在Java的运算中存在误差。

### 1.5 运算符优先级
| 优先级 | 运算符 | 运算    | 结合关系 | 举例      |
|-----|-----|-------|------|---------|
| 1   | +   | 单目取正  | 自右向左 | a* + b  |
| 1   | -   | 单目取负  | 自右向左 | a* - b  |
| 2   | *   | 乘法    | 自左向右 | a * b   |
| 2   | /   | 除法    | 自左向右 | a/b     |
| 2   | %   | 取余    | 自左向右 | a%b     |
| 3   | +   | 加法    | 自左向右 | a + b   |
| 3   | -   | 加法    | 自左向右 | a - b   |
| 3   | +   | 字符串连接 | 自左向右 | "a"+"b" |
| 4   | =   | 赋值    | 自右向左 | a = b   |
当不同的运算符同时出现时，优先级高的先进行运算。

### 1.6 类型转换
```java
public class Trans{
    public static void main(String[] args) {
        double a = 9.123;
        int b;
        b = (int)a;
    }
}
```
使用```(int)a```这样的形式可以将变量的类型进行转换。
### 1.7 比较
可以使用比较运算符进行比较，返回值是一个布尔型的函数。
关系运算符

| 运算符 | 意义    |
|-----|-------|
| ==  | 相等    |
| !=  | 不相等   |
| \>  | 大于    |
| <   | 大于等于  |
| >=  | 小于    |
| <=  | 小于等于  |

在判断两个浮点数时一般不可以使用相等，应该使用两个数的绝对值相减是否小于一个极小的数，因为浮点运算存在误差

### 1.8 if语句
使用if语句进行判断，控制相关的语句，例如根据两支球队的比分情况输出结果。

```java
import java.util.Scanner;

public class whoiswin {
    public static void main(String[] args) {
        int homeScore = 0;
        int awayScore = 0;
        Scanner in = new Scanner(System.in);
        homeScore = in.nextInt();
        awayScore = in.nextInt();
        if(homeScore > awayScore){
            System.out.println("Home win!");
        } 
        else if (homeScore == awayScore) {
            System.out.println("Draw!");
        }
        else {
            System.out.println("Away win!");
        }
    }
}
```
通过上述一个简单的通过比分判断比赛结果的例子可以很好的展示if-else的用法。

### 1.9 多路分支 Switch Case

```java
import java.util.Scanner;

public class choose {
    public static void main(String[] args) {
        int a = 0;
        Scanner in = new Scanner(System.in);
        a = in.nextInt();
        switch (a) {
            case 1:
            {
                System.out.println("1");
                break;
            }
            case 2:
            {
                System.out.println("2");
                break;
            }
            default:
            {
                System.out.println("None!");
                break;
            }
        }
    }
}
```
其中 如果所有的case都不匹配，就执行default里面的内容，并且，在每个case中需要有break才能终止switch内容中的执行。
## 2
### 2.1 while循环
```java
public class buy {
    public static void main(String[] args) {
        while(true) {
            System.out.println("test");
        }
    }
}
```

### 2.2 do while循环
```java
public class buy {
    public static void main(String[] args) {
        do {
            System.out.println("123");
        }while (true);
    }
}
```

### 2.3 for循环
```java
public class circle {
    public static void main(String[] args) {
        int sum = 0;
        for(int i = 0;i < 100; i++)
        {
            sum += i;
        }
        System.out.println(sum);
    }
}
```

### 2.4 break & continue 循环控制
在循环中使用break可以跳出循环。
在循环中使用continue可以结束当前轮次的循环进入下一个轮次的循环。

### 2.5 逻辑运算
逻辑运算是对逻辑量进行的运算。

- !a：代表与a相反的布尔型
- a&&b：全真为真
- a||b：全假为假

## 3. 数组
### 3.1 数组基础
数组就是将一组数按照一定的顺序进行存储的数据结构。

### 3.1 数组的创建
其使用方法如下：
```java
public class nubmers {
    public static void main(String[] args) {
        int[] num = new int[100];
    }
}
```

定义方法
> <类型>[] <name> = new<类型>[元素个数]
- int[] a = new int[100];
- double[] b = new double[1000];

- 元素个数必须是整数
- 元素个数必须给出
- 元素个数可以是变量

### 3.2 访问数组
数组的第一个元素的下标是0，最后一个下标为-1。
编译器不会检查你的数组下标是否合法，但在运行时如果出现了无效的数组下标会导致程序抛出异常。

### 3.3 数组变量
- new创建的数组会得到默认的0值
- int[] scores = {87,98,69,54,65,99};
- 可以直接使用大括号给出所数组的所有元素的初始值
- 不需要给出数组的大小，编译器会自动设定长度。

> 数组变量
- 数组变量是数组的管理者而非数组本身
- 数组必须创建出来然后交给数组变量来管理
- 数组变量之间的赋值是管理权限的赋予
- 数组变量之间的比较是判断是否管理的同一个数组。

> 数组的复制
- 数组的复制必须将数组进行遍历并进行逐一的复制。

### 3.4 数组的遍历
> 找到数组中是否存在某个数

```java
import java.util.Scanner;

public class find {
    public static void main(String[] args) {
        int[] nums = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        Scanner in = new Scanner(System.in);
        int x = in.nextInt();
        int locs = -1;
        for (int i = 0; i < nums.length; i++)
        {
            if(x == nums[i])
            {
                locs = i;
                break;
            }
        }
        System.out.println(x + "'s position is " + locs);
    }
}
```
> 另一种for循环的方法

```java
import java.util.Scanner;

public class find {
    public static void main(String[] args) {
        int[] num = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        boolean isin = false;
        Scanner in = new Scanner(System.in);
        int x = in.nextInt();
        for (int k : num)
        {
            if(k == x)
            {
                isin = true;
                break;
            }
        }
        if(isin){
            System.out.println("Is In!");
        }
        else {
            System.out.println("Is Not IN!");
        }
    }
}
```

可以使用这种方式直接对数组进行遍历。

### 3.5 二维数组
- int[][] a = new int[][];
- 这样定义的a是一个3行5列的矩阵

> 二维数组的初始化
```java
public class shuzu {
    public static void main(String[] args) {
        int[][] nums = {
                {1,2,3,4}, 
                {5,6,7},
        };
    }
}
```

- 通过这样的方式初始化编译器会自己设定二维数组的大小
- 每行一个{}，都好分割
- 最后一个逗号可以存在
- 如果省略，默认补零

## 4. 字符
### 4.1 字符类型
- 单个出现的字符是一种特殊的字符类型：char
- 用单引号表示的字符字面量：'a','1'
- Java使用Unicode来表示字符，可以表达包括汉字在内的多种文字。

### 4.2 逃逸字符
- 用来表达无法印出来的控制字符和特殊字符，它由一个反斜杠“\”开头，后面跟上另一个字符
，这两个字符合起来，组成了一个字符。

其中几个比较常见的逃逸字符如下：
- \b 回退一格
- \t 到下一个表格位
- \n 换行
- \r 回车
- \" 双引号
- \' 单引号
- \\ 反斜杠本身

### 4.3 包裹类型
- 每种基础类型都有对应的包裹类型

| 基础类型    | 包裹类型      |
|---------|-----------|
| boolean | Boolean   |
| char    | Character |
| int     | Integer   |
| double  | Double    |

> 包裹类型的用处
- 获得该类型的最大值最小值
- Integer.MIN_VALUE
- Integer.MAX_VALUE

> .运算符
- 当需要让一个类或对象做事情的时候，用. 运算符
- a.length
- Integer.MAX_VALUE

### 4.4 字符串变量
- String s;
- String是一个类，String的变量是对象的管理者而非所有者
- 字符串比较要用equal

```java
import java.util.Scanner;

public class str {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        String s = new String("a string");
        s = in.next();
        s = in.nextLine();
        System.out.println(s + 12 + 24);
        System.out.println(s.equals("test"));
    }
}
```

### 4.5 字符串操作

- compareTo() 字符串比大小
- compareToIgnoreCase() 忽略大小写比大小
- charAt() 在某处的字符是什么
- substr()
- indexOf()
- startsWith()
- endsWith()
- trim() 去两端的空格
- replace() 字符串替换
- toLowerCase()
- toUpperCase()

```java
import java.util.Scanner;

public class sss {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        string s1;
        string s2;
        s1 = in.next();
        s2 = in.next();
        System.out.println(s1.compareTo(s2));
        System.out.println(s1.compareToIgnoreCase(s2));
        System.out.println(s1.charAt(1));
        System.out.println(s1.substr(0, 2));
        System.out.println(s1.indexOf('A'));
    }
}
```

需要注意的是，上述的方法都不会改变string本身，只是将操作后的字符串作为返回值返回。
- switch-case也可以使用字符串作为case的入口

### 4.6 Math类
Math为我们提供了多种可以使用的数学方法用于日常程序中需要的大部分基本数学操作。
- round() 四舍五入取整
- random() 给出一个0,1之间的随机数
- pow() 进行乘方操作

## 5. 函数
### 5.1 定义函数
- 什么是函数？

函数就是一个代码块，通过接收参数并使用参数进行相关的操作，并返回一个结果（返回值）
，同时也可以没有返回值，只是对传入的参数进行一些操作。

函数的定义方法如下：

```java
import java.util.Scanner;

public class hanshu {
    //函数定义部分
    public static void sum(int a, int b) {
        int i;
        int sum = 0;
        for (i = a; i <= b; i++) {
            sum += i;
        }
        System.out.println(sum);
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int a = in.nextInt();
        int b = in.nextInt();
        sum(a, b);
    }
}
```

### 5.2 调用函数
调用函数的方式```函数名（参数值）```

函数的返回值使用return进行返回，返回类型和定义函数时定义的函数返回值类型一致

void是没有返回值的函数
- void 函数名(参数表)
- 不能使用带值的return
- 可以没有return
- 调用的时候不能做返回值的赋值

### 5.3 参数的传递
对于我们定义的函数，在使用时需要将我们想要参与操作的参数传入到函数中进行运算
，在某些类型下，在传递参数时函数会自动帮助我们完成类型转换。
可转换的类型如下：
- char -> int -> double

但是当类型之间无法进行转换时，就要将正确的函数参数类型传入到函数当中，才能得到
目标返回值，否则可能会出现编译出错或无法执行的情况。

### 5.4 形式参数和实际参数
在使用函数时，我们实际上是将参数传入到函数当中，在函数中对我们传入的参数是无法进行改变的，
想要改变我们传入的，

### 5.5 变量的生存期和作用域
- 生存期：什么时候变量开始出现了，到什么时候消亡
- 作用域：在什么范围内可以访问这个变量
- 对于本地变量来说，这两个问题的答案是统一的

本地变量的规则：
- 本地变量是定义在块内的
- 它可以定义在函数的块内和语句的块内
- 程序运行到这个块之前的时候其中的变量才存在，其他时候不存在。
- 块外面定义的变量在里面仍然有效。
- 不能在一个块内定义同名的变量
- 本地变量不会被默认初始化。