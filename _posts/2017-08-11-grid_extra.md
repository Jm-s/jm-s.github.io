---
title: Graph example - multiple plot in one page using 'gridExtra'
date: 2017-08-11 21:48
---


ggplot 으로 그림을 그리면, multiple plot 을 하기위해서 다른 패키지가 필요하다.
여러가지 종류가 있을 것 같은데, 우선 쉽게 말그대로 그냥 plot 을 넣기만 하는 패키지가 있음. 
'gridExtra' 라는 패키지인데, axis 를 맞추거나 하는 기능은 없는데, 급하게 플롯 여러게를 모아서 넣기에는 괜찮은듯.... 

```r
library ("ggplot2")
library ("gridExtra")
```
패키지 로딩하고~ 

데이터 리딩

```r
dat <- read.csv("rbd_dat_for_r_0810.csv")
dat
```

```
##    no RBDQ  RSWA ds_duration PSQI age sex PLMSI GDS  AHI gAHI
## 1  25   25 73.24           1    3  56   F  71.1   5  4.2    0
## 2  24   69 35.71          10    5  66   M   4.1   2 57.5    4
## 3  22   58 32.56          10    3  64   F   0.0   8  1.4    0
## 4  21   33 15.14           1    5  54   F   2.9  13  8.2    1
## 5  20   47 34.62           8    7  75   M   0.0   7 25.5    3
## 6  18   59 17.91           6    6  74   F   0.0  12  7.4    2
## 7  17   77 51.26           3   19  56   M   0.0  22 10.2    2
## 8  16   NA 37.58           2    5  68   M  12.0   0  8.2    2
## 9  13   84 19.09           2    2  79   M  28.4  10 26.1    3
## 10 12  100 10.32           7   13  68   M  45.0  20 15.6    3
## 11 11   67 64.29           1    6  71   M   4.6   8 10.9    2
## 12  9   58 53.71           1    7  72   M  62.2  15 24.5    3
## 13  8   46 38.74           1    9  45   M  11.1   9  8.0    2
## 14  7   26 40.38           1    3  74   M   0.0  16 52.0    4
## 15  6   48 44.20           7    6  75   M  35.8   9 41.1    4
## 16  4   38  5.19           2    3  71   F   0.0   9 10.1    2
## 17  3   52 19.61           5   13  73   F   0.0  14  5.5    2
## 18  2   44 30.95           3    8  51   F  20.4  19 33.7    4
```

숫자 데이터들로 correlation 을 보려고 하는데, 그러면 역시나, scatterplot 을 그려보는게
중요하다. 여러개를 그리려면 좀 귀찮은데, 우선은 하나씩 그려서, gridExtra package 를
이용해서, 한장에 넣었음.

```r
a <- ggplot (dat, aes(x=age, fill=factor(sex))) + 
        geom_dotplot(binwidth = 1.5, stackgroups=T, binpositions="all") +
        scale_y_continuous(NULL, breaks=NULL) + 
        theme(legend.position = c(.85,.80), legend.title = element_text(F), legend.background = element_blank())


b <- ggplot(dat, aes(x=ds_duration, y=RBDQ)) + 
        geom_jitter(width=0.1, height=0) +
        labs(x="RBD Sx duration (years)", y="RBDQ-HK") 


c <- ggplot(dat, aes(x=ds_duration, y=RSWA))+ 
        geom_jitter(width=0.1, height=0) +
        labs(x="RBD Sx duration(year)", y="RSWA(%)") 


d <- ggplot(dat, aes(x=RBDQ, y=RSWA)) + 
        geom_jitter(width=0.1, height=0) +
        labs(x="RBDQ-HK", y="RSWA(%)") 
```


```r
grid.arrange(a,b,c,d)
```


![plot of chunk unnamed-chunk-4]({{ site.url }}/assets/unnamed-chunk-4-1.png)
