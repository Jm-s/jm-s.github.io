---
title: Multiple Shapiro-Wilk test
date: 2017-07-26
---



 shapiro test 함수는 list 형태로 결과물을 반환해서, 자료에서 여러번 시행하려면, 계속 반복해서 실행해줘야 하는 어려움이 있는데, 이를 해결하기 위해 list 형태에서 p value 만 추출하고 for 문을 통해 data.frame 에 자료를 넣어 table 형태로 출력 할 수 있다.

#### Data import

```r
dat <- read.csv("rswa_dat_0713.csv")
head(dat)
```
#### numeric column selection

```python
a1 <- sapply(dat, is.numeric)
a2<- dat[,a1]   
head(a2)
```
 - sapply는 데이터에 해당 함수를 적용하여 행렬로 반환하는 함수, is.numeric 함수를 이용하여 숫자형 변수를 골라낼 수 있음. 

#### multiple shapiro-wilk test as list 

```r
b1 <- lapply(a2, shapiro.test) 
```

```
## Error in FUN(X[[i]], ...): all 'x' values are identical
```
*N3 column filtering and shapiro-wilk test again*

```r
a2 <- a2[,-17]
b1 <- lapply(a2, shapiro.test) 
```
 - shapiro.test 함수는 list 형태로 결과값이 나오므로, lapply로 적용해야함. 
 
#### making table

```python
c <- data.frame()
for (i in 1:length(b1)) {
  c[i,1] <- names(b1)[i] 
  c[i,2] <- round(as.numeric(b1[[i]][2]), digits=4)
}
names(c) <- c("variable", "p value")
print(c)
```


|   | variable | p value|
|---| ---|---|
| 1 | age | `0.0260`|
| 2 | onset_age | 0.5835|
| 3 | duration | 0.0265|
| 4 | RBDQ_HK | 0.4934 |
| 5 | RBDQ_dream | 0.3850|
| 6 | RBDQ_behavior | `0.0118`|
| 7 | height | 0.1194 |
| 8 | weight | 0.8138 |
| 9 |    BMI | 0.2671 |
 10     | freq_DEB | `0.0002`
 11      |     RWA | 0.2546
 12       |    TIB | 0.0000
 13        |    N1 | 0.0000
 14         |  TST | `0.0210`
 15          |  N2 | `0.0020`
 16           | SE | `0.0103`
 17            | R | 0.3376
 18          |WASO | `0.0001`
 19           |AHI | `0.0094`
 20            |SL | `0.0000`
 21   |         RL | `0.0396`
 22    |       RDI | `0.0094`
 23     |    PLMSI | `0.0003`
 24      |  PLM_AI | `0.0000`
 25   |  Total.ArI | 0.1157
 26    |      PSQI | 0.0932
 27   |  SCOPA_AUT | `0.0019`

