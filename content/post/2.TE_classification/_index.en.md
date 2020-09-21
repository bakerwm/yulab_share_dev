---
title: "2. TE classification"
draft: false
date: 2020-08-20T11:02:05+06:00
lastmod: 2020-08-22T10:42:26+06:00
# search related keywords
keywords: ["germline", "somatic", "TE"]
weight: 3
---



## Reference

1.Malone, C. D. et al. Specialized piRNA pathways act in germline and somatic tissues of the Drosophila ovary. Cell vol. 137 522–535 (2009). DOI: [10.1016/j.cell.2009.03.040](https://doi.org/10.1016/j.cell.2009.03.040)

2.Li, C. et al. Collapse of Germline piRNAs in the Absence of Argonaute3 Reveals Somatic piRNAs in Flies. Cell 137, 509–521 (2009). DOI: [10.1016/j.cell.2009.04.027](https://doi.org/10.1016/j.cell.2009.04.027)



> Germline element
>
> A transposon, which is expressed and silenced predominantly within germline cells of the ovary. Regulation occurs predominantly by Aub and AGO3 (weak Piwi bias) via the ping-pong cycle (strong ping-pong signal). piRNAs matching these elements are also efficiently deposited into the embryo (strong inheritance).

> Intermediate element    
>
>A transposon, which is expressed and regulated within both germline and somatic cells of the ovary. Regulation occurs through Piwi, Aub and AGO3 (intermediate Piwi bias, moderate ping-pong signal). Corresponding piRNAs are moderately deposited into the embryo (intermediate inheritance).

> Somatic element
>
>A transposon, which is expressed and silenced predominantly within somatic cells of the ovary. Regulation occurs predominantly by Piwi (strong Piwi bias) independent of the ping-pong cycle (weak or no ping-pong signal). piRNAs matching these elements are also not efficiently deposited into the embryo (weak inheritance).


> Inheritance analysis  
> 
> A measure of how effectively piRNAs expressed within the diverse tissues of the ovary are deposited into the embryo. Here, germline piRNAs are deposited, but piRNAs acting in somatic cells of the ovary are not, as somatic cells are unable to contribute to maternal deposition. This measure is calculated by dividing normalized piRNA levels from adult ovaries, by those found in early embryonic libraries (reflecting the maternally deposited pool of piRNAs).


```
score = (adult ovary) / (early embryo)   

adult ovary: germline cell deposited, soma cell not.

early embryo: maternal deposite piRNAs, germline only, 

```

> we divided transposons into three groups (Figures 1A and 2A). Those with strong maternal deposition (red) are considered to have a dominant germline silencing component. Those with intermediate levels of maternal deposition (yellow) are considered to be expressed


+ maternal deposition, target germline (red)    
+ intermediate, maternal deposition, target both germline and follicle (soma) TEs (yellow)    
+ weak maternal deposition, target soma TEs (green)    



Figure 1A, 
![](https://els-jbs-prod-cdn.literatumonline.com/cms/attachment/3106884c-77e2-486a-9bce-1d57ba2dd8f9/gr1.jpg)

> (A) The log2 fold ratio between ovarian and embryonic piRNAs over the 86 most targeted transposons is shown (right). The extent of maternal piRNA deposition is defined as **strong (red), intermediate (yellow), or weak (green)**. _Gypsy_-family LTR retrotransposons are shown in red. For each element, the Piwi bias (log2 fold ratio of Piwi-bound piRNAs to Aub/AGO3-bound piRNAs) is shown in heat map form (center; green indicates strong, red weak Piwi bias). To the left, the sequence contribution of each element to the _42AB_ and _flamenco_ piRNA clusters is shown in orange and black, respectively.




## Content

+ soma: piRNAs from flamenco cluster    
+ germline: various

## 2 TE classification 

Type of Transposons:

+ Class I (retrotransposons), require RNA intermediate  

+ Class II (DNA transposons), through `cut-and-paste` mechanism. 


Tissue-Specific TE

+ germline

all three Piwi-clade bind piRNAs    
variety of clusters    
targe broad range of elements (TAHRE, TART, HetA, copia, I-element)


+ soma (somatic cells of ovary)

only Piwi-bind piRNAs,     
exclusively from flamenco,    
target gypsy family TEs. (gypsy, ZAM, Idefix)



> Piwi- and Aub-associated piRNAs reflect the antisense bias of the system, whereas AGO3-bound piRNAs are typically sense to transposons. Sense and antisense piRNAs bound by AGO3 and Aub, respectively, show a prevalent relationship with their 5′ ends, overlapping by precisely 10 nt.  

  - AGO3 piRNAs, sense of TE    
  - Aub piRNAs, antisense of TE
  
  5' end overlap, 10nt, 1U (ping-pong cycle)
  
  - Piwi piRNAs, antisense of TE    
  - 
  

Expression of Piwi proteins:

> In the Drosophila ovary, all three Piwi-family members (Piwi, Aub, and AGO3) are expressed in germline cells (Brennecke et al., 2007; Cox et al., 2000; Gunawardane et al., 2007; Harris and Macdonald, 2001; Saito et al., 2006), while Piwi alone is expressed in gonadal somatic cells. This implied possible differences in the architecture of the piRNA pathway, and perhaps the elements that it controls, in germline and somatic tissues. We therefore sought to separately analyze piRNAs present in these two compartments.

+ germline cells:  Piwi, Aub, AGO3   

+ gondal somatic cells: Piwi


Developement of Drosophila, 0-2 hr embryo, mirrored total ovary.

+ egg chamber are syncytial (多核体)   
+ nearly all cytoplasmic content of nurse cells into late-stage of oocytes    
+ follicular epithelium shed from laid egg





