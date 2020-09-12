# Linux命令基础

## 学习资料

* 常用命令行介绍：<https://github.com/tws-practice/console/blob/master/COMMANDS.md>
* 每个程序员都应该知道的8个Linux命令：<http://www.imooc.com/article/1276>
* 慕课网上更多Linux相关课程：<http://www.imooc.com/course/list?c=linux>
* 书籍《鸟哥的Linux私房菜》：<https://book.douban.com/subject/4889838/>



## 常用Linux命令行

* 文件/目录: cd, mkdir, cp, rm, mv, pwd, ls, tar, zip, find, grep, less, tail, tree
* 帐号操作: su, sudo, whoami, passwd
* 包管理: apt-get, 添加软件源
* 进程相关: ps, kill
* 系统信息相关: top, df, uname
* 网络相关：ping, telnet, curl, netstat，修改hosts 这里仅列出部分，可以先掌握它们，然后在后面的学习中不断补充。

## 开始使用控制台

* 运行命令

  * **ls** -- 列出目录内容
    * -**l** -- 长格式列表
    * -**a** -- 包含名称以点(.)开头的目录项。
    * ls -l ：对文件和目录的权限不确定时，用该命令来检测权限

  * **clear** -- 清除终端屏幕

* 在文件系统中移动
  * **cd** -- 改变目录
  * **pwd** -- 打印工作目录

* 读文件

  * **less** -- Less是一个类似于more的程序，但是它允许文件的向后移动和向前移动。此外，less不必在启动前读取整个输入文件，因此对于大型输入文件，它的启动速度比vi等文本编辑器更快。less使用termcap(或某些系统上的terminfo)，因此它可以在各种终端上运行。甚至对硬拷贝终端的支持也很有限。(在硬拷贝终端上，应该打印在屏幕顶部的行以插入符号作为前缀。)
  * **cat** -- 连接和打印文件
  * **cat a.txt > txt.a** -- 将文本文件a.txt的文件名称改为txt.a，保持a.txt文件内容不变

* 编辑文件

  * **touch** -- 更改文件访问和修改时间
  * **nano** -- nano是一个小型的、免费的、友好的编辑器，它的目标是取代Pico(非免费Pine包中包含的默认编辑器)。nano不仅复制了Pico的外观，还在Pico中实现了一些缺失(或默认情况下禁用)的功能，比如“搜索并替换”和“转到行号和列号”。

* 高级编辑器

  * vim
  * emacs
  * 在vi编辑器里，**:200**能将光标移到第200行
  * 在vi编辑器里，命令**"dd"**用来删除当前的**行**

* 移动和删除文件

  * **mv** -- 移动文件
  * **cp** -- 拷贝文件
    * -R或-r -- 递归的拷贝目录
  * **rm** -- 移除文件
    * -r -- 递归的移除目录和其他内容
  * **mkdir** -- 创建目录
  * **mkdir -p** -- 创建多级目录命令

* 如果你有任何问题
  * **man** -- 格式化和显示联机手册页

* shell中变量的赋值方法
  * 直接赋值
  * 使用read命令
  * 使用命令行参数
  * 使用命令的输出

## 用户和许可

* 创建用户
  * **whoami** -- 打印你是哪个用户
  * **adduser** -- 用于创建用户的交互式工具
  * **su** -- 切换用户，su命令可以将普通用户转换成超级用户
  * **sudo** -- 作为超级用户执行命令
* 文件许可
  * **ls** -**l** -- 列出长格式的文件，包括权限信息
  * **chmod** -- 更改文件或目录的权限(模式)

在ls -l中，每个文件都有10个字符的权限表示，比如drwxrwxrwx。每个字符表示文件上的权限。如果将字母替换为破折号(-)，则表示没有授予该许可。例如-rwxr-xr-x(755)。

第一个字符表示是否为目录。d表示目录，-，表示不是目录。

接下来的9个字符可以分成rwx的三个一组。最左边的三元组是**文件的所有者**，中间是**组所有者**，右边是**其他人的权限**。rwx分别代表读、写和执行权限。

你可以使用3位八进制数读取或设置权限。这些数字从左到右表示所有者、组和其他权限。每个数字可以是0到7，表示读r、写w和执行x的不同组合。r(4);w(2);x(1);无(0)。多权限用数字相加。

要计算每个数字的含义，请使用这个公式。

read/r = 4

write/w = 2

execute/x = 1

对于要授予的每个权限，将它们的值相加。

* 文件附属权
  * **chown** -- 改变文件或目录的所有者
* Sudo
  * **sudo** -- 以超级用户的身份运行一个命令
  * **sudo !!** -- 以超级用户的身份运行前面的命令。

## 进程

* 进程

  * **top** -- 展示活动进程
  * **ps** -- 显示进程状态
  * **grep** -- 寻找匹配

* 通过名字发现进程

  使用以下命令搜索使用模式的正在运行的进程。

  ```ps aux | grep "SEARCH PATTERN"```

* 暂停和恢复

  * **ctrl + z** -- 停止(暂停)一个进程
  * **ctrl + c** -- 终止(退出)一个进程
  * **fg** -- 把工作放在前台
  * **jobs** -- 为你的会话列出任务

* 杀死进程

  * **kill** -- 发送一个信号给进程
  * **KILL** or **9** -- 强制一个进程退出
  * **TERM** (default) -- 请求一个进程正常终止
  * **STOP** -- 停止或暂停进程

## 环境和重定向

* 环境变量
  * **VARIABLE=value** -- 设置一个本地环境变量
  * **export VARIABLE=value** -- 设置对子进程可见的环境变量
  * **env** -- 查看环境变量
  * **bash** -- 在当前会话中启动一个新会话
  * **echo** -- 显示发送到echo的参数
* 发现和查找
  * **find . -name "search"** -- 从当前位置开始搜索带有名称search的文件
  * **find .-name "*.txt"** -- 列出当前目录以及子目录下所有扩展名为“.txt”的文件
  * **grep "pattern" file** -- 查找给定文件中包含pattren的任何行
* 管道和重定向
  * **somecommand < inputfile** -- 使用inputfile的input而不是键盘输入运行somecommand
  * **somecommand > inputfile** -- 运行一些命令，输出到输出文件而不是终端屏幕。
  * **command1|command2** -- command1的输出到command 2的输入管道

## 安装软件

* 从源代码构建软件
  * **sudo apt-get update** -- 更新计算机上可用软件的目录
  * **sudo apt-get install build-essential** -- 安装从源代码构建软件所需的工具
  * **curl -O URL** -- 在URL下载文件
  * **tar -xvf FILENAME.tar.gz** -- 将tar.gz文件解压缩到当前目录
  * **./configure** -- 运行源代码附带的configure脚本。这将创建一个Makefile
  * **make** -- 运行在Makefile中指定的构建
  * **sudo make install** -- 从Makefile运行安装脚本。这将安装程序
  * **which** -- 在用户路径中定位程序文件
* 包管理简介
  * **apt-get update** -- 更新计算机上的包目录
  * **apt-cache search PATTERN** -- 在可用的包中搜索模式
  * **apt-get install** -- 安装一个或多个包
  * **apt-get upgrade** -- 所有安装包更新到最新版本
  * **apt-get remove PACKAGE** -- 从计算机中删除或卸载软件包

## 每个程序员都应该知道的8个Linux命令

* 文件数据

  ```
  order.out.log
    8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
    8:23:45 112, 1, Joy of Clojure, Hardcover, 29.99
    8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  
    order.in.log
    8:22:20 111, Order Complete
    8:23:50 112, Order sent to fulfillment
    8:24:20 113, Refund sent to processing
  ```

  

* **cat**

  ```
  cat -- 连接文件，并输出结果
  ```

  ```
  jfields$ cat order.out.log 
  8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:23:45 112, 1, Joy of Clojure, Hardcover, 29.99
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  ```

  可以用cat来连接多个文件

  ```
  jfields$ cat order.* 
  8:22:20 111, Order Complete
  8:23:50 112, Order sent to fulfillment
  8:24:20 113, Refund sent to processing
  8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:23:45 112, 1, Joy of Clojure, Hardcover, 29.99
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  ```

  如果你想看这些log文件的内容，你可以把它们连接起来并输出到标准输出上，就是上面的例子展示的。这很有用，但输出的内容可以更有逻辑些。

* **sort**

  ```
  sort -- 文件里的文字按行排序
  ```

  此时sort命令显然是你最佳的选择。

  ```
  jfields$ cat order.* | sort
  8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:22:20 111, Order Complete
  8:23:45 112, 1, Joy of Clojure, Hardcover, 29.99
  8:23:50 112, Order sent to fulfillment
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:24:20 113, Refund sent to processing
  ```

  就像上面例子显示的，文件里的数据已经经过排序。对于一些小文件，你可以读取整个文件来处理它们，然而，真正的log文件通常有大量的内容，你不能不考虑这个情况。此时你应该考虑过滤出某些内容，把cat、sort后的内容通过管道传递给过滤工具。

* **grep**

  ```
  grep, egrep, fgrep -- 打印出匹配条件的文字行
  ```

  假设我们只对Patterns of Enterprise Architecture这本书的订单感兴趣。使用grep，我们能限制只输出含有Patterns字符的订单。

  ```
  jfields$ cat order.* | sort | grep Patterns
  8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  ```

  假设退款订单113出了一些问题，你希望查看所有相关订单——你又需要使用grep了。

  ```
  jfields$ cat order.* | sort | grep ":\d\d 113, "
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:24:20 113, Refund sent to processing
  ```

  你会发现在grep上的匹配模式除了“113”外还有一些其它的东西。这是因为113还可以匹配上书目或价格，加上额外的字符后，我们可以精确的搜索到我们想要的东西。

  现在我们已经知道了退货的详细信息，我们还想知道日销售和退款总额。但我们只关心Patterns of Enterprise Architecture这本书的信息，而且只关心数量和价格。我现在要做到是切除我们不关心的任何信息。

* **cut**

  ```
  cut -- 删除文件中字符行上的某些区域
  ```

  又要使用grep，我们用grep过滤出我们想要的行。有了我们想要的行信息，我们就可以把它们切成小段，删除不需要的部分数据。

  ```
  jfields$ cat order.* | sort | grep Patterns
  8:22:19 111, 1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  8:24:19 113, -1, Patterns of Enterprise Architecture, Kindle edition, 39.99
  
  jfields$ cat order.* | sort | grep Patterns | cut -d"," -f2,5
   1, 39.99
   -1, 39.99
  ```

  现在，我们把数据缩减为我们计算想要的形式，把这些数据粘贴到Excel里立刻就能得到结果了。

  cut是用来消减信息、简化任务的，但对于输出内容，我们通常会有更复杂的形式。假设我们还需要知道订单的ID，这样可以用来关联相关的其他信息。我们用cut可以获得ID信息，但我们希望把ID放到行的最后，用单引号包上。

* **sed**

  ```
  sed -- 一个流编辑器，它是用来在输入流上执行基本的文本变换
  ```

  下面的例子展示了如何用sed命令变换我们的文件行，之后我们在再用cut移除无用的信息。

  ```
  jfields$ cat order.* | sort | grep Patterns \
  >| sed s/"[0-9\:]* \([0-9]*\)\, \(.*\)"/"\2, '\1'"/
  1, Patterns of Enterprise Architecture, Kindle edition, 39.99, '111'
  -1, Patterns of Enterprise Architecture, Kindle edition, 39.99, '113'
  
  lmp-jfields01:~ jfields$ cat order.* | sort | grep Patterns \
  >| sed s/"[0-9\:]* \([0-9]*\)\, \(.*\)"/"\2, '\1'"/ | cut -d"," -f1,4,5
  1, 39.99, '111'
  -1, 39.99, '113'
  ```

  我们对例子中使用的正则表达式多说几句，不过也没有什么复杂的。正则表达式做了下面几种事情：

  * 删除时间戳
  * 捕捉订单号
  * 删除订单号后的逗号和空格
  * 捕捉余下的行信息

  里面的引号和反斜杠有点乱，但使用命令行时必须要用到这些。

  一旦捕捉到了我们想要的数据，我们可以使用 \1 & \2 来存储它们，并把它们输出成我们想要的格式。我们还在其中加入了要求的单引号，为了保持格式统一，我们还加入了逗号。最后，用cut命令把不必要的数据删除。

  现在我们有麻烦了。我们上面已经演示了如何把log文件消减成更简洁的订单形式，但我们的财务部门需要知道订单里一共有哪些书。

* **uniq**

  ```
  uniq -- 删除重复的行
  ```

  下面的例子展示了如何过滤出跟书相关的交易，删除不需要的信息，获得一个不重复的信息。

  ```
  jfields$ cat order.out.log | grep "\(Kindle\|Hardcover\)" | cut -d"," -f3 | sort | uniq -c
     1  Joy of Clojure
     2  Patterns of Enterprise Architecture
  ```

  看起来这是一个很简单的任务。

  这都是很好用的命令，但前提是你要能找到你想要的文件。有时候你会发现一些文件藏在很深的文件夹里，你根本不知道它们在哪。但如果你是知道你要寻找的文件的名字的话，这对你就不是个问题了。

* **find**

  ```
  find -- 在文件目录中搜索文件
  ```

  在上面的例子中我们处理了order.in.log和order.out.log这两个文件。这两个文件放在我的home目录里的。下面了例子将向大家展示如何在一个很深的目录结构里找到这样的文件。

  ```
  jfields$ find /Users -name "order*"
  Users/jfields/order.in.log
  Users/jfields/order.out.log
  ```

  find命令有很多其它的参数，但99%的时间里我只需要这一个就够了。

  简单的一行，你就能找到你想要的文件，然后你可以用cat查看它，用cut修剪它。但文件很小时，你用管道把它们输出到屏幕上是可以的，但当文件大到超出屏幕时，你也许应该用管道把它们输出给less命令。

* **less**

  ```
  less -- 在文件里向前或向后移动
  ```

  让我们再回到简单的 cat | sort 例子中来，下面的命令就是将经过合并、排序后的内容输出到less命令里。在 less 命令，使用“/”来执行向前搜索，使用“？”命令执行向后搜索。搜索条件是一个正则表达式。

  ```
  jfields$ cat order* | sort | less
  ```

  如果你在 less 命令里使用 /113.*，所有113订单的信息都会高亮。你也可以试试?.*112，所有跟订单112相关的时间戳都会高亮。最后你可以用 ‘q’ 来退出less命令。

  linux里有很丰富的各种命令，有些是很难用的。然而，学会了前面说的这8个命令，你已经能处理大量的log分析任务了，完全不需要用脚本语言写程序来处理它们。
