---
title: "5. 客户端使用指南"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["Nextcloud", "manual"]
weight: 51
---


{{< notice tip >}}
保持 `Nextcloud` 客户端运行，开机启动    
{{</ notice >}}

## 5.1 编辑文件

+ 在文件浏览器（打开我的电脑，或者任意一个文件夹）窗口左侧，有一个 `yulab_cloud` ，点击该文件夹即可进入`Yulab Share`。

+ 进到文件夹 `D:\yulab_cloud`，也是同样有效

在该文件夹内，可以进行 `新建文件`、`新建文件夹`、`编辑文件`等操作。


## 5.2 删除文件

所有用户都没有 `删除` 权限，如遇到意外操作，需要删除文件时，请将文件的路径，发送给管理员 wangming@ibp.ac.cn 或 微信，如下格式：

```
[yulab_cloud: 删除文件]
1. yulab_share\test.txt    
2. yulab_share\group_meeting\20200808\abc.pptx
```

## 5.3 同步

客户端能够**自动**同步文件

`Nextcloud`客户端运行状态下，`D:\yulab_cloud`文件夹内新增、修改的文件，都会随时同步到服务器。

如果是长时间未运行客户端，选择手动同步。


<figure>
  <img src="nextcloud-sync-01.png" alt="Nextcloud-sync" width="100%" height="300">
</figure>


## 5.4 同步失败

遇到同步失败，手动强制同步也失败，并且出现过多报错的情况，请回到 **安装和设置**，重新设置客户端。


