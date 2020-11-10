---
layout: post
title:  "우분투 설치후"
categories: net
tags: 우분투,
author: hopeone
description: 기본설정
comments: true
---
# 우분투(20.) 설치후 세팅순서


## 1. root 계정 활성화

```
 sudo passwd root
New password: 
Retype new password: 
passwd: password updated successfully

```


## 2. 미러변경

``` 
`sudo vi /etc/apt/sources.list`
```

확인해보면 기본적으로

http://kr.archive.ubuntu.com/


ubuntu/

위 주소로 되어있다

vi 에서 치환으로 

```
%s/kr.archive.ubuntu.com/ftp.daumkakao.com
```

변경
 

## 3. Apache 설치

### Step 1 : 
```
sudo apt install -y apache2 apache2-utils
```

```
systemctl status apache2$$$
```




아파치 서비스 시작

``` 
sudo systemctl start apache2 
```

아파치 기본 페이지 나오면 아파치 설치 완료


html 디렉토리 소유권 변경

```
sudo chown www-data:www-data /var/www/html/ -R
```


Step 3 : Mysql 설치

```
sudo apt install mariadb-server mariadb-client
```

```
systemctl status mariadb
```

설치확인
```
systemctl status mariadb
● mariadb.service - MariaDB 10.3.22 database server
     Loaded: loaded (/lib/systemd/system/mariadb.service; enabled; vendor preset: enabl>
     Active: active (running) since Thu 2020-05-14 00:20:21 UTC; 8s ago
       Docs: man:mysqld(8)
             https://mariadb.com/kb/en/library/systemd/
   Main PID: 6769 (mysqld)
     Status: "Taking your SQL requests now..."
      Tasks: 31 (limit: 9359)
     Memory: 67.4M
     CGroup: /system.slice/mariadb.service
             └─6769 /usr/sbin/mysqld
```

mysql 시작

```
sudo systemctl start mariadb
```

자동시작

```
sudo systemctl enable mariadb
```

인스톨 스크립트 실행

```
sudo mysql_secure_installation
```

```
sudo mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] y
New password: 
Re-enter new password: 
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] 
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] 
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] 
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] 
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!


```


[TOC]





