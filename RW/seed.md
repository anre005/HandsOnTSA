# `set.seed()`
The `set.seed()` function is needed to specify the state of `R`'s internal random number generator (RNG). 
Without this function we are not able to achive reproducible results.


```r
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  8.676409 11.241025  9.496123  4.480163 11.054355 10.438237  6.728537
##  [8]  9.176640  7.851433 11.002539
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
