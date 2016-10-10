## 软件包管理系统
1 Debian和Ubuntu使用DPKG管理软件包
> ```dpkg --install 安装软件包```

> ```dpkg -l 查看已安装的软件包```

> ```dpkg --remove 卸载软件包```

2 rpm适用于绝大多数的Liunx发型版本
> ```rpm -i  安装软件包```
  
> ```rpm -U 升级软件包```

> ```rpm -qa 查看已安装的软件包```

> ```rpm -e 卸载软件包 ```

3 高级软件包工具apt
> 全称为Advanced Pakage Tool 高级软件包工具 

> ``` apt-get update更新当前apt-get缓存中的软件包信息```

> ```apt-get install 下载并安装软件包```

> ```apt-get upgrade 下载并安装在本系统上已有的软件包的最新版本```

> ```apt-get remove 卸载待定的软件包```

> ```apt-get source 下载特定的软件源代码```

> ```apt-get clean 删除所有已下载的包文件 ```

> 安装源所放路径 ```/etc/apt/sources.list```

4 源代码编译软件
1. ```./configure --prefix=/usr/local/games/foobillard ``` ```/usr/local/games/foobillard``` 为安装目录