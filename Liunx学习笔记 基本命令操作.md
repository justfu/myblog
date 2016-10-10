## liunx学习笔记1

1 查看文件开头或者结尾几行的数据
> ``` head -n 2 index.php ```

> ``` tail -n 2 index.php ```

2 使用less和more 更好的查看文件内容
> ```less index.php```

> ```more index.php```

3 更快速地定位文件
> ```locate *.php```

> ```更新locate数据库 updatedb 需耗时一分钟```

4 查找特定程序可执行文件以及手册所放地方
> ```whereis find ```

5 寻求帮助(查看命令使用方法)
> ```man find ```

6 建立符号连接(软链接)
> ``` ln -s index.php index.php.href```后面的为链接

7 管道：|
> 通过一根竖线| 将一条命令的输出连接到另一条命令输入

8 查找文件内容 grep 
> ``` grep de index.php```
```|```
-----------------------------
## Liunx系统主要目录及其内容

目录   |     内容
--- |---
 /bin| 构建最小系统所需要的命令
/boot | 内核与启动文件
/dev  | 各种设备文件
/etc  | 系统软件的启动和配置文件
/home | 用户的主目录
/lib  | C编译器的库
/media| 可移动介质的安装点
/opt  | 可选的应用软件包
/proc | 进程的映像
/root | 超级用户root的主目录
/sbin | 和系统操作有关的命令
/tmp  | 临时文件存放点
/usr  | 非系统的程序和命令
/var  | 系统专用的数据和配置文件


