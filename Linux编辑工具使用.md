# Vim

Vim是从 vi 发展出来的一个文本编辑器。代码补完、编译及错误跳转等方便编程的功能特别丰富。
**vim键盘图：**

![在这里插入图片描述](http://www.runoob.com/wp-content/uploads/2015/10/vi-vim-cheat-sheet-sch.gif)

## vim的使用

基本上 vi/vim 共分为三种模式，分别是命令模式（Command mode），输入模式（Insert mode）和底线命令模式（Last line mode）。 这三种模式的作用分别是：

### 命令模式：

刚刚启动vi/vim，便进入命令模式
**常用的几个命令：**

-   i 切换到输入模式，以输入字符串
-   x 删除当前光标所在处的字符
-   : 切换到底线命令模式，以在最底层一行输入命令

### 输入模式

**常用按键：**

- ENTER，回车键，换行
- DEL，删除键
- 方向键，文本中移动光标
- HOME/END，移动光标到行首/行尾
- Insert，切换光标尾输入/替换模式，光标将变成竖线/下划线
- ESC，退出输入模式，切换到命令模式

### 底线命令模式

**基本命令：**

- **q** 退出
- **q！** 强制退出，不保存
- **wq！** 强制保存并退出
- **w <文件路径>** 另存为
- **saveas <文件路径>** 另存为
- **x** 保存并退出
- **wq** 保存并退出

##### vim命令图

![在这里插入图片描述](https://img-blog.csdn.net/20160712110935064?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

# vim高级功能

### 多文件编辑

编辑多个文件有两种形式，一种是在进入vim前使用的参数就是多个文件。另一种就是进入vim后再编辑其他的文件。

1. `vim 1.txt 2.txt` 同时创建两个新文件并编辑，默认进入1.txt文件编辑界面

- 命令行模式下输入：n编辑2.txt文件，可以加！即强制切换文件，之前文件内的输入没有保存
- 命令行模式下输入：N编辑1.txt文件，可以加！即强制切换文件，之前文件内的输入没有保存

2. 进入vim后打开新文件

- 命令行模式下输入：`e 3.txt` 打开新文件3.txt
- 命令行模式下输入：`e#` 回到前一个文件
- 命令行模式下输入：`b 2.txt` 直接进入2.txt
- 命令行模式下输入：`bd 2.txt`删除以前编辑过的列表中的文件
- 命令行模式下输入：`e！ 4.txt`，新打开4.txt，放弃正在编辑的文件
- 命令行模式下输入：`f` 显示正在编辑的文件名
- 命令行模式下输入：`f new.txt`，改变正在编辑的文件名为new.txt

3. 恢复文件
文档为保存二意外关机，可采用恢复方式：vim -r进入文档后，输入：`ewcover 1.txt`来恢复

### 文档加密

`vim -x file` 输入密码，确认密码，下次打开需输入密码

### vim中执行外命令
在命令行模式中输入！可以执行外部的shell命令

- `:!ls` 用于显示当前目录的内容
- `:!rm FILENAME` 用于删除名为FILENAME的文件
- `:w FILENAME`可将当前 VIM 中正在编辑的文件另存为 FILENAME 文件

