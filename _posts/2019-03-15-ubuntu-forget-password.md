---
layout: post
title: ubuntu 忘记密码重置方法
---

## 一.先输入如下指令
```
sudo cat /etc/mysql/debian.cnf
```

## 二.接着再输入
```
mysql -u debian-sys-maint -p
```
> 密码输入是输入第一条指令获得的信息中的 password = XXXXXXXXXX 而来
  
## 三.修改密码
```mysql
use mysql;
update mysql.user set authentication_string=password('root') where user='root' and Host ='localhost';
update user set plugin="mysql_native_password"; 
flush privileges;
```

## 四.重启 mysql
> sudo service mysql restart

## ok~~
