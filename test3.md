#****read trainning and test datasets*******


```r
training_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Training data.csv")
testing_assig=read.csv("C:/Yohannes/Coursera/Predictive modelling/Assignment/Testing data.csv")
```

********checking the sanity of data********



```
##   X user_name raw_timestamp_part_1 raw_timestamp_part_2  cvtd_timestamp
## 1 1  carlitos           1323084231               788290 5/12/2011 11:23
## 2 2  carlitos           1323084231               808298 5/12/2011 11:23
## 3 3  carlitos           1323084231               820366 5/12/2011 11:23
## 4 4  carlitos           1323084232               120339 5/12/2011 11:23
## 5 5  carlitos           1323084232               196328 5/12/2011 11:23
## 6 6  carlitos           1323084232               304277 5/12/2011 11:23
##   new_window num_window roll_belt pitch_belt yaw_belt total_accel_belt
## 1         no         11      1.41       8.07    -94.4                3
## 2         no         11      1.41       8.07    -94.4                3
## 3         no         11      1.42       8.07    -94.4                3
## 4         no         12      1.48       8.05    -94.4                3
## 5         no         12      1.48       8.07    -94.4                3
## 6         no         12      1.45       8.06    -94.4                3
##   kurtosis_roll_belt kurtosis_picth_belt kurtosis_yaw_belt
## 1                                                         
## 2                                                         
## 3                                                         
## 4                                                         
## 5                                                         
## 6                                                         
##   skewness_roll_belt skewness_roll_belt.1 skewness_yaw_belt max_roll_belt
## 1                                                                      NA
## 2                                                                      NA
## 3                                                                      NA
## 4                                                                      NA
## 5                                                                      NA
## 6                                                                      NA
##   max_picth_belt max_yaw_belt min_roll_belt min_pitch_belt min_yaw_belt
## 1             NA                         NA             NA             
## 2             NA                         NA             NA             
## 3             NA                         NA             NA             
## 4             NA                         NA             NA             
## 5             NA                         NA             NA             
## 6             NA                         NA             NA             
##   amplitude_roll_belt amplitude_pitch_belt amplitude_yaw_belt
## 1                  NA                   NA                   
## 2                  NA                   NA                   
## 3                  NA                   NA                   
## 4                  NA                   NA                   
## 5                  NA                   NA                   
## 6                  NA                   NA                   
##   var_total_accel_belt avg_roll_belt stddev_roll_belt var_roll_belt
## 1                   NA            NA               NA            NA
## 2                   NA            NA               NA            NA
## 3                   NA            NA               NA            NA
## 4                   NA            NA               NA            NA
## 5                   NA            NA               NA            NA
## 6                   NA            NA               NA            NA
##   avg_pitch_belt stddev_pitch_belt var_pitch_belt avg_yaw_belt
## 1             NA                NA             NA           NA
## 2             NA                NA             NA           NA
## 3             NA                NA             NA           NA
## 4             NA                NA             NA           NA
## 5             NA                NA             NA           NA
## 6             NA                NA             NA           NA
##   stddev_yaw_belt var_yaw_belt gyros_belt_x gyros_belt_y gyros_belt_z
## 1              NA           NA         0.00         0.00        -0.02
## 2              NA           NA         0.02         0.00        -0.02
## 3              NA           NA         0.00         0.00        -0.02
## 4              NA           NA         0.02         0.00        -0.03
## 5              NA           NA         0.02         0.02        -0.02
## 6              NA           NA         0.02         0.00        -0.02
##   accel_belt_x accel_belt_y accel_belt_z magnet_belt_x magnet_belt_y
## 1          -21            4           22            -3           599
## 2          -22            4           22            -7           608
## 3          -20            5           23            -2           600
## 4          -22            3           21            -6           604
## 5          -21            2           24            -6           600
## 6          -21            4           21             0           603
##   magnet_belt_z roll_arm pitch_arm yaw_arm total_accel_arm var_accel_arm
## 1          -313     -128      22.5    -161              34            NA
## 2          -311     -128      22.5    -161              34            NA
## 3          -305     -128      22.5    -161              34            NA
## 4          -310     -128      22.1    -161              34            NA
## 5          -302     -128      22.1    -161              34            NA
## 6          -312     -128      22.0    -161              34            NA
##   avg_roll_arm stddev_roll_arm var_roll_arm avg_pitch_arm stddev_pitch_arm
## 1           NA              NA           NA            NA               NA
## 2           NA              NA           NA            NA               NA
## 3           NA              NA           NA            NA               NA
## 4           NA              NA           NA            NA               NA
## 5           NA              NA           NA            NA               NA
## 6           NA              NA           NA            NA               NA
##   var_pitch_arm avg_yaw_arm stddev_yaw_arm var_yaw_arm gyros_arm_x
## 1            NA          NA             NA          NA        0.00
## 2            NA          NA             NA          NA        0.02
## 3            NA          NA             NA          NA        0.02
## 4            NA          NA             NA          NA        0.02
## 5            NA          NA             NA          NA        0.00
## 6            NA          NA             NA          NA        0.02
##   gyros_arm_y gyros_arm_z accel_arm_x accel_arm_y accel_arm_z magnet_arm_x
## 1        0.00       -0.02        -288         109        -123         -368
## 2       -0.02       -0.02        -290         110        -125         -369
## 3       -0.02       -0.02        -289         110        -126         -368
## 4       -0.03        0.02        -289         111        -123         -372
## 5       -0.03        0.00        -289         111        -123         -374
## 6       -0.03        0.00        -289         111        -122         -369
##   magnet_arm_y magnet_arm_z kurtosis_roll_arm kurtosis_picth_arm
## 1          337          516                                     
## 2          337          513                                     
## 3          344          513                                     
## 4          344          512                                     
## 5          337          506                                     
## 6          342          513                                     
##   kurtosis_yaw_arm skewness_roll_arm skewness_pitch_arm skewness_yaw_arm
## 1                                                                       
## 2                                                                       
## 3                                                                       
## 4                                                                       
## 5                                                                       
## 6                                                                       
##   max_roll_arm max_picth_arm max_yaw_arm min_roll_arm min_pitch_arm
## 1           NA            NA          NA           NA            NA
## 2           NA            NA          NA           NA            NA
## 3           NA            NA          NA           NA            NA
## 4           NA            NA          NA           NA            NA
## 5           NA            NA          NA           NA            NA
## 6           NA            NA          NA           NA            NA
##   min_yaw_arm amplitude_roll_arm amplitude_pitch_arm amplitude_yaw_arm
## 1          NA                 NA                  NA                NA
## 2          NA                 NA                  NA                NA
## 3          NA                 NA                  NA                NA
## 4          NA                 NA                  NA                NA
## 5          NA                 NA                  NA                NA
## 6          NA                 NA                  NA                NA
##   roll_dumbbell pitch_dumbbell yaw_dumbbell kurtosis_roll_dumbbell
## 1      13.05217      -70.49400    -84.87394                       
## 2      13.13074      -70.63751    -84.71065                       
## 3      12.85075      -70.27812    -85.14078                       
## 4      13.43120      -70.39379    -84.87363                       
## 5      13.37872      -70.42856    -84.85306                       
## 6      13.38246      -70.81759    -84.46500                       
##   kurtosis_picth_dumbbell kurtosis_yaw_dumbbell skewness_roll_dumbbell
## 1                                                                     
## 2                                                                     
## 3                                                                     
## 4                                                                     
## 5                                                                     
## 6                                                                     
##   skewness_pitch_dumbbell skewness_yaw_dumbbell max_roll_dumbbell
## 1                                                              NA
## 2                                                              NA
## 3                                                              NA
## 4                                                              NA
## 5                                                              NA
## 6                                                              NA
##   max_picth_dumbbell max_yaw_dumbbell min_roll_dumbbell min_pitch_dumbbell
## 1                 NA                                 NA                 NA
## 2                 NA                                 NA                 NA
## 3                 NA                                 NA                 NA
## 4                 NA                                 NA                 NA
## 5                 NA                                 NA                 NA
## 6                 NA                                 NA                 NA
##   min_yaw_dumbbell amplitude_roll_dumbbell amplitude_pitch_dumbbell
## 1                                       NA                       NA
## 2                                       NA                       NA
## 3                                       NA                       NA
## 4                                       NA                       NA
## 5                                       NA                       NA
## 6                                       NA                       NA
##   amplitude_yaw_dumbbell total_accel_dumbbell var_accel_dumbbell
## 1                                          37                 NA
## 2                                          37                 NA
## 3                                          37                 NA
## 4                                          37                 NA
## 5                                          37                 NA
## 6                                          37                 NA
##   avg_roll_dumbbell stddev_roll_dumbbell var_roll_dumbbell
## 1                NA                   NA                NA
## 2                NA                   NA                NA
## 3                NA                   NA                NA
## 4                NA                   NA                NA
## 5                NA                   NA                NA
## 6                NA                   NA                NA
##   avg_pitch_dumbbell stddev_pitch_dumbbell var_pitch_dumbbell
## 1                 NA                    NA                 NA
## 2                 NA                    NA                 NA
## 3                 NA                    NA                 NA
## 4                 NA                    NA                 NA
## 5                 NA                    NA                 NA
## 6                 NA                    NA                 NA
##   avg_yaw_dumbbell stddev_yaw_dumbbell var_yaw_dumbbell gyros_dumbbell_x
## 1               NA                  NA               NA                0
## 2               NA                  NA               NA                0
## 3               NA                  NA               NA                0
## 4               NA                  NA               NA                0
## 5               NA                  NA               NA                0
## 6               NA                  NA               NA                0
##   gyros_dumbbell_y gyros_dumbbell_z accel_dumbbell_x accel_dumbbell_y
## 1            -0.02             0.00             -234               47
## 2            -0.02             0.00             -233               47
## 3            -0.02             0.00             -232               46
## 4            -0.02            -0.02             -232               48
## 5            -0.02             0.00             -233               48
## 6            -0.02             0.00             -234               48
##   accel_dumbbell_z magnet_dumbbell_x magnet_dumbbell_y magnet_dumbbell_z
## 1             -271              -559               293               -65
## 2             -269              -555               296               -64
## 3             -270              -561               298               -63
## 4             -269              -552               303               -60
## 5             -270              -554               292               -68
## 6             -269              -558               294               -66
##   roll_forearm pitch_forearm yaw_forearm kurtosis_roll_forearm
## 1         28.4         -63.9        -153                      
## 2         28.3         -63.9        -153                      
## 3         28.3         -63.9        -152                      
## 4         28.1         -63.9        -152                      
## 5         28.0         -63.9        -152                      
## 6         27.9         -63.9        -152                      
##   kurtosis_picth_forearm kurtosis_yaw_forearm skewness_roll_forearm
## 1                                                                  
## 2                                                                  
## 3                                                                  
## 4                                                                  
## 5                                                                  
## 6                                                                  
##   skewness_pitch_forearm skewness_yaw_forearm max_roll_forearm
## 1                                                           NA
## 2                                                           NA
## 3                                                           NA
## 4                                                           NA
## 5                                                           NA
## 6                                                           NA
##   max_picth_forearm max_yaw_forearm min_roll_forearm min_pitch_forearm
## 1                NA                               NA                NA
## 2                NA                               NA                NA
## 3                NA                               NA                NA
## 4                NA                               NA                NA
## 5                NA                               NA                NA
## 6                NA                               NA                NA
##   min_yaw_forearm amplitude_roll_forearm amplitude_pitch_forearm
## 1                                     NA                      NA
## 2                                     NA                      NA
## 3                                     NA                      NA
## 4                                     NA                      NA
## 5                                     NA                      NA
## 6                                     NA                      NA
##   amplitude_yaw_forearm total_accel_forearm var_accel_forearm
## 1                                        36                NA
## 2                                        36                NA
## 3                                        36                NA
## 4                                        36                NA
## 5                                        36                NA
## 6                                        36                NA
##   avg_roll_forearm stddev_roll_forearm var_roll_forearm avg_pitch_forearm
## 1               NA                  NA               NA                NA
## 2               NA                  NA               NA                NA
## 3               NA                  NA               NA                NA
## 4               NA                  NA               NA                NA
## 5               NA                  NA               NA                NA
## 6               NA                  NA               NA                NA
##   stddev_pitch_forearm var_pitch_forearm avg_yaw_forearm
## 1                   NA                NA              NA
## 2                   NA                NA              NA
## 3                   NA                NA              NA
## 4                   NA                NA              NA
## 5                   NA                NA              NA
## 6                   NA                NA              NA
##   stddev_yaw_forearm var_yaw_forearm gyros_forearm_x gyros_forearm_y
## 1                 NA              NA            0.03            0.00
## 2                 NA              NA            0.02            0.00
## 3                 NA              NA            0.03           -0.02
## 4                 NA              NA            0.02           -0.02
## 5                 NA              NA            0.02            0.00
## 6                 NA              NA            0.02           -0.02
##   gyros_forearm_z accel_forearm_x accel_forearm_y accel_forearm_z
## 1           -0.02             192             203            -215
## 2           -0.02             192             203            -216
## 3            0.00             196             204            -213
## 4            0.00             189             206            -214
## 5           -0.02             189             206            -214
## 6           -0.03             193             203            -215
##   magnet_forearm_x magnet_forearm_y magnet_forearm_z classe
## 1              -17              654              476      A
## 2              -18              661              473      A
## 3              -18              658              469      A
## 4              -16              658              469      A
## 5              -17              655              473      A
## 6               -9              660              478      A
```

```
##           X user_name raw_timestamp_part_1 raw_timestamp_part_2
## 19617 19617    adelmo           1322832937               588324
## 19618 19618    adelmo           1322832937               588376
## 19619 19619    adelmo           1322832937               596287
## 19620 19620    adelmo           1322832937               636283
## 19621 19621    adelmo           1322832937               964299
## 19622 19622    adelmo           1322832937               972293
##        cvtd_timestamp new_window num_window roll_belt pitch_belt yaw_belt
## 19617 2/12/2011 13:35         no        864       148      -34.7      129
## 19618 2/12/2011 13:35         no        864       147      -34.8      129
## 19619 2/12/2011 13:35         no        864       145      -35.3      130
## 19620 2/12/2011 13:35         no        864       145      -35.5      130
## 19621 2/12/2011 13:35         no        864       143      -35.9      131
## 19622 2/12/2011 13:35        yes        864       143      -36.0      132
##       total_accel_belt kurtosis_roll_belt kurtosis_picth_belt
## 19617               21                                       
## 19618               21                                       
## 19619               19                                       
## 19620               19                                       
## 19621               18                                       
## 19622               18          -1.175902           -1.063259
##       kurtosis_yaw_belt skewness_roll_belt skewness_roll_belt.1
## 19617                                                          
## 19618                                                          
## 19619                                                          
## 19620                                                          
## 19621                                                          
## 19622           #DIV/0!            0.19686            -0.572396
##       skewness_yaw_belt max_roll_belt max_picth_belt max_yaw_belt
## 19617                              NA             NA             
## 19618                              NA             NA             
## 19619                              NA             NA             
## 19620                              NA             NA             
## 19621                              NA             NA             
## 19622           #DIV/0!           132             25         -1.2
##       min_roll_belt min_pitch_belt min_yaw_belt amplitude_roll_belt
## 19617            NA             NA                               NA
## 19618            NA             NA                               NA
## 19619            NA             NA                               NA
## 19620            NA             NA                               NA
## 19621            NA             NA                               NA
## 19622           123             18         -1.2                   9
##       amplitude_pitch_belt amplitude_yaw_belt var_total_accel_belt
## 19617                   NA                                      NA
## 19618                   NA                                      NA
## 19619                   NA                                      NA
## 19620                   NA                                      NA
## 19621                   NA                                      NA
## 19622                    7                  0               5.6268
##       avg_roll_belt stddev_roll_belt var_roll_belt avg_pitch_belt
## 19617            NA               NA            NA             NA
## 19618            NA               NA            NA             NA
## 19619            NA               NA            NA             NA
## 19620            NA               NA            NA             NA
## 19621            NA               NA            NA             NA
## 19622      151.1481           4.7532       22.5926       -33.6259
##       stddev_pitch_belt var_pitch_belt avg_yaw_belt stddev_yaw_belt
## 19617                NA             NA           NA              NA
## 19618                NA             NA           NA              NA
## 19619                NA             NA           NA              NA
## 19620                NA             NA           NA              NA
## 19621                NA             NA           NA              NA
## 19622            1.3952         1.9466     126.8889          2.7503
##       var_yaw_belt gyros_belt_x gyros_belt_y gyros_belt_z accel_belt_x
## 19617           NA         0.37         0.00        -0.62           49
## 19618           NA         0.37        -0.02        -0.67           50
## 19619           NA         0.39        -0.02        -0.67           47
## 19620           NA         0.37         0.00        -0.64           47
## 19621           NA         0.37        -0.02        -0.59           46
## 19622       7.5641         0.35        -0.02        -0.57           42
##       accel_belt_y accel_belt_z magnet_belt_x magnet_belt_y magnet_belt_z
## 19617           25         -195           191           540          -415
## 19618           26         -193           190           552          -412
## 19619           15         -179           192           558          -389
## 19620           13         -177           191           560          -386
## 19621           18         -172           190           565          -370
## 19622           25         -171           194           566          -349
##       roll_arm pitch_arm yaw_arm total_accel_arm var_accel_arm
## 19617    -99.1     -33.7    79.4              48            NA
## 19618    -99.4     -33.8    79.0              47            NA
## 19619    -99.6     -34.5    77.3              45            NA
## 19620    -99.6     -35.1    76.3              44            NA
## 19621    -98.6     -36.7    73.5              41            NA
## 19622    -97.6     -37.7    71.5              41       54.2564
##       avg_roll_arm stddev_roll_arm var_roll_arm avg_pitch_arm
## 19617           NA              NA           NA            NA
## 19618           NA              NA           NA            NA
## 19619           NA              NA           NA            NA
## 19620           NA              NA           NA            NA
## 19621           NA              NA           NA            NA
## 19622     -91.6481          9.1687      84.0649      -37.6519
##       stddev_pitch_arm var_pitch_arm avg_yaw_arm stddev_yaw_arm
## 19617               NA            NA          NA             NA
## 19618               NA            NA          NA             NA
## 19619               NA            NA          NA             NA
## 19620               NA            NA          NA             NA
## 19621               NA            NA          NA             NA
## 19622           3.6161       13.0764     66.3111        15.4797
##       var_yaw_arm gyros_arm_x gyros_arm_y gyros_arm_z accel_arm_x
## 19617          NA        0.31       -0.45        0.28          67
## 19618          NA        0.55       -0.51        0.25          75
## 19619          NA        0.88       -0.71        0.21          52
## 19620          NA        0.98       -0.82        0.23          62
## 19621          NA        1.35       -1.00        0.49          70
## 19622     239.621        1.51       -1.06        0.59          58
##       accel_arm_y accel_arm_z magnet_arm_x magnet_arm_y magnet_arm_z
## 19617        -181        -432          268         -138         -566
## 19618        -184        -415          272         -134         -562
## 19619        -163        -406          288         -112         -559
## 19620        -167        -391          309         -103         -541
## 19621        -164        -359          339          -91         -543
## 19622        -152        -365          362          -84         -539
##       kurtosis_roll_arm kurtosis_picth_arm kurtosis_yaw_arm
## 19617                                                      
## 19618                                                      
## 19619                                                      
## 19620                                                      
## 19621                                                      
## 19622          -1.32631            0.50959         -0.62736
##       skewness_roll_arm skewness_pitch_arm skewness_yaw_arm max_roll_arm
## 19617                                                                 NA
## 19618                                                                 NA
## 19619                                                                 NA
## 19620                                                                 NA
## 19621                                                                 NA
## 19622          -0.51721           -1.26872          -0.7715        -33.7
##       max_picth_arm max_yaw_arm min_roll_arm min_pitch_arm min_yaw_arm
## 19617            NA          NA           NA            NA          NA
## 19618            NA          NA           NA            NA          NA
## 19619            NA          NA           NA            NA          NA
## 19620            NA          NA           NA            NA          NA
## 19621            NA          NA           NA            NA          NA
## 19622          79.5          49        -43.5          27.5          25
##       amplitude_roll_arm amplitude_pitch_arm amplitude_yaw_arm
## 19617                 NA                  NA                NA
## 19618                 NA                  NA                NA
## 19619                 NA                  NA                NA
## 19620                 NA                  NA                NA
## 19621                 NA                  NA                NA
## 19622                9.8                  52                24
##       roll_dumbbell pitch_dumbbell yaw_dumbbell kurtosis_roll_dumbbell
## 19617      38.60998      -22.79150    -111.6131                       
## 19618      36.41318      -22.86197    -113.4998                       
## 19619      35.15281      -22.97191    -114.5256                       
## 19620      30.06028      -20.99018    -120.0318                       
## 19621      22.86333      -21.75662    -125.2459                       
## 19622      20.80000      -19.70000    -128.2000                -1.1322
##       kurtosis_picth_dumbbell kurtosis_yaw_dumbbell skewness_roll_dumbbell
## 19617                                                                     
## 19618                                                                     
## 19619                                                                     
## 19620                                                                     
## 19621                                                                     
## 19622                 -0.7225               #DIV/0!                 0.0955
##       skewness_pitch_dumbbell skewness_yaw_dumbbell max_roll_dumbbell
## 19617                                                              NA
## 19618                                                              NA
## 19619                                                              NA
## 19620                                                              NA
## 19621                                                              NA
## 19622                  0.1057               #DIV/0!             -19.7
##       max_picth_dumbbell max_yaw_dumbbell min_roll_dumbbell
## 19617                 NA                                 NA
## 19618                 NA                                 NA
## 19619                 NA                                 NA
## 19620                 NA                                 NA
## 19621                 NA                                 NA
## 19622                -92             -1.1             -33.1
##       min_pitch_dumbbell min_yaw_dumbbell amplitude_roll_dumbbell
## 19617                 NA                                       NA
## 19618                 NA                                       NA
## 19619                 NA                                       NA
## 19620                 NA                                       NA
## 19621                 NA                                       NA
## 19622             -128.2             -1.1                   13.41
##       amplitude_pitch_dumbbell amplitude_yaw_dumbbell total_accel_dumbbell
## 19617                       NA                                          19
## 19618                       NA                                          19
## 19619                       NA                                          18
## 19620                       NA                                          19
## 19621                       NA                                          19
## 19622                     36.2                      0                   19
##       var_accel_dumbbell avg_roll_dumbbell stddev_roll_dumbbell
## 19617                 NA                NA                   NA
## 19618                 NA                NA                   NA
## 19619                 NA                NA                   NA
## 19620                 NA                NA                   NA
## 19621                 NA                NA                   NA
## 19622             0.4217           37.3418               9.7828
##       var_roll_dumbbell avg_pitch_dumbbell stddev_pitch_dumbbell
## 19617                NA                 NA                    NA
## 19618                NA                 NA                    NA
## 19619                NA                 NA                    NA
## 19620                NA                 NA                    NA
## 19621                NA                 NA                    NA
## 19622           95.7038           -26.8182                4.0098
##       var_pitch_dumbbell avg_yaw_dumbbell stddev_yaw_dumbbell
## 19617                 NA               NA                  NA
## 19618                 NA               NA                  NA
## 19619                 NA               NA                  NA
## 19620                 NA               NA                  NA
## 19621                 NA               NA                  NA
## 19622            16.0788        -109.9671              9.7475
##       var_yaw_dumbbell gyros_dumbbell_x gyros_dumbbell_y gyros_dumbbell_z
## 19617               NA             0.34            -0.31            -0.51
## 19618               NA             0.32            -0.26            -0.36
## 19619               NA             0.24            -0.24             0.05
## 19620               NA             0.22            -0.27             0.21
## 19621               NA             0.13            -0.14             0.34
## 19622          95.0143             0.02             0.02             0.36
##       accel_dumbbell_x accel_dumbbell_y accel_dumbbell_z magnet_dumbbell_x
## 19617              -42               70             -167              -624
## 19618              -42               66             -168              -618
## 19619              -41               62             -164              -618
## 19620              -38               54             -170              -621
## 19621              -40               42             -176              -628
## 19622              -36               38             -176              -627
##       magnet_dumbbell_y magnet_dumbbell_z roll_forearm pitch_forearm
## 19617               127                 8            0             0
## 19618               134                 0            0             0
## 19619               116                 7            0             0
## 19620               113                -9            0             0
## 19621               116                 0            0             0
## 19622               119                 2            0             0
##       yaw_forearm kurtosis_roll_forearm kurtosis_picth_forearm
## 19617           0                                             
## 19618           0                                             
## 19619           0                                             
## 19620           0                                             
## 19621           0                                             
## 19622           0               #DIV/0!                #DIV/0!
##       kurtosis_yaw_forearm skewness_roll_forearm skewness_pitch_forearm
## 19617                                                                  
## 19618                                                                  
## 19619                                                                  
## 19620                                                                  
## 19621                                                                  
## 19622              #DIV/0!               #DIV/0!                #DIV/0!
##       skewness_yaw_forearm max_roll_forearm max_picth_forearm
## 19617                                    NA                NA
## 19618                                    NA                NA
## 19619                                    NA                NA
## 19620                                    NA                NA
## 19621                                    NA                NA
## 19622              #DIV/0!                0                 0
##       max_yaw_forearm min_roll_forearm min_pitch_forearm min_yaw_forearm
## 19617                               NA                NA                
## 19618                               NA                NA                
## 19619                               NA                NA                
## 19620                               NA                NA                
## 19621                               NA                NA                
## 19622         #DIV/0!                0                 0         #DIV/0!
##       amplitude_roll_forearm amplitude_pitch_forearm amplitude_yaw_forearm
## 19617                     NA                      NA                      
## 19618                     NA                      NA                      
## 19619                     NA                      NA                      
## 19620                     NA                      NA                      
## 19621                     NA                      NA                      
## 19622                      0                       0               #DIV/0!
##       total_accel_forearm var_accel_forearm avg_roll_forearm
## 19617                  27                NA               NA
## 19618                  29                NA               NA
## 19619                  29                NA               NA
## 19620                  29                NA               NA
## 19621                  32                NA               NA
## 19622                  33          30.10541                0
##       stddev_roll_forearm var_roll_forearm avg_pitch_forearm
## 19617                  NA               NA                NA
## 19618                  NA               NA                NA
## 19619                  NA               NA                NA
## 19620                  NA               NA                NA
## 19621                  NA               NA                NA
## 19622                   0                0                 0
##       stddev_pitch_forearm var_pitch_forearm avg_yaw_forearm
## 19617                   NA                NA              NA
## 19618                   NA                NA              NA
## 19619                   NA                NA              NA
## 19620                   NA                NA              NA
## 19621                   NA                NA              NA
## 19622                    0                 0               0
##       stddev_yaw_forearm var_yaw_forearm gyros_forearm_x gyros_forearm_y
## 19617                 NA              NA            1.75           -1.91
## 19618                 NA              NA            1.73           -1.75
## 19619                 NA              NA            1.59           -1.36
## 19620                 NA              NA            1.54           -1.20
## 19621                 NA              NA            1.48           -0.90
## 19622                  0               0            1.38           -0.64
##       gyros_forearm_z accel_forearm_x accel_forearm_y accel_forearm_z
## 19617           -0.38            -255             -50             -30
## 19618           -0.25            -271             -68             -37
## 19619            0.00            -271             -91             -43
## 19620            0.05            -263             -99             -45
## 19621            0.05            -270            -141             -51
## 19622            0.08            -278            -159             -52
##       magnet_forearm_x magnet_forearm_y magnet_forearm_z classe
## 19617             -226             -570               27      E
## 19618             -205             -587                6      E
## 19619             -151             -635              -36      E
## 19620             -116             -654              -70      E
## 19621              -68             -678              -98      E
## 19622              -60             -686             -110      E
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
barplot(xx,col="grey")
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6-1.png) 
```

