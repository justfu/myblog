1 安装nginx时必须先安装相应的编译工具
> ``` yum -y install gcc gcc-c++ autoconf automake```

> ```yum -y install zlib zlib-devel openssl openssl-devel pcre-devel```

2 建立nginx 组(可以省略)
```
groupadd -r nginx
useradd -s /sbin/nologin -g nginx -r nginx
id nginx
```
> zlib:nginx提供gzip模块，需要zlib库支持

> openssl:nginx提供ssl功能

>pcre:支持地址重写rewrite功能

3 tar -zxvf nginx-1.2.8.tar.gz

4 cd nginx-1.2.8

5 
```./configure \
--prefix=/usr \
--sbin-path=/usr/sbin/nginx \
--conf-path=/etc/nginx/nginx.conf \
--error-log-path=/var/log/nginx/error.log \
--pid-path=/var/run/nginx/nginx.pid \
--user=nginx \
--group=nginx \
--with-http_ssl_module \
--with-http_flv_module \
--with-http_gzip_static_module \
--http-log-path=/var/log/nginx/access.log \
--http-client-body-temp-path=/var/tmp/nginx/client \
--http-proxy-temp-path=/var/tmp/nginx/proxy \
--http-fastcgi-temp-path=/var/tmp/nginx/fcgi \
--with-http_stub_status_module```

6. ```make && make install```