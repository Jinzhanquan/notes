# 系统时间设置

* 安装时间同步工具
```
yum install ntpdate
```

* 同步时间
```
ntpdate -u ntp.api.bz
```

* 查看时间
```
hwclock -r
```

* 写时间
```
hwclock -w
```
