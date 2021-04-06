---
title: Git 여러 계정 설정(git config)
description: 
categories: 
tags: git
---

![Github](http://blog.weirdx.io/wp-content/uploads/2017/10/github.png)

## 계정 확인
`git config user.email`

## 글로벌 계정 설정
`git config --global user.name "user"`
`git config --global user.email "user@email.com"`

## 저장소별(로컬) 계정 설정

저장소마다 다른 계정으로 로그인하고 싶을 때

`git config --local user.name "user"`
`git config --local user.email "user@email.com"`