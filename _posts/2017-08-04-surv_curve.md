---
title: Graph example - Survival Curve
date: 2017-08-04 20:02
---



### Survival package loading

```r
library (survival)
library (dplyr)
```

### Data munging

```r
t_dat <- read.csv("data.csv")
tdat <- t_dat[complete.cases(t_dat$EDSS),]
f2dat <- select(tdat, no,onset, relapse_t, relapse_e)

print (f2dat)
```

|   | no | onset | relapse_t | relapse_e |
|:-:|:----:|:-------:|:-----------:|:-----------:|
| 1 | 1  | 1     | 29.17     | 1         |
| 2 | 2  | 1     | 12.97     | 1         |
| 3 | 3  | 1     | 6.93      | 1         |
|5|5|1|7.53|1|
|6|6|1|14.43|0|
|...|...|...|...|...|



### Making survival curve 

```r
f2 <- survfit(Surv(relapse_t,relapse_e)~onset,data=f2dat)
```

- 일반적인 변수 넣는 법

```r
survfit(formula=Surv(time, status)~treatment, datat=XXX)
```

### Plotting

```r
plot(f2,lty=c(1,2), mark.time=F, axes=T, bty="l", lwd=2, ylab = "Cumulative Probability of remaining relapse free", 
     xlab = "disease duration (months)", ylim = c(0, 1))
legend(x=180, y=1, c("LO-NMOSD","EO-NMOSD"), lty=c(1,2), lwd=2, cex=0.8)
```

![plot of chunk unnamed-chunk-5]({{site.url}}/assets/surv.png)


### Log-rank test

```r
survdiff(Surv(relapse_t,relapse_e)~onset,data=f2dat)
```

```
## Call:
## survdiff(formula = Surv(relapse_t, relapse_e) ~ onset, data = f2dat)
## 
##           N Observed Expected (O-E)^2/E (O-E)^2/V
## onset=1  45       31     27.4     0.462     0.636
## onset=2 102       88     91.6     0.139     0.636
## 
##  Chisq= 0.6  on 1 degrees of freedom, p= 0.425
```
