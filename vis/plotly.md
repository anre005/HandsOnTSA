

# plotly Package
Yo can create easily interactive graphics with the help of the [`plotly`](https://plot.ly/r/) package.

```r
> library(plotly)
```

Using plotly is free if you permit them to publish your plots on their website.
Nevertheless, you have to create an account and register it in the `R` session.

A starting guide for using the `plotly` package in `R` can be found [here](https://plot.ly/r/getting-started/).




```r
> Sys.setenv("plotly_username"="YOUR_USERNAME")
> Sys.setenv("plotly_api_key"="YOUR_API_KEY")
```

Let's take our `ggplot2` plot we have created in the previous section. 
Turning this into interactive graphic is very simple thanke to `ggplotly()` function.

```r
> p <- autoplot.zoo(bmw_2014_xts, 
+                   main = "BMW OHLC plot with ggplot2",
+                   facets = NULL) + xlab("") +  facet_free()
> gg <- ggplotly(p)
> gg
```

```
Success! Created a new plotly here -> https://plot.ly/~anre005/570
```

<iframe height="600" id="igraph" scrolling="no" seamless="seamless" src="https://plot.ly/~anre005/570.embed" width="800" frameBorder="0"></iframe>

It is also easy to plot single time series, e.g. the traded volume per day for *BMW*, and even to annotate the plot.
The help page of the `plot_ly()` function tells us that the data should be a `data.frame`. 
Again we use our *BMW* `data.frame` from chapter 1.


```r
> # find the maximum volume
> max_vol <- max(bmw[,"Volume"])
> 
> # find the index (rownumber) the maximum volume occurs
> ind <- which(bmw[,"Volume"] == max_vol)
> 
> # find the corresponding date
> date_max_vol <- bmw[ind,"Date"]
> 
> # plot Volume vs. Date
> p <- plot_ly(bmw, x = Date, y = Volume, type = "bar")
> 
> # finally, add annotation
> layout(p, annotations = list(x = date_max_vol, y = max_vol,
+                              text = "Maximum Volume", showarrow = T))
```

```
Success! Created a new plotly here -> https://plot.ly/~anre005/572
```

<iframe height="600" id="igraph" scrolling="no" seamless="seamless" src="https://plot.ly/~anre005/572.embed" width="800" frameBorder="0"></iframe>
