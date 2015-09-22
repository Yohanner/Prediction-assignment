****read training and test datasets*******


```r
training_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Training data.csv")
testing_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Testing data.csv")
```

checking the sanity of data



```r
head(training_assig)
tail(training_assig)
```


```r
table(training_assig2$classe)
```

```
## 
##    A    B    C    D    E 
## 5580 3797 3422 3216 3607
```

```r
training_assig3=training_assig2[,-c(1:7)]
xx=table(training_assig3$classe)
```



```r
barplot(xx,col="grey")
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6-1.png) 

```r
dev.copy(png, file="plot1.png", width=480, height=480)
```

```
## png 
##   5
```

```r
dev.off()
```

```
## RStudioGD 
##         2
```

