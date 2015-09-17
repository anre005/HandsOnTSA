# Exercises

1.  **Download Historical Data**
    - Get the code for *S & P 500* Index using the Yahoo Finance database either from the Quandl website or the `R` console.
    - Download historical close prices for the years 2010 -- 2014 and save them in the variable `close_prices`.
    
2.  **Visual Inspection of the Data**
    - Plot the close prices as a linechart. What kind of process would be appropriate?
    - Plot the logarithm (`log()`) of the close prices as a linechart. What kind of process would be appropriate?
    - Calculate the log - returns and save your results in the variable `log_returns`.
    - Plot the log - returns. What kind of process would be appropriate?
    - Plot the acf `acf()` of the log - returns and the squared log - returns.
    
3. **Fitting a GARCH model to historical data**
    - Use the `garchFit()` function to fit a GARCH(1,1) model (slide 39) to the log - returns.
    - Replace the normal distribution with a Student - t - distribution.
    - Which model explains the data better?
    
4. **Forecasting Volatility (maybe Homework)**
    - Write your own function `vola_forecast()` for forecasting volatility of the two models from exercise 3.
    - You can use the following forecasting relations for a GARCH(1,1) model
      where \\(\mathcal{F}_T\\) is the information set until timestamp \\(T\\):
$$    
\begin{align*}
        E\left(\sigma_{T+1}|\mathcal{F}_T\right) &= \omega + \alpha_1 \epsilon_T^2 + \beta_1 \sigma_T^2 \\ \\
        E\left(\sigma_{T+h}|\mathcal{F}_T\right) &= \dfrac{\omega (1 - (\alpha_1 + \beta_1)^{h-1})}{1 - \alpha_1 + \beta_1} + 
                                            (\alpha_1 + \beta_1)^{h-1} E\left(\sigma_{T+1}|\mathcal{F}_T\right),
\end{align*}
$$


```r
vola_forecast <- function(ARGUMENTS) {
  
  Body 
  
}
```