---
layout: post
title:  "한드림넷 기본설정"
categories: net
tags: 한드림,l2,net
author: hopeone
description: 기본설정
comments: true
---


###### 
##### NSH-2128 기본설정


```

SG2128GXP>conf
SG2128GXP>enable 
SG2128GXP#configure terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
SG2128GXP(config)#show conf
SG2128GXP(config)#show running-config 
!
service password-encryption
service password-security
!
username root password ********
!
ip domain-lookup
!
!
snmp-server disable
!
bridge 1 protocol rstp vlan-bridge
!
vlan database
 vlan range 106 bridge 1
!
bridge 1 rstp  priority 4096
!
mds enable ge1-22 detect
mds uplink ge23-24
mds syslog enable
!
maximum-paths 8
mls qos enable
login-fail auto-deny 5
!
lldp enable
lldp port both ge
lldp tlv dot3tlv power-via-mdi ge
!
interface ge1
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge2
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge3
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge4
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge5
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge6
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge7
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge8
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge9
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge10
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge11
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge12
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge13
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge14
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge15
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge16
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge17
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge18
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge19
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge20
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge21
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge22
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge23
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface ge24
 switchport mode trunk
 switchport mode trunk acceptable-frame-type all
 switchport trunk allowed vlan add 106
!
interface up1
!
interface up2
!
interface up3
!
interface up4
!
interface lo
 ip address 127.0.0.1/8
 ipv6 address ::1/128
!
interface vlan1.1
 ip address x.x.x.x/24
!
interface vlan1.106
 ip address x.x.x.x/24
!
timezone GMT+9
!
!
service dhcp
no service sshd
service telnetd
line con 0
 login local
line vty 0 5
 login local
!
end

SG2128GXP(config)#

```

 
