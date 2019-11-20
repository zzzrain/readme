# Git

##一、安装与配置
- 安装自行百度

- 个人信息配置
````
git config --global user.name 我是JOJO
git config --global user.email jojo@163.com
git config -l
````

- 本机首次配置
````
1、创建ssh key
ssh-keygen -t rsa -C jojo@163.com

2、找到.ssh目录的钥匙（win7在C盘User目录下）
id_rsa：私钥   id_rsa_pub：公钥

3、添加到git个人账号上，位置：
Settings -- SSH and GPG keys

4、检测连接  ssh -T git@github.com
````

##二、创建项目
- 直接拉取远程仓库
````
git clone xxx(远程地址)
````

- 本地仓库
````
1、初始化  git init

2、连接    git remote add origin

3、查看    git remote -v

4、删除    git remote rm origin
````

##三、常用命令
事实上可视化工具、编辑器插件的存在，已经不常用了
````
1、添加到暂存区，加文件名，.代表全部    git add .

2、提交到版本库    git commit -m 第一次提交

3、同步代码  git pull

4、上传代码  git push

5、查看状态  git status

6、切换分支  git checkout xxx

7、合并分支  git merge xxx
。
。
。
8、事实上，有一个比较危险但实用的，工具/插件可能执行不了   git push --force
````

##四、图解
如下图，LICENSE是本次实践的一个文件。

- LICENSE一开始放在本地文件夹中，相当于工作区

<img src='https://github.com/zzzrain/images/blob/master/git/state1.jpg'><br>

- git add相当于把LICENSE丢到暂存区

<img src='https://github.com/zzzrain/images/blob/master/git/state2.jpg'><br>

- git add相当于把LICENSE丢到分支上

<img src='https://github.com/zzzrain/images/blob/master/git/state3.jpg'><br>

注意事项：
- 这些都是本地操作，最后还要git push；
- 协作开发需要git pull解决冲突；
- 当然，最好一人一个分支或者一人一个模块尽量避免冲突。

##五、版本管理
````
1、查看最近  git log
2、查看所有  git reflog  （很重要，能找回被覆盖的数据）
3、版本回退  git reset   （也能穿回未来）
4、参数，一个^一个版本
   上一版本 --hard HEAD^
   上上版本 --hard HEAD^^
   。。。
   指定版本 --hard xxx
   
   --hard   还原到上一次提交（清除所有改动）
   --mixed  还原到工作区（清除commit，清除add）
   --soft   还原到暂存区（清除commit，保留add）
   
5、只要保留本地仓库(.git)，所有commit过的记录都能找回来。
````
