学习使用键盘来代替鼠标执行操作，节省大量的时间，高效的完成开发任务。 <!--more-->



## 学习资源与工具

* [IntelliJ IDE 下载链接(请下载Community版)](https://www.jetbrains.com/idea/download/#section=windows)
* [设置快捷键版本](https://www.jetbrains.com/help/idea/settings-keymap.html)
* [快捷键参照表](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)



## 下载IntelliJ IDEA

下载[地址](https://www.jetbrains.com/idea/download/#section=windows)

## [配置JDK](https://www.cnblogs.com/Knowledge-has-no-limit/p/7234360.html)

1. 首先要下载Java开发工具包JDK，下载地址：<http://www.oracle.com/technetwork/java/javase/downloads/index.html>

   在下载页面点击接受许可，并根据自己的系统选择对应的版本。

   下载成功后，双击图标即可安装，安装过程中直接下一步即可，也可修改安装目录。

2. **环境变量配置**

   * 安装完成后，右击“我的电脑”，点击“属性”，选择“高级系统设置”

   * 选择“高级”选项卡，点击“环境变量”

   * 在"系统变量"中设置3项属性，配置系统环境变量，JAVA_HOME，PATH，CLASSPATH(大小写无所谓),若已存在则点击"编辑"，不存在则点击"新建"。

   * 变量名：**JAVA_HOME**

     变量值：**D:\tools\jdk1.8.0_77**        // 要根据自己的实际路径

   * 变量名：**CLASSPATH**

     变量值：**.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;**         //记得前面有个"."

   * 变量名：**Path**

     变量值：**%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;**

3. 测试JDK是否安装成功

   * “开始” -> "运行"，键入“cmd”
   * 键入命令：java -version、java、javac几个命令，出现正常的提示信息，说明环境变量配置成功。

4. IDEA配置JDK

   * Create New Project
   * 点击Project SDK中的New，在弹出框选择JDK安装路径，点击OK即可配置成功。