官方中文文档：https://docs.github.com/cn/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

# 零基础（新建仓库）

## 安装Git

## Git初始设置

```
$ git config --global user.name "Firstname Lastname"
$ git config --global user.email "your_email@example.com"
```

初始设置完成后，会在"~/.gitconfig"文件夹中显示。

## GitHub上创建账户

## 设置SSH Key

参考链接：https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## 在GitHub上创建一个（远程）仓库

假设名字为testa。

## 初始化（本地）仓库

可以新建一个文件夹test，打卡Git Bash，转到testb目录下，输入：

```
$ git init
```

会生成".git"文件，那么整个testb就会等价于GitHub上创建的仓库testa。

## 在testa下添加文件或目录

## 将文件放入暂存区

```
$ git add .
```

or

```
$ git add "filename"
```

##  保存仓库的历史记录

```
$ git commit -m "description"
```

## 设置本地仓库的远程仓库

```
$ git remote add origin git@github.com:berry-raccoon/testa.git
```

### remote拓展

1. "fatal: remote origin already exists"

```
$ git remote set-url origin git@github.com:ppreyer/first_app.git
```



##  将文件上传

```
$ git branch
$ git push origin -u your-branch-name
```

会出现" * your-branch-name"，可以查看当前所在的分支，再通过push上传文件。

### **branch** 拓展

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

###  **push**拓展：

1. 参数 -u

   将origin(仓库)的master分支设置为本地仓库当前分支的upstream。

## 删除仓库



以上是新建一个仓库的玩法，那如果是已经创建好仓库怎么管理。

-------------------

首先要下载原仓库内容，初始化等操作。

[git 上传代码到GitHub 以及git删除github上文件和文件的命令](https://blog.csdn.net/weixin_42350212/article/details/80560272)

```
$ git pull origin master
$ git pull origin master
```

