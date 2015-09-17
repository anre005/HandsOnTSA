

### Exercises

1.  **Download Time Series**
    - Get the Quandl code for the monthly retailer sales data in millions of dollars,
      which are not seasonally adjusted, from the *Federal Reserve Economic Data* database (FRED)
      either from the Quandl website or the `R` console.
    - Download all available data for this time series specifying the `type` argument of the 
      `Quandl()` function that it matches the recommendation from the `stl()` help page.
    
2.  **Decomposing Time Series**
    - Decompose your time series from exercise 1 with `stl()` function
      assuming that the seasonal pattern is constant through time.
    - Seasonally adjust the time series and detrend it. 
      This means removing the seasonal component and the trend component from the raw data.
