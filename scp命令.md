* svn 删除所有的 .svn文件
```
find . -name .svn -type d -exec rm -fr {} \;
```

* linux之cp/scp命令＋scp命令详解  
 
名称：cp

使用权限：所有使用者

使用方式：
```
cp [options] source dest

cp [options] source... directory
```
>说明：将一个档案拷贝至另一档案，或将数个档案拷贝至另一目录。


-a 尽可能将档案状态、权限等资料都照原状予以复制。

-r 若 source 中含有目录名，则将目录下之档案亦皆依序拷贝至目的地。

-f 若目的地已经有相同档名的档案存在，则在复制前先予以删除再行复制。

范例：

将档案 aaa 复制(已存在)，并命名为 bbb :
```
cp aaa bbb
```
将所有的C语言程式拷贝至 Finished 子目录中 :
```
cp *.c Finished
```
命令：scp

* 不同的Linux之间copy文件常用有3种方法：

  * 第一种就是ftp，也就是其中一台Linux安装ftp Server，这样可以另外一台使用ftp的client程序来进行文件的copy。

  *  第二种方法就是采用samba服务，类似Windows文件copy 的方式来操作，比较简洁方便。

  * 第三种就是利用scp命令来进行文件复制。

    scp是有Security的文件copy，基于ssh登录。操作起来比较方便，比如要把当前一个文件copy到远程另外一台主机上，可以如下命令。

```
scp /home/daisy/full.tar.gz root@172.19.2.75:/home/root
```

然后会提示你输入另外那台172.19.2.75主机的root用户的登录密码，接着就开始copy了。

    如果想反过来操作，把文件从远程主机copy到当前系统，也很简单。

linux之cp/scp命令＋scp命令详解(转) - linmaogan - 独木★不成林scp root@/full.tar.gz 172.19.2.75:/home/root/full.tar.gz home/daisy/full.tar.gz

linux 的 scp 命令 可以 在 linux 之间复制 文件 和 目录； 

================== 
scp 命令 
================== 
scp 可以在 2个 linux 主机间复制文件； 

命令基本格式： 
       scp [可选参数] file_source file_target 

====== 
从 本地 复制到 远程 
====== 
* 复制文件： 
        * 命令格式： 
        ```
                scp local_file remote_username@remote_ip:remote_folder 
                或者 
                scp local_file remote_username@remote_ip:remote_file 
                或者 
                scp local_file remote_ip:remote_folder 
                或者 
                scp local_file remote_ip:remote_file 
        ```
                第1,2个指定了用户名，命令执行后需要再输入密码，第1个仅指定了远程的目录，文件名字不变，第2个指定了文件名； 
                第3,4个没有指定用户名，命令执行后需要输入用户名和密码，第3个仅指定了远程的目录，文件名字不变，第4个指定了文件名； 
        * 例子：
        ```
                scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music 
                scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music/001.mp3 
                scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music 
                scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music/001.mp3 
                ```
```
* 复制目录： 
        * 命令格式： 
                scp -r local_folder remote_username@remote_ip:remote_folder 
                或者 
                scp -r local_folder remote_ip:remote_folder 

                第1个指定了用户名，命令执行后需要再输入密码； 
                第2个没有指定用户名，命令执行后需要输入用户名和密码； 
        * 例子： 
                scp -r /home/space/music/ root@www.cumt.edu.cn:/home/root/others/ 
                scp -r /home/space/music/ www.cumt.edu.cn:/home/root/others/ 

                上面 命令 将 本地 music 目录 复制 到 远程 others 目录下，即复制后有 远程 有 ../others/music/ 目录 

```
====== 
从 远程 复制到 本地 
====== 
从 远程 复制到 本地，只要将 从 本地 复制到 远程 的命令 的 后2个参数 调换顺序 即可； 

例如： 
```
        scp root@www.cumt.edu.cn:/home/root/others/music                              /home/space/music/1.mp3 
        scp -r www.cumt.edu.cn:/home/root/others/ /home/space/music/
```
>最简单的应用如下 : 

* scp 本地用户名 @IP 地址 : 文件名 1 远程用户名 @IP 地址 : 文件名 2 

* [ 本地用户名 @IP 地址 :] 可以不输入 , 可能需要输入远程用户名所对应的密码 . 

可能有用的几个参数 : 

 * -v 和大多数 linux 命令中的 -v 意思一样 , 用来显示进度 . 可以用来查看连接 , 认证 , 或是配置错误 . 

 * -C 使能压缩选项 . 

 * -P 选择端口 . 注意 -p 已经被 rcp 使用 . 

 * -4 强行使用 IPV4 地址 . 

 * -6 强行使用 IPV6 地址 .

 

注意两点：
1.如果远程服务器防火墙有特殊限制，scp便要走特殊端口，具体用什么端口视情况而定，命令格式如下：
```
#scp -p 4588 remote@www.abc.com:/usr/local/sin.sh /home/administrator
```
2.使用scp要注意所使用的用户是否具有可读取远程服务器相应文件的权限。


## ```scp -r wx.php root@119.29.204.106:/data/wwwroot/wx```