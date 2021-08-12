## 分支
### 分支的概念
分支就是科幻电影里面的平行宇宙，当你正在电脑前努力学习Git的时候，另一个你正在另一个平行宇宙里努力学习SVN。

如果两个平行宇宙互不干扰，那对现在的你也没啥影响。不过，在某个时间点，两个平行宇宙合并了，结果，你既学会了Git又学会了SVN！
![[Pasted image 20210809162103.png]]


### 分支的基本操作.

```shell
# 创建分支
git branch name //创建名为name的分支

#切换分支
git checkout name //这个是什么意思? 切换名字到为name的分支
# 上面两行可以改成一行
git checkout -b name


#切换分支还可以用
git switch -c dev  // 创建名为dev的分支,并切换到该分支
git switch dev      //切换到已有的dev分支.

# 修改完了代码，需要push到远程分支上，可以下面操作
git push --set-upstream origin 分支名

# 查看分支
git branch   # 本地分支
git branch -r   # 远程分支
git brance -a  # 查看所有分支

#合并分支
git merge dev //比如说当前所在分支为main,然后我使用这个命令,就会将dev和main合并到一起.

#删除分支
git branch -d name #删除分支,这个一般在当前分支开发完成,merge之后使用..



```

```ad-attention

在新建的分支上面做了更改之后,需要commit之后,才能看到两个的区别,不然,就会发现,两个分支的东西是一样的了.

也就是下面这个问题.

![[Pasted image 20210809163653.png]]

```
