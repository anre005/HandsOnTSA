# `set.seed()`
The `set.seed()` function is needed to specify the state of `R`'s internal random number generator (RNG). 
Without this function we are not able to achive reproducible results.


```r
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  8.866197  7.437372 10.878218  8.214348 10.230676  9.228255 12.234759
##  [8] 10.977893 10.415212 10.778078
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
