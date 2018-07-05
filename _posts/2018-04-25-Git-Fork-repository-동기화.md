---
title: Github에서 fork한 repository 최신으로 동기화하기
description: 
categories: 
tags: git
---

![Github](http://blog.weirdx.io/wp-content/uploads/2017/10/github.png)

## 원본 repository를 remote repository 로 추가

```shell
$ git remote -v
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
```

동기화해오고 싶은 원본 repository를 upstream 이라는 이름으로 추가
```shell
$ git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
```


upstream repository 가 제대로 추가 되었는지 확인한다.
```shell
$ git remote -v
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
```

## upstream repository로부터 최신 업데이트를 가져오기

Git 의 fetch 명령어를 통해 upstream repository 의 내용을 불러온다.
```shell
$ git fetch upstream
remote: Counting objects: 75, done.
remote: Compressing objects: 100% (53/53), done.
remote: Total 62 (delta 27), reused 44 (delta 9)
Unpacking objects: 100% (62/62), done.
From https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY
 * [new branch]      master     -> upstream/master
```

upstream repository 의 master branch (혹은 원하는 branch) 로부터 나의 local master branch 로 merge 한다.
```shell
$ git checkout master
Switched to branch 'master'

$ git merge upstream/master
Updating a422352..5fdff0f
Fast-forward
 README                    |    9 -------
 README.md                 |    7 ++++++
 2 files changed, 7 insertions(+), 9 deletions(-)
 delete mode 100644 README
 create mode 100644 README.md
```

push 를 통해 remote repository 에도 적용시켜주면 끝난다.
```shell
$ git push origin master
```

## 정리

1. `git remote add upstream 깃허브주소`
2. `git remote -v` 확인
3. `git fetch upstream`
4. `git checkout master`
5. `git merge upstream/master`
6. `git push origin master`