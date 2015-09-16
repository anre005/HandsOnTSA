

# Downloading Data from Quandl Databases

The workhorse is the `Quandl()` function.

```r
> Quandl(code, type = c("raw", "ts", "zoo", "xts", "timeSeries"), start_date,
+   end_date, transformation = c("", "diff", "rdiff", "normalize", "cumul",
+   "rdiff_from"), collapse = c("", "daily", "weekly", "monthly", "quarterly",
+   "annual"), sort = c("desc", "asc"), meta = FALSE,
+   authcode = Quandl.auth(), ...)
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
'data.frame':	1194 obs. of  6 variables:
 $ Date  : Date, format: "2015-09-15" "2015-09-14" ...
 $ Open  : num  85.8 86 86.4 85 86.7 ...
 $ High  : num  87.8 86.2 86.4 87 88.2 ...
 $ Low   : num  85.8 85 85.1 84.6 85.4 ...
 $ Close : num  87.7 85.5 86.1 86.5 85.4 ...
 $ Volume: num  5164 1897 4836 9095 11818 ...
 - attr(*, "freq")= chr "daily"
```


```r
> head(bmw)
```

```
        Date  Open  High   Low Close Volume
1 2015-09-15 85.85 87.81 85.76 87.65   5164
2 2015-09-14 86.00 86.24 84.98 85.55   1897
3 2015-09-11 86.40 86.40 85.10 86.07   4836
4 2015-09-10 85.05 87.00 84.60 86.48   9095
5 2015-09-09 86.70 88.23 85.38 85.38  11818
6 2015-09-08 81.30 84.87 81.20 84.25   5177
```


```r
> tail(bmw)
```

```
           Date  Open  High   Low Close Volume
1189 2011-01-10 58.90 59.26 58.43 58.56  13532
1190 2011-01-07 59.55 60.07 58.83 59.47  15508
1191 2011-01-06 60.00 61.02 59.70 59.83   8911
1192 2011-01-05 60.40 60.55 58.42 60.06  21851
1193 2011-01-04 61.44 61.57 60.09 60.77  30843
1194 2011-01-03 59.70 61.54 59.70 61.31  19869
```


```r
> summary(bmw)
```

```
      Date                 Open             High             Low        
 Min.   :2011-01-03   Min.   :  0.00   Min.   : 46.64   Min.   : 43.56  
 1st Qu.:2012-02-28   1st Qu.: 61.19   1st Qu.: 61.78   1st Qu.: 60.50  
 Median :2013-05-06   Median : 72.06   Median : 72.64   Median : 71.33  
 Mean   :2013-05-05   Mean   : 75.43   Mean   : 76.30   Mean   : 74.55  
 3rd Qu.:2014-07-09   3rd Qu.: 87.58   3rd Qu.: 88.38   3rd Qu.: 86.14  
 Max.   :2015-09-15   Max.   :122.89   Max.   :123.70   Max.   :120.22  
                      NA's   :2        NA's   :2        NA's   :2       
     Close            Volume      
 Min.   : 44.94   Min.   :     0  
 1st Qu.: 61.28   1st Qu.:  5704  
 Median : 71.97   Median :  9478  
 Mean   : 75.45   Mean   : 12346  
 3rd Qu.: 87.30   3rd Qu.: 15208  
 Max.   :123.00   Max.   :185389  
                                  
```
