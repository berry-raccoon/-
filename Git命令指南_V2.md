官方中文文档：https://docs.github.com/cn/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

**更新说明**

| 日期     | 版本 | 说明                                                         |
| -------- | ---- | ------------------------------------------------------------ |
| 20220308 | V2.0 | 看我有了什么突破性进展，今天逛抖音的时候，看到小刘不是程序员推荐了几个上传程序的方式，他推荐了三个存储代码的网站，分别是[gitee](https://gitee.com/)、[coding devops](https://cloud.tencent.com/product/coding)、[azure devops](https://azure.microsoft.com/zh-cn/services/devops/)，然后我在gitee里发现比较通俗易懂的[git使用教程](https://gitee.com/oschina/git-osc/wikis/%E5%B8%AE%E5%8A%A9)。 |

# 下载安装Git

```
http://git-scm.com/downloads
```



# Git初始设置

**Git全局设置**

"Firstname Lastname"：用户名

"your_email@example.com"：注册邮箱

```
$ git config --global user.name "Firstname Lastname"
$ git config --global user.email "your_email@example.com"

```

初始设置完成后，会在"~/.gitconfig"文件夹中显示。

**GitHub上创建账户**

**在GitHub上创建一个（远程）仓库**

假设名字为testa。

**初始化（本地）仓库**

- 本地无仓库啊

  打开Git Bash输入：

  ```shell
  $ mkdir filename  //新建文件夹，名字为filename
  $ cd filename  // 转到filename文件夹下
  $ git init  // git 初始化，会生成".git"文件，
  $ git remote add origin https://xxxx.git(http)或git@xxx.git(ssh) // 设置本地仓库的远程仓库
  /* ----测试能否与网络端仓库连接----- */
  $ touch README.md
  $ git add README.md
  $ git commit -m "first commit"
  $ git push -u origin "master"
  ```

  那么整个testb就会等价于GitHub上创建的仓库testa。

- 本地已有仓库

  ```shell
  $ cd filename  // 转到filename文件夹下
  $ git init  // git 初始化，会生成".git"文件，
  $ git remote add origin https://xxxx.git或git@xxx.git // 设置本地仓库的远程仓库
  $ git push -u origin "master"
  ```



# 更新仓库内容

![](D:\桌面\刷题攻略\Carl\git上传文件简易版.png)

```shell
$ cd filename  // 转到filename文件夹下
$ git add .
$ git commit -m "commit" // 提交修改说明
$ git push -u origin "master"  // 将文件更新到master分支下
```



# 设置SSH Key

参考链接：https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent





# 命令说明

## 将文件放入暂存区

```shell
$ git add .
```

​	or

```shell
$ git add "filename"
```



## 保存仓库的历史记录

```shell
$ git commit -m "description"
```



## 查看仓库状态

```shell
$ git status
```



## 设置本地仓库的远程仓库

```shell
$ git remote add origin git@github.com:berry-raccoon/testa.git
```

remote拓展

1. "fatal: remote origin already exists"

```shell
$ git remote set-url origin git@github.com:ppreyer/first_app.git
```



## 将文件上传

```shell
$ git branch
$ git push origin -u your-branch-name
```

会出现" * your-branch-name"，可以查看当前所在的分支，再通过push上传文件。

push拓展：

1. 参数 -u

   将origin(仓库)的master分支设置为本地仓库当前分支的upstream。

   

## branch

1. 创建新分支

   ```
   $ git checkout -b new-branch-name  
   ```

2. 切换分支

   ```
   $ git checkout master
   ```

3. 主干分支

   主干分支master没有开发到一半的程序，如需多个版本可使用tag标签。

4. 合并分支

   切换到master分支下进行合并。

   ```
   $ git merge --no-ff merged-branch-name
   ```

5. 以图标形式查看分支

   ```
   git log --graph
   ```





# 删除仓库

[git 上传代码到GitHub 以及git删除github上文件和文件的命令](https://blog.csdn.net/weixin_42350212/article/details/80560272)

```
$ git pull origin master
$ git pull origin master
```

