

# Solutions 


```r
> # Solution Exercise 1
> Quandl.search("retailer sales", source = "FRED")
```

```
Retail Sales (Discontinued Series)
Code: FRED/RETAIL
Desc: Millions of Dollars Seasonally Adjusted, Discontinued Series 
Freq: monthly
Cols: c("Date", "Value")

Retailers Sales
Code: FRED/RETAILSMSA
Desc: Millions of Dollars Seasonally Adjusted 
Freq: monthly
Cols: c("Date", "Value")

Retailers Sales
Code: FRED/RETAILSMNSA
Desc: Millions of Dollars Not Seasonally Adjusted 
Freq: monthly
Cols: c("Date", "Value")
```

```r
> # Solution Exercise 2
> sales <- Quandl("FRED/RETAILSMNSA", type = "ts")
> sales_stl <- stl(sales, s.window = "periodic")
> sales_adj <- sales_stl$time.series[,"remainder"]
```
