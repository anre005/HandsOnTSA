# Solutions




```r
> # Solution Exercise 1
> ar1 <- armaFit(~arma(1,0), data = sales_adj, method = "ML")
```

```
Error in as.matrix(data): Fehler bei der Auswertung des Argumentes 'x' bei der Methodenauswahl
für Funktion 'as.matrix': Fehler: Objekt 'sales_adj' nicht gefunden
```

```r
> ma1 <- armaFit(~arma(0,1), data = sales_adj, method = "ML")
```

```
Error in as.matrix(data): Fehler bei der Auswertung des Argumentes 'x' bei der Methodenauswahl
für Funktion 'as.matrix': Fehler: Objekt 'sales_adj' nicht gefunden
```

```r
> arma11 <- armaFit(~arma(1,1), data = sales_adj, method = "ML")
```

```
Error in as.matrix(data): Fehler bei der Auswertung des Argumentes 'x' bei der Methodenauswahl
für Funktion 'as.matrix': Fehler: Objekt 'sales_adj' nicht gefunden
```

```r
> arma22 <- armaFit(~arma(2,2), data = sales_adj, method = "ML")
```

```
Error in as.matrix(data): Fehler bei der Auswertung des Argumentes 'x' bei der Methodenauswahl
für Funktion 'as.matrix': Fehler: Objekt 'sales_adj' nicht gefunden
```

```r
> ar1@fit$aic
```

```
Error in eval(expr, envir, enclos): Objekt 'ar1' nicht gefunden
```

```r
> ma1@fit$aic
```

```
Error in eval(expr, envir, enclos): Objekt 'ma1' nicht gefunden
```

```r
> arma11@fit$aic
```

```
Error in eval(expr, envir, enclos): Objekt 'arma11' nicht gefunden
```

```r
> arma22@fit$aic
```

```
Error in eval(expr, envir, enclos): Objekt 'arma22' nicht gefunden
```

```r
> # Solution Exercise 2
> polyroot(c(1, -arma22@fit$coef[c("ar1","ar2")]))
```

```
Error in polyroot(c(1, -arma22@fit$coef[c("ar1", "ar2")])): Objekt 'arma22' nicht gefunden
```

```r
> polyroot(c(1, arma22@fit$coef[c("ma1","ma2")]))
```

```
Error in polyroot(c(1, arma22@fit$coef[c("ma1", "ma2")])): Objekt 'arma22' nicht gefunden
```

```r
> # No roots in common and all roots lie outside the unit circle
> 
> # Solution Exercise 3
> predict(arma22, n.ahead = 6)
```

```
Error in predict(arma22, n.ahead = 6): Fehler bei der Auswertung des Argumentes 'object' bei der Methodenauswahl
für Funktion 'predict': Fehler: Objekt 'arma22' nicht gefunden
```

```r
> predict(arma22, n.ahead = 12)
```

```
Error in predict(arma22, n.ahead = 12): Fehler bei der Auswertung des Argumentes 'object' bei der Methodenauswahl
für Funktion 'predict': Fehler: Objekt 'arma22' nicht gefunden
```
