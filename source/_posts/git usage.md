---
title: git 用法学习
date: 2019-12-5 03:54:45
cover: ../img/image2.jpg
---

# git常用命令
## 初始化本地仓库
    git init 初始化一个仓库
    git add <filename>添加一个文件
    git commit -m "改动说明" 将改动提交
    可以一次改动add多个文件在commit
    git status 查看当前的仓库状态
    git diff <filename>查看不同

## 版本控制
    git log查看提交历史
    git reflog查看命令历史
    git reset --hard commit_id
    HEAD 指向当前版本，HEAD^前一个版本HEAD~100前一百个版本
    git checkout --filename 删除当前工作区的修改
    git reset HEAD filename撤销暂存区的修改回到工作区
## 远端仓库
    git remote add origin ssh地址 关联一个远端仓库
    git push -u origin master第一次推送master分支的所有内容
    git push origin master 推送最新的修改
    git clone ssh地址从远端库克隆it
    git remote -v 查看远程库信息
    git pull 抓取远程的新提交
    git checkout -b branch-name origin/branch-name在本地创建与远程对应的分支
    git branch --set-upstream branch-name origin/branch-name 建立本地与远程分支联系
## 分支管理
    git branch 查看分支
    git branch filename创建分支
    git checkout filename 切换分支
    git checkout -b filename切换加创建分支
    git merge filename 合并到当前分支
    git branch -d filename 删除分支
    git merge --no-ff -m "statement" filename 禁用fastforword合并
    git stash 将工作区内容暂时保存
    git stash list 查看stash列表
    git stash apply listname 将listname对应的缓存放到工作区
    git stash drop 删除list中对应的记录
    git stash pop 恢复的同时把list对应删除
## 标签
    git tag tagname 创建标签 -m ""可以加说明 -s私密签名
    git tag 查看标签列表
    git tag tagname commit_id 给对应的历史版本打标签
    git show tagname 查看
    git tag -d tagname 删除一个本地标签
    git push origin :refs/tegs/tagname 删除远程标签
    git push origin tagname 推送一个本地标签
    git push origin --tags推送所有本地标签
