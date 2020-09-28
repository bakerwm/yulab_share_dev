---
title: "4. 设置客户端"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["Nextcloud", "Settings"]
weight: 31
---


## 4.1 启动Nextcloud

双击桌面 `Nextcloud` 图标，启动应用程序，默认点击 **下一步**

## 4.2 填入**服务器地址**

见到如下页面，填入服务器地址：**http://192.168.206.171/yulab_cloud**

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-01.png" alt="Yulab share configure 01" width="600" height="300">
</figure>

## 4.3  选择**登录**

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-02.png" alt="Yulab share configure 01" width="280" height="210">
</figure>

## 4.4 填入用户名，密码

{{< notice tip >}}
参考第1节，申请账号。
{{</ notice >}}

输入用户名 和 密码 后，继续点击下一步。

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-03.png" alt="Yulab share configure 01" width="200" height="140">
</figure>

## 4.5 选择**授权访问**

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-04.png" alt="Yulab share configure 01" width="200" height="140">
</figure>

## 4.6 修改**上传文件上限**

+ 出现在下图界面时，更改 `询问确认`，若同步文件大于~~500M~~, 改为 `50M`    
+ 在电脑D盘新建一个文件夹： `yulab_cloud`    
+ 在`本地文件夹`右侧填入`D:\yulab_cloud`

{{< notice tip >}}
如果电脑上已经存在 `D:\yulab_cloud` 文件夹，需要先将 旧的文件夹 重命名，或者删除旧的文件夹      
然后，重新创建一个空白的文件夹 `D:\yulab_cloud`
{{</ notice >}}

<figure>
  <img src="http://159.226.118.232/upload/img/yulab_share_config/desktop-app-login-05.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

## 4.7 确认同步

在同步过程中，会在客户端界面弹出“发现50M的文件需要同步，是否继续？”，选择 **确定**

随后，等待软件同步即可。（大约20分钟可以完成）


### 4.3.7 同步完成

打开 Nextcloud软件，在软件的同步界面上，所有文件条目的左侧都是 绿色的对勾✅，表示已经完成同步。


