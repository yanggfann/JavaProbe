## Junit

* [下载地址](http://www.junit.org)，下载最新版本的Junit.jar

* 设置Junit环境

  1. 将JUNIT_HOME环境变量设置为指向计算机上存储JUNIT jar的基目录位置。
  2. 向环境变量类路径（CLASSPATH）添加%JUNIT_HOME%\junit-4.13-beta-2.jar;.;

* **问题解决**

  * import org.junit.Test;

    junit为红色，点到红色的junit上显示Cannot resolve symbol 'junit'

    **解决方法：**

    File -> Project Struct... -> Libraies -> 点击加号 -> Java -> 找到 IDEA 安装路径下的 Lib 中的junit-4.13 -> 确定完就行了，点击OK就出去了