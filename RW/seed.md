# `set.seed()`
The `set.seed()` function is needed to specify the state of `R`'s internal random number generator (RNG). 
Without this function we are not able to achive reproducible results.


```r
rnorm(10, mean = 10, sd = 2)
```

```
##  [1]  7.473931  8.442752 12.222052 16.364020 12.650064  9.418299  8.978327
##  [8]  6.564607 11.510352  8.841170
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
