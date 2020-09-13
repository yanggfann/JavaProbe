学习使用键盘来代替鼠标执行操作，节省大量的时间，高效的完成开发任务。 <!--more-->

## 设置快捷键版本

Windows and Linux：File|Settings|Keymap|Default

macOS：IntelliJ IDEA|Preferences|Keymap|Mac OS X 10.5+

## [快捷键参照表](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)

### 挑战快捷键1

* 万能的 Alt + Enter

  * Alt + Enter(mac) / Alt + Enter(windows/Linux)

  * 自动创建类(按 Alt + Enter选择Create class)和方法(按 Alt + Enter选择Create method)

    按F2可以定位到下一个错误的地方

    可以进行意图驱动编程，节省操作和返工

  * 反转if条件(按 Alt + Enter选择invert 'if' condition)

  * 绑定构造器参数到字段

    构造函数有参数没有赋值给字段，按 Alt + Enter选择Bind constructor parameters to fields，可以直接创造字段并赋值，例如this.name = name;

  * 创建字段并赋值

    在一个已经存在的构造函数上新增了一个参数之后，按 Alt + Enter选择Create field for parameter 'gender'，可以创建字段并赋值。

* CMD + D(mac) / Ctrl + D(windows/Linux)：复制行

* CMD + X(mac) / Ctrl + X(windows/Linux)：剪切行

* CMD + DEL(mac) / Ctrl + Y(windows/Linux)：删除行

* Alt + CMD + Enter(mac) / Alt + Ctrl + Enter(windows/Linux)：上方插入行

* Shift + Enter(mac) / Shift + Enter(windows/Linux)：下方插入行

* CMD + Shift + 方向键(mac) / Ctrl + Shift + 方向键(windows/Linux)：移动行，且在IntelliJ IDEA中不会移出方法，移动方法

* Alt + 上方向键(mac) / Ctrl + W(windows/Linux)：扩大选区

* CMD + Shift + Enter(mac) / Ctrl + Shift + Enter(windows/Linux)：自动补全代码

### 挑战快捷键2

* CMD + Alt + V(mac) / Ctrl + Alt + V(windows/Linux)：抽取变量
* CMD + Alt + C(mac) / Ctrl + Alt + C(windows/Linux)：抽取常量
* CMD + Alt + M(mac) / Ctrl + Alt + M(windows/Linux)：抽取方法
* CMD + Alt + F(mac) / Ctrl + Alt + F(windows/Linux)：抽取字段
* CMD + Alt + P(mac) / Ctrl + Alt + P(windows/Linux)：抽取参数
* CMD + Alt + N(mac) / Ctrl + Alt + N(windows/Linux)：内联
* Shift + F6(mac) / Shift + F6(windows/Linux)：重命名（变量，方法）
* CMD + T(mac) / Ctrl + T(windows/Linux)：弹出当前位置可以使用的一些重构手法的菜单

### 挑战快捷键3

* 向后声明：

  “123”.var      --->   String s = "123";

  words.for     --->   for (String word : words){}

  words.fori    --->   for (int i = 0; i < words.length; i++){}

* Search every where

  按两次Shift键打开一个窗口，在这里可以查找文件，方法等

* Tab:

  sout 按Tab键        --->      System.out.println();

  soutm 按Tab键     --->      System.out.println("wordFrequency.getString");  //打印方法的名称，查看方法有没有被调用到

  soutp 按Tab键       --->      System.out.println("words = [" + words + "]");   //查看方法的参数传进来的是否正确

* fori    --->     for (int i = 0; i< ; i++){}

* CMD + O(mac) / Ctrl + N(windows/Linux)：打开类

* CMD + Shift + O(mac) / CtrL + Shift + N(windows/Linux)：打开文件

* CMD + E(mac) / Ctrl + E (windows/Linux)：打开最近打开过的文件

* Ctrl + Tab(mac) / Ctrl + Tab(windows/Linux)：打开上次打开过的文件

* CMD + Alt + L(mac) / Ctrl + Alt + L(windows/Linux)：格式化代码 

* Alt + Ctrl + R(mac) / Alt + Shift + F10(windows/Linux)：运行程序，调出运行菜单

* CMD + Shift + T(mac) ：在实现文件和单元测试之间快速切换，如果没有的话可以选择创建新的测试

* CMD + R(mac)：直接运行上一次的测试

* CMD+ Ctrl + R(mac)：调试程序

* CMD + Shift + A(mac)：忘记一些快捷键的时候可以通过该命令，打开find action的窗口

* Preferences -> live Templates

