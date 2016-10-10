* linux下解压命令大全
 ```
.tar 
解包：tar xvf FileName.tar
打包：tar cvf FileName.tar DirName
（注：tar是打包，不是压缩！）
———————————————
.gz
解压1：gunzip FileName.gz
解压2：gzip -d FileName.gz
压缩：gzip FileName

.tar.gz 和 .tgz
解压：tar zxvf FileName.tar.gz
压缩：tar zcvf FileName.tar.gz DirName
———————————————
.bz2
解压1：bzip2 -d FileName.bz2
解压2：bunzip2 FileName.bz2
压缩： bzip2 -z FileName

.tar.bz2
解压：tar jxvf FileName.tar.bz2
压缩：tar jcvf FileName.tar.bz2 DirName
———————————————
.bz
解压1：bzip2 -d FileName.bz
解压2：bunzip2 FileName.bz
压缩：未知

.tar.bz
解压：tar jxvf FileName.tar.bz
压缩：未知
———————————————
.Z
解压：uncompress FileName.Z
压缩：compress FileName
.tar.Z

解压：tar Zxvf FileName.tar.Z
压缩：tar Zcvf FileName.tar.Z DirName
———————————————
.zip
解压：unzip FileName.zip
压缩：zip FileName.zip DirName
———————————————
.rar
解压：rar x FileName.rar
压缩：rar a FileName.rar DirName
———————————————
.lha
解压：lha -e FileName.lha
压缩：lha -a FileName.lha FileName
———————————————
.rpm
解包：rpm2cpio FileName.rpm | cpio -div
———————————————
.deb
解包：ar p FileName.deb data.tar.gz | tar zxf -
```

* 查看运行进程端口号
1. linux 查询某个端口被什么进程占用的命令
```lsof -i``` : 端口号即可获取进程号

2. linux查询进程占用哪些端口
```netstat -nlap```
* 查看系统监听的服务
```
netstat -ln
netstat -tulpn
```
3. nohup命令
```
nohup Command &
jobs 查看任务(终端关闭将查看不了 使用ps -ef查看服务器所有运行进程)
fg %n 关闭
使用时采用exit退出命令终端
```
* 验证是否在后台执行
关闭该连接工具后在打开查看，这时候jobs已经不能使用，只能通过以下方式查看后台执行的脚本是否正在执行
```
ps -ef查看系统所有运行的进程
[root@NAS script]# ps -ef | grep rm
```

* 终止后台运行的删除脚本
  * 删除命令：```kill -9```  进程号
  * 注意：删除的时候不能删除查找查找命令，否则会照成关机
4. 重命名文件或者文件夹
  * 使用mv命令 ``` mv a b```
  * 使用rename命令 ``` rename a b *```