# `set.seed()`
The `set.seed()` function is needed to specify the state of `R`'s internal random number generator (RNG). 
Without this function we are not able to achive reproducible results.


```r
rnorm(10, mean = 10, sd = 2)
```

```
##  [1] 10.223739  8.114010 12.989474  8.841767 10.187737 10.828329  5.895853
##  [8]  7.325723 10.687711 10.068956
```


```r
set.seed(123)
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  8.879049  9.539645 13.117417 10.141017 10.258575 13.430130 10.921832
##  [8]  7.469878  8.626294  9.108676
```


```r
set.seed(123)
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  8.879049  9.539645 13.117417 10.141017 10.258575 13.430130 10.921832
##  [8]  7.469878  8.626294  9.108676
```
