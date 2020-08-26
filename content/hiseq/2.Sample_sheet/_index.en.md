---
title: "2. 填写样本信息单"
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
weight: 2
draft: false
# search related keywords
keywords: ["samplesheet", "HiSeq", "ATACseq", "RNAseq", "ChIPseq"]
---

{{< notice note >}}
需要准备两份表格：    
1 `样本信息单` 由课题组内归档，    
2 `送样清单` 发送给测序公司    

{{</ notice>}}


## 2.1 确认实验内容

关于样本设置、对照设置等，需要和 `@俞老师`讨论，并得到俞老师确认后方可进行下一步。

## 2.2 样本信息单

### 2.2.1 下载模板 

[样本信息单 模板](YY00_20200621_YY_RNAseq.xlsx)  

### 2.2.2 样本名称

样本名称的要求如下：

`{文库类型}_{基因}_{处理条件}_{来源}_{rep1}`

+ 一条Lane混合样品等名称**不可以重复**

+ 使用 `字母`, `数字`, `下划线`, `减号`   
  
+ 包含`文库类型`，例如`RNAseq`, `ATACseq`等    

+ `基因`该样品针对等基因名称，例如 `piwi`    

+ `处理条件` 例如 knock_down (KO), wildtype (WT)    

+ `来源` 样本来源，例如HEK293，Ovary， OSC等  

+ `rep1` 需要使用 rep1或者 r1 格式表示样品等重复

例如样品名称: `mRNAseq_Piwi-KD_embryo_rep1`


### 2.2.3 Barcode 和 P7-index

`Barcode`是指在插入序列两侧的指定长度序列，通常在GoldCLIP和smallRNAseq文库中使用；常用 

  - `P7_1A`... `P7_8B` 16个：   
  
  - `iCLIP1-16` 16个：

`P7-index`在所有Illumina文库中都会使用（除第1版GoldCLIP外）。

  - `TruSeq1-48`: 48   
  
  - `Next_Ad2.1-24`: 24


保证在样品中`Barcode` + `P7-index`没有重复。


{{< notice tip >}}
以上`2.2`, `2.3`, `2.4` 步骤，可以在[填写样本信息单](http://192.168.206.171:6611/tools/hiseq_sample/)网站的协助下完成。

{{</ notice >}}

### 2.2.4 表单其他信息

在表单`sample_sheet`，其他表格填写规则如下：  

  - Lib_number: 例如：`YY45`        
  - Lib_user: 以自己的**姓名首字母** + **两个数字**格式填写，例如 `LWW03`      
  
  以上信息，可以从 [HiSeq Summary](http://192.168.206.171:6611/tools/hiseq_summary/)中查询。
  
  - **Sample_name**, : 见上文 `2.2.2`     
  - RBP, 针对CLIP实验，需要填写具体的蛋白名称，其他实验填写`Null`    
  - Cell_line, 从下拉菜单中选择，列表中没有时，填写`Null`    
  - **Species**，从下拉菜单中选择，例如 `Human`   
  - **Spike-in**，从下拉菜单中选择，如果掺入了Spike-in样品，请**务必确认**    
  - **P7_index_id**，从下拉菜单中选择，**务必确认**，不能够有重复    
  - **Barcode_id**，同上   
  - **Seq_type**，通常有两个选项，`PE`， `SE`，如果不清楚怎么填，请在**Yulab_HiSeq微信群** 询问`@王明`    
  - Lib_type，这是指文库类型，如果不清楚，同上。    
  - **Reads, M**，这里对每个样品预期产出reads数量估计，Million数。

这一个表单`sample_sheet`的其他地方就不需要填写，也请不要修改。
  
### 2.2.5 实验设计

在`样本信息单`的`Design`表单内填写实验设计，包括以下内容：

  - Lane编号，是指当前文库的编号，**B1**中查询到的结果。      
  - 实验负责人，具体由谁负责的实验，填写全名        
  - 文库负责人，填写全名       
  - 样品数量，例如 `6`      
  - 样品来源，例如`Ovary`       
  - 样本类型，从列表中选择，例如`1.Transcriptome mRNA`    
  - 文库类型，从列表中选择，例如`2.small RNA library`    
  - 实验设计，填写实验组和对照组的样品名称    
  - 研究内容，分为两个部分，填写实验设计的基本内容，需要检测的对象，和 参考文献


## 2.3 送样清单    

`送样清单`是发送给测序公司的文件，包括样品文库类别、样品名称、数量、浓度、体积等；[这里是模板]()


在表单`文库信息单`中，填写以下几条  

  - **文库名**，填写当前编号（例如：YY47， YS05）
  - index序列，填写 "包lane, 无需拆分"     
  - **浓度 (ng/ul)**, 填写准确的浓度  
  - **体积**， 填写具体体积（ul）
  - **测序数据量**， 填写 `400`   
  - **数据量单位**，填写 `M reads`

+ 最后，将这个Excel文档命名为: `生物物理所俞洋组_YY47_20200310_送样信息单.xlsx`


## 2.4 核对信息

准备好上述两个表格 `样本信息单`, `送样清单`之后，上传至`Yulab Cloud`的相应目录，并在`Yulab HiSeq`微信群内@wangming，确认信息单内容



