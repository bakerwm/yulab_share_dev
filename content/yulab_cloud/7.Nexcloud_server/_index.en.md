---
title: "7.Yulab Cloud服务器设置"
draft: true
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["Nextcloud", "server"]
weight: 71
---

{{< notice note >}}
`NextCloud`是为小规模团队文件共享而创建的私有云。内置了文件管理、图片相册、日历联系人丰富的应用。
{{</ notice >}}

<!--more-->

管理员账号 `ncadmin`


## 7.1 用户管理

### 7.1.1 增加\删除用户

使用管理员账号登录网页，`设置->用户` 进行相关操作。

### 7.1.2 禁用\开启 用户

命令行操作方式：

```bash
$ sudo -u www-data php occ user:disable <username>
$ sudo -u www-data php occ user:enable <username>
```

### 7.1.3 找回管理员密码

```bash
$ sudo -u www-data php /var/www/nextcloud/occ user:resetpassword admin
```

### 7.1.4 恢复被误删的文件

```
$ 
```

### 7.1.5 备份和恢复

+ Backup and Recover

data files, MySQL, configuration files

+ 备份数据文件

```bash
$ rsync -Aavx nextcloud/ nextcloud-dirbkp_`date +"%Y%m%d"`/
```

+ 备份数据库：

```bash
$ mysqldump --single-transaction -h [server] -u [username] -p[password] [db_name] > nextcloud-sqlbkp_`date +"%Y%m%d"`.bak

```

+ 恢复数据文件夹

```
$ rsync -Aax nextcloud-dirbkp/ nextcloud/
```

+ 恢复数据库

```bash
# 清除现有的数据库
$ mysql -h [server] -u [username] -p[password] -e "DROP DATABASE nextcloud"
$ mysql -h [server] -u [username] -p[password] -e "CREATE DATABASE nextcloud"

# 恢复备份数据库
$ mysql -h [server] -u [username] -p[password] [db_name] < nextcloud-sqlbkp.bak
```


测试环境：`Ubuntu 18.04 LTS`

## 7.2 安装Nextcloud server

### 7.2.1 LAMP + NextCloud (推荐）

+ 安装 LAMP

`NextCloud`需要使用`Apache2`的web服务和`MySQL|MariaDB`提供的数据库服务，以及已经`PHP`，因此需要先安装以下几个软件包。.

```bash
$ sudo apt-get install apache2 mariadb-server libapache2-mod-php7.2
$ sudo apt-get install php7.2-gd php7.2-json php7.2-mysql php7.2-curl php7.2-mbstring
$ sudo apt-get install php7.2-intl php-imagick php7.2-xml php7.2-zip
```

### 7.2.2 安装NextCloud Server

接下来安装 `NextCloud Server`，推荐从官方网站下载最新安装文件：`nextcloud-x.y.z.tar.bz2`    

+ 访问官网 [https://nextcloud.com](https://nextcloud.com)，指定 NextCloud Server, 下载 `*.bz2`文件。

(stable version 14.0.4) 

```
1.  Download the  [.tar.bz2](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.tar.bz2)  or  [.zip](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.zip)  archive.
2.  Check package integrity using MD5 ([.tar.bz2](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.tar.bz2.md5)  /  [.zip](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.zip.md5)) or SHA256 ([.tar.bz2](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.tar.bz2.sha256)  /  [.zip](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.zip.sha256))
3.  Verify the authenticity via PGP ([.tar.bz2](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.tar.bz2.asc) /[.zip](https://download.nextcloud.com/server/releases/nextcloud-14.0.4.zip.asc)). The Nextcloud GPG key  [is here](https://nextcloud.com/nextcloud.asc).

```

从官网下载 `nextcloud-x.y.z.tar.bz2`  
`Download Nextcloud Server > Download > Archive file for server owners `

解压并安装：

```bash
$ tar -jxf nextcloud-x.y.z.tar.bz2
$ sudo cp -r nextcloud /var/www/
```

### 7.2.3 配置LAMP

创建configure文档，`/etc/apache2/sites-available/nextcloud.conf` 
填入以下内容：

```bash
Alias /nextcloud "/var/www/nextcloud/"

<Directory /var/www/nextcloud/>
  Options +FollowSymlinks
  AllowOverride All

 <IfModule mod_dav.c>
  Dav off
 </IfModule>

 SetEnv HOME /var/www/nextcloud
 SetEnv HTTP_HOME /var/www/nextcloud

</Directory>
```

然后使应用这个配置文件生效

```bash
$ sudo a2ensite nextcloud.conf
```

还需要其他`mod`

```bash
$ sudo a2enmod rewrite
$ sudo a2enmod headers
$ sudo a2enmod env
$ sudo a2enmod dir
$ sudo a2enmod mime
```

重启`Apache`服务

```bash
$ sudo service apache2 restart
```

### 7.2.4 配置NextCloud Server

使用命令行安装的方法比较简单：

```bash
$ sudo chown -R www-data:www-data /var/www/nextcloud/ # 修改网站路径下的文件权限

$ cd /var/www/nextcloud/
$ sudo -u www-data php occ maintenance:install --database "mysql" --database-name "nextcloud"  --database-user "root" --database-pass "password" --admin-user "admin" --admin-pass "password"
```

通常到此为止，NextCloud服务已经正常开启。可以访问https://localhost/nextcloud进行访问和更多设置。

### 7.2.5 设置 trusted domain

在 `/var/www/nextcloud/config/config.php`中添加当前服务器的ip地址：

```bash
'trusted_domains' =>
  array (
    0 => 'localhost',
    1 => '192.168.206.1',
  ),
```

### 7.2.6 转移 data 目录

策略：在指定目录创建 `data`目录后，在`/var/www/nextcloud/`目录下创建软连接

首先在 `/etc/apache2/sites-available/nextcloud.conf` 中增加如下：

```bash
<Directory /path/to/nextcloud/> 
        Options +FollowSymlinks 
        ... 
</Directory>
```

接着创建新的 data 目录：

```bash
$ sudo -u www-data php /path/to/nextcloud/occ maintenance:mode --on
$ mkdir -p /new/path/to/data
$ cp -a /path/to/data/. /new/path/to/data
$ mv /path/to/data /path/to/dataBackup
$ ln -s /new/path/to/data /path/to/data
$ chown -d www-data:www-data /path/to/data # To set symlink ownership
$ chown -R www-data:www-data /new/path/to/data # To set actual data dir ownership
$ sudo -u www-data php /path/to/nextcloud/occ maintenance:mode --off
```
到此，已修改完成


### 7.2.7 备份

> **遇到的问题**
> 
> 在另一台电脑上转移网站主目录，会导致nextcloud服务不可用！

参考[官方文档](https://docs.nextcloud.com/server/stable/admin_manual/maintenance/backup.html) 和 [Carsten Rieger 的博客](https://www.c-rieger.de/nextcloud-backup-and-restore/)

数据备份涉及几种类型：

1. 网站主目录 `/var/www/nextcloud`    
2. 网站数据目录 `/var/www/nextcloud/data` 可能保存在其他路径    
3. 数据库 `nextcloud`    

命令行界面下的操作，需要先进入维护模式，禁止用户登录和同步。

+ 1. 打开维护模式  

```
cd /var/www/nextcloud
sudo -u www-data php occ maintenance:mode --on
```

+ 2. 备份主目录

```
rsync -Aavx /var/www/nextcloud/ /path-to-backup/nextcloud-dirbkp_`date +"%Y%m%d"`/  
```

+ 3. 备份数据库

```
mysqldump --single-transaction -h localhost -uroot -p nextcloud > nextcloud-sqlbkp_`date +"%Y%m%d"`.bak
```

+ 4. 关闭维护模式

```
sudo -u www-data php occ maintenance:mode --off
```

### 7.2.8 恢复

同样需要对三种数据进行恢复

1. 打开维护模式 

```bash
$ sudo -u www-data php occ maintenance:mode --on
```

2. 停止网络服务

```bash
$ sudo service apache2 stop
```

3. 删除旧目录

```bash 
$ sudo rm -r /var/www/nextcloud/
```

4. 创建新目录

```bash 
$ sudo mkdir -p /var/www/nextcloud
rsync -Aax /path-to-backup/nextcloud-dirbkp/ /var/www/nextcloud/ 
```

5. 修改权限

```bash 
$ sudo chwon -R www-data:www-data /var/www/nextcloud
```

6. 恢复数据库 

操作步骤是，先删除旧的数据库，创建一个空的同名数据库，再恢复

```bash 
$ mysql -h localhost -uroot -p -e "DROP DATABASE nextcloud"
$ mysql -h localhost -uroot -p -e "CREATE DATABASE nextcloud  CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci"
```

7. 授权  (不确定是否必须要做！）

```bash 
$ mysql -hlocalhost -uroot -p -e "GRANT ALL PRIVILEDGES on nextcloud.* to nextcloud@localhost"
```

8. 恢复数据库

```bash 
$ mysql -h localhost -uroot -p nextcloud < /path-to-backup/nextcloud-sqlbkp.bak
```

9. 重启网络服务

```bash 
$ sudo service apache2 start
``` 

10. Fingerprint

```bash 
$ sudo -u www-data php occ maintenance:data-fingerprint
```

11. 关闭维护模式

```bash 
$ sudo -u www-data php occ maintenance:mode --off
```


**Debug**

遇到mysql登录的问题，会导致删除创建账号不成功


## 参考资料  相关链接：  

[Install on Linux](https://docs.nextcloud.com/server/14/admin_manual/installation/source_installation.html#pretty-urls-label)

[命令行安装NextCloud](https://docs.nextcloud.com/server/14/admin_manual/installation/command_line_installation.html)



此外，针对Ubuntu用户，还可尝试`snap`一步法安装，我还没有测试过：
```
$ sudo snap install nextcloud
```

#### FAQ

更新 Mariadb `10.1` to `10.3`

+ step1: 添加Mariadb repository

```bash
$ sudo apt update
$ sudo apt-get install software-properties-common
$ sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8`

`sudo sh -c "echo 'deb https://mirrors.evowise.com/mariadb/repo/10.3/ubuntu '$(lsb_release -cs)' main' > /etc/apt/sources.list.d/MariaDB103.list"`

+ step2: Install the latest Mariadb 

```
sudo apt-get update
sudo apt-get install mariadb-server mariadb-client
```
配置Mariadb
```
mysql_secure_installation
Follow this guide below in answering the questions:

-   Enter current password for root (enter for none):  **Enter current password****.**
-   Change root password?  **N**
-   Remove anonymous users?  **Y**
-   Disallow root login remotely? **Y**
-   Remove test database and access to it?  **Y**
-   Reload privilege tables now?  **Y**
mysql -V
mysql Ver 15.1 Distrib 10.3.11-MariaDB, for debian-linux-gnu (i686) using readline 5.2

```






