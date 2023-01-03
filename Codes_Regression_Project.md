Applied Regression Analysis
================
2022-12-20

``` r
library(mclust)
```

    ## Warning: package 'mclust' was built under R version 4.2.2

    ## Package 'mclust' version 6.0.0
    ## Type 'citation("mclust")' for citing this R package in publications.

``` r
head(thyroid)
```

    ##   Diagnosis RT3U   T4  T3 TSH DTSH
    ## 1    Normal  107 10.1 2.2 0.9  2.7
    ## 2    Normal  113  9.9 3.1 2.0  5.9
    ## 3    Normal  127 12.9 2.4 1.4  0.6
    ## 4    Normal  109  5.3 1.6 1.4  1.5
    ## 5    Normal  105  7.3 1.5 1.5 -0.1
    ## 6    Normal  105  6.1 2.1 1.4  7.0

``` r
model_1= lm(TSH ~ T3 + T4 + DTSH + RT3U + Diagnosis, data=thyroid)
summary(model_1)
```

    ## 
    ## Call:
    ## lm(formula = TSH ~ T3 + T4 + DTSH + RT3U + Diagnosis, data = thyroid)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -10.621  -0.822  -0.094   0.517  42.442 
    ## 
    ## Coefficients:
    ##                 Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)     10.16710    3.92043   2.593   0.0102 *  
    ## T3              -0.10635    0.34952  -0.304   0.7612    
    ## T4              -0.25666    0.13671  -1.877   0.0619 .  
    ## DTSH             0.08186    0.05268   1.554   0.1217    
    ## RT3U             0.01935    0.02991   0.647   0.5185    
    ## DiagnosisNormal -8.65124    1.45573  -5.943 1.17e-08 ***
    ## DiagnosisHyper  -6.02693    2.46207  -2.448   0.0152 *  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.566 on 208 degrees of freedom
    ## Multiple R-squared:  0.4585, Adjusted R-squared:  0.4429 
    ## F-statistic: 29.36 on 6 and 208 DF,  p-value: < 2.2e-16
