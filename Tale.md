# 如何使用Tale 

* 必须环境
  JDK8
在命令行下输入：java -version进行查看，如果你还没有JDK8环境，请复制以下网址下载安装
```
https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=0&rsv_idx=1&tn=baidu&wd=%E5%AE%89%E8%A3%85jdk8&rsv_pq=e8c007db000fce85&rsv_t=5a722NwTBlSPtvRjGgFxMBa5TeujOyaXY60bDEfTBX0O38Sjkde8BY6%2BJ7o&rqlang=cn&rsv_enter=1&rsv_sug3=14&rsv_sug1=11&rsv_sug7=100&rsv_sug2=0&inputT=3400&rsv_sug4=3505
```
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

