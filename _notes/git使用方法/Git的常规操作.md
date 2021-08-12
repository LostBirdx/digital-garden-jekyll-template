---
title: "Git的常规操作"
---

## Git的常规操作

```shell
# 克隆项目下来
git clone git@github.com:zhongqiangwu960812/AI-RecommenderSystem.git

# 如果新改了某个文件，需要同步到远程

# 如果是新增了某个文件，可以直接
git add 文件名    
git status  # 可以查看修改情况
git commit -m '新加文件'     # 提交说明
git push    # 提交  

# 这样，就搞定了

# 如果是删除了某个或者修改了很多地方等，可以
git add .
git commit -m 'update many'
git push

#  如果是从远程仓库改了文件，需要先拉到本地，让本地和远程保持一致之后再push
git pull
```