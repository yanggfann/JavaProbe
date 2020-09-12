学习使用基本git指令对项目进行版本控制；学习使用github作为项目托管平台。<!--more-->



## 学习资料

* git教学网站：<http://try.github.com/>
* git完整命令手册地址：<https://git-scm.com/docs>
* git bash下载地址：<https://gitforwindows.org/>
* git commit资料：<http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html>
* git小步提交资料：<http://www.10tiao.com/html/568/201512/401030521/1.html>



## git命令

* **git checkout -b dev**   创建dev分支，并切换到dev分支

  ```
  $ git checkout -b dev
  Switched to a new branch 'dev'
  ```

  `git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

  ```
  $ git branch dev
  $ git checkout dev
  Switched to branch 'dev'
  ```

* **git branch -a**     查看所有分支包括本地分支和远程分支

* **git branch -r**      查看远程分支

* **git branch**          查看当前分支

  `git branch`命令会列出所有分支，当前分支前面会标一个`*`号。

  ```
  $ git branch
  * dev
    master
  ```

  然后，我们就可以在`dev`分支上正常提交。

* **git checkout master**    切换至master分支

  ```
  $ git checkout master
  Switched to branch 'master'
  ```

* **git merge**    合并指定分支到当前分支

  ```
  $ git merge dev
  Updating d17efd8..fec145a
  Fast-forward
   readme.txt |    1 +
   1 file changed, 1 insertion(+)
  ```

  git merge dev表示将dev分支的工作成果合并到master分支上。

  `Fast-forward`表示这次合并是“快进模式”，也就是直接把`master`指向`dev`的当前提交，所以合并速度非常快。

* **git branch -d dev**      删除dev分支

  ```
  $ git branch -d dev
  Deleted branch dev (was fec145a).
  ```

  因为创建、合并和删除分支非常快，所以Git鼓励使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。



## git 提交

```
# git init
# git add .
# git commit -m "提交说明"
# git remote add origin https://github.com/your_username/your_username.github.io.git
# git push -u origin master
```



## git 练习总结

1. 本地创建项目仓库文件夹

2. github上创建一个新的仓库（与本地文件夹同名）

3. 本地仓库添加文件，并在git bash本地仓库位置下执行以下命令

   ```
   # git init
   # git add .
   # git commit -m "提交说明"
   # git remote add origin https://github.com/your_username/your_username.github.io.git
   # git push -u origin master
   ```

4. 本地创建项目分支仓库文件夹

5. 本地分支仓库添加文件，并在git bash本地分支仓库位置下执行以下命令

   ```
   # git init
   # git add .
   # git branch
   # git commit -m "提交说明"
   # git checkout -b test
   # git branch
   # git remote add origin https://github.com/your_username/your_username.github.io.git
   # git push origin test
   ```

   

## git commit

Git 每次提交代码，都要写 Commit message（提交说明），否则就不允许提交。

```
$ git commit -m "hello world"
```

上面代码的`-m`参数，就是用来指定 commit mesage 的。

如果一行不够，可以只执行`git commit`，就会跳出文本编辑器，让你写多行。

```
$ git commit
```

一般来说，commit message 应该清晰明了，说明本次提交的目的。

目前，社区有多种 Commit message 的[写法规范](https://github.com/ajoslin/conventional-changelog/blob/master/conventions)。本文介绍[Angular 规范](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#heading=h.greljkmo14y0)（见上图），这是目前使用最广的写法，比较合理和系统化，并且有配套的工具。



### Commit message的作用

格式化的Commit message，有几个好处。

**（1）提供更多的历史信息，方便快速浏览。**

比如，下面的命令显示上次发布后的变动，每个commit占据一行。你只看行首，就知道某次 commit 的目的。

```
$ git log <last tag> HEAD --pretty=format:%s
```

**（2）可以过滤某些commit（比如文档改动），便于快速查找信息。**

比如，下面的命令仅仅显示本次发布新增加的功能。

```
$ git log <last release> HEAD --grep feature
```

**（3）可以直接从commit生成Change log。**

Change Log 是发布新版本时，用来说明与上一个版本差异的文档。

### Commit message的格式

每次提交，Commit message 都包括三个部分：Header，Body 和 Footer。

```
<type>(<scope>): <subject>
// 空一行
<body>
// 空一行
<footer>
```

其中，Header 是必需的，Body 和 Footer 可以省略。

不管是哪一个部分，任何一行都不得超过72个字符（或100个字符）。这是为了避免自动换行影响美观。

* **Header**

  Header部分只有一行，包括三个字段：`type`（必需）、`scope`（可选）和`subject`（必需）。

  * **type**

    `type`用于说明 commit 的类别，只允许使用下面7个标识。

    ```
    feat：新功能（feature）
    fix：修补bug
    docs：文档（documentation）
    style： 格式（不影响代码运行的变动）
    refactor：重构（即不是新增功能，也不是修改bug的代码变动）
    test：增加测试
    chore：构建过程或辅助工具的变动
    ```

    如果`type`为`feat`和`fix`，则该 commit 将肯定出现在 Change log 之中。其他情况（`docs`、`chore`、`style`、`refactor`、`test`）由你决定，要不要放入 Change log，建议是不要。

  * **scope**

    `scope`用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同。

  * **subject**

    `subject`是 commit 目的的简短描述，不超过50个字符。

    ```
    以动词开头，使用第一人称现在时，比如change，而不是changed或changes
    第一个字母小写
    结尾不加句号（.）
    ```

    

* **body**

  Body 部分是对本次 commit 的详细描述，可以分成多行。下面是一个范例。

  ```
  More detailed explanatory text, if necessary.  Wrap it to 
  about 72 characters or so. 
  
  Further paragraphs come after blank lines.
  
  - Bullet points are okay, too
  - Use a hanging indent
  ```

  有两个注意点。

  （1）使用第一人称现在时，比如使用`change`而不是`changed`或`changes`。

  （2）应该说明代码变动的动机，以及与以前行为的对比。

  

* **Footer**

  Footer 部分只用于两种情况。

  **（1）不兼容变动**

  如果当前代码与上一个版本不兼容，则 Footer 部分以`BREAKING CHANGE`开头，后面是对变动的描述、以及变动理由和迁移方法。

  ```
  BREAKING CHANGE: isolate scope bindings definition has changed.
  
      To migrate the code follow the example below:
  
      Before:
  
      scope: {
        myAttr: 'attribute',
      }
  
      After:
  
      scope: {
        myAttr: '@',
      }
  
      The removed `inject` wasn't generaly useful for directives so there should be no code using it.
  ```

  **（2）关闭 Issue**

  如果当前 commit 针对某个issue，那么可以在 Footer 部分关闭这个 issue 。

  ```
  Closes #234
  ```

  也可以一次关闭多个 issue 。

  ```
  Closes #123, #245, #992
  ```

  

* **Revert**

  还有一种特殊情况，如果当前 commit 用于撤销以前的 commit，则必须以`revert:`开头，后面跟着被撤销 Commit 的 Header。

  ```
  revert: feat(pencil): add 'graphiteWidth' option
  
  This reverts commit 667ecc1654a317a13331b17617d973392f415f02.
  ```

  Body部分的格式是固定的，必须写成`This reverts commit &lt;hash>.`，其中的`hash`是被撤销 commit 的 SHA 标识符。

  如果当前 commit 与被撤销的 commit，在同一个发布（release）里面，那么它们都不会出现在 Change log 里面。如果两者在不同的发布，那么当前 commit，会出现在 Change log 的`Reverts`小标题下面。



### Commitizen

[Commitizen](https://github.com/commitizen/cz-cli)是一个撰写合格 Commit message 的工具。

安装命令如下。

```
$ npm install -g commitizen
```

然后，在项目目录里，运行下面的命令，使其支持 Angular 的 Commit message 格式。

```
$ commitizen init cz-conventional-changelog --save --save-exact
```

以后，凡是用到`git commit`命令，一律改为使用`git cz`。这时，就会出现选项，用来生成符合格式的 Commit message。



### validate-commit-msg

[validate-commit-msg](https://github.com/kentcdodds/validate-commit-msg) 用于检查 Node 项目的 Commit message 是否符合格式。

它的安装是手动的。首先，拷贝下面这个[JS文件](https://github.com/kentcdodds/validate-commit-msg/blob/master/index.js)，放入你的代码库。文件名可以取为`validate-commit-msg.js`。

接着，把这个脚本加入 Git 的 hook。下面是在`package.json`里面使用 [ghooks](http://npm.im/ghooks)，把这个脚本加为`commit-msg`时运行。

```
"config": {
    "ghooks": {
      "commit-msg": "./validate-commit-msg.js"
    }
  }
```

然后，每次`git commit`的时候，这个脚本就会自动检查 Commit message 是否合格。如果不合格，就会报错。

```
$ git add -A 
$ git commit -m "edit markdown" 
INVALID COMMIT MSG: does not match "<type>(<scope>): <subject>" ! was: edit markdown
```



### 生成Change log

如果你的所有 Commit 都符合 Angular 格式，那么发布新版本时， Change log 就可以用脚本自动生成（[例1](https://github.com/ajoslin/conventional-changelog/blob/master/CHANGELOG.md)，[例2](https://github.com/karma-runner/karma/blob/master/CHANGELOG.md)，[例3](https://github.com/btford/grunt-conventional-changelog/blob/master/CHANGELOG.md)）。

生成的文档包括以下三个部分。

```
New features
Bug fixes
Breaking changes.
```

每个部分都会罗列相关的 commit ，并且有指向这些 commit 的链接。当然，生成的文档允许手动修改，所以发布前，你还可以添加其他内容。

[conventional-changelog](https://github.com/ajoslin/conventional-changelog) 就是生成 Change log 的工具，运行下面的命令即可。

```
$ npm install -g conventional-changelog
$ cd my-project
$ conventional-changelog -p angular -i CHANGELOG.md -w
```

上面命令不会覆盖以前的 Change log，只会在`CHANGELOG.md`的头部加上自从上次发布以来的变动。

如果你想生成所有发布的 Change log，要改为运行下面的命令。

```
$ conventional-changelog -p angular -i CHANGELOG.md -w -r 0
```

为了方便使用，可以将其写入`package.json`的`scripts`字段。

```
{
  "scripts": {
    "changelog": "conventional-changelog -p angular -i CHANGELOG.md -w -r 0"
  }
}
```

以后，直接运行下面的命令即可。

```
$ npm run changelog
```



## git小步提交

在Git中每次Commit都可以被算作是一个版本。

**小步快跑**的意思就是通过把大的功能点切分成若干小的子功能，在一定时间范围内只针对某个子功能进行集中开发，也可以理解为各个击破的意思。这种开发模式的好处是帮助我们把问题降低维度，由繁变简，不过随着开发工作的继续，问题也会显现出来，就是太多小的Commit导致Git历史过于琐碎，没法梳理出有用信息。

#### 利用Git技巧进行小步快跑

* **无痛重置**

  无痛重置，是采用「小步快跑」后带来的第一个好处，因为是小步快跑所以改动的内容也不会很多，重新开始的代价基本为零，相反如果两个版本之间划分跨度较大，这时重头再来的代价就会变很高，让你望而却步。

  删除未被追踪的文件和文件夹

  ```
  git clean -fd
  ```

  reset 删除Commit

  ```
  git reset —hard HEAD 
  git reset —hard HEAD^
  git reset —soft HEAD^
  ```

  上面第一条不带脱字符(^)的reset命令是将存在于stage的改动删除，第二条命令用来回到上一个版本，并删除当前版本。最后一条也是回到上一次Commit的状态，不过不会像使用`hard`参数那样删掉当前版本，而是将Commit重新放回到了stage中。对于小步快跑而言soft的意义不大，因为已经是小步提交了，所以出现的场景应该是要么删要么留，不会有需要修改Commit提交本身的需求。

* **合并Commit**

  小步给我们带来便捷的同时，也带来了一堆琐碎的Commit，如果任由这些Commit进入到最后的History，那么最后将会导致无法凸显出有用的Commit信息来。正确的做法是，在本地进行小步快跑，并只在本地合并小版本的Commit后再推到远程服务器。合并Commit，会涉及到修改Git的历史，我们需要用到`git rebase -i`这个命令，关于这个命令的使用可以参考[Git: 重写提交历史](http://mp.weixin.qq.com/s?__biz=MzAwNDYwNzU2MQ==&mid=400090340&idx=1&sn=85a16c05928d6d660b4c26d6934a6acc&scene=21#wechat_redirect) 。