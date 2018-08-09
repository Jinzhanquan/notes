# git github
* 首先安装好Git
```
yum install git
```
* 把本地的仓库内容推送到GitHub仓库
```
在本地仓库下运行命令：

mkdir runoob-git-test                           # 创建测试目录
cd runoob-git-test/                              # 进入测试目录
echo "# 菜鸟教程 Git 测试" >> README.md          # 创建 README.md 文件并写入内容
ls                                               # 查看目录下的文件
README
git init                                         # 初始化
git add README.md                                # 添加文件
git commit -m "添加 README.md 文件"              # 提交并备注信息
[master (root-commit) 0205aab] 添加 README.md 文件
1 file changed, 1 insertion(+)
create mode 100644 README.md
```
* 提交到 Github
```
git remote add origin git@github.com:tianqixin/runoob-git-test.git
git push -u origin master
```
以下命令请根据你在Github成功创建新仓库的地方复制，而不是根据我提供的命令，因为我们的Github用户名不一样，仓库名也不一样。
* 更多GitHub教程，请访问以下网址：
http://www.runoob.com/git/git-remote-repo.html