# Linux基本概念与指令

### 简介

### 什么是linux

Linux是一套免费使用和自由传播的类Unix操作系统，是一个多用户、多任务、支持多线程和多CPU的操作系统。它能运行主要的UNIX工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。®

- 严格来讲，Linux这个词本身只表示Linux内核，但实际上人们已经习惯了用Linux来形容整个基于Linux内核，并且使用GNU 工程各种工具和数据库的操作系统。
- 目前国内Linux更多的是应用于服务器上（Linux + Apache + MySQL + PHP），而桌面操作系统更多使用的是 Windows。
- Linux是一个多用户多任务的操作系统，也是一款自由软件，完全兼容POSIX标准，拥有良好的用户界面，支持多种处理器架构，移植方便。。
- 系统中的所有都归结为一个文件，包括命令、硬件和软件设备、操作系统、进程等等对于操作系统内核而言，都被视为拥有各自特性或类型的文件。
- 在Linux中，所有的数据都被保存在文件中，所有的文件又被分配到不同的目录；目录是一种类似树的结构，称为文件系统。

### Linux的优点

- 大量的可用软件及免费软件Apache、Samba(文件共享服务)、PHP、MySQL等，但办公游戏娱乐方面软件匮乏。

- 良好的可移植性及灵活性几乎支持所有的CPU平台，便于裁剪和定制，可放在U盘、光盘中。

- 优良的稳定性和安全性“足够多的眼睛，就可让所有问题浮现。”——埃里克•雷蒙德（EricS.Raymond）

- 支持几乎所有的网络协议及开发语言UNIX由C语言开发，Linux是UNIX的一种，C语言衍生出PHP、Java、C艹等。

### Linux的缺点

- 没有特定的支持厂商,在linux上的所有套件几乎都是自由软件，自由软件的开发者大部分都不是盈利型的团体。所以在linux上面的软件如果发生问题，只能自己寻找解决方案

- 游戏支持度不足,现在游戏的风靡程度超乎想像，但在Linux上开发的大型游戏几乎没有，这也间接让linux很难进入一般家庭。

- 专业软件支持度不足,很多专业型软件在linux上无法运行（例如很多市面上的专业绘图软件）

### linux系统安装过程
准备工具：

- VMware Workstation

- X-Shell客户端

- ContOS镜像文件(推荐7.0+版本)

下面打开VMware， 正式安装：

![img](https://images2018.cnblogs.com/blog/1363214/201808/1363214-20180815114613676-343972670.png)

注意：版本这里一定要选择 Red Hat Enterprise Linux 7 64 位，否则安装完成之后，执行ip addr命令只有一个ifcfg-io回环网卡配置文件。

![img](https://img2018.cnblogs.com/blog/1363214/201910/1363214-20191030142914843-1418793248.png)

![img](https://images2018.cnblogs.com/blog/1363214/201808/1363214-20180815134503599-762157965.png)

![img](https://images2018.cnblogs.com/blog/1363214/201808/1363214-20180815135035408-2116156725.png)

![img](https://images2018.cnblogs.com/blog/1363214/201808/1363214-20180815143942270-1720733793.jpg)

 **接下来，我们开始装系统：** 启动虚拟机，选择系统语言， 选择内存大小，开启以太网连接，创建管理员账号密码，等待安装就好了。

 centos安装好之后默认是无法上网的，我们需要通过vi /etc/sysconfig/network-scripts/ifcfg-xxx(把onboot修改为yes才能激活网卡上网) 。然后service network restart重启服务，这时我们可以看到服务已经分配网络ip了。

![img](https://images2018.cnblogs.com/blog/1363214/201808/1363214-20180815182253678-1851341820.png)

这个时候我们可以安装一些常用的工具：

-  yum install net-tools -y (ifconfig, route, arp和netstat等命令工具统称为net-tools)

- yum install vim -y  文本编辑器

- yum install lrzsz -y 文件上传下载

- yum install unzip -y 解压zip文件得工具

- yum install wget -y 在线下载工具

#### XShell远程连接服务器：

　　直接默认安装下载好的xshell客户端， 执行  ssh 账号@端口(例： ssh root@192.168.194.128)  ，输入弹出的密码框，就能连接了我们的linux服务器了。

##### 远程文本编辑器：

![img](https://img2018.cnblogs.com/blog/1363214/201809/1363214-20180924162624568-300005414.png)

![img](https://img2018.cnblogs.com/blog/1363214/201809/1363214-20180924162654356-887236602.png)

### 处理目录常用命令（创建、删除）

- ls: 列出目录
- cd：切换目录
- pwd：显示目前的目录
- mkdir：创建一个新的目录
- rmdir：删除一个空的目录
- cp: 复制文件或目录
- rm: 移除文件或目录
- mv: 移动文件与目录，或修改文件与目录的名称

### 文件（创建、删除、查看）

- vi filename 创建文件
- 当文件被打开后，可以按 i 键进入编辑模式，按照自己的方式编辑文件。如果想移动光标，必须先按 esc 键退出编辑模式，然后使用下面的按键在文件内移动光标
- l 键向右移动
- h 键向左移动
- k 键向上移动
- j 键向下移动
- 使用上面的按键，可以将光标快速定位到你想编辑的地方。定位好光标后，按 i 键再次进入编辑模式。编辑完成后按 esc 键退出编辑模式或者按组合键 Shift+ZZ 退出当前文件。
- cat filename 查看文件内容
- cat -b filename 显示行号
- cp source_file destination_file 复制文件
- mv old_file new_file 重命名文件
- rm filename 删除文件
- rm filename1 filename2 filename3 一次删除多个文件

### 文件内容查看

- cat 由第一行开始显示文件内容
- tac 从最后一行开始显示，可以看出 tac 是 cat 的倒著写！
- nl 显示的时候，顺道输出行号！
- more 一页一页的显示文件内容
- less 与 more 类似，但是比 more 更好的是，他可以往前翻页！
- head 只看头几行
- tail 只看尾巴几行

### 补充

- 可以使用 man [命令] 来查看各个命令的使用文档，如 ：man cp
- 一个点号(.)表示当前目录，两个点号(…)表示上级目录（父目录）。
- ls 命令的 -a 选项可以查看所有文件，包括隐藏文件；-l 选项可以查看文件的所有信息

