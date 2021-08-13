# nginx安装配置


基于Centos 7.5 版本的 ，源码方式安装nginx

<!--more-->

# nginx 源码方式安装



## 下载nginx包

[nginx下载]: http://nginx.org/en/download.html	"“nginx下载"



## 解压安装包

``` 
# 进入nginx安装目录
cd /usr/local/src

#解压nginx
tar -zxvf nginx-1.21.1.tar.gz
```



## 配置nginx

```
# 进入nginx目录
cd nginx-1.21.1/

./configure
```



执行`./configure`可能会报错，是因为服务器缺少依赖程序

> 安装c++编译环境
>
> 安装 make: 
>
> yum -y install autoconf automake make
>
> 安装g++:
>
> yum -y install gcc gcc-c++
>
>  
>
> 安装 nginx 依赖程序包
>
> yum -y install pcre pcre-devel
>
> yum -y install zlib zlib-devel
>
> yum install -y openssl openssl-devel
>



出现下图，则说明执行 `configure` 成功

![image-20210812164945850](/images/linux/install/nginx-configuration.png) 



## 编译nginx代码

```
# 配置完成之后执行make 命令 进行编译 执行目录为nginx目录
make 
```

出现下图则 编译成功

![image-20210812165846281](/images/linux/install/nginx-make.png)



## 安装nginx代码

```
make install
```

安装成功如下图

![image-20210812170132460](/images/linux/install/nginx-install-success.png)



## 查看nginx安装位置

```
[root@VM-0-14-centos nginx-1.21.1]# whereis nginx
nginx: /usr/local/nginx
```



## nginx 目录结构

```
drwxr-xr-x 2 root root 4096 Aug 12 17:00 conf   配置文件
drwxr-xr-x 2 root root 4096 Aug 12 17:06 html  静态网页文件
drwxr-xr-x 2 root root 4096 Aug 12 17:00 logs  日志文件
drwxr-xr-x 2 root root 4096 Aug 12 17:00 sbin  二进制程序
```

好了，到了这一步就说明nginx安装完成了。❤

最后为了方便 nginx 在任何一个目录都可以使用，所以还需要配置环境便令

## 环境变量配置

```
# 编辑环境变量
vim /etc/profile
# 并在文章最后追加以下信息
export PATH=$PATH:/usr/local/nginx/sbin/

# 刷新环境变量信息
source /etc/profile
```

✔nginx安装完成。






