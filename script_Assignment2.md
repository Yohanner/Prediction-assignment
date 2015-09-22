Read trainning and test datasets


```r
training_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Training data.csv")
testing_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Testing data.csv")
```

Checking the sanity of data



```r
head(training_assig)
tail(training_assig)
str(training_assig)
dim(training_assig)
head(training_assig$classe)
colSums(is.na(training_assig))
```
```

Remove variables with significant missing values



```r
training_assig2=select(training_assig,c(-starts_with("avg")),c(-starts_with("var")),c(-starts_with("max")),c(-starts_with("min")),c(-starts_with("amplitude")),c(-starts_with("stddev")),c(-starts_with("min")),c(-starts_with("amplitude")),c(-starts_with("avg"),c(-starts_with("kurtosis")),-starts_with("skewness")))
names(training_assig2)
head(training_assig2)
str(training_assig2)
summary(training_assig2)
table(training_assig2$classe)
```
```

Exclude variables



```r
training_assig3=training_assig2[,-c(1:7)]
head(training_assig3)
dim(training_assig3)
str(training_assig3)
names(training_assig3)
```
```

classe Frequency
#+ Classe Frequency, fig.path='', dev=c('png', 'pdf')



```r
table(training_assig3$classe)%>%barplot(col="grey")
```

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-9-1.png) 
```

PREDICTION
FITTING CLASSIFICATION TREES
CREATE TRAINING AND TEST DATASETS



```r
set.seed(2)
inTrain=createDataPartition(y=training_assig3$classe,p=0.7,list=FALSE)
Train_sets=training_assig3[inTrain,]
Test_sets=training_assig3[-inTrain,]
```

```r
dim(Train_sets)
```

```
## [1] 13737    53
```

```r
dim(Test_sets)
```

```
## [1] 5885   53
```
```

FIT TREE TO TRAINING SET, PREDICT TEST SET AND CALCULATE MISCLASS RATE



```r
class_tree2=tree(classe~.,Train_sets)
summary(modelfit)
summary(class_tree2) #the prediction gives 18 nodes
tree.pred=predict(class_tree2,Test_sets,type="class")
```
```

CALCULATE ACCURAY



```r
confusionMatrix(tree.pred,Test_sets$classe) #gives 66% accuracy
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1421  229   13   29   10
##          B   28  375   32   16    5
##          C   31  126  775  226  124
##          D  171  246  133  671  246
##          E   23  163   73   22  697
## 
## Overall Statistics
##                                           
##                Accuracy : 0.6693          
##                  95% CI : (0.6571, 0.6813)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.5832          
##  Mcnemar's Test P-Value : < 2.2e-16       
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            0.8489  0.32924   0.7554   0.6961   0.6442
## Specificity            0.9333  0.98293   0.8957   0.8382   0.9415
## Pos Pred Value         0.8349  0.82237   0.6045   0.4574   0.7127
## Neg Pred Value         0.9395  0.85927   0.9455   0.9337   0.9215
## Prevalence             0.2845  0.19354   0.1743   0.1638   0.1839
## Detection Rate         0.2415  0.06372   0.1317   0.1140   0.1184
## Detection Prevalence   0.2892  0.07749   0.2178   0.2493   0.1662
## Balanced Accuracy      0.8911  0.65608   0.8255   0.7672   0.7928
```
```

JUST A NOTE, THE FOLLOWING GIVE DIFFERENT ACCURACY RATE, using TRAIN function
gives 50% and Rpart 75%



```r
modelfit=train(classe~.,method="rpart",data=training_assig3)
modelfit2=rpart(classe~.,data=training_assig3, method="class")

pred1=predict(modelfit,Test_sets)
pred2=predict(modelfit2,Test_sets,type="class")
```

```r
confusionMatrix(pred1,Test_sets$classe)
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1529  461  485  451  148
##          B   21  394   27  169  149
##          C  121  284  514  344  293
##          D    0    0    0    0    0
##          E    3    0    0    0  492
## 
## Overall Statistics
##                                           
##                Accuracy : 0.4977          
##                  95% CI : (0.4849, 0.5106)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.3433          
##  Mcnemar's Test P-Value : NA              
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            0.9134  0.34592  0.50097   0.0000  0.45471
## Specificity            0.6331  0.92288  0.78555   1.0000  0.99938
## Pos Pred Value         0.4974  0.51842  0.33033      NaN  0.99394
## Neg Pred Value         0.9484  0.85463  0.88173   0.8362  0.89054
## Prevalence             0.2845  0.19354  0.17434   0.1638  0.18386
## Detection Rate         0.2598  0.06695  0.08734   0.0000  0.08360
## Detection Prevalence   0.5223  0.12914  0.26440   0.0000  0.08411
## Balanced Accuracy      0.7732  0.63440  0.64326   0.5000  0.72704
```

```r
confusionMatrix(pred2,Test_sets$classe)
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1510  175   18   53   20
##          B   49  708   89   83  102
##          C   38  122  839  139  127
##          D   50   78   54  621   53
##          E   27   56   26   68  780
## 
## Overall Statistics
##                                           
##                Accuracy : 0.7575          
##                  95% CI : (0.7464, 0.7684)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.6927          
##  Mcnemar's Test P-Value : < 2.2e-16       
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            0.9020   0.6216   0.8177   0.6442   0.7209
## Specificity            0.9368   0.9319   0.9123   0.9522   0.9631
## Pos Pred Value         0.8502   0.6867   0.6632   0.7255   0.8150
## Neg Pred Value         0.9601   0.9112   0.9595   0.9318   0.9387
## Prevalence             0.2845   0.1935   0.1743   0.1638   0.1839
## Detection Rate         0.2566   0.1203   0.1426   0.1055   0.1325
## Detection Prevalence   0.3018   0.1752   0.2150   0.1455   0.1626
## Balanced Accuracy      0.9194   0.7768   0.8650   0.7982   0.8420
```
```

USING CROSS VALIDATION TO PRUNE THE TREE



```r
set.seed(3)
cv.class_tree2=cv.tree(class_tree2,FUN=prune.misclass)
```

```r
cv.class_tree2
```

```
## $size
##  [1] 18 17 16 15 14 13  7  6  5  4  2  1
## 
## $dev
##  [1] 4536 4536 4584 4662 4925 4925 6803 7038 7256 7623 8692 9831
## 
## $k
##  [1]      -Inf    0.0000   67.0000   78.0000  125.0000  132.0000  283.8333
##  [8]  324.0000  359.0000  418.0000  491.0000 1139.0000
## 
## $method
## [1] "misclass"
## 
## attr(,"class")
## [1] "prune"         "tree.sequence"
```
```

The smallest cross validation error occurred for 18 and 17 nodes, 
hence pruning didnt give better results  
USING BAGGING...USING ALL THE PREDICTORS



```r
names(Train_sets)
cv.class.bag=randomForest(classe~.,data=Train_sets,mtry=52,importance=TRUE)
tree.pred_bag=predict(cv.class.rf,Test_sets)
```

```r
confusionMatrix(tree.pred_bag,Test_sets$classe) ##gives 98.9% accuracy
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1674    3    0    0    0
##          B    0 1136    0    0    0
##          C    0    0 1026    4    0
##          D    0    0    0  960    1
##          E    0    0    0    0 1081
## 
## Overall Statistics
##                                           
##                Accuracy : 0.9986          
##                  95% CI : (0.9973, 0.9994)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.9983          
##  Mcnemar's Test P-Value : NA              
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            1.0000   0.9974   1.0000   0.9959   0.9991
## Specificity            0.9993   1.0000   0.9992   0.9998   1.0000
## Pos Pred Value         0.9982   1.0000   0.9961   0.9990   1.0000
## Neg Pred Value         1.0000   0.9994   1.0000   0.9992   0.9998
## Prevalence             0.2845   0.1935   0.1743   0.1638   0.1839
## Detection Rate         0.2845   0.1930   0.1743   0.1631   0.1837
## Detection Prevalence   0.2850   0.1930   0.1750   0.1633   0.1837
## Balanced Accuracy      0.9996   0.9987   0.9996   0.9978   0.9995
```
```

RANDOM FOREST



```r
cv.class.bag=train(classe~.,data=training_assig3,method="rf",prox=TRUE)#this took too long to run
cv.class.rf=randomForest(classe~.,data=Train_sets,mtry=8,importance=TRUE)
tree.pred_rf=predict(cv.class.rf,Test_sets)
```

```r
confusionMatrix(tree.pred_rf,Test_sets$classe) ##gives 99.4% accuracy
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1673    6    0    0    0
##          B    0 1133    8    0    0
##          C    0    0 1018   13    0
##          D    0    0    0  950    6
##          E    1    0    0    1 1076
## 
## Overall Statistics
##                                           
##                Accuracy : 0.9941          
##                  95% CI : (0.9917, 0.9959)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.9925          
##  Mcnemar's Test P-Value : NA              
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            0.9994   0.9947   0.9922   0.9855   0.9945
## Specificity            0.9986   0.9983   0.9973   0.9988   0.9996
## Pos Pred Value         0.9964   0.9930   0.9874   0.9937   0.9981
## Neg Pred Value         0.9998   0.9987   0.9984   0.9972   0.9988
## Prevalence             0.2845   0.1935   0.1743   0.1638   0.1839
## Detection Rate         0.2843   0.1925   0.1730   0.1614   0.1828
## Detection Prevalence   0.2853   0.1939   0.1752   0.1624   0.1832
## Balanced Accuracy      0.9990   0.9965   0.9948   0.9921   0.9970
```
```

PREDICTIING THE TEST SET (THE 20 OBSERVATIONS)



```r
testing_assig2=select(testing_assig,c(-starts_with("avg")),c(-starts_with("var")),c(-starts_with("max")),c(-starts_with("min")),c(-starts_with("amplitude")),c(-starts_with("stddev")),c(-starts_with("min")),c(-starts_with("amplitude")),c(-starts_with("avg"),c(-starts_with("kurtosis")),-starts_with("skewness")))
names(testing_assig2)
testing_assig3=testing_assig2[,-c(1:7)]
pred_final=predict(cv.class.rf,testing_assig3)
```

```r
table$pred_final
```

```
## Error in table$pred_final: object of type 'closure' is not subsettable
```
```

