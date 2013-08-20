Lognormal Median Estimators
==========================
*Published to [RPubs](http://rpubs.com/Zhenglei/lognormalMedian)*













Now the actual simulation:







```r
require(animation)
# saveVideo({ allres <-
# anim_LNestimator(mu=log(50),cv=2,N=c(5,10,20,100,300,1000),mcN=10000) },
# video.name='anim_SampleSize.mp4')
saveGIF({
    allres <- anim_LNestimator(mu = log(50), cv = 2, N = c(5, 10, 20, 100, 300, 
        1000), mcN = 1e+05)
}, movie.name = "anim_SampleSize.gif")
```

```
## Warning: running command 'convert --version' had status 4
```

```
## I cannot find ImageMagick with convert = "convert"
```

```
## Warning: ImageMagick not installed yet!
```

```
## NULL
```

 ![Animation SampleSize](anim_SampleSize.gif)



![Animation CV](anim_CV.gif)


```r
pdf("trendN.pdf")
plot_LNestimator(allres, cv = 2, N = c(5, 10, 20, 100, 300, 1000), trend = "N")
```

```
## Error: could not find function "ldply"
```

```r
dev.off()
```

```
## pdf 
##   2
```

```r
pdf("trendCV.pdf")
plot_LNestimator(allresCV, cv = c(0.1, seq(0.2, 2, by = 0.2)), N = 5, trend = "CV")
```

```
## Error: could not find function "ldply"
```

```r
dev.off()
```

```
## pdf 
##   2
```


# Cross Validated Question:
1. [The question](http://stats.stackexchange.com/questions/64587/when-to-use-sample-median-as-an-estimator-for-the-median-of-a-lognormal-distribu)

2. [Does median-unbiased estimator minimize ]

Monte Carlo evaluation of the proposed estimator demonstrates that...rel-
ative efficiency gains increasing with the degree of endogeneity... We also evaluate the robustness of the median unbiased estimator to the choice of a loss function and find that it retains desirable characteristics under asymmetric losses, in contrast to
some of the alternative procedures.

Turning to empirical applicability we note that the property of median unbiased-
ness characterizes estimators that are as likely to underestimate as to overestimate
the true value, a highly desirable characteristic when any systematic biases affect
the estimation. It is particularly relevant in forecasting, a setting in which median
unbiased estimation results in same frequency of positive and negative forecast er-
rors





# Gather Materials

* [Modes, Medians and Means: A Unifying Perspective](http://www.johnmyleswhite.com/notebook/2013/03/22/modes-medians-and-means-an-unifying-perspective/)

* [Shiny Talk by Joe Chung](https://github.com/jcheng5/seattle-meetup)

* [Writing docx files in R](https://github.com/davidgohel/R2DOCX)

* [R plot resolution](http://stackoverflow.com/questions/8166931/plots-with-good-resolution-for-printing-and-screen-display)



