# Exercises
1.  **ARMA Model Fitting**
    - Use the detrended and seasonally adjusted time series from exercise 2 from chapter *Decomposing Time Series*. 
      Fit an AR(1), MA(1), ARMA(1,1) and ARMA(2,2) model to the data using ML estimation.
      Choose the best out of these four approaches using the Akaike Information Criteria.

2.  **Forecasting**
    - Predict the values of the detrended and seasonally - adjusted retailers sales time series for the next six months (for the next 12 months)
      using the best model from exercise 1.

3.  **Causality and Invertibility** (Homework)
    - Check if the best model from exercise 1 is causal w.r.t \\(\epsilon\\) by using the `polyroot()` function.
    - Check if the best model from exercise 1 is invertible w.r.t \\(\epsilon\\) by using the `polyroot()` function.
    - **Note**: More about causality and invertibility of \\(ARMA(p,q)\\) processes can be found [here](http://www.maths.qmul.ac.uk/~bb/TS_Chapter6_1.pdf)
