---
title: "1.Nextcloud backup/maintaince"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["Nextcloud", "manual"]
weight: 1
---



## NextCloud 备份/恢复

### 1. 备份

+ 1.1 打开 maintenance mode

```
$ sudo -u www-data php occ maintenance:mode --on
```

+ 1.2 备份文件夹

```
$ rsync -avx nextcloud/ nextcloud-dirbkp/
```

+ 1.3 备份database

```
$ mysqldump --single-transaction -h [server] -u [username] -p [password] [db_name] > nextcloud-sqkbkp.bak
```


### 2. 恢复

恢复的关键是：`文件夹`和`database`两者必须一致

+ 2.1 恢复文件夹

```
$ rsync -Aax nextcloud_bak/ nextcloud/
```

+ 2.2 删除现有的 database

**关键** 先删除已有的database，再恢复

```
$ mysql -h [server] -u [username] -p [password] -e "DROP DATABASE nextcloud"
$ mysql -h [server] -u [username] -p [password] -e "CREATE DATABASE nextcloud"
```

+ 2.3 恢复

```
$ mysql -h [server] -u [username] -p [password] [db_name] <nextcloud-sqlbak.bak
```



## MySQL常用命令

+ 1. 基本命令

```
create database name; 创建数据库

use databasename; 选择数据库

drop database name 直接删除数据库，不提醒

show tables; 显示表

describe tablename; 表的详细描述

select 中加上distinct去除重复字段

mysqladmin drop databasename 删除数据库前，有提示。

select version(),current_date; 显示当前mysql版本和当前日期
``` 

+ 2. 备份恢复

```
$ mysqldump -h [host] -u [user] -p [password] [dbname] > dbname.bak

$ mysqldump -h [host] -u [user] -p [password] [dbname] < dbname.bak

```

+ 3. Change password for root on mysql

```
# 1. add the following lines to /etc/mysql/my.cnf

[mysql]
skip-grant-tables

# 2. restart mysql

$ sudo service mysql restart

# 3. login mysql, change password

$ mysql -uroot
mysql> use mysql;
mysql> update user set authentication_string=password('new_password') where user='root';
mysql> quit;

# 4. comment the skip-grant-tables line

[mysql]
# skip-grant-tables

# 5. restart mysql

$ sudo service mysql restart

```



### FAQ

+ 1. ERROR 1054 (42S22): Unknown column 'password' in 'field list'

```
mysql> update mysql.user set password=password('password') where user='root';
mysql> ERROR 1054 (42S22): Unknown column 'password' in 'field list'
```

错误原因：mysql数据库下已经没有password这个字段了，password字段改成了authentication_string。

正确的命令：

```
mysql> update mysql.user set authentication_string=PASSWORD('password') where User='root';
```




