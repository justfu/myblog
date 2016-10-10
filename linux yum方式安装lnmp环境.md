```
yum list php php-fpm 
```
> 列出php 和php-fpm 是否存在

yum -y install php php-fpm     #安装php 和php-fpm软件包

#看见｛Complete! }  安装成功。

------------------------------------

启动php-fpm：

/etc/init.d/php-fpm start                    #1

``` 
service php-fpm start                         #2