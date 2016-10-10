```
vim /etc/yum.repos.d/nginx.repo 新增yum源
```

> 填入下面的内容
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=0
enabled=1
```

> 查询yum是否存在
```yum list | grep nginx```

> yum安装mysql
对于centos7的操作系统 yum去除了mysql的版本  而是采用mysql的一个分支MariaDB来使用

安装命令

```
yum install mariadb

yum install mariadb-server

service mariadb start 启动
```