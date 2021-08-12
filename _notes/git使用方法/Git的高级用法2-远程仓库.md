---
title: "Git的高级用法2-远程仓库"
---

```C++

```## 操作远程库的基本流程
假设什么也没有,那就从第1步开始最后.
假设已经有了本地库,那就从第二步开始.(不过好像还是得新建一个.因为不能 和别的乱七八糟的库关联啊...)
### 1. 先在Github新建一个仓库

### 2. clone 下来之后,创建两者之间的关联.

```shell
git remote add origin git@github.com:username/responame.git   //这里要使用ssh地址,而不是https地址了.因为你使用了ssh连接.
```
如果发现关联错误,需要解除远程关联
[[#^52c9a6|解除远程关联的方法]]
### 3. push到远程仓库

在本地的分支进行了提交之后,就可以push到远程仓库了.

```shell
git push -u origin main //第一次push
git push origin main     //后面的push
```

## 附:解除和远程库的关联

^52c9a6




如果添加的时候地址写错了，或者就是想删除远程库，可以用git remote rm <name>命令。使用前，建议先用git remote -v查看远程库信息：

```shell
$ git remote -v
origin  git@github.com:michaelliao/learn-git.git (fetch)
origin  git@github.com:michaelliao/learn-git.git (push)
```
然后，根据名字删除，比如删除origin：

```shell
$ git remote rm origin
```
此处的“删除”其实是`解除了本地和远程的绑定关系`，`并不是物理上删除了远程库`。远程库本身并没有任何改动。要真正删除远程库，需要登录到GitHub，在后台页面找到删除按钮再删除。