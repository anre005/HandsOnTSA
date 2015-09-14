

# Installation and Authentication in `R`

Once you created an free account you can find your authentification token in the settings of your account on the 
[Quandl Homepage](https://www.quandl.com). You can verify that you are a registered user directly in R with the 
`Quandl.auth()` function from `R` package `Quandl`.

Installing the `R` package `Quandl` if not installed already,


```r
> install.packages("Quandl")
```

else load the package.



```r
> library("Quandl")
```


```r
> Quandl.auth("YourAPItoken")
```
