Linear Regression Prediction of Dax from Cac
========================================================
author: V Oliveira
date: 14/12/2017
autosize: true


Developing Data Products, Project Assignment Week 4
========================================================

Please check out my Shiny App on how to predict the value 
of the german equity index Dax by means of a linear regression 
from the french equity index CAC. The app can be found here: <https://datasailing.shinyapps.io/appddp_pa4/>.

The Data
========================================================

The Data used in the development of the app is the standard dataset from R called "EuStockMarkets". 
But only the DAX and CAC variables are used.

```r
d <- as.data.frame(EuStockMarkets)
str(d)
```

```
'data.frame':	1860 obs. of  4 variables:
 $ DAX : num  1629 1614 1607 1621 1618 ...
 $ SMI : num  1678 1688 1679 1684 1687 ...
 $ CAC : num  1773 1750 1718 1708 1723 ...
 $ FTSE: num  2444 2460 2448 2470 2485 ...
```


Server Calculations and Scatterplot of Dax and Cac
========================================================

```r
d <- as.data.frame(EuStockMarkets)
model <- lm(DAX ~ CAC, data = d)
cacInput <- 3000    
    
modelpred <- predict(model, newdata = data.frame(CAC = cacInput))
```
        

<img src="DDP_PA4-figure/unnamed-chunk-3-1.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />


Instructions and Reproducibility
========================================================

The full instructions for running the app can be found on the app
itself and it is easy to follow and interact with it.

The full code for reproducing the app can be found in the github repository below.
The code is split in 2 files, a ui.R and a server.R file.

<https://github.com/datasailing/ShinyApp-DDP-Assignment>.
