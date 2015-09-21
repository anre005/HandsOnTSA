# Solutions




```r
> # Solution Exercise 1
> Quandl.search("S&P 500", database_code = "YAHOO")
```

```
SPDR S&P 500 (SPY)
Code: YAHOO/INDEX_SPY
Desc: SPY: SPDR S&P 500 (SPY)
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close

S&P 500 Index
Code: YAHOO/INDEX_GSPC
Desc: GSPC: S&P 500 Index. The S&P 500, or the Standard & Poor's 500, is an American stock market index based on the market capitalizations of 500 large companies having common stock listed on the NYSE or NASDAQ.
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close

S27: SPDR S&P500 10US$
Code: YAHOO/SI_S27
Desc:  Currency: SGD
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close

I17: IS S&P500 10US$
Code: YAHOO/SI_I17
Desc: There is no Profile data available for I17.SI. Currency: SGD
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close

MDSRX: Blackrock S&P 500 Index A
Code: YAHOO/FUND_MDSRX
Desc: The investment seeks to match the performance of the Standard & Poor&#39;sÂ® 500 Index (the 'S&P 500') as closely as possible before the deduction of fund expenses.
 The fund is a 'feeder' fund that invests all of its assets in Master S&P 500 Index Series of Quantitative Master Series LLC, which has the same investment objective and strategies as the fund. It will be substantially invested in securities in the S&P 500, and will invest, under normal circumstances, at least 80% of its assets in securities or other financial instruments that are components of or have economic characteristics similar to the securities included in the S&P 500.
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close

S&P 500 Dividend Aristocrats (^SPDAUDP)
Code: YAHOO/SPDAUDP
Desc: This dataset has no description.
Freq: daily
Cols: Date | Open | High | Low | Close

S&P 500 Managed Distribution In (^SPXMDUT)
Code: YAHOO/SPXMDUT
Desc: This dataset has no description.
Freq: daily
Cols: Date | Open | High | Low | Close

S&P 500 Dividend Aristocrats (T (^SPDAUDT)
Code: YAHOO/SPDAUDT
Desc: This dataset has no description.
Freq: daily
Cols: Date | Open | High | Low | Close

S&P 500 Managed Distribution In (^SPXMDUP)
Code: YAHOO/SPXMDUP
Desc: This dataset has no description.
Freq: daily
Cols: Date | Open | High | Low | Close

Ishares S&P 500 (IVV.AX)
Code: YAHOO/ASX_IVV_AX
Desc: Historical stock prices for Ishares S&P 500 (IVV.AX). The fund invests at least 90% of assets in S&P 500 index securities. The index measures the performance of the large-capitalization sector of the U.S. equity market. As of May 31, 2010, the index included approximately 75% of the market capitalization of all publicly-traded U.S. equity securities.
Freq: daily
Cols: Date | Open | High | Low | Close | Volume | Adjusted Close
```

```r
> sp500 <- Quandl("YAHOO/INDEX_GSPC.4",
+                 start_date = "2010-01-01", end_date = "2014-12-31",
+                 order = "asc")
> 
> close_prices <- sp500[,"Close"]
> 
> # Solution Exercise 2
> plot(close_prices, type = "l") # Random Walk (with drift)
```

<img src="figure/unnamed-chunk-1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

```r
> plot(log(close_prices), type = "l") # Random Walk (with drift)
```

<img src="figure/unnamed-chunk-1-2.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

```r
> log_returns <- diff(log(close_prices))
> plot(log_returns, type = "l")
```

<img src="figure/unnamed-chunk-1-3.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

```r
> acf(log_returns)
```

<img src="figure/unnamed-chunk-1-4.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

```r
> acf(log_returns^2)
```

<img src="figure/unnamed-chunk-1-5.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

```r
> # Solution Exercise 3
> garch_fit <- garchFit(formula = ~ garch(1,1), data = log_returns,
+                       include.mean = FALSE, trace = FALSE)
> 
> fGarch::summary(garch_fit)
```

```

Title:
 GARCH Modelling 

Call:
 garchFit(formula = ~garch(1, 1), data = log_returns, include.mean = FALSE, 
    trace = FALSE) 

Mean and Variance Equation:
 data ~ garch(1, 1)
<environment: 0x91e6218>
 [data = log_returns]

Conditional Distribution:
 norm 

Coefficient(s):
     omega      alpha1       beta1  
3.4478e-06  1.3105e-01  8.3410e-01  

Std. Errors:
 based on Hessian 

Error Analysis:
        Estimate  Std. Error  t value Pr(>|t|)    
omega  3.448e-06   8.287e-07    4.161 3.17e-05 ***
alpha1 1.310e-01   2.094e-02    6.257 3.92e-10 ***
beta1  8.341e-01   2.310e-02   36.109  < 2e-16 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Log Likelihood:
 4171.777    normalized:  3.318836 

Description:
 Mon Sep 21 23:55:09 2015 by user:  


Standardised Residuals Tests:
                                Statistic p-Value     
 Jarque-Bera Test   R    Chi^2  105.2718  0           
 Shapiro-Wilk Test  R    W      0.980603  6.029324e-12
 Ljung-Box Test     R    Q(10)  10.61118  0.3886017   
 Ljung-Box Test     R    Q(15)  14.0323   0.523081    
 Ljung-Box Test     R    Q(20)  16.99841  0.6530769   
 Ljung-Box Test     R^2  Q(10)  18.928    0.04118679  
 Ljung-Box Test     R^2  Q(15)  25.2936   0.04613669  
 Ljung-Box Test     R^2  Q(20)  28.62356  0.0954406   
 LM Arch Test       R    TR^2   20.3511   0.06072906  

Information Criterion Statistics:
      AIC       BIC       SIC      HQIC 
-6.632898 -6.620639 -6.632910 -6.628291 
```

```r
> garch_fit_std <- garchFit(formula = ~ garch(1,1), data = log_returns,
+                           cond.dist = "std", include.mean = FALSE, trace = FALSE)
> 
> fGarch::summary(garch_fit_std)
```

```

Title:
 GARCH Modelling 

Call:
 garchFit(formula = ~garch(1, 1), data = log_returns, cond.dist = "std", 
    include.mean = FALSE, trace = FALSE) 

Mean and Variance Equation:
 data ~ garch(1, 1)
<environment: 0x7a22e90>
 [data = log_returns]

Conditional Distribution:
 std 

Coefficient(s):
     omega      alpha1       beta1       shape  
3.4572e-06  1.3286e-01  8.3737e-01  5.7242e+00  

Std. Errors:
 based on Hessian 

Error Analysis:
        Estimate  Std. Error  t value Pr(>|t|)    
omega  3.457e-06   1.046e-06    3.305  0.00095 ***
alpha1 1.329e-01   2.686e-02    4.946 7.58e-07 ***
beta1  8.374e-01   2.784e-02   30.075  < 2e-16 ***
shape  5.724e+00   1.027e+00    5.574 2.49e-08 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Log Likelihood:
 4194.235    normalized:  3.336702 

Description:
 Mon Sep 21 23:55:09 2015 by user:  


Standardised Residuals Tests:
                                Statistic p-Value     
 Jarque-Bera Test   R    Chi^2  105.7119  0           
 Shapiro-Wilk Test  R    W      0.9805931 5.976025e-12
 Ljung-Box Test     R    Q(10)  10.70223  0.3811829   
 Ljung-Box Test     R    Q(15)  14.11272  0.5169982   
 Ljung-Box Test     R    Q(20)  17.0778   0.6479163   
 Ljung-Box Test     R^2  Q(10)  19.13703  0.03855632  
 Ljung-Box Test     R^2  Q(15)  25.5461   0.04307303  
 Ljung-Box Test     R^2  Q(20)  28.90868  0.08957304  
 LM Arch Test       R    TR^2   20.5752   0.05695793  

Information Criterion Statistics:
      AIC       BIC       SIC      HQIC 
-6.667041 -6.650695 -6.667061 -6.660898 
```

```r
> # The model with lower AIC or BIC or SIC or HQIC
> 
> garch_fit@fit$ics
```

```
      AIC       BIC       SIC      HQIC 
-6.632898 -6.620639 -6.632910 -6.628291 
```

```r
> garch_fit_std@fit$ics
```

```
      AIC       BIC       SIC      HQIC 
-6.667041 -6.650695 -6.667061 -6.660898 
```

```r
> # Solution Exercise 4
> vola_forecast <- function(fit, n.ahead=1) {
+   # fit is an object of class "fGarch"
+   vola <- numeric(n.ahead + 1)
+   coefs <- coef(fit)
+   h_init <- fit@h.t[length(fit@h.t)] # last value of fitted sigma^2
+   eps <- fit@residuals[length(fit@residuals)]  # last value of eps_t
+   
+   h <- coefs["omega"] + coefs["alpha1"] * eps^2 +
+        coefs["beta1"] * h_init # one-step ahead forecast
+   
+   if(n.ahead == 1) {
+     res <- h
+     names(res) <- NULL
+     return(sqrt(res))
+   } else {
+     vola_part1 <- coefs["omega"] *
+                   (1 - (coefs["alpha1"] + coefs["beta1"])^(1:(n.ahead-1)))/
+                   (1 - (coefs["alpha1"] + coefs["beta1"]))
+     
+     vola_part2 <- (coefs["alpha1"] + coefs["beta1"])^(1:(n.ahead-1)) * h
+   
+     vola <- vola_part1 + vola_part2
+     res <- c(h,vola)
+     names(res) <- NULL
+     return(sqrt(res))
+   }
+ }
```
