# `set.seed()`
The `set.seed()` function is needed to specify the state of `R`'s internal random number generator (RNG). 
Without this function we are not able to achive reproducible results.


```r
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  9.180603  5.367401  8.557000 13.528418  9.302157  8.900103 11.489525
##  [8] 10.494833  8.591165  8.202785
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
