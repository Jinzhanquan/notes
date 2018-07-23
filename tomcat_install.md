# 部署tomcat

## 前言

安装环境 CentOS Linux release 7.5.1804 (Core) 


## 操作步骤

* 安装jdk1.8 
```
$ yum install  java
```

* 下载tomcat 

```
yum install wget   #如果没有安装wget 则需要执行该命令
wget http://mirrors.tuna.tsinghua.edu.cn/apache/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz
```

* 解压
```
tar -xzvf apache-tomcat-9.0.10.tar.gz
mv apache-tomcat-9.0.10 tomcat
```

* 前台启动tomcat （option）

```
cd tomcat 
./bin/catalina.sh run   # 前台启动
curl http://localhost:8080   # 重新建一个链接，使用个该命令测试服务器是否打开
```
> 前台启动，可做测试使用，测试完毕之后，使用CTL+C退出

* 后台启动tomcat  

```
./bin/startup.sh 
tail -20 logs/catalina.out  # 查看日志最后20行，验证是否启动成功
curl http://localhost:8080
curl http://192.168.1.243:8080  # ip地址根据实际填写
```


