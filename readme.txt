1、安装git for windows
2、配置全区变量，name和email
3、初始化仓库  git init
4、建立.gitignore文件
5、拷贝源代码到仓库根目录
6、git add 所有需要添加到仓库的文件。
7、git commit -m "提交一个原始文档"
8、git status查看状态
9、git log查看提交历史
10、git reflog查看命令历史
11、git reset --hard commit_id  回退到某一版本
12、git diff可以查看修改内容
13、git branch 查看分支
14、git checkout master 切换分支
15、git tag v1.0   创建标签
16、git tag查看标签
17、git tag -d v0.1  删除标签


远程仓库
1、本地生成key
$ ssh-keygen -t rsa -C "youremail@example.com"
在用户主目录下，有.ssh目录，目录下有id_rsa和id_rsa.pub这两个文件
这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
2、在代码托管网站添加公钥

3、在代码托管网站新建仓库，例如Master5
4、远程关联
$ git remote add origin git@code.csdn.net:yuanjianming/master5.git
  git remote add origin https://github.com/JamieYuanChina/Test.git

5、推送
$ git push -u origin master

这个过程会要求提供github的用户名和密码

推送标签
$ git push origin v1.0
推送全部本地标签
$ git push origin --tags

出现错误的主要原因是github中的README.md文件不在本地代码目录中
可以通过如下命令进行代码合并【注：pull=fetch+merge]
git pull --rebase origin master

总结：
一个简单的git仓库创建共分为六步
1本地创建目录并git init初始化
2git add添加文件到编辑区
3git commit -m "test"提交
4在github创建仓库，不要自动添加readme
5远程添加仓库
git remote add origin https://github.com/JamieYuanChina/LearnGit.git
6推送并关联本地仓库git push -u origin master  