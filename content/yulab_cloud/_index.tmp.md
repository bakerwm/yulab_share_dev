---
date: "2019-12-29T11:02:05+06:00"
draft: false
keywords:
- "cloud" 
- "NextCloud" 
lastmod: "2020-01-05T10:42:26+06:00"
title: Installation
weight: 1
---

> 以下访问需要连接到 实验室的网络

`Yulab Cloud`是俞洋组的数据中心，保存实验室日常数据；可通过以下两种途径访问：

  - 1 网页直接访问    
  
  - 2 客户端访问

## 1 网页直接访问

### 1.1 在浏览器输入以下网址

[`http://192.168.206.171/yulab_cloud`](http://192.168.206.171/yulab_cloud)

随后按照网页上的提示进行操作。

## 2 客户端访问

### 2.1 下载客户端

客户端名称是 `NextCloud` ，官网链接[Nextcloud官网](https://nextcloud.com/install/#install-clients)，软件下载地址如下：

+ Windows 10: [extcloud-3.0.0-setup.exe](https://download.nextcloud.com/desktop/releases/Windows/latest)

+ macOS: [Nextcloud-3.0.0.pkg](https://download.nextcloud.com/desktop/releases/Mac/Installer/latest)


### 2.2 安装

按照 **默认** 方式安装

### 2.3 设置Nextcloud

双击桌面 `Nextcloud` 图标，启动应用程序，默认点击 **下一步**

#### 2.3.1 填入**服务器地址**

见到如下页面是，填入服务器地址：**http://192.168.206.171/yulab_cloud**

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-01.png" alt="Yulab share configure 01" width="600" height="300">
</figure>

#### 2.3.2  选择**登录**

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-02.png" alt="Yulab share configure 01" width="280" height="210">
</figure>

#### 2.3.3 填入用户名，密码

> 参考第1节，申请账号。

输入用户名 和 密码 后，继续点击下一步。

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-03.png" alt="Yulab share configure 01" width="200" height="140">
</figure>

####  2.3.4 选择 "授权访问"

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-04.png" alt="Yulab share configure 01" width="200" height="140">
</figure>

#### 2.3.5 修改**上传文件上限**

+ 出现在下图界面时，更改 `询问确认`，若同步文件大于~~500M~~, 改为 `50M`    
+ 在电脑D盘新建一个文件夹： `yulab_cloud`    
+ 在`本地文件夹`右侧填入`D:\yulab_cloud`

> 如果电脑上已经存在 `D:\yulab_cloud` 文件夹，需要先将 旧的文件夹 重命名，或者删除旧的文件夹  
> 然后，重新创建一个空白的文件夹 `D:\yulab_cloud`

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-05.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

#### 2.3.6 确认同步

在同步过程中，会在客户端界面弹出“发现50M的文件需要同步，是否继续？”，选择 **确定**

随后，等待软件同步即可。（大约20分钟可以完成）


#### 2.3.7 同步完成

打开 Nextcloud软件，在软件的同步界面上，所有文件条目的左侧都是 绿色的对勾✅，表示已经完成同步。


### 2.4 使用Yulab Share

> 保持 `Nextcloud` 客户端运行的状态下，

在文件浏览器（打开我的电脑，或者任意一个文件夹）窗口左侧，有一个 `yulab_cloud` ，点击该文件夹即可进入`Yulab Share`。

在该文件夹内，可以进行 `新建文件`、`新建文件夹`、`打开文件并进行编辑`等操作。




## 3 去哪里找文件




<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/yulab_cloud-login-02.png" alt="Yulab share configure 02" width="600" height="450">
</figure>

还有基本使用介绍：

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/yulab_cloud-login-03.png" alt="Yulab share configure 03" width="600" height="450">
</figure>


## 管理文档

+ 1. 请在 `Yulab_Share`文件夹上传|下载文档    
+ 2. 文件尽量包含日期+标题+上传人（例如：`20181024-yulab_cloud_manual-wm.pdf`）    
+ 3. `Photos`    用来存放照片的（参加聚会了，出去开会了，谁又画了一只叮当猫了，等等，都往这里放吧；同样需要你修改好名字，例如：`20181001-做实验的机器猫-LX.jpg`)    
+ 4. `Vectors_new` 保存载体（SnapGene导出的文件.dna)

### Yulab_Share/Archive

```
Archive
+--- Cell_lines     # 课题组公共细胞系
|
+--- Flystock # 共同果蝇stocks
|
+--- HiSeq # 高通量测序相关信息
|
+--- Linux_learning # 生物信息学相关资料
|
+--- Primers # 引物序列
|
+--- Proteins # 纯化蛋白清单
|
+--- Protocol # 常用的protocol
|
+--- Yulab_quip_materials # 课题组试剂耗材清单
```


### Journal_club

每次上传一个文件夹，包含以下内容：

+ 参考文献，和相关的其他文献 （PDF)

+ 阅读报告 (PPT）

+ 阅读笔记 （Word, 这个可以有) 

**修改文件夹名称**， 例如：`20181024-journal_club-gridseq-mm`

### Lab_meeting

每次上传一个文件夹，包含以下内容：

+ 上传各自的 PPT，修改名称：`20181024-lab-meeting-mm.pptx`

+ 其他相关的文档或图片等。


### Vectors

按照 `载体名称 + 基因名称 + 其他说明`的方式进行命名。

当前文件夹下的文件太复杂，命名方式没有规律，难以认识包含什么内容。

**因此**，请同学们自发的来修改，保存到最上层的目录下`Vectors_new`


### Work_report


分享有些分析结果，工作报告等。

## 电脑客户端

既然称作`云`，怎么少得了客户端访问呢。

[官方下载地址](https://nextcloud.com/install/#install-clients)

+ 1. 填入服务器地址：http://192.168.206.171/yulab_cloud

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-01.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 2. 选择“登录”

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-02.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 3. 填写用户名 ：`yuftp` 和 密码 (咨询管理员）

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-03.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 4. 选择 "授权访问"

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-04.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 5. 更改 询问确认，若同步文件大于~~500M~~, 改为 50M

在电脑D盘新建一个文件夹： `yulab_cloud`

在本地文件夹右侧填入：`D:\yulab_cloud`

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-05.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

接下来正常使用就可以了。


## 手机客户端

从手机的应用市场搜索 "nextcloud" （例如，豌豆荚）并安装。

Enjoy.




