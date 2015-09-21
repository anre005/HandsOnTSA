# Querying Quandl Databases from R Console
As mentioned before you can find codes for datasets directly on the [Quandl website](https://www.quandl.com) 
or you can use the `Quandl.search()` function. 
It has only one mandatory argument `query` which you have to use to enter your search term.
Optional arguments of `Quandl.search()` are 

* `per_page`: specifies the number of results returned per page
* `silent`: if set to **FALSE** results are printed to the console
* `...` : additional named arguments which are interpretted as Quandl API parameters.

We have to look in the [Quandl API documentation](https://www.quandl.com/docs/api) to see which
additional arguments can be used.
For example, we can set the database we want to get results from with the 
`database_code` argument.

A function call to `Quandl.search()` for finding historical data for International Business Machines (IBM) by using
the Yahoo Finance Database is given below.


```r
ibm <- Quandl.search("IBM", silent = TRUE, database_code = "YAHOO")
```

The API call above returns a `data.frame` with the following column names.


```r
colnames(ibm)
```

```
##  [1] "id"                    "dataset_code"         
##  [3] "database_code"         "name"                 
##  [5] "description"           "refreshed_at"         
##  [7] "newest_available_date" "oldest_available_date"
##  [9] "column_names"          "frequency"            
## [11] "type"                  "premium"              
## [13] "database_id"
```

The code which can be used with the `Quandl()` function is a string with the structure `database_code`/`dataset_code`.
