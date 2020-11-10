---
layout: post
title:  "Hp스위치 웹 접속"
categories: net
tags: hp,l2,web,hpe,switch
author: hopeone
description: 기본설정 
comments: true
---

###### . 로컬 사용자 계정 생성 및 서비스 타입 및 레벨 설정 (telnet)

#### ==1 .Web 접속 활성화==
```
[hp]ip http enable 


```

```
[HP]local-user webuser  

New local user added.

[HP-user-webuser]password simple password 

[HP-user-webuser]authorization-attribute level 3    .

[HP-user-webuser]service-type web
```


