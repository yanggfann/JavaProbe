## Java基础语法

####Java学习资料
* [Java教学网站](<https://www.tutorialspoint.com/java/index.htm>)
* 安装jdk
  * [Windows环境安装Java](<http://www.cnblogs.com/liuhongfeng/p/4177568.html>)
  * [Ubuntu环境下安装Java](<http://topspeedsnail.com/ubuntu16-install-java-jdk/>)
  * [Mac环境下安装Java](<https://www.jianshu.com/p/0036a344509e>)

#### 对象、类、方法、实例变量

* **对象**：对象是类的一个实例，有状态和行为。
* **类**：类是一个模板，它描述一类对象的行为和状态。
* **方法**：方法就是行为，一个类可以有很多方法。
* **实例变量**：每个对象都有独特的实例变量，对象的状态由这些实例变量的值决定。

#### 基本语法

* **大小写敏感**：Java 是大小写敏感的，这就意味着标识符 Hello 与 hello 是不同的。
* **类名**：对于所有的类来说，类名的首字母应该大写。如果类名由若干单词组成，那么每个单词的首字母应该大写，例如 **MyFirstJavaClass**。
* **方法名**：所有的方法名都应该以小写字母开头。如果方法名含有若干单词，则后面的每个单词首字母大写。
* **源文件名**：源文件名必须和类名相同。当保存文件的时候，你应该使用类名作为文件名保存（切记 Java 是大小写敏感的），文件名的后缀为 **.java**。（如果文件名和类名不相同则会导致编译错误）。
* **主方法入口**：所有的 Java 程序由 **public static void main(String[] args)** 方法开始执行。

#### Java标识符

类名、变量名以及方法名都被称为标识符。

* 所有的标识符都应该以字母（A-Z 或者 a-z）,美元符（$）、或者下划线（_）开始
* 首字符之后可以是字母（A-Z 或者 a-z）,美元符（$）、下划线（_）或数字的任何字符组合
* 关键字不能用作标识符
* 标识符是大小写敏感的
* 合法标识符举例：age、$salary、_value、__1_value
* 非法标识符举例：123abc、-salary

#### Java修饰符

Java可以使用修饰符来修饰类中方法和属性。

* 访问控制修饰符 : default, public , protected, private
* 非访问控制修饰符 : final, abstract, static, synchronized

#### Java变量

* 局部变量
* 类变量（静态变量）
* 成员变量（非静态变量）

#### Java数组

数组是储存在堆上的对象，可以保存多个同类型变量。

#### Java枚举

枚举限制变量只能是预先设定好的值。使用枚举可以减少代码中的 bug。

#### Java关键字

关键字不能用于常量、变量、和任何标识符的名称。

## Java基本数据类型

#### 内置数据类型

* **Byte**
  * byte 数据类型是8位、有符号的，以二进制补码表示的整数；
  * 默认值是 **0**；
* **Short**
  * short 数据类型是 16 位、有符号的以二进制补码表示的整数
  * 默认值是 **0**；
* **Integer**
  * int 数据类型是32位、有符号的以二进制补码表示的整数；
  * 一般地整型变量默认为 int 类型；
  * 默认值是 **0** ；
* **Long**
  * long 数据类型是 64 位、有符号的以二进制补码表示的整数；
  * 这种类型主要使用在需要比较大整数的系统上；
  * 默认值是 **0L**；
* **Float**
  * float 数据类型是单精度、32位、符合IEEE 754标准的浮点数；
  * float 在储存大型浮点数组的时候可节省内存空间；
  * 默认值是 **0.0f**；
  * 浮点数不能用来表示精确的值，如货币；
* **Double**
  * double 数据类型是双精度、64 位、符合IEEE 754标准的浮点数；
  * 浮点数的默认类型为double类型；
  * double类型同样不能表示精确的值，如货币；
  * 默认值是 **0.0d**；
* **Boolean**
  * boolean数据类型表示一位的信息；
  * 只有两个取值：true 和 false；
  * 默认值是 **false**；
* **Character**
  * char类型是一个单一的 16 位 Unicode 字符；
  * char 数据类型可以储存任何字符；

对于数值类型的基本类型的取值范围，我们无需强制去记忆，因为它们的值都已经以常量的形式定义在对应的包装类中了。

```
public class PrimitiveTypeTest {  
    public static void main(String[] args) {  
        // byte  
        System.out.println("基本类型：byte 二进制位数：" + Byte.SIZE);  
        System.out.println("包装类：java.lang.Byte");  
        System.out.println("最小值：Byte.MIN_VALUE=" + Byte.MIN_VALUE);  
        System.out.println("最大值：Byte.MAX_VALUE=" + Byte.MAX_VALUE);  
        System.out.println();
    }
}
```

实际上，JAVA中还存在另外一种基本类型void，它也有对应的包装类 java.lang.Void，不过我们无法直接对它们进行操作。

#### 引用类型

* 在Java中，引用类型的变量非常类似于C/C++的指针。
* 对象、数组都是引用数据类型。
* 所有引用类型的默认值都是null。
* 一个引用变量可以用来引用任何与之兼容的类型。

#### Java常量

常量在程序运行时是不能被修改的。

在 Java 中使用 final 关键字来修饰常量，声明方式和变量类似：

```
final double PI = 3.1415927;
```

Java语言支持一些特殊的转义字符序列。

| 符号   | 字符含义                 |
| ------ | ------------------------ |
| \n     | 换行 (0x0a)              |
| \r     | 回车 (0x0d)              |
| \f     | 换页符(0x0c)             |
| \b     | 退格 (0x08)              |
| \0     | 空字符 (0x20)            |
| \s     | 字符串                   |
| \t     | 制表符                   |
| \\"    | 双引号                   |
| \\‘    | 单引号                   |
| \\\    | 反斜杠                   |
| \ddd   | 八进制字符 (ddd)         |
| \uxxxx | 16进制Unicode字符 (xxxx) |

#### 自动类型转换

**整型、实型（常量）、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后进行运算。**

转换从低级到高级。

```
低  ------------------------------------>  高

byte,short,char—> int —> long—> float —> double 
```

数据类型转换必须满足以下规则：

* 不能对boolean类型进行类型转换。

* 不能把对象类型转换成不相关类的对象。

* 在把容量大的类型转换为容量小的类型时必须使用强制类型转换。

* 转换过程中可能导致溢出或损失精度，例如：

  ```
  int i =128;   
  byte b = (byte)i;
  ```

  因为 byte 类型是 8 位，最大值为127，所以当 int 强制转换为 byte 类型时，值 128 时候就会导致溢出。

* 浮点数到整数的转换是通过舍弃小数得到，而不是四舍五入，例如：

  ```
  (int)23.7 == 23;        
  (int)-45.89f == -45
  ```

## Java 变量类型

在Java语言中，所有的变量在使用前必须声明。声明变量的基本格式如下：

```
type identifier [ = value][, identifier [= value] ...] ;
```

格式说明：type为Java数据类型。identifier是变量名。可以使用逗号隔开来声明多个同类型变量。

Java语言支持的变量类型有：

1. 类变量：独立于方法之外的变量，用 static 修饰。
2. 实例变量：独立于方法之外的变量，不过没有 static 修饰。
3. 局部变量：类的方法中的变量。

```
public class Variable{
    static int allClicks=0;    // 类变量
 
    String str="hello world";  // 实例变量
 
    public void method(){
 
        int i =0;  // 局部变量
 
    }
}
```

#### Java局部变量

* 局部变量声明在方法、构造方法或者语句块中；
* 局部变量在方法、构造方法、或者语句块被执行的时候创建，当它们执行完成后，变量将会被销毁；
* 访问修饰符不能用于局部变量；
* 局部变量只在声明它的方法、构造方法或者语句块中可见；
* 局部变量是在栈上分配的。
* 局部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

#### 实例变量

* 实例变量声明在一个类中，但在方法、构造方法和语句块之外；
* 当一个对象被实例化之后，每个实例变量的值就跟着确定；
* 实例变量在对象创建的时候创建，在对象被销毁的时候销毁；
* 实例变量的值应该至少被一个方法、构造方法或者语句块引用，使得外部能够通过这些方式获取实例变量信息；
* 实例变量可以声明在使用前或者使用后；
* 访问修饰符可以修饰实例变量；
* 实例变量对于类中的方法、构造方法或者语句块是可见的。一般情况下应该把实例变量设为私有。通过使用访问修饰符可以使实例变量对子类可见；
* 实例变量具有默认值。数值型变量的默认值是0，布尔型变量的默认值是false，引用类型变量的默认值是null。变量的值可以在声明时指定，也可以在构造方法中指定；
* 实例变量可以直接通过变量名访问。但在静态方法以及其他类中，就应该使用完全限定名：ObejectReference.VariableName。

#### 类变量（静态变量）

* 类变量也称为静态变量，在类中以 static 关键字声明，但必须在方法之外。
* 无论一个类创建了多少个对象，类只拥有类变量的一份拷贝。
* 静态变量除了被声明为常量外很少使用。常量是指声明为public/private，final和static类型的变量。常量初始化后不可改变。
* 静态变量储存在静态存储区。经常被声明为常量，很少单独使用static声明变量。
* 静态变量在第一次被访问时创建，在程序结束时销毁。
* 与实例变量具有相似的可见性。但为了对类的使用者可见，大多数静态变量声明为public类型。
* 默认值和实例变量相似。数值型变量默认值是0，布尔型默认值是false，引用类型默认值是null。变量的值可以在声明的时候指定，也可以在构造方法中指定。此外，静态变量还可以在静态语句块中初始化。
* 静态变量可以通过：*ClassName.VariableName*的方式访问。
* 类变量被声明为public static final类型时，类变量名称一般建议使用大写字母。如果静态变量不是public和final类型，其命名方式与实例变量以及局部变量的命名方式一致。

## Java修饰符

#### 访问控制修饰符

* **public** : 对所有类可见。使用对象：类、接口、变量、方法
* **protected** : 对同一包内的类和所有子类可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**。
* **default** (即缺省，什么也不写）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。
* **private** : 在同一类内可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**

| 修饰符      | 当前类 | 同一包内 | 子孙类（同一包） | 子孙类（不同包） | 其他包 |
| ----------- | ------ | -------- | ---------------- | ---------------- | ------ |
| `public`    | Y      | Y        | Y                | Y                | Y      |
| `protected` | Y      | Y        | Y                | Y/N              | N      |
| `default`   | Y      | Y        | Y                | N                | N      |
| `private`   | Y      | N        | N                | N                | N      |

#### 访问控制和继承

* 父类中声明为 public 的方法在子类中也必须为 public。
* 父类中声明为 protected 的方法在子类中要么声明为 protected，要么声明为 public，不能声明为 private。
* 父类中声明为 private 的方法，不能够被继承。

#### 非访问修饰符

* **static** 

  static 修饰符，用来修饰类方法和类变量。

* **final**

  final 修饰符，用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。

* **abstract**

  abstract 修饰符，用来创建抽象类和抽象方法。

* **synchronized** 和 **volatile** 修饰符，主要用于线程的编程。

## Java运算符

#### 算术运算符

| 操作符 | 描述                              |
| ------ | --------------------------------- |
| +      | 加法 - 相加运算符两侧的值         |
| -      | 减法 - 左操作数减去右操作数       |
| *      | 乘法 - 相乘操作符两侧的值         |
| /      | 除法 - 左操作数除以右操作数       |
| ％     | 取余 - 左操作数除以右操作数的余数 |
| ++     | 自增: 操作数的值增加1             |
| --     | 自减: 操作数的值减少1             |

**前缀自增自减法(++a,--a):** 先进行自增或者自减运算，再进行表达式运算。

**后缀自增自减法(a++,a--):** 先进行表达式运算，再进行自增或者自减运算。

#### 关系运算符

| 运算符 | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| ==     | 检查如果两个操作数的值是否相等，如果相等则条件为真。         |
| !=     | 检查如果两个操作数的值是否相等，如果值不相等则条件为真。     |
| >      | 检查左操作数的值是否大于右操作数的值，如果是那么条件为真。   |
| <      | 检查左操作数的值是否小于右操作数的值，如果是那么条件为真。   |
| >=     | 检查左操作数的值是否大于或等于右操作数的值，如果是那么条件为真。 |
| <=     | 检查左操作数的值是否小于或等于右操作数的值，如果是那么条件为真。 |

#### 位运算符

| 操作符 | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| ＆     | 如果相对应位都是1，则结果为1，否则为0                        |
| \|     | 如果相对应位都是0，则结果为0，否则为1                        |
| ^      | 如果相对应位值相同，则结果为0，否则为1                       |
| 〜     | 按位取反运算符翻转操作数的每一位，即0变成1，1变成0。         |
| <<     | 按位左移运算符。左操作数按位左移右操作数指定的位数。A = 60 =0011 1100 ，A << 2得到240，即 1111 0000 |
| >>     | 按位右移运算符。左操作数按位右移右操作数指定的位数。         |
| >>>    | 按位右移补零操作符。左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充。 |

#### 逻辑运算符

| 操作符 | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| &&     | 称为逻辑与运算符。当且仅当两个操作数都为真，条件才为真。     |
| \| \|  | 称为逻辑或操作符。如果任何两个操作数任何一个为真，条件为真。 |
| ！     | 称为逻辑非运算符。用来反转操作数的逻辑状态。如果条件为true，则逻辑非运算符将得到false。 |

**短路逻辑运算符**

当使用与逻辑运算符时，在两个操作数都为true时，结果才为true，但是当得到第一个操作为false时，其结果就必定是false，这时候就不会再判断第二个操作了。

```
 int a = 5;//定义一个变量；
 boolean b = (a<4)&&(a++<10);
 该程序使用到了短路逻辑运算符(&&)，首先判断 a<4 的结果为 false，则 b 的结果必定是 false，所以不再执行第二个操作 a++<10 的判断，所以 a 的值为 5。
```

#### 赋值运算符

| 操作符  | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| =       | 简单的赋值运算符，将右操作数的值赋给左侧操作数               |
| + =     | 加和赋值操作符，它把左操作数和右操作数相加赋值给左操作数     |
| - =     | 减和赋值操作符，它把左操作数和右操作数相减赋值给左操作数     |
| * =     | 乘和赋值操作符，它把左操作数和右操作数相乘赋值给左操作数     |
| / =     | 除和赋值操作符，它把左操作数和右操作数相除赋值给左操作数     |
| （％）= | 取模和赋值操作符，它把左操作数和右操作数取模后赋值给左操作数 |
| << =    | 左移位赋值运算符                                             |
| >> =    | 右移位赋值运算符                                             |
| ＆=     | 按位与赋值运算符                                             |
| ^ =     | 按位异或赋值操作符                                           |
| \| =    | 按位或赋值操作符                                             |

#### 条件运算符（？：）

条件运算符也被称为三元运算符。该运算符有3个操作数，并且需要判断布尔表达式的值。该运算符主要是决定哪个值应该赋值给变量。

```
variable x = (expression) ? value if true : value if false
```

#### instanceof运算符

该运算符用于操作对象实例，检查该对象是否是一个特定类型（类类型或接口类型）。

instanceof运算符使用格式如下：

```
( Object reference variable ) instanceof  (class/interface type)
```

如果运算符左侧变量所指的对象，是操作符右侧类或接口(class/interface)的一个对象，那么结果为真。

下面是一个例子：

```
String name = "James";
boolean result = name instanceof String; // 由于 name 是 String 类型，所以返回真
```

## Java 循环结构

#### while 循环

```
while( 布尔表达式 ) {
  //循环内容
}
```

只要布尔表达式为 true，循环就会一直执行下去。

#### do...while 循环

对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。

do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。

```
do {
       //代码语句
}while(布尔表达式);
```

#### for循环

```
for(初始化; 布尔表达式; 更新) {
    //代码语句
}
```

#### 增强for循环

Java5 引入了一种主要用于数组的增强型 for 循环。

```
for(声明语句 : 表达式)
{
   //代码句子
}
```

**声明语句：**声明新的局部变量，该变量的类型必须和数组元素的类型匹配。其作用域限定在循环语句块，其值与此时数组元素的值相等。

**表达式：**表达式是要访问的数组名，或者是返回值为数组的方法。

#### break 关键字

break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块。

break 跳出最里层的循环，并且继续执行该循环下面的语句。

#### continue 关键字

continue 适用于任何循环控制结构中。作用是让程序立刻跳转到下一次循环的迭代。

在 for 循环中，continue 语句使程序立即跳转到更新语句。

在 while 或者 do…while 循环中，程序立即跳转到布尔表达式的判断语句。

## Java条件语句 - if...else

```
if(布尔表达式 1){
   //如果布尔表达式 1的值为true执行代码
}else if(布尔表达式 2){
   //如果布尔表达式 2的值为true执行代码
}else if(布尔表达式 3){
   //如果布尔表达式 3的值为true执行代码
}else {
   //如果以上布尔表达式都不为true执行代码
}
```

## Java switch case语句

```
switch(expression){
    case value :
       //语句
       break; //可选
    case value :
       //语句
       break; //可选
    //你可以有任意数量的case语句
    default : //可选
       //语句
}
```

* switch 语句中的变量类型可以是： byte、short、int 或者 char。从 Java SE 7 开始，switch 支持字符串 String 类型了，同时 case 标签必须为字符串常量或字面量。
* switch 语句可以拥有多个 case 语句。每个 case 后面跟一个要比较的值和冒号。
* case 语句中的值的数据类型必须与变量的数据类型相同，而且只能是常量或者字面常量。
* 当变量的值与 case 语句的值相等时，那么 case 语句之后的语句开始执行，直到 break 语句出现才会跳出 switch 语句。
* 当遇到 break 语句时，switch 语句终止。程序跳转到 switch 语句后面的语句执行。case 语句不必须要包含 break 语句。如果没有 break 语句出现，程序会继续执行下一条 case 语句，直到出现 break 语句。
* switch 语句可以包含一个 default 分支，该分支一般是 switch 语句的最后一个分支（可以在任何位置，但建议在最后一个）。default 在没有 case 语句的值和变量值相等的时候执行。default 分支不需要 break 语句。

**switch case 执行时，一定会先进行匹配，匹配成功返回当前 case 的值，再根据是否有 break，判断是否继续输出，或是跳出判断。**

## Java Number & Math类

| 方法                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [xxxValue()](http://www.runoob.com/java/number-xxxvalue.html) | 将 Number 对象转换为xxx数据类型的值并返回。                  |
| [compareTo()](http://www.runoob.com/java/number-compareto.html) | 将number对象与参数比较。                                     |
| [equals()](http://www.runoob.com/java/number-equals.html)    | 判断number对象是否与参数相等。                               |
| [valueOf()](http://www.runoob.com/java/number-valueof.html)  | 返回一个 Number 对象指定的内置数据类型                       |
| [toString()](http://www.runoob.com/java/number-tostring.html) | 以字符串形式返回值。                                         |
| [parseInt()](http://www.runoob.com/java/number-parseInt.html) | 将字符串解析为int类型。                                      |
| [abs()](http://www.runoob.com/java/number-abs.html)          | 返回参数的绝对值。                                           |
| [ceil()](http://www.runoob.com/java/number-ceil.html)        | 返回大于等于( >= )给定参数的的最小整数，类型为双精度浮点型。 |
| [floor()](http://www.runoob.com/java/number-floor.html)      | 返回小于等于（<=）给定参数的最大整数 。                      |
| [rint()](http://www.runoob.com/java/number-rint.html)        | 返回与参数最接近的整数。返回类型为double。                   |
| [round()](http://www.runoob.com/java/number-round.html)      | 它表示**四舍五入**，算法为 **Math.floor(x+0.5)**，即将原来的数字加上 0.5 后再向下取整，所以，Math.round(11.5) 的结果为12，Math.round(-11.5) 的结果为-11。 |
| [min()](http://www.runoob.com/java/number-min.html)          | 返回两个参数中的最小值。                                     |
| [max()](http://www.runoob.com/java/number-max.html)          | 返回两个参数中的最大值。                                     |
| [exp()](http://www.runoob.com/java/number-exp.html)          | 返回自然数底数e的参数次方。                                  |
| [log()](http://www.runoob.com/java/number-log.html)          | 返回参数的自然数底数的对数值。                               |
| [pow()](http://www.runoob.com/java/number-pow.html)          | 返回第一个参数的第二个参数次方。                             |
| [sqrt()](http://www.runoob.com/java/number-sqrt.html)        | 求参数的算术平方根。                                         |
| [sin()](http://www.runoob.com/java/number-sin.html)          | 求指定double类型参数的正弦值。                               |
| [cos()](http://www.runoob.com/java/number-cos.html)          | 求指定double类型参数的余弦值。                               |
| [tan()](http://www.runoob.com/java/number-tan.html)          | 求指定double类型参数的正切值。                               |
| [asin()](http://www.runoob.com/java/number-asin.html)        | 求指定double类型参数的反正弦值。                             |
| [acos()](http://www.runoob.com/java/number-acos.html)        | 求指定double类型参数的反余弦值。                             |
| [atan()](http://www.runoob.com/java/number-atan.html)        | 求指定double类型参数的反正切值。                             |
| [atan2()](http://www.runoob.com/java/number-atan2.html)      | 将笛卡尔坐标转换为极坐标，并返回极坐标的角度值               |
| [toDegrees()](http://www.runoob.com/java/number-todegrees.html) | 将参数转化为角度。                                           |
| [toRadians()](http://www.runoob.com/java/number-toradians.html) | 将角度转换为弧度。                                           |
| [random()](http://www.runoob.com/java/number-random.html)    | 返回一个随机数。                                             |

## Java Character类

Character类提供了一系列方法来操纵字符。你可以使用Character的构造方法创建一个Character类对象

```
Character ch = new Character('a');
```

Character 类在对象中包装一个基本类型 **char** 的值

```
char ch = 'a';
```

#### Character方法

| 方法                                                         | 描述                                    |
| ------------------------------------------------------------ | --------------------------------------- |
| [isLetter()](http://www.runoob.com/java/character-isletter.html) | 是否是一个字母                          |
| [isDigit()](http://www.runoob.com/java/character-isdigit.html) | 是否是一个数字字符                      |
| [isWhitespace()](http://www.runoob.com/java/character-iswhitespace.html) | 是否是一个空白字符                      |
| [isUpperCase()](http://www.runoob.com/java/character-isuppercase.html) | 是否是大写字母                          |
| [isLowerCase()](http://www.runoob.com/java/character-islowercase.html) | 是否是小写字母                          |
| [toUpperCase()](http://www.runoob.com/java/character-touppercase.html) | 指定字母的大写形式                      |
| [toLowerCase()](http://www.runoob.com/java/character-tolowercase.html) | 指定字母的小写形式                      |
| [toString()](http://www.runoob.com/java/character-tostring.html) | 返回字符的字符串形式，字符串的长度仅为1 |

## Java String 类

字符串广泛应用 在Java 编程中，在 Java 中字符串属于对象，Java 提供了 String 类来创建和操作字符串。

#### 创建字符串

```
String greeting = "菜鸟教程";
```

String 类是不可改变的，所以你一旦创建了 String 对象，那它的值就无法改变了。

如果需要对字符串做很多修改，那么应该选择使用 [StringBuffer & StringBuilder 类](http://www.runoob.com/java/java-stringbuffer.html)

#### 字符串长度

用于获取有关对象的信息的方法称为访问器方法。

String 类的一个访问器方法是 **length()** 方法，它返回字符串对象包含的字符数。

#### 连接字符串

String 类提供了连接两个字符串的方法：concat() 方法。

```
string1.concat(string2);
```

更常用的是使用'+'操作符来连接字符串

#### 创建格式化字符串

输出格式化数字可以使用 printf() 和 format() 方法。

String 类使用静态方法 format() 返回一个String 对象而不是 PrintStream 对象。

String 类的静态方法 format() 能用来创建可复用的格式化字符串，而不仅仅是用于一次打印输出。

````
System.out.printf("浮点型变量的值为 " +
                  "%f, 整型变量的值为 " +
                  " %d, 字符串变量的值为 " +
                  "is %s", floatVar, intVar, stringVar);
````

```
String fs;
fs = String.format("浮点型变量的值为 " +
                   "%f, 整型变量的值为 " +
                   " %d, 字符串变量的值为 " +
                   " %s", floatVar, intVar, stringVar);
```

#### String方法

| 方法                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [char charAt(int index)](http://www.runoob.com/java/java-string-charat.html) | 返回指定索引处的 char 值。                                   |
| [int compareTo(Object o)](http://www.runoob.com/java/java-string-compareto.html) | 把这个字符串和另一个对象比较。                               |
| [int compareTo(String anotherString)](http://www.runoob.com/java/java-string-compareto.html) | 按字典顺序比较两个字符串。                                   |
| [int compareToIgnoreCase(String str)](http://www.runoob.com/java/java-string-comparetoignorecase.html) | 按字典顺序比较两个字符串，不考虑大小写。                     |
| [String concat(String str)](http://www.runoob.com/java/java-string-concat.html) | 将指定字符串连接到此字符串的结尾。                           |
| [boolean contentEquals(StringBuffer sb)](http://www.runoob.com/java/java-string-contentequals.html) | 当且仅当字符串与指定的StringBuffer有相同顺序的字符时候返回真。 |
| [static String copyValueOf(char[] data)](http://www.runoob.com/java/java-string-copyvalueof.html) | 返回指定数组中表示该字符序列的 String。                      |
| [static String copyValueOf(char[] data, int offset, int count)](http://www.runoob.com/java/java-string-copyvalueof.html) | 返回指定数组中表示该字符序列的 String。                      |
| [boolean endsWith(String suffix)](http://www.runoob.com/java/java-string-endswith.html) | 测试此字符串是否以指定的后缀结束。                           |
| [boolean equals(Object anObject)](http://www.runoob.com/java/java-string-equals.html) | 将此字符串与指定的对象比较。                                 |
| [boolean equalsIgnoreCase(String anotherString)](http://www.runoob.com/java/java-string-equalsignorecase.html) | 将此 String 与另一个 String 比较，不考虑大小写。             |
| [byte[] getBytes()](http://www.runoob.com/java/java-string-getbytes.html) | 使用平台的默认字符集将此 String 编码为 byte 序列，并将结果存储到一个新的 byte 数组中。 |
| [byte[] getBytes(String charsetName)](http://www.runoob.com/java/java-string-getbytes.html) | 使用指定的字符集将此 String 编码为 byte 序列，并将结果存储到一个新的 byte 数组中。 |
| [void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)](http://www.runoob.com/java/java-string-getchars.html) | 将字符从此字符串复制到目标字符数组。                         |
| [int hashCode()](http://www.runoob.com/java/java-string-hashcode.html) | 返回此字符串的哈希码。                                       |
| [int indexOf(int ch)](http://www.runoob.com/java/java-string-indexof.html) | 返回指定字符在此字符串中第一次出现处的索引。                 |
| [int indexOf(int ch, int fromIndex)](http://www.runoob.com/java/java-string-indexof.html) | 返回在此字符串中第一次出现指定字符处的索引，从指定的索引开始搜索。 |
| [int indexOf(String str)](http://www.runoob.com/java/java-string-indexof.html) | 返回指定子字符串在此字符串中第一次出现处的索引。             |
| [int indexOf(String str, int fromIndex)](http://www.runoob.com/java/java-string-indexof.html) | 返回指定子字符串在此字符串中第一次出现处的索引，从指定的索引开始。 |
| [String intern()](http://www.runoob.com/java/java-string-intern.html) | 返回字符串对象的规范化表示形式。                             |
| [int lastIndexOf(int ch)](http://www.runoob.com/java/java-string-lastindexof.html) | 返回指定字符在此字符串中最后一次出现处的索引。               |
| [int lastIndexOf(int ch, int fromIndex)](http://www.runoob.com/java/java-string-lastindexof.html) | 返回指定字符在此字符串中最后一次出现处的索引，从指定的索引处开始进行反向搜索。 |
| [int lastIndexOf(String str)](http://www.runoob.com/java/java-string-lastindexof.html) | 返回指定子字符串在此字符串中最右边出现处的索引。             |
| [int lastIndexOf(String str, int fromIndex)](http://www.runoob.com/java/java-string-lastindexof.html) | 返回指定子字符串在此字符串中最后一次出现处的索引，从指定的索引开始反向搜索。 |
| [int length()](http://www.runoob.com/java/java-string-length.html) | 返回此字符串的长度。                                         |
| [boolean matches(String regex)](http://www.runoob.com/java/java-string-matches.html) | 告知此字符串是否匹配给定的正则表达式。                       |
| [boolean regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len)](http://www.runoob.com/java/java-string-regionmatches.html) | 测试两个字符串区域是否相等。                                 |
| [boolean regionMatches(int toffset, String other, int ooffset, int len)](http://www.runoob.com/java/java-string-regionmatches.html) | 测试两个字符串区域是否相等。                                 |
| [String replace(char oldChar, char newChar)](http://www.runoob.com/java/java-string-replace.html) | 返回一个新的字符串，它是通过用 newChar 替换此字符串中出现的所有 oldChar 得到的。 |
| [String replaceAll(String regex, String replacement)](http://www.runoob.com/java/java-string-replaceall.html) | 使用给定的 replacement 替换此字符串所有匹配给定的正则表达式的子字符串。 |
| [String replaceFirst(String regex, String replacement)](http://www.runoob.com/java/java-string-replacefirst.html) | 使用给定的 replacement 替换此字符串匹配给定的正则表达式的第一个子字符串。 |
| [String[] split(String regex)](http://www.runoob.com/java/java-string-split.html) | 根据给定正则表达式的匹配拆分此字符串。                       |
| [String[] split(String regex, int limit)](http://www.runoob.com/java/java-string-split.html) | 根据匹配给定的正则表达式来拆分此字符串。                     |
| [boolean startsWith(String prefix)](http://www.runoob.com/java/java-string-startswith.html) | 测试此字符串是否以指定的前缀开始。                           |
| [boolean startsWith(String prefix, int toffset)](http://www.runoob.com/java/java-string-startswith.html) | 测试此字符串从指定索引开始的子字符串是否以指定前缀开始。     |
| [CharSequence subSequence(int beginIndex, int endIndex)](http://www.runoob.com/java/java-string-subsequence.html) | 返回一个新的字符序列，它是此序列的一个子序列。               |
| [String substring(int beginIndex)](http://www.runoob.com/java/java-string-substring.html) | 返回一个新的字符串，它是此字符串的一个子字符串               |
| [String substring(int beginIndex, int endIndex)](http://www.runoob.com/java/java-string-substring.html) | 返回一个新字符串，它是此字符串的一个子字符串。               |
| [char[] toCharArray()](http://www.runoob.com/java/java-string-tochararray.html) | 将此字符串转换为一个新的字符数组。                           |
| [String toLowerCase()](http://www.runoob.com/java/java-string-tolowercase.html) | 使用默认语言环境的规则将此 String 中的所有字符都转换为小写。 |
| [String toLowerCase(Locale locale)](http://www.runoob.com/java/java-string-tolowercase.html) | 使用给定 Locale 的规则将此 String 中的所有字符都转换为小写。 |
| [String toString()](http://www.runoob.com/java/java-string-tostring.html) | 返回此对象本身（它已经是一个字符串！）。                     |
| [String toUpperCase()](http://www.runoob.com/java/java-string-touppercase.html) | 使用默认语言环境的规则将此 String 中的所有字符都转换为大写。 |
| [String toUpperCase(Locale locale)](http://www.runoob.com/java/java-string-touppercase.html) | 使用给定 Locale 的规则将此 String 中的所有字符都转换为大写。 |
| [String trim()](http://www.runoob.com/java/java-string-trim.html) | 返回字符串的副本，忽略前导空白和尾部空白。                   |
| [static String valueOf(primitive data type x)](http://www.runoob.com/java/java-string-valueof.html) | 返回给定data type类型x参数的字符串表示形式。                 |

## Java StringBuffer和StringBuilder类

当对字符串进行修改的时候，需要使用 StringBuffer 和 StringBuilder 类。

和 String 类不同的是，StringBuffer 和 StringBuilder 类的对象能够被多次的修改，并且不产生新的未使用对象。

```
public class Test{
  public static void main(String args[]){
    StringBuffer sBuffer = new StringBuffer("菜鸟教程官网：");
    sBuffer.append("www");
    sBuffer.append(".runoob");
    sBuffer.append(".com");
    System.out.println(sBuffer);  
  }
}
```


#### StringBuffer方法

| 方法                                    | 描述                                                     |
| --------------------------------------- | -------------------------------------------------------- |
| public StringBuffer append(String s)    | 将指定的字符串追加到此字符序列。                         |
| public StringBuffer reverse()           | 将此字符序列用其反转形式取代。                           |
| public delete(int start, int end)       | 移除此序列的子字符串中的字符。                           |
| public insert(int offset, int i)        | 将 `int` 参数的字符串表示形式插入此序列中。              |
| replace(int start, int end, String str) | 使用给定 `String` 中的字符替换此序列的子字符串中的字符。 |

## Java 数组

#### 声明数组变量

```
dataType[] arrayRefVar; 
```

#### 创建数组

```
arrayRefVar = new dataType[arraySize];
```

数组变量的声明，和创建数组可以用一条语句完成:

```
dataType[] arrayRefVar = new dataType[arraySize];
```

#### 处理数组

for循环

#### 多维数组

```
type[][] typeName = new type[typeLength1][typeLength2];
```

type 可以为基本数据类型和复合数据类型，arraylenght1 和 arraylenght2 必须为正整数，arraylenght1 为行数，arraylenght2 为列数。

#### Arrays类

java.util.Arrays 类能方便地操作数组，它提供的所有方法都是静态的。

| 方法                                                       | 说明                                                         |
| ---------------------------------------------------------- | ------------------------------------------------------------ |
| public static int **binarySearch**(Object[] a, Object key) | 用**二分查找算法**在给定数组中搜索给定值的对象(Byte,Int,double等)。数组在调用前必须排序好的。如果查找值包含在数组中，则返回搜索键的索引；否则返回 (-(*插入点*) - 1)。**查找数组元素** |
| public static boolean **equals**(long[] a, long[] a2)      | 如果两个指定的 long 型数组彼此*相等*，则返回 true。如果两个数组包含相同数量的元素，并且两个数组中的所有相应元素对都是相等的，则认为这两个数组是相等的。换句话说，如果两个数组以相同顺序包含相同的元素，则两个数组是相等的。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。**比较数组** |
| public static void **fill**(int[] a, int val)              | 将指定的 int 值分配给指定 int 型数组指定范围中的每个元素。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。**给数组赋值** |
| public static void **sort**(Object[] a)                    | 对指定对象数组根据其元素的自然顺序进行**升序排列**。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。**对数组排序** |

## Java集合

集合是存储对象的容器，集合中可以存储任意类型的对象，而且长度可变。

Java中的集合框架大类可分为Collection和Map。

#### 泛型

**泛型是类型的一部分，类名+泛型是一个整体**

```
package  好好学java;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class Test {

    public static void main(String[] args) {
        // 不加泛型，添加和遍历
        List list = new ArrayList<>();
        list.add(1);
        list.add("123");
        list.add("hello");
        
        Iterator it = list.iterator();
        while(it.hasNext()){
            // 没有添加泛型，这里只能使用Object接收
            Object obj = it.next();
            System.out.println(obj);
        }
    }

}
package  好好学java;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class Test {

    public static void main(String[] args) {
        // 加泛型，添加和遍历
        List<String> list = new ArrayList<String>();
        list.add("123");
        list.add("hello");
        
        Iterator<String> it = list.iterator();
        while(it.hasNext()){
            // 因为添加了泛型，就说明集合中装的全部都是String类型的数据
            // 所以这里用String类型接收，就不会发生异常，并且可以使用String的方法
            String str = it.next();
            System.out.println(str.length());
        }
    }

}
```

#### Collection

| Collection     | 我们需要保存若干个对象的时候使用集合                         |
| -------------- | ------------------------------------------------------------ |
| List（线性表） | 如果我们需要保留存储顺序，并且保留重复元素，使用List.<br />如果查询较多，那么使用ArrayList<br />如果存取较多，那么使用LinkedList<br />如果需要线程安全，那么使用Vector |
| Set（集）      | 如果我们不需要保留存储顺序，并且需要去掉重复元素，使用Set.<br />如果我们需要将元素排列，那么使用TreeSet<br />如果我们不需要排序，使用HashSet，HashSet比TreeSet效率高<br />如果我们需要保留存储顺序，又要过滤重复元素，那么使用LinkedHashSet |



#### Map

Map 是“键值对”映射的抽象接口。

**[HashMap](<http://www.cnblogs.com/skywang12345/p/3310835.html>)** 是基于“拉链法”实现的散列表。一般用于单线程程序中。

**[Hashtable](<http://www.cnblogs.com/skywang12345/p/3310887.html>)** 也是基于“拉链法”实现的散列表。它一般用于多线程程序

**[WeakHashMap](<http://www.cnblogs.com/skywang12345/p/3311092.html>)** 也是基于“拉链法”实现的散列表，它一般也用于单线程程序中。相比HashMap，WeakHashMap中的键是“弱键”，当“弱键”被GC回收时，它对应的键值对也会被从WeakHashMap中删除；而HashMap中的键是强键。

**[TreeMap](<http://www.cnblogs.com/skywang12345/p/3310928.html>)** 是有序的散列表，它是通过红黑树实现的。它一般用于单线程中存储有序的映射。



## Java语句

* Collection（集合）

* removeall

  ```
  //从collection1中移除collection2中包含的所有元素
  collection1.removeall(collection2)
  ```

* Arrays.aslist

  利用Arrays.asList方法返回的List集合是不允许add和remove的,这种list的长度不可变，因为底层依然是写数组。

  和Collection的toArray对应，是数组和集合间相互转换的两个桥梁方法。

* contains和containsAll

* hashmap

  **put方法**

  ```
  public V put(K key, V value) {
      return putVal(hash(key), key, value, false, true);
  }
  ```

  **get方法**

  ```
  public V get(Object key) {
      Node<K,V> e;
      return (e = getNode(hash(key), key)) == null ? null : e.value;
  }
  ```

* **keySet**

  调用map集合的方法keySet(),所有的键存储到keySet集合中

  Set<String> keySet = map.keySet();

* **Integer.parseInt(String s)**

  返回用十进制参数表示的整数值

* **split**

  split()方法根据匹配给定的正则表达式来拆分字符串。

  `.`,`|`,`*`等转义字符，必须得加`\\`。

  多个分隔符，可以用`|`作为连字符。

