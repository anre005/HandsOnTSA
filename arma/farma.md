

# `fArma` package


```r
> library(fArma)
```

We will use the `armaFit()` function from the `fArma` package for fitting ARMA models to historical time series.


```r
> armaFit(formula, data, method = "ML")
> # additional arguments removed
```

With `formula` argument one can specify which type of ARMA model should be fitted to `data`, which is the time series. 
Mandatory argument `formula` can be set in a `~arma(p,q)` style with the AR order \\(p\\) and the MA order \\(q\\).
Using the birth rates time series from the previous chapter one can fit a ARMA(1,1) to the data with the following line of code.

```r
> births_arma <- armaFit(formula = ~arma(1,1), data = births, method = "ML")
```

```
Error in as.matrix(data): Fehler bei der Auswertung des Argumentes 'x' bei der Methodenauswahl
für Funktion 'as.matrix': Fehler: Objekt 'births' nicht gefunden
```

```r
> class(births_arma)
```

```
Error in eval(expr, envir, enclos): Objekt 'births_arma' nicht gefunden
```

Applying the `summary` function to the `births_arma` object, which has class `fARMA`, by default gives an overview about the results
of the model estimation and produces some plots which can be used to interpret the goodness of fit.


```r
> summary(births_arma)
```

```
Error in summary(births_arma): Objekt 'births_arma' nicht gefunden
```


One can also forecast the time series with the `predict()` function. By default ten values are predicted.


```r
> predict(births_arma)
```

```
Error in predict(births_arma): Objekt 'births_arma' nicht gefunden
```
