---
title: "1. FAQ"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["samplesheet", "HiSeq", "ATACseq", "RNAseq", "ChIPseq"]
weight: 1
---

{{< notice note >}}
  查阅HiSeq相关内容，需要Yulab Cloud账号有相应授权，如需帮助，请@管理员。
{{</ notice >}}


{{< notice tip >}}
  请加入`Yulab HiSeq` 微信群，接收相关updates。
{{</ notice >}}



{{< faq "1 Sample Sheet" >}}
**样本信息单**是保存课题组内构建HiSeq文库信息，由实验室内部存档。包括两个关键信息，`样本名称等`、`实验设计`。具体如何填写，请查阅下一节 **填写样本信息单**。

同时还需要准备一份 **送样清单**，这份文件发送给测序公司；具体细节，请查阅下一节 **填写样本信息单**。

{{</ faq >}}


{{< faq "2 Sequencing depth" >}}
+ 常用`Million (M)` 作为数据量单位 (Single-End, 指reads数量； Paired-end，表示 read-pair 数量)  

+ 常用测序规则是`PE150`，指双端测序150bp，即每`read-pair`包括300 bp。

+ 常用 `10X` 格式表示测序深度，是由测序数据 （`总测序数量` x `read长度`) / `物种基因组长度` 计算得来。例如，人基因组长度约为3Gbp (3000Mbp)，测序得到PE150数据30M，公式计算如下：`（30 M x 150 bp x 2) / 3000 Mbp = 3`, 测序深度为 `3X`。


根据实验室经验，推荐以下测序数据量：

| 序号  | 建库内容    | 数据量 M  | 参考文献   |
| ---- |:----------:|:--------:|:--------:|
| 1    | smRNAseq   | 10+       | ref-1    |
| 2    | mRNAseq    | 10+ (果蝇) 20+ (人、鼠) | ref-2 |
| 3    | CLIPseq    | 30+ (果蝇) 40+ (人、鼠) | ref-3 |
| 4    | ChIPseq    | 20+       | ref-4    |
| 5    | ADARseq    | 20+       | ref-5    |
| 6    | ATACseq    | 30+       | ref-6    |

{{</ faq >}}


{{< faq "3 HiSeq index and primer" >}}

+ HiSeq引物是指，构建文库最后一步 PCR 反应时所加入的引物，常用

  - `P5` 表示扩增5'端的引物，通常不包含`Index`；
  
  - `P7` 表示扩增3'端的引物，通常包括`i7 index`序列。 
  
详情请查阅 下一节 **HiSeq文库结构**。


+ 常用两种HiSeq文库 

  - `TruSeq`: 常见RNAseq，ChIPseq，DNAseq；    
  - `Nextera`：常见ATACseq，DNAseq
  
实际应用中多是这两种文库的修改版本。

+ `TruSeq` 和 `Nextera`文库可以混合，但是**不推荐**；如必须混合测序，请在此检查 index 兼容性 <a href="http://192.168.206.171:6611/tools/hiseq_index/" target="_blank">
检查P7 Index</a>

+ [Illumina Adapter Sequences 2020-07-15 v14](https://sapac.support.illumina.com/content/dam/illumina-support/documents/documentation/chemistry_documentation/experiment-design/illumina-adapter-sequences-1000000002694-14.pdf)

+ [Overview of Illumina Chemistry](http://nextgen.mgh.harvard.edu/IlluminaChemistry.html) from Harvard Medical School.


+ [Illumina adapter sequences](https://support.illumina.com/downloads/illumina-adapter-sequences-document-1000000002694.html) from Illumina official website.

+ [Illumina adapters, bioinfo](http://bioinformatics.cvr.ac.uk/blog/illumina-adapter-and-primer-sequences/) from Bioinformatics I/O website. 

+ [Nextera Library](https://www.illumina.com/documents/products/datasheets/datasheet_nextera_dna_sample_prep.pdf)  from Illumina official website.

{{</ faq >}}


{{< faq "4 requirements for samples in one Lane" >}}

+ 1 一条Lane数据产量预计 `400M` reads (HiSeq X Ten)   

+ 2 样品`P7 index`的序列兼容，**不支持**重复
 
+ 3 样本名称**不支持**重复

详情请查阅 **填写样本信息单** 
{{</ faq >}}


{{< faq "5 HiSeq results" >}}
HiSeq相关结果都保存在 Yulab Cloud的 `HiSeq_results`目录内。查阅 **Yulab Cloud**操作指南。

{{</ faq >}}


{{< faq "6 Can I mix TruSeq and Nextera samples?" >}}

`Illumina 不支持，强烈反对` 参考Illumina官网FAQ：

> [Can I run TruSeq HT libraries with Nextera libraries on the same lane or same flow cell? Are the indexes the same or different?](https://support.illumina.com/sequencing/sequencing_kits/nextera_xt_dna_kit/questions.html)    
> **Illumina does not support, and strongly advises against**, running libraries prepared with different library prep kits in the same lane of a flow cell. Running libraries prepared by different library prep kits in different lanes of the same flow cell or spiking in Illumina PhiX control library in the same lane as any user-prepared libraries is supported.
>
> If different library types are run in different lanes, dual index recipes and the Dual Index Primer Box are required. The indexes for TruSeq HT and Nextera are unique and not shared.

{{</ faq >}}



