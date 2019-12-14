---
layouts: post
title: "常用git指令"
description: "收录日常工作中常用到的git指令"
date: 2019-12-01
img: github.png
tags: ["git", "git command", "notes", "tech"]
---

# 显示commit日志.
```
git log --oneline --abbrev-commit --all --graph
```

# 将新的修改添加到已经存在的commit.
```
git commit --amend 
```

# 遍历所有的branch和tag，删除掉不能到达的commit.
```
git gc
```

# 查看本地和远端的所有分支
```
git branch --all
```

# 查看所有远程仓库
```
git remote -v
```
{{% admonition example %}}
-v means verbose(详细的）
{{% /admonition %}}

# 查看远程主机的详细信息
```
git remote show 'name'
```
# 从远程主机拉取
```
git fetch
```
{{% admonition example %}}
拉取所有分支
{{% /admonition %}}

```
git fetch <远程主机名> <分支名>
```
{{% admonition example %}}
拉取指定分支代码
{{% /admonition %}}

# 拉取分支并且合并
```
git pull <远程主机名> <远程分支名>:<本地分支名>
```
{{% admonition example %}}
git pull = git fetch + git merge.但是建议git fetch + git merge，git的过程更加清晰。
{{% /admonition %}}

# 推送修改到远端
```
git push <远程主机名> <本地分支名>:<远程分支名>
```
{{% admonition example %}}
git push 和git pull 格式能被统一为 git push/pull <远程主机名> <源地址>:<目标地址>
{{% /admonition %}}

```
git push origin master。
```
{{% admonition example %}}
会将本地的master分支上传到远端的关联分支上去.如果远端的分支不存在，则创建同名分支
{{% /admonition %}}

```
git push
```
{{% admonition example %}}
如果本地分支只有一个远程主机，且待提交分支与远端分支有连接关系可以直接使用。
{{% /admonition %}}
{{% admonition type="note" title="tips" details="true" %}}
git 2.0之后有两种推送分支的方式：simple 和matching.
simple : 只推送当前分支
matching : 推送所有有关联的分支
默认采用simple的方式进行推送，可以通过<em><b> git config --global push.default matching </b></em>来设置成matching模式
{{% /admonition %}}


# 创建新分支
```
git checkout -b newbranch
```
{{% admonition example %}}
从当前分支创建新的分支,并切换到新分支
{{% /admonition %}}

# 删除远端分支
```
git push origin :test

git push origin --delete test
```
{{% admonition example %}}
两条指令具有相同的作用，推荐使用后者，语意更加明确
{{% /admonition %}}

# 删除本地分支
```
git branch -d test
```

# 版本回退
```
git reset --soft HEAD~
```
{{% admonition example %}}
只修改HEAD. index(暂存区)和working tree(工作区）不变
{{% /admonition %}}

```
git reset --mixed HEAD~
```
{{% admonition example %}}
修改HEAD和index, working tree不变
{{% /admonition %}}

```
git reset --hard HEAD~
```
{{% admonition example %}}
HEAD, index, working tree 全部修改
{{% /admonition %}}
