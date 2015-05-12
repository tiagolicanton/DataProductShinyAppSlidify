---
title       : ShinyApp for mtcars linear model training
subtitle    : 
author      : Tiago Li
job         : 
framework   : io2012       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : mathjax            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Motivation

Remember in *Linear Regression* project we are asked to train a model to predict `mpg` based on `mtcars` dataset? 


```r
data(mtcars)
head(mtcars,3)
```

```
##                mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4     21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag 21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710    22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
```

--- .class #id 

## Linear model training in R

It's very straight forward to train a model using predictor(s) from the dataset and plot the result in R Studio. However it's tedious to try out every combination and type them in command line. What if the user knows nothing about R?


```r
fit <- lm(mpg~cyl,data=mtcars);
plot(mpg~cyl,data=mtcars);abline(fit)
```

<img src="assets/fig/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

--- 

## Linear model training with ShinyApp

My [ShinyApp](https://tiagolicanton.shinyapps.io/data_prod/) provides an interactive way to

1. to select/deselect predictors 
2. present trained model immediately
3. record the best $R^2$ so far

---

## Usage
The only input widget is the checkbox in the left side, play with it and the corresponding model will be calculated accordingly. The model with max $R^2$ will be recorded in case you forget the best model so far. Lastly, please note that $R^2_{max}$ is not the indicator of how good the model is. User should make a tradeoff between model precision and simplicity in his/her discretion. 

<img src="image/screenshot.png" style="width: 800px;"/>
