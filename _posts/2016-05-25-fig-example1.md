---
title: Graph example-pre_post change
date: 2016-05-25 03:55 
---

같은 대상자에서 전후 비교하는 그래프.   
자료 수정이 필요한데, `gather`함수가 아주 유용하게 쓰임
더 편하게 할 수 있는 방법이 있을 수도 있을 것 같은데, 잘 모르겠다.   
`ggplot2`패키지의 `facet_grid`에 좀더 익숙해질 필요가 있음. 


### **데이터 정리하기**

```r
library(dplyr)
library(tidyr)
library(ggplot2)
```
패키 로딩 ~  'Hadley Wickham' 성님 

```r
dat <- read.csv("initialAttack_AQP4_0627_off.csv")
mdat <- select (dat, Number, mod_F_type, F_nEDSS, F_rEDSS)
mdat[which(mdat$Number==69),"mod_F_type"] <- 4
```
데이터정리한거 신경안써도 됨.  

아래부터는 그래프를 나눠그리기 위해 데이터 필터링 한 것

```r
ond <- filter(mdat, mod_F_type==1)
tmd <- filter(mdat, mod_F_type==3)
brd <- filter(mdat, mod_F_type==4)
cod <- filter(mdat, mod_F_type==7)
```

```r
print(ond)
```

|   |Number|mod_F_type|F_nEDSS|F_rEDSS|
|---|------|----------|-------|-------|
|1  |     6|         1|      3|      1|
|2  |     7|         1|      3|      1|
|3  |    20|         1|      3|      1|
|4  |    28|         1|      3|      3|
|5  |    32|         1|      3|      1|
|...|...   |...       |...    |...    |



```r
m_ond <- gather (ond, when, EDSS, 3:4)
m_tmd <- gather (tmd, when, EDSS, 3:4)
m_brd <- gather (brd, when, EDSS, 3:4)
m_cod <- gather (cod, when, EDSS, 3:4)
```

```r
print(m_ond)
```
`gather` 함수를 이용하면 자료가 이런식으로 변함


|   |Number|mod_F_type|when   |EDSS|   
|---|------|----------|-------|----|   
|1  |     6|         1|F_nEDSS|   3|
|2  |     7|         1|F_nEDSS|   3|
|3  |    20|         1|F_nEDSS|   3|
|4  |    28|         1|F_nEDSS|   3|
|...|...   |...       |...    |... |
   
   


### **Graph 그리기** 

```r
ggplot (m_ond, aes(x=when, y=EDSS)) +
        geom_point(shape=1, size=3, position=position_jitter(w=0.005, h=0))+
        geom_path(aes(group=Number))+
        scale_x_discrete(labels=c("at nadir", "at recovery"))+
        scale_y_continuous(limits=c(0,10), breaks=c(0,2,4,6,8,10))+
        xlab("")+labs(title="Optic Neuritis")+theme_bw(base_size=16)
```

![plot of chunk unnamed-chunk-5]({{ site.url }}/assets/unnamed-chunk-5-1.png)

```r
ggplot (m_tmd, aes(x=when, y=EDSS)) +
        geom_point(shape=2, size=3, position=position_jitter(w=0.005, h=0))+
        geom_path(aes(group=Number))+
        scale_x_discrete(labels=c("at nadir", "at recovery"))+
        scale_y_continuous(limits=c(0,10), breaks=c(0,2,4,6,8,10))+
        xlab("")+ylab("")+labs(title="Transverse Myelitis")+theme_bw(base_size=16)
```

![plot of chunk unnamed-chunk-6]({{ site.url }}/assets/unnamed-chunk-6-1.png)

```r
ggplot (m_brd, aes(x=when, y=EDSS)) +
        geom_point(shape=0, size=3, position=position_jitter(w=0.005, h=0))+
        geom_path(aes(group=Number))+
        scale_x_discrete(labels=c("at nadir", "at recovery"))+
        scale_y_continuous(limits=c(0,10), breaks=c(0,2,4,6,8,10))+
        xlab("")+ylab("")+labs(title="Brain/Brainstem")+theme_bw(base_size=16)
```

![plot of chunk unnamed-chunk-7]({{ site.url }}/assets/unnamed-chunk-7-1.png)

```r
ggplot (m_cod, aes(x=when, y=EDSS)) +
        geom_point( size=3)+
        geom_path(aes(group=Number))+
        scale_x_discrete(labels=c("at nadir", "at recovery"))+
        scale_y_continuous(limits=c(0,10), breaks=c(0,2,4,6,8,10))+
        xlab("")+ylab("")+labs(title="Combined")+theme_bw(base_size=16)
```

![plot of chunk unnamed-chunk-8]({{ site.url }}/assets/unnamed-chunk-8-1.png)


이제 이 내용들을 합쳐서 facet_grid 를 이용해서 그래프 마무리

```r
c <- c("Optic neuritis", "", "Transverse myelitis","Brain/Brainstem","","","Combined")
type_labeller <- function(variable,value){
        return(c[value])
}

ggplot(a2, aes(x=condition, y=EDSS, group=1)) +
        geom_line() +
        geom_errorbar(width=.15, aes(ymin=q25, ymax=q75)) +
        geom_point(shape=21, size=3.5, fill="white") +
        scale_y_continuous(limits=c(0,10), breaks=c(0,3,6,9))+
        xlab("")+theme_bw(base_size=16)+facet_grid(~type, labeller = type_labeller)+theme(strip.text.x = element_text(size=16))
```

![plot of chunk unnamed-chunk-9]({{ site.url }}/assets/fig1_md.png)
