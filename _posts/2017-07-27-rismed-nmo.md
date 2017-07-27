---
title: RISmed package 를 이용한 그래프
date: 2017-07-27 11:54
---

가끔 발표를 하다보면, pubmed 에 내가 관심있는 키워드로 년도별 논문이 얼마나 퍼블리싱
되고 있는지 보여주는 그래프가 있는데, 'RISmed' package 를 통해 이 그래프를 그릴 수 있다.

```r
library(RISmed)
library(dplyr)
library(ggplot2)
```

- EUtilsSummary 함수로 만든 query에서 EUtilsGet 함수로 fetching 하는데 이건 시간이 많이 걸리는듯

```r
res <- EUtilsSummary("neuromyelitis optica", type="esearch", db="pubmed", datetype="edat", mindate=2000, maxdate=2017, retmax=10000)

a <- EUtilsGet(res, type="efetch", db="pubmed")
```


```r
y <- YearPubmed(a)
```

- 그래프그리기 

```r
count<-table(y)
count<-as.data.frame(count)
names(count)<-c("Year", "Counts")
num <- data.frame(Year=count$Year, Counts=count$Counts, cumsum=cumsum(count$Counts))
num$g <- "g"

ggplot(num, aes(Year, Counts)) + geom_col() + geom_text(aes(label=Counts), nudge_y = 100)+
        geom_point(aes(x=Year, y=cumsum, group=g), data=num, shape=1) + 
        geom_line(aes(x=Year, y=cumsum, group=g), data=num) + theme_classic() + 
        annotate ("text", x=18, y=num[nrow(num),"cumsum"]+100, label=num[nrow(num),"cumsum"])+
        labs(title="Result of a PubMed search using the keywards 'Neuromyelitis optica'", x="Year of publication")
```

![plot of chunk unnamed-chunk-3](img/unnamed-chunk-3-1.png)

