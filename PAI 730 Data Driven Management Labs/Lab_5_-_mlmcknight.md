# Lab 5 - Matt_McKnight
Matt McKnight  
February 25, 2017  

# Plot Function

```r
library(Lahman)
data(Teams)
```

## QUESTION 1
###	Drop all of the data before 1990.

```r
which(Teams$yearID == 1990)
```

```
##  [1] 2048 2049 2050 2051 2052 2053 2054 2055 2056 2057 2058 2059 2060 2061
## [15] 2062 2063 2064 2065 2066 2067 2068 2069 2070 2071 2072 2073
```

```r
Teams_90 <- Teams[-c(1:2047), ]
```


## QUESTION 2
### Examine the relationship between Hits and Wins using a scatterplot. Use meaningful labels and a visually appealing style.

```r
plot(
      x=Teams_90$H, y=Teams_90$W, 
      main="Key Performance Indicators: Offense",
      xlab="Total Hits Per Season Per Team", ylab="Total Wins",
      pch=19,
      col="darkorchid1",
      cex=.75,
      bty="L"
      )
```

![](Lab_5_-_Matt_McKnight_files/figure-html/unnamed-chunk-3-1.png)<!-- -->



## QUESTION 3
### Annotate two outliers on the graph with the teamID. 

```r
#identify ( Teams_90$H, Teams_90$W )

plot(
      x=Teams_90$H, y=Teams_90$W, 
      main="Key Performance Indicators: Offense",
      xlab="Total Hits Per Season Per Team", ylab="Total Wins",
      pch=19,
      col="darkorchid1",
      cex=.75,
      bty="L",

      text( x=Teams_90$H[c(333,379)], y=Teams_90$W[c(333,379)],
      labels=Teams_90$teamID[c(333,379)], pos=4 )
      )
```

![](Lab_5_-_Matt_McKnight_files/figure-html/unnamed-chunk-4-1.png)<!-- -->



## QUESTION 4
### Examine the relationship between ERA and Wins using a scatterplot. Use meaningful labels and a visually appealing style.

```r
plot(
      x=Teams_90$ERA, y=Teams_90$W, 
      main="Key Performance Indicators: Offense",
      xlab="Earned Run Average Per Season Per Team", ylab="Total Wins",
      pch=19,
      col="paleturquoise3",
      cex=.75,
      bty="L"
      )
```

![](Lab_5_-_Matt_McKnight_files/figure-html/unnamed-chunk-5-1.png)<!-- -->



## QUESTION 5
### Annotate two outliers on the graph with the teamID.

```r
#identify ( Teams_90$ERA, Teams_90$W )

plot(
      x=Teams_90$ERA, y=Teams_90$W, 
      main="Key Performance Indicators: Offense",
      xlab="Earned Run Average Per Season Per Team", ylab="Total Wins",
      pch=19,
      col="paleturquoise3",
      cex=.75,
      bty="L",

      text( x=Teams_90$ERA[c(333,379)], y=Teams_90$W[c(333,379)],
      labels=Teams_90$teamID[c(333,379)], pos=2 )
      )
```

![](Lab_5_-_Matt_McKnight_files/figure-html/unnamed-chunk-6-1.png)<!-- -->


## QUESTION 6 - BONUS
### Add a trend line to the scatterplot to highlight the relationship.

```r
plot(
      x=Teams_90$ERA, y=Teams_90$W, 
      main="Key Performance Indicators: Offense",
      xlab="Earned Run Average Per Season Per Team", ylab="Total Wins",
      pch=19,
      col="paleturquoise3",
      cex=.75,
      bty="L",

      text( x=Teams_90$ERA[c(333,379)], y=Teams_90$W[c(333,379)],
      labels=Teams_90$teamID[c(333,379)], pos=2 )
      )

lines(lowess(Teams_90$ERA,Teams_90$W), col="darkblue", lwd=3)
```

![](Lab_5_-_Matt_McKnight_files/figure-html/unnamed-chunk-7-1.png)<!-- -->





