---
layouts: post
titile: "常用git指令"
description: "收录日常工作中常用到的git指令"
date: 2019-12-01
img: github.png
tags: ["git", "git command", "notes"]
---


# 常用git指令

1. 显示commit日志.
    ***git log --oneline --abbrev-commit --all --graph***

2. Commands that affect local branch references include ***commit*** ***merge*** ***rebase*** ***reset***.

3. Commands that affect remote branch references include ***fetch*** ***push***.

4. ***pull*** command is special case, it combines ***fetch*** and either ***merge*** or ***rebase***.

5. 一个小的修改不想增加新的commit，可以使用 ***git commit --amend*** .

6. ***git gc*** 将遍历所有的branch和tag，删除掉不能达到的commit.

7. ***git config --get name*** 显示配置信息.

8. ***git branch --all*** 显示本地分支和远端分支。

9. ***git remote*** 列出所有的远程主机名.

10. ***git remote show 'name'*** 显示'name'主机的详细信息.

11. ***git fetch <远程主机名> <分支名>*** 从远端分支取到最新的代码.

12. ***git pull <远程主机名> <远程分支名>:<本地分支名>*** 从远端分支拉取最新的代码，并且合并到本地的分支.git pull相当于git fetch和git merge的组合.但是建议时候后者，git的过程中最好时有清晰的流程，减少出错.

13. ***git checkout -b newbranch*** 以当前分支建立新的分支.

14. ***git reset --hard*** 放弃本地代码的修改，回退到上一个版本.

15. ***git push <远程主机名> <本地分支名>:<远程分支名>*** 其中 ***git pull*** 指令和 ***git push*** 指令都可以统一为
***<来源地>:<目的地>***.

16. ***git push*** 指令中的远程分支可以省略，会默认上传到远程和该分支有追踪关系的分支上去.比如
***git push origin master*** 会将本地的master分支上传到远端的关联分支上去.如果远端的分支不存在，则创建同名分支。

17. ***git push origin :test*** 表示删除远端分支.等同于 ***git push origin --delete test***.

18. 如果当前分支和远端分支存在追踪关系，那么本地分支和远端分支都可以省略. ***git push origin***.

19. 如果当前分支只有一个追踪分支，那么主机名可以省略. ***git push***.

20. 当使用 ***git push*** 去推送分支到远端的时候，在git 2.0之后采用 ‘simple’ 方法，就是只推送当前的分支，另外一种推送的方法叫做 ‘matching’,会将本地所有有关联关系的分支推送到默认的远端主机上去.可以通过 ***git config --global push.default matching*** 指令来设置.

21.  
```
git remote -v
```
显示当前远程分支的详细信息。
