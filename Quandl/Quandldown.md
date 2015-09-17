

# Downloading Data from Quandl Databases

The workhorse is the `Quandl()` function.

```r
> Quandl(code, type = c("raw", "ts", "zoo", "xts", "timeSeries"), start_date,
+        end_date, transformation = c("", "diff", "rdiff", "normalize", "cumul",
+        "rdiff_from"), collapse = c("", "daily", "weekly", "monthly", "quarterly",
+        "annual"), sort = c("desc", "asc"), meta = FALSE,
+        authcode = Quandl.auth(), ...)
```

You can start downloading data by only using the `code` argument.
Codes can be found on the website of [Quandl](https://www.quandl.com) 
or you can query the databases directly within `R`. (see chapter 1.4).
Suppose we want the data for the automobile manufacturer *BMW* from Frankfurt Stock Exchange
using Google Finance as database.


```r
> bmw <- Quandl("GOOG/FRA_BMW")
```


```r
> str(bmw)
```

```
'data.frame':	1195 obs. of  6 variables:
 $ Date  : Date, format: "2015-09-16" "2015-09-15" ...
 $ Open  : num  87.7 85.8 86 86.4 85 ...
 $ High  : num  88.7 87.8 86.2 86.4 87 ...
 $ Low   : num  87 85.8 85 85.1 84.6 ...
 $ Close : num  87.6 87.7 85.5 86.1 86.5 ...
 $ Volume: num  3761 5164 1897 4836 9095 ...
 - attr(*, "freq")= chr "daily"
```


```r
> head(bmw)
```

```
        Date  Open  High   Low Close Volume
1 2015-09-16 87.70 88.71 86.95 87.64   3761
2 2015-09-15 85.85 87.81 85.76 87.65   5164
3 2015-09-14 86.00 86.24 84.98 85.55   1897
4 2015-09-11 86.40 86.40 85.10 86.07   4836
5 2015-09-10 85.05 87.00 84.60 86.48   9095
6 2015-09-09 86.70 88.23 85.38 85.38  11818
```


```r
> tail(bmw)
```

```
           Date  Open  High   Low Close Volume
1190 2011-01-10 58.90 59.26 58.43 58.56  13532
1191 2011-01-07 59.55 60.07 58.83 59.47  15508
1192 2011-01-06 60.00 61.02 59.70 59.83   8911
1193 2011-01-05 60.40 60.55 58.42 60.06  21851
1194 2011-01-04 61.44 61.57 60.09 60.77  30843
1195 2011-01-03 59.70 61.54 59.70 61.31  19869
```


```r
> summary(bmw)
```

```
      Date                 Open             High             Low        
 Min.   :2011-01-03   Min.   :  0.00   Min.   : 46.64   Min.   : 43.56  
 1st Qu.:2012-02-28   1st Qu.: 61.20   1st Qu.: 61.78   1st Qu.: 60.50  
 Median :2013-05-07   Median : 72.09   Median : 72.64   Median : 71.35  
 Mean   :2013-05-06   Mean   : 75.44   Mean   : 76.31   Mean   : 74.56  
 3rd Qu.:2014-07-10   3rd Qu.: 87.68   3rd Qu.: 88.46   3rd Qu.: 86.19  
 Max.   :2015-09-16   Max.   :122.89   Max.   :123.70   Max.   :120.22  
                      NA's   :2        NA's   :2        NA's   :2       
     Close            Volume      
 Min.   : 44.94   Min.   :     0  
 1st Qu.: 61.28   1st Qu.:  5696  
 Median : 71.98   Median :  9477  
 Mean   : 75.47   Mean   : 12339  
 3rd Qu.: 87.41   3rd Qu.: 15206  
 Max.   :123.00   Max.   :185389  
                                  
```
