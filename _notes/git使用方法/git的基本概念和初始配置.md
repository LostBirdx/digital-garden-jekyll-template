---
layout: note
title: "git的基本概念和初始配置"
---


```ad-attention

不会用Git的开发人员,绝对没有真正的写过代码

```


GIT 是一个版本控制软件.

从github 上面新建一个仓库的时候,只需要按照提示来一步一步进行就可以了.

如果下次你在远程仓库修改了文件,那么在push之前你就需要先pull.

## ssh连接和https连接.
### ssh 连接和https连接的区别.
使用https连接,每次都要输入用户名和密码,而且那个用户名和密码好像有点BUG,都得输入两次才能对.很离谱

  第一次使用Git时候,需要配置好自己的用户名和邮箱,这是在每一次提交的时候都要使用的信息.
  ```shell
  # github或者gitlab用到的用户名和邮箱
  $ git config --global user.name "John Doe"
  $ git config --global user.email "johndoe@example.com"

  # 查看基本配置
  git config --list
  ```


### 如何配置ssh连接github 账户

```shell
# 生成秘钥
ssh-keygen -t rsa -C "johndoe@example.com"  # ~/.ssh目录下面会有id_rsa和id_rsa.pub两个文件

cat id_rsa.pub  # 把这个里面的内容复制
```
  复制上面的内容之后，打开你的github，进入配置页：Settings – SSH and GPG keys，添加本地生成的ssh秘钥，选择New SSH key（这里已经配置了一个key，如果是未配置秘钥的用户，这里是空的），把复制的内容贴过来，然后保存：

  ```shell
  #测试是否配置成功sfd

  用ssh链接git：ssh -T git@github.com
  ```




[[Git的常规操作]]
