---
layout: post
title:  "Vlan 기본설정"
categories: net
tags: vlan,기본
author: hopeone
description: 기본설정
---


###### 
##### vlan 기본설정


```

1. 3com 백본 7605
기본계정 User=admin, Password= 없음
 sys
 vlan 10x
 interface Vlan-interface10x
 ip address x.x.x.x 255.255.255.0
 interface GigabitEthernet1/0/1
   port link-type hybrid
   port hybrid vlan 10x tagged
 save 저장

2. 블랙8810 백본
기본계정 User=admin, Password= 없음
create vlan "voice"
configure vlan voice tag 10x
configure vlan voice add ports 1:1-4, 2:1, 2:3-4, 2:6-48, 3:7-21, 3:25-48, 10:1-48 tagged  
configure vlan voice ipaddress x.x.x.x 255.255.255.0
enable ipforwarding vlan voice
enable ipforwarding vlan Default -> Default에 대해 ipforwarding이 안되어 있을 경우
save conf 저장

3. 다산PoE V2324G / 삼성PoE스위치
기본계정 User=admin, Password=admin
conf 
VLAN database
  VLAN 10x name voice media ethernet state active
interface ethernet 1/1-24
  switchport allowed vlan add 10x tagged
copy r s 저장

4. ALCATEL장비
기본계정 User=admin    Password=switch
Web으로 접속설정
-> aaa authentication http local

5. Entrasys 장비
기본계정 User=admin, Password= 없음
set vlan create 10x
set vlan egress 106 ge.1.1-24;ge.2.1-24;ge.3.1-24;lag.0.1-6 tagged
save 저장

6. xDSL집합장비 V5824
기본계정 User=root, Password=vertex25
conf t
bridge
set vlan create brvoice 10x
set bridge brvoice flood enable
set bridge brvoice broadcast enable
set vlan add brvoice ethernet 1 tagged
set vlan add brvoice dsl 1.1-24.1,1.2-24.2,1.3-24.3,1.4-24.4 tagged
copy r s 저장

7. 익스트림 450e
기본계정 User=admin, Password= 없음
create vlan voice
configure vlan voice tag 10x
configure vlan voice add ports 1-24 tagged
enable ipforwarding vlan voice
enable ipforwarding vlan Default -> Default에 대해 ipforwarding이 안되어 있을 경우

8, nst 2128

interface gi1
 ip acl ssh
 switchport mode hybrid
 switchport hybrid allowed vlan add 101-102,116-117,137 tagged
 no spanning-tree
!


```

 
