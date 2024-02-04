# study_note

## Flutter
### 自定义Plugin, Package
#### 导入既存的自定义包
##### git地址的方式导入

```
dependencies:
  medicine_record:
  git:
    url: https://git-codecommit.ap-northeast-1.amazonaws.com/v1/repos/medicine_record
    ref: feature/AN_OD-4593
```

#### 创建Plugin
1. 创建： `flutter create --template=plugin -i swift -a kotlin test_01_package`
2. 修改发布配置
3. 发布前检查  `flutter packages pub publish --dry-run`
4. 发布 `flutter packages pub publish`
5. LICENSE 证书问题  BSD 3-Clause

## Git
### 基本操作

1. git init 创建版本库

2. git add file1.text    添加文件到暂存区

3. git commit -m "change content" 将暂存区文件添加到当前分支

4. git push 推送到远程仓库

### 放弃更改

1. git checkout -- name.text 未add

2. git checkout .   未add

3. git reset HEAD readme.md add完成

4. git reset HEAD . add完成

### 其他操作

* git commit 或者 git commit -m "xxxxx"

* git add --all 添加所有修改文件到暂存区

* git log 打印日志

* git reflog    打印命令日志

* git reset --hard HEAD^ 回退到上一个版本

* git reset --hard 547b108 指向指定版本

* git checkout -b dev 创建dev分支，并指向dev分支

* git branch dev    创建dev分支

* git checkout dev  指向dev分支

* git checkout master   指向master

* git merge dev 将dev合并到当前分支

* git branch -d dev 删除dev分支

* git log --graph --pretty=oneline --abbrev-commit  查看分支情况

* git branch -r 查看所有远程分支

* git branch -a 查看所有分支包括本地分支

* git merge --no-ff -m "merge with no-ff" dev   "--no-ff"禁用Fast forward模式, 将dev合并到master，分别指向各自的分支

* git stash 暂存当前修改, 清空工作区，之后可以恢复

* git branch -D feature-vulcan 删除未合并的分支时，需要强制删除

* git push origin master    推送分支到远程仓库

* git push origin BranchName		推送本地分支到远程

* git log --graph --all --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative

### 标签

* git tag v1.0  打标签

* git tag   查看标签版本

* git tag v0.9 f52c633  给制定版本打标签

* git show v0.9 查看标签详情

* git tag -a v0.1 -m "version 0.1 released" 1094adb 注释    "-a"标签名, "-m"注释

* git tag -d v0.1   删除标签

* git push origin v1.0  推送标签到远程

* git push origin --tags    推送所有标签到远程

* git tag -d v0.9   先删除本地标签

* git push origin :refs/tags/v0.9   再删除远程标签

### 查看远程仓库

* git remote -v

* git remote

### bug分支

* git stash apply   恢复暂存，但不删除暂存区内容

* git stash pop     恢复暂存，删除暂存区内容

* git stash list    查看暂存区内容





### 回退版本

1. git reset --hard HEAD^ 回退到上一个版本

2. git reset --hard 547b108 指向指定版本

### 回退远程版本

1. git reset --hard HEAD^ 回退到上一个版本

2. git reset --hard 547b108 指向指定版本

3. git push --force / git push -f 强制推送到远程

### 合并commit

1. git rebase -i HEAD~2	/// 合并前两个commit

    git rebase -i 3a4226b // 3a4226b之前，不包括3a4226b

2. git push -f

### 删除commit

1. git rebase -i [commmit id]

2.drop

### 删除未跟踪的文件

git clean -f

### 拉取远程分支到本地。

git checkout -b BR_topic/1.1.0/VoiceImpliment origin/BR_topic/1.1.0/VoiceImpliment

### 将某个commit合并到当前分支
git cherry-pick 5d47ecb

### 将已经commit，返回工作区 git reset --soft HEAD^

### 修改commit 注释
git commit --amend

### 重置git账号密码
1. 路径
git config --show-origin --get credential.helper
2. 打开gitconfig 删除[credential]	helper = osxkeychain

### 本地仓库推送到远程

Git remote add origin https://~~
Git push -u origin master