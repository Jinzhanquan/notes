# 如何使用Tale 

* 必须环境
  JDK8
在命令行下输入：java -version进行查看，如果你还没有JDK8环境，可以在[官网](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)下载安装

* 安装Tale
复制以下网址下载最新版Tale,该程序是个zip包，解压后的目录结构如下：

```
网址：http://static.biezhi.me/tale-least.zip?1231
```
```tale
    ├── lib
    ├── resources
    └── tale-least.jar
```

执行 java -jar tale-least.jar 即可启动web服务器，访问 http://host:9000/install 进行安装。

如果您没有域名，请确认防火墙已经关闭才可访问端口。
## 使用脚本启动
新版本的 tale 程序解压后会有一个 bin 目录，里面有一个 tale-cli 的小工具，支持在linux平台使用，请先对它授权 chmod +x tale-cli。

* 启动博客程序
```
./tale-cli start
```

* 关闭博客程序
```
./tale-cli stop
```

* 查看日志
```
./tale-cli log
```

* 查看启动状态
```
./tale-cli status
```

* 升级tale
```
./tale-cli upgrade
```


## 防火墙设置

* 检查网络的工具没有安装
```
yum install net-tools
```

* 检查端口是否被打开
```
netstat -ano | grep 9000
```

* 检查防火墙

```
[root@bogon tale]# firewall-cmd --state
running
[root@bogon tale]# firewall-cmd --zone=public --query-port=9000/tcp
no
[root@bogon tale]# firewall-cmd --zone=public --add-port=9000/tcp --permanent 
success
[root@bogon tale]# firewall-cmd --reload 
success
```

## 使用浏览器检查

http://192.168.1.243:9000