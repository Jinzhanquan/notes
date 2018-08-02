# 安装mysql
* 安装环境：centos7
* 下载并安装mysql官方的YUM REPOSITORY
```
[root@localhost ~]# wget -i -c http://dev.mysql.com/get/mysql57-community-release-el7-10.noarch.rpm
```
使用上面的命令就直接下载了安装用的Yum Repository，大概25KB的样子，然后就可以直接yum安装了

```
[root@localhost ~]# yum -y install mysql57-community-release-el7-10.noarch.rpm
```
之后就开始安装MySQL服务器。

```
[root@localhost ~]# yum -y install mysql-community-server
```
这步可能会花些时间，安装完成后就会覆盖掉之前的mariadb。
```
Installed:
  mysql-community-libs.x86_64 0:5.7.23-1.el7                      mysql-community-libs-compat.x86_64 0:5.7.23-1.el7                   
  mysql-community-server.x86_64 0:5.7.23-1.el7                   

Dependency Installed:
  mysql-community-client.x86_64 0:5.7.23-1.el7                       mysql-community-common.x86_64 0:5.7.23-1.el7                      

Replaced:
  mariadb-libs.x86_64 1:5.5.56-2.el7                 
 ```
  至此MySQL就安装完成了，然后是对MySQL的一些设置
* Mysql数据库设置

   * 首先启动MySQL
   ```
   [root@localhost ~]# systemctl start  mysqld.service
   ```
   *   查看MySQL运行状态
   ```
   [root@localhost ~]# systemctl status mysqld.service
   ```
   运行状态如图：
   ```
    [图片.png]()
    