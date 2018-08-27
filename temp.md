./migrate up 


一，从0开始；

1、执行脚本*up*.sql
2、新建migrate数据表，如果不存在
```sql
CREATE TABLE IF NOT EXISTS migrate
(
id int,
version char(80)
)
```


3、把*up*.sql数据表文件名，写入migrate表
```
  1,20180308-145756_up_oneTimeFreeFlag  
```

4、如果未执行完，则循环1·3，直到up 文件被执行完


二、中间版本

1、对所有UP文件进行排序，并且存储到数组中；
2、读migrate表最后一条数据，存储在变量中；
3、比较1、2值，剩下没有执行的文件；
4、执行脚本*up*.sql
5、新建migrate数据表，如果不存在
```sql
CREATE TABLE IF NOT EXISTS migrate
(
id int,
version char(80)
)
```
6、把*up*.sql数据表文件名，写入migrate表
```
  1,20180308-145756_up_oneTimeFreeFlag  
```

7、如果未执行完，则循环4·7，直到up 文件被执行完




例子：

第一次部署；

1、对所有UP文件进行排序，并且存储到数组中；  20180308-145756_up_oneTimeFreeFlag.sql  
2、读migrate表最后一条数据，存储在变量中；  不存在
3、比较1、2值，剩下没有执行的文件；         全部没执行 20180308-145756_up_oneTimeFreeFlag.sql 
4、按时间顺序执行脚本*up*.sql
5、新建migrate数据表，如果不存在
```sql
CREATE TABLE IF NOT EXISTS migrate
(
id int,
version char(80)
)
```
6、把*up*.sql数据表文件名，写入migrate表
```
  1,20180308-145756_up_oneTimeFreeFlag  
```

7、如果未执行完，则循环4·7，直到up 文件被执行完



第二次升级；

1、对所有UP文件进行排序，并且存储到数组中；  20180308-145756_up_oneTimeFreeFlag.sql  20180313-121754_up_addTimeRevise.sql
2、读migrate表最后一条数据，存储在变量中；  20180308-145756_up_oneTimeFreeFlag.sql
3、比较1、2值，剩下没有执行的文件；         全部没执行   20180313-121754_up_addTimeRevise.sql
4、按时间顺序执行脚本*up*.sql
5、新建migrate数据表，如果不存在
```sql
CREATE TABLE IF NOT EXISTS migrate
(
id int,
version char(80)
)
```
6、把*up*.sql数据表文件名，写入migrate表
```
  1,20180308-145756_up_oneTimeFreeFlag  
  2,20180313-121754_up_addTimeRevise
```

7、如果未执行完，则循环4·7，直到up 文件被执行完






/migrate new addUser 


20180308-145756_down_addUser.sq
20180308-145756_up_addUser.sql

upfile=`find -name '*_up_*'`
echo " ${upfile[0]}"


