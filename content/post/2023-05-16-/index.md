---
title: 相关系数矩阵图
author: 陈鑫
date: '2023-05-16'
categories:
  - R
tags:
  - plot
---

# 设置工作路径

```r
#getwd()
#setwd("[]:[]/[]/[]")
```

# 加载R包——corrplot

```r
#install.packages("corrplot")#下载corrplot
library(corrplot)
## corrplot 0.92 loaded
```

# 导入数据

```r
#导入数据——mtcars
df <- mtcars 
#df <- read.table()
#相关系数矩阵，即协方差计算——res为相关系数矩阵即可
res <- cor(df)
```

# 绘制相关系数矩阵图——上正圆下数

```r

corrplot(res, type = "upper", order = "AOE", tl.col = "black",tl.srt=45, cex.main = 1, mar = c(2,2,3,2),tl.pos="d")  #上三角
corrplot(res,add=TRUE, type="lower", method="number",order="AOE",diag=FALSE,tl.pos="n", cl.pos="n")
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-4-1.png" width="672" />

# 绘制相关系数矩阵图--上椭圆下数

```r
corrplot(res,type = "upper",method="ellipse",order="AOE",shade.col=NA,tl.col="black",tl.srt=45, cex.main = 1, mar = c(2,2,3,2),tl.pos="d") #椭圆
corrplot(res,add=TRUE, type="lower", method="number",order="AOE",diag=FALSE,tl.pos="n", cl.pos="n")
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-5-1.png" width="672" />

# 绘制相关系数矩阵图--上pie图下数

```r

corrplot(res,type = "upper",method="pie",order="AOE",shade.col=NA,tl.col="black",tl.srt=45, cex.main = 1, mar = c(2,2,3,2),tl.pos="d") #椭圆
corrplot(res,add=TRUE, type="lower", method="number",order="AOE",diag=FALSE,tl.pos="n", cl.pos="n")
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-6-1.png" width="672" />

# 绘制相关系数矩阵图--上热图下数

```r
corrplot(res,type = "upper",method="color",order="AOE",shade.col=NA,tl.col="black",tl.srt=45, cex.main = 1, mar = c(2,2,3,2)) #椭圆
corrplot(res,add=TRUE, type="lower", method="number",order="AOE",diag=FALSE, cl.pos="n")
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-7-1.png" width="672" />
