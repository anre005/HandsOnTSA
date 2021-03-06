# Random Walk and White Noise

On the lecture slides the definition of a random walk is given as

$$
\begin{aligned}
  y_t &= y_{t-1} + u_t, \quad &\text{for}\: t = 1,2,\ldots \quad &(\text{random walk without drift})  \\ 
  y_t &= \mu + y_{t-1} + u_t, \quad &\text{for}\: t = 1,2,\ldots \quad &(\text{with drift parameter } \mu),
\end{aligned}
$$

with white noise \\(u_t\\), which means \\(E(u_t) = 0\\) and \\(Var(u_t) = \sigma_u^2\\)
and \\(Corr(u_t,u_s) = 0 \\) for \\(t \neq s\\),
and assuming that the initial value \\(y_0\\) equals 0.

The two equations above can be rewritten as a cumulative sum of white noise variates.
First, rewrite the equation for a random walk without drift,

$$
\begin{aligned}
  y_t &= y_{t-1} + u_t \\ 
  y_t &= y_{t-2} + u_{t-1} + u_t \\
  y_t &= y_{t-3} + u_{t-2} +  u_{t-1} + u_t \\
  \vdots \\
  y_t &= \sum\limits_{j = 1}^{j = t} u_j,
\end{aligned}
$$

and for a random walk with drift parameter \\(\mu\\),

$$
\begin{aligned}
  y_t &= \mu + y_{t-1} + u_t \\ 
  y_t &= \mu + \mu + y_{t-2} + u_{t-1} + u_t \\
  y_t &= \mu + \mu + \mu + y_{t-3} + u_{t-2} + u_{t-1} + u_t \\
  \vdots \\
  y_t &= \mu t + \sum\limits_{j = 1}^{j = t} u_j.
\end{aligned}
$$

To generate a gaussian random walk (with and without drift) in `R` we need the functions `rnorm()`, `set.seed()`, and `cumsum()`.
