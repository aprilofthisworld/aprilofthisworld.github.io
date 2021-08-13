# linux 服务器JDK安装


CentOS 7.5 64位 安装jdk1.8

<!--more-->

下载JDK源码包[Java SE 下载]: https://www.oracle.com/java/technologies/javase-downloads.html

页面选择需要的版本。

执行以下命令，新建JDK安装目录

```
mkdir /usr/java
```

执行以下命令，将JDK源码包解压到指定位置

```
tar xzf jdk-8u221-linux-x64.tar.gz -C /usr/java
```

执行一下命令，打开profile文件

```
vim /etc/profile
```

按`i`切换至编辑模式，在  `export PATH USER ...`后另起一行，根据您实际使用的JDK版本添加以下内容

```
export JAVA_HOME=/usr/java/jdk1.8.0_221(下载的JDK版本)
export CLASSPATH=$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib
export PATH=$JAVA_HOME/bin:$PATH
```



添加完成后，如下图所示

![环境变量配置](/images/install-jdk/linux-jdk-path-success.png "环境变量配置")


按 `Esc`, 输入`:wq`，保存文件并返回。

执行以下命令，读取环境变量

执行一下命令，查看JDK是否安装成功

```
java -version
```

返回如下信息，则表示安装成功
![安装成功提示](/images/install-jdk/linux-jdk-install-success.png "安装成功提示")



