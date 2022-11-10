\mainmatter

# 牛刀小试 {#intro}

现在我们可以试试 **bookdown** 的一些初级功能了，例如图表。图 \@ref(fig:hello) 是一幅无趣的散点图，表 \@ref(tab:iris) 是一份枯燥的数据。


```r
par(mar = c(4, 4, 1, .1))
plot(cars, pch = 19)
```

<div class="figure">
<img src="01-introduction_files/figure-html/hello-1.png" alt="雷猴啊，散点图！" width="90%" />
<p class="caption">(\#fig:hello)雷猴啊，散点图！</p>
</div>


```r
knitr::kable(
  head(iris), caption = '雷猴啊，iris 数据！',
  booktabs = TRUE
)
```



Table: (\#tab:iris)雷猴啊，iris 数据！

| Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |
|------------:|-----------:|------------:|-----------:|:-------|
|          5.1|         3.5|          1.4|         0.2|setosa  |
|          4.9|         3.0|          1.4|         0.2|setosa  |
|          4.7|         3.2|          1.3|         0.2|setosa  |
|          4.6|         3.1|          1.5|         0.2|setosa  |
|          5.0|         3.6|          1.4|         0.2|setosa  |
|          5.4|         3.9|          1.7|         0.4|setosa  |

就这样，你可以一直编下去，直到编不下去。
