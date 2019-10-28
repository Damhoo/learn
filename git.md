#### 全局配置

##### 设置
```
git config --global user.name "dehoo"
git config --global user.email "shitsui@sina.com"
```

如果使用的GPG的验证方式，则需要添加以下一行

````
git config --global user.signingKey GPG_KEY
````

注意：上述命令的`GPG_KEY`要使用软件生成。

- WIN平台下载地址：https://gpg4win.org/
- MAC平台下载地址：https://gpgtools.org/
- Linux平台不需要安装，可通过以下命令安装

以下安装方式只针对类unix平台。

```
# yum install -y gnupg2
```

##### 查看
```
git config --global --list
```

##### 删除

```
git config --global -d CONFIG_NAME
```

注意：上述命令的`CONFIG_NAME`是你配置时的名字，例：user.name。

#### 初始化

当我们在本地生成一个项目时，需要先进行初始化，命令如下：

```
# mkdir project1
# cd project1
# git init
```

#### 把项目添加到暂存区

当我们的项目完成一个功能的时候，我们要及时把项目文件添加到暂存区。

```
# git add .
```

#### 把项目推送到GIT仓库中

项目添加到暂存区还不行，我们必须要将项目推送到仓库中，这才能进行版本控制。

```
# git commit -m 'add file to repo'
```

#### 删除项目文件

当你要删除项目中的某些文件时，请不要右键直接删除，最好用git的删除方式。

```
# git rm FILE_NAME
```

#### 远程仓库配置

##### 添加远程仓库

如果我们的项目不是个人项目，而是团队项目，并且希望在互联网上被其他人访问，那么我们就必须配置远程仓库，最大的网上托管平台如github/gitee/gitlab等。
本次就以github为例。

```
# git remote add ALIAS_NAME git@github.com:Damhoo/wintest.git
```

注意：`ALIAS_NAME`是给远程仓库起的别名，如果不起别名，那你每次把项目推送到远程仓库，需要写`git@github.com:Damhoo/wintest.git`完整路径。

##### 查看远程仓库

```
# git remote -v
lg  git@github.com:Damhoo/wintest.git (fetch)
lg  git@github.com:Damhoo/wintest.git (push)
```

以上命令`git remote -v`显示结果中的lg就是远程仓库别名。

##### 更新远程仓库别名

```
# git remote rename OLD_NAME NEW_NAME
```

##### 更改远程仓库URL地址

如果你只是想更改远程仓库的地址，不需要改别名，那么就用以下命令：

```
# git remote set-url "git@github.com:Damhoo/JavaPro.git"
```

若还有其他的更改需求，使用`git remote help`可查看更多命令。


##### 删除远程仓库

注意，这里删除远程仓库，不是把远程的仓库给删除了，而是删除本地的远程仓库别名。

```
# git remote remove ALIAS_NAME
```

#### 分支配置

为什么要用到分支？

举个例子：老板要你写一个微信支付功能，当你开发到一半的时候，原有项目的支付宝功能出现了一个BUG，需要马上修改，这时你就想，如果回退到上个版本，那么你现在写到一半的功能就没有了；但是如果不回退，你的功能没有完成又会影响线上的展示，为了保证你现在编写的代码保留下来，又能回退到上个版本，此时就必须用到分支了。


##### 查看分支

```
# git branch
```

##### 添加分支

```
# git branch BRANCH_NAME
```

注意：BRANCH_NAME是分支名。

##### 切换分支

```
# git checkout BRANCH_NAME
```

##### 合并分支

```
# git merge BRANCH_NAME
```

##### 删除分支

```
# git branch -d BRANCH_NAME
```

当把以上命令熟练运用时，你就能完全会用GIT版本控制了，也能在任何需要使用GIT的公司上班了。