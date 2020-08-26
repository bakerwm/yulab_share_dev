---
title: "6.网站导航"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["Nextcloud", "manual"]
weight: 61
---

{{< notice tip >}}
`Yulab Cloud` 网站主要包含两个部分：`Yulab_share`, `HiSeq_report`
{{</ notice >}}

## 6.1 Yulab_share

该文件夹内主要保存实验室日常文件，包括`组会报告`、`质粒载体`、`引物`、`文献`等信息

### 6.1.1 Archive

归档内容，例如，俞老师要求大家存档的引物序列、质粒等

```
Archive
+--- Cell_lines  # 课题组公共细胞系
|
+--- Flystock    # 共同果蝇stocks
|
+--- Linux_learning # 生物信息学相关资料
|
+--- Primers     # 引物序列
|
+--- Proteins    # 纯化蛋白清单
|
+--- Protocol    # 常用的protocol
|
+--- Yulab_quip_materials # 课题组试剂耗材清单
```

### 6.1.2 Lab_meeting

实验室组会PPT，文件命名：`20181024-lab-meeting-miaona.pptx`

+ 每次组会，由第一个上传文件的人创建一个新的文件夹：`20200808_lab_meetign.lww.lxh.mn`    

+ 每个人的PPT文件命名方式为：`20200808_lab_meeting.lww.pptx`

{{< notice note >}}
文件名称内，请用**下划线**代替**空格**
{{</ notice >}}

### 6.1.3 Journal_club

实验室Journal club的 PPT 和 文献

+ 创建一个文件夹，例如：`20181024-journal_club-gridseq-ljl`

+ 保存 PPT, 文献，阅读笔记等：

### 6.1.4 Vectors

实验室已知载体序列，按照 `载体名称 + 基因名称 + 其他说明`的方式命名    
目前，这个文件夹的信息太混乱，命名方式没有规律，难以认识包含什么内容。

{{< notice tip >}}
请大家自愿修改，保存到最上层目录`Vectors_new`
{{</ notice >}}

### 6.1.5 Papers

参考文献，以及俞老师每次在微信里群发的文献；
请使用合适的命名：`2018-Cell-piRNA-CLASH.pdf`

### 6.1.6 其他

+ `Photos` 保存实验室日常、聚会、聚餐等照片，按年份归档，文件名称包含：日期+简要说明 `20181001-做实验的叮当猫-LX.jpg`    

+ `Vectors_new` 保存日常使用的载体信息，格式为SnapGene导出的 `*.dna`文件  



## 6.2 HiSeq_reports

高通量测序相关的文件，包括：`样品信息单`，`分析结果`，`高通量测序基础信息`等，（该文件夹只有部分人可访问）


### 6.2.1 HiSeq_sample_sheet 

样品信息单模板，送样信息单模板等

存放在相应编号的文件夹内，例如 **YY38**

参考 **HiSeq**模块，学习如何填写样本信息单

### 6.2.2 HiSeq_results

分析结果，通常有两种类型的文件夹

+ a. YY36_20190425

这种以 `YY`开头的文件夹，对每条Lane测序结果进行评估，包括数据产量、数据质量等

+ b. 20190425_LXH_smRNA

这种以 `20190425`日期开头的文件夹，包含每个具体项目的分析结果

### 6.2.3 Library_structures

存放课题组常用高通量测序的文库信息，例如：`NSR`, `GoldCLIP`, `ATAC-seq`等等





