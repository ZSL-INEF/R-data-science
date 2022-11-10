--- 
title: "麻麻说我们可以用 R Markdown 写书了"
author: "张三"
date: "2022-11-10"
documentclass: ctexbook
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
colorlinks: yes
lot: yes
lof: yes
geometry: [b5paper, tmargin=2.5cm, bmargin=2.5cm, lmargin=3.5cm, rmargin=2.5cm]
site: bookdown::bookdown_site
description: "一个简单的中文书示例。"
github-repo: yihui/bookdown-chinese
#cover-image: images/cover.jpg
---



# 前言 {-}

你好，世界。我写了一本书。这本书是这样的，第 \@ref(intro) 章介绍了啥啥，第 \@ref(wind) 章说了啥啥，然后是啥啥……

我用了两个 R 包编译这本书，分别是 **knitr**\index{knitr} [@xie2015] 和 **bookdown**\index{bookdown} [@R-bookdown]。以下是我的 R 进程信息：


```r
sessionInfo()
```

```
## R version 4.2.1 (2022-06-23 ucrt)
## Platform: x86_64-w64-mingw32/x64 (64-bit)
## Running under: Windows 10 x64 (build 19043)
## 
## Matrix products: default
## 
## locale:
## [1] LC_COLLATE=Chinese_China.936 
## [2] LC_CTYPE=Chinese_China.936   
## [3] LC_MONETARY=Chinese_China.936
## [4] LC_NUMERIC=C                 
## [5] LC_TIME=Chinese_China.936    
## system code page: 65001
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets 
## [6] methods   base     
## 
## loaded via a namespace (and not attached):
##  [1] bookdown_0.29   digest_0.6.29   R6_2.5.1       
##  [4] jsonlite_1.8.2  magrittr_2.0.3  evaluate_0.16  
##  [7] stringi_1.7.8   cachem_1.0.6    rlang_1.0.6    
## [10] cli_3.4.1       rstudioapi_0.14 jquerylib_0.1.4
## [13] bslib_0.4.0     rmarkdown_2.16  tools_4.2.1    
## [16] stringr_1.4.1   xfun_0.33       yaml_2.3.5     
## [19] fastmap_1.1.0   compiler_4.2.1  htmltools_0.5.3
## [22] knitr_1.40      sass_0.4.2
```

## 致谢 {-}

非常感谢谁谁以及谁谁对我的帮助。艾玛，要不是他们神一样的队友，我两年前就写完这本书了。

\BeginKnitrBlock{flushright}<p class="flushright">张三  
于 A 村某角落</p>\EndKnitrBlock{flushright}

