---
title       : Taller
subtitle    : 
author      : Rafael Eduardo Díaz
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Slide 1


```r
library(tables, quietly = TRUE)
```

```
## 
## Attaching package: 'Hmisc'
```

```
## The following objects are masked from 'package:base':
## 
##     format.pval, round.POSIXt, trunc.POSIXt, units
```

```r
library(pander)
tab <- tabular( (Species + 1) ~ (n=1) + Format(digits=2)*
         (Sepal.Length + Sepal.Width)*(mean + sd), data=iris )
pander(tab)
```


-------------------------------------------------------------------
      \         \     Sepal.Length\     \     Sepal.Width\     \   
   Species       n         mean         sd        mean         sd  
-------------- ----- ---------------- ------ --------------- ------
   *setosa*     50         5.01        0.35       3.43        0.38 

 *versicolor*   50         5.94        0.52       2.77        0.31 

 *virginica*    50         6.59        0.64       2.97        0.32 

    *All*       150        5.84        0.83       3.06        0.44 
-------------------------------------------------------------------

## Slide 2


```r
library(ggplot2)
box <- ggplot(data=iris, aes(x=Species, y=Sepal.Length))
box + geom_boxplot(aes(fill=Species)) + 
  ylab("Sepal Length") + ggtitle("Iris Boxplot") +
  stat_summary(fun.y=mean, geom="point", shape=5, size=4) 
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)

## Slide 3

![iris](http://www.spataru.at/iris-dataset-svm/iris_types.jpg)
