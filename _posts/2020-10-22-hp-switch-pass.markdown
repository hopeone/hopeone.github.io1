---
layout: post
title:  "Hp-switch-Password"
categories: net
tags: hp,password,
author: hopeone
description: 기본설정 
comments: true
---

###### . 로컬 사용자 계정 생성 및 서비스 타입 및 레벨 설정 (telnet)



```
<HP> system-view

[HP] telnet server enable

[HP] local-user admin

[HP] authorization-attribute level 3

[HP] password simple/cipher xxxxx

[HP] service-type ssh telnet terminal
```

 