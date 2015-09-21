#****read trainning and test datasets*******


```r
training_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Training data.csv")
testing_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Testing data.csv")
```

********checking the sanity of data********
#head(training_assig)
#tail(training_assig)



```r
table(training_assig2$classe)
```

```
## 
##    A    B    C    D    E 
## 5580 3797 3422 3216 3607
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png) 
```

