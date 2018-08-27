# linux mv 命令
Linux mv命令用来为文件或目录改名、或将文件或目录移入其它位置.
* 语法1：mv 文件名 文件名	 #将源文件名改为目标文件名
```
    将文件 aaa 更名为 bbb : mv aaa bbb
```
* 语法2：mv 文件名 目录名	 #将文件移动到目标目录
```
   将info目录放入logs目录中。注意，如果logs目录不存在，则该命令将info改名为logs.
   mv info/ logs 
```
* 语法3：mv 目录名 目录名	#目标目录已存在，将源目录移动到目标目录；目标目录不存在则改名
```
    再如将/usr/student下的所有文件和目录移到当前目录下，命令行为：
    $ mv /usr/student/*  . 
```
* 参数说明：
```
   * -i: 若指定目录已有同名文件，则先询问是否覆盖旧文件;
   * -f: 在mv操作要覆盖某已有的目标文件时不给任何指示;
```