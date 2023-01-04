--- 
title: "麻麻说我们可以用 R Markdown 写书了"
author: "张三"
date: "2023-01-04"
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
## R version 4.1.2 (2021-11-01)
## Platform: x86_64-apple-darwin17.0 (64-bit)
## Running under: macOS Catalina 10.15.7
## 
## Matrix products: default
## BLAS:   /Library/Frameworks/R.framework/Versions/4.1/Resources/lib/libRblas.0.dylib
## LAPACK: /Library/Frameworks/R.framework/Versions/4.1/Resources/lib/libRlapack.dylib
## 
## locale:
## [1] zh_CN.UTF-8/zh_CN.UTF-8/zh_CN.UTF-8/C/zh_CN.UTF-8/zh_CN.UTF-8
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets 
## [6] methods   base     
## 
## loaded via a namespace (and not attached):
##  [1] bookdown_0.29   digest_0.6.30   R6_2.5.1       
##  [4] jsonlite_1.8.0  magrittr_2.0.3  evaluate_0.18  
##  [7] stringi_1.7.8   rlang_1.0.6     cli_3.4.1      
## [10] rstudioapi_0.13 jquerylib_0.1.4 bslib_0.3.1    
## [13] rmarkdown_2.14  tools_4.1.2     stringr_1.4.1  
## [16] xfun_0.34       yaml_2.3.6      fastmap_1.1.0  
## [19] compiler_4.1.2  htmltools_0.5.3 knitr_1.40     
## [22] sass_0.4.2
```

## 致谢 {-}

非常感谢谁谁以及谁谁对我的帮助。艾玛，要不是他们神一样的队友，我两年前就写完这本书了。

难以置信我慢慢就写完了这本书，感谢的人有很多，重要的是要自己的爷爷
```

