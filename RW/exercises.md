# Exercises

1.  **Random Walk without Drift**
    - Set the seed of `R`'s RNG to $111$.
    - Generate $100$ normally distributed random numbers with mean $0$ and standard deviation $1$
       and save your results in a variable *wn*.
    - Calculate the random walk without drift and save it in the variable *rw_wo_drift*.
    - Plot the random walk as a dashed red line.
    - Take a look at your neighbour's display. It should show the same result as yours.
    
    
2.  **Random Walk with Drift**
    - Generate $100$ normally distributed random numbers with mean $0$ and standard deviation $1$
      and save your results in a variable *wn_drift*.
    - Calculate the random walk with drift, use $\mu = 0.2$, and save it in the variable *rw_drift*.
    - Use your results from the first exercise and visualize both random walks in one plot with colors 
      and linetypes of your choice.
    - Add a legend to the plot.
    
3.  **Portmanteau Tests**
    - Use the function `Box.test()` to calculate the Box - Pierce and Ljung - Box test statistic
      for both random walks.
    - Make a decision by using the functions output.
    - Use the `diff()` function to compute the lagged differences of the random walk without drift.
      Calculate the Box - Pierce and Ljung - Box test statistic for the differenced time series.
    - What kind of stochastic process is the result of a differenced random walk without drift?
