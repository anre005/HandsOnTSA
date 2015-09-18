# Decomposing Time Series 

A time series \\(y_t\\) can be splitted up into 
trend component \\(\tau_t\\), seasonal component \\(s_t\\) and the remainder \\(u_t\\).

$$
\begin{aligned}
y_t = \tau_t + s_t +  u_t
\end{aligned}
$$

In `R` the function `stl()` can be used for seasonal decomposition of a time 
series.
