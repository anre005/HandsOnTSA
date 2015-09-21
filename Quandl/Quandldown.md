

# Downloading Data from Quandl Databases

The workhorse is the `Quandl()` function.

```r
> Quandl(code, type = c("raw", "ts", "zoo", "xts", "timeSeries"),
+        transform = c("", "diff", "rdiff", "normalize", "cumul", "rdiff_from"),
+        collapse = c("", "daily", "weekly", "monthly", "quarterly", "annual"),
+        order = c("desc", "asc"), meta = FALSE, force_irregular = FALSE, ...)
```

* `code`: dataset code on Quandl specified as a string or an array of strings
* `type`: type of data returned
* `transform`: apply Quandl API data transformations
* `order`: select if data returned by `R` is in ascending or descending format
* `meta`: adds meta data as an attribute to the returned data
* `force_irregular`: if set to `TRUE`, forces the index of the data to be of date format `yyyy-mm-dd`
* `...`: additional named values that are interpreted as Quandl API parameters. Please see [https://www.quandl.com/docs/api#retrieve-data-and-metadata](https://www.quandl.com/docs/api#retrieve-data-and-metadata) for a full list of parameters.
                     
You can start downloading data by only using the `code` argument.
Codes can be found on the website of [Quandl](https://www.quandl.com) 
or you can query the databases directly within `R`. (see chapter *Querying Quandl Databases from R Console*).
Suppose we want the data for the automobile manufacturer *BMW* from Frankfurt Stock Exchange
using Google Finance as database.


```r
> bmw <- Quandl("GOOG/FRA_BMW")
```


```r
> str(bmw)
```

```
'data.frame':	1197 obs. of  6 variables:
 $ Date  : Date, format: "2015-09-18" "2015-09-17" ...
 $ Open  : num  88.3 87.8 87.7 85.8 86 ...
 $ High  : num  88.3 88.5 88.7 87.8 86.2 ...
 $ Low   : num  84.9 87.8 87 85.8 85 ...
 $ Close : num  86 88 87.6 87.7 85.5 ...
 $ Volume: num  10712 3715 3761 5164 1897 ...
 - attr(*, "freq")= chr "daily"
```


```r
> head(bmw)
```

```
        Date  Open  High   Low Close Volume
1 2015-09-18 88.35 88.35 84.91 85.97  10712
2 2015-09-17 87.80 88.48 87.80 88.04   3715
3 2015-09-16 87.70 88.71 86.95 87.64   3761
4 2015-09-15 85.85 87.81 85.76 87.65   5164
5 2015-09-14 86.00 86.24 84.98 85.55   1897
6 2015-09-11 86.40 86.40 85.10 86.07   4836
```


```r
> tail(bmw)
```

```
           Date  Open  High   Low Close Volume
1192 2011-01-10 58.90 59.26 58.43 58.56  13532
1193 2011-01-07 59.55 60.07 58.83 59.47  15508
1194 2011-01-06 60.00 61.02 59.70 59.83   8911
1195 2011-01-05 60.40 60.55 58.42 60.06  21851
1196 2011-01-04 61.44 61.57 60.09 60.77  30843
1197 2011-01-03 59.70 61.54 59.70 61.31  19869
```


```r
> summary(bmw)
```

```
      Date                 Open             High             Low        
 Min.   :2011-01-03   Min.   :  0.00   Min.   : 46.64   Min.   : 43.56  
 1st Qu.:2012-02-29   1st Qu.: 61.21   1st Qu.: 61.79   1st Qu.: 60.52  
 Median :2013-05-08   Median : 72.09   Median : 72.67   Median : 71.37  
 Mean   :2013-05-07   Mean   : 75.46   Mean   : 76.33   Mean   : 74.58  
 3rd Qu.:2014-07-14   3rd Qu.: 87.70   3rd Qu.: 88.47   3rd Qu.: 86.28  
 Max.   :2015-09-18   Max.   :122.89   Max.   :123.70   Max.   :120.22  
                      NA's   :2        NA's   :2        NA's   :2       
     Close            Volume      
 Min.   : 44.94   Min.   :     0  
 1st Qu.: 61.29   1st Qu.:  5693  
 Median : 71.99   Median :  9477  
 Mean   : 75.48   Mean   : 12330  
 3rd Qu.: 87.50   3rd Qu.: 15200  
 Max.   :123.00   Max.   :185389  
                                  
```
