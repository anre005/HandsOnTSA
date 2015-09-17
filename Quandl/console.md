# Querying Quandl Databases from R Console
As mentioned before you can find codes for datasets directly on the [Quandl website](https://www.quandl.com) 
or you can use the `Quandl.search()` function. 
It has only one mandatory argument `query` which you have to use to enter your search term.
Optional arguments of `Quandl.search()` are 

* `page`: specifies which page of the search results should be returned
* `source`: allows the user to specify a database which should be queried
* `silent`: if set to **FALSE** first three results are printed to the console
* `authcode`: if not set before with `Quandl.auth` function you can enter your API token here

An example call to `Quandl.search()` to find historical data for International Business Machines (IBM) by using
the Yahoo Finance Database is given below.


```r
ibm <- Quandl.search("IBM", source = "YAHOO", silent = TRUE)
```

The API call above returns a list of length 16 where the code needed for `Quandl` function and several other details can be extracted.


```r
str(ibm)
```

```
## List of 16
##  $ :List of 7
##   ..$ name        : chr "IBM: International Business Machines -"
##   ..$ code        : chr "YAHOO/IBM"
##   ..$ description : chr "Exchange : . Key Statistics"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "1962-01-02"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Stuttgart Stock Exchange"
##   ..$ code        : chr "YAHOO/SG_IBM"
##   ..$ description : chr "Exchange : Stuttgart Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2007-12-28"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Hanover Stock Exchange"
##   ..$ code        : chr "YAHOO/HA_IBM"
##   ..$ description : chr "Exchange : Hanover Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2001-01-04"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Munich Stock Exchange"
##   ..$ code        : chr "YAHOO/MU_IBM"
##   ..$ description : chr "Exchange : Munich Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-03"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Dusseldorf Stock Exchange"
##   ..$ code        : chr "YAHOO/DU_IBM"
##   ..$ description : chr "Exchange : Dusseldorf Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-03"
##   ..$ to_date     : chr "2015-09-11"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Frankfurt Stock Exchange"
##   ..$ code        : chr "YAHOO/F_IBM"
##   ..$ description : chr "Exchange : Frankfurt Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-03"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Berlin Stock Exchange"
##   ..$ code        : chr "YAHOO/BE_IBM"
##   ..$ description : chr "Exchange : Berlin Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-03"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - London Stock Exchange"
##   ..$ code        : chr "YAHOO/L_IBM"
##   ..$ description : chr "Exchange : London Stock Exchange. Key Statistics Currency: GBP"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2001-06-11"
##   ..$ to_date     : chr "2015-09-11"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Mexico Stock Exchange"
##   ..$ code        : chr "YAHOO/MX_IBM"
##   ..$ description : chr "Exchange : Mexico Stock Exchange. Key Statistics Currency: MXN"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2003-05-29"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBM: IBM - Hamburg Stock Exchange"
##   ..$ code        : chr "YAHOO/HM_IBM"
##   ..$ description : chr "Exchange : Hamburg Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-03"
##   ..$ to_date     : chr "2015-09-16"
##  $ :List of 7
##   ..$ name        : chr "IBMA: IBM - Amersterdam Stock Exchange"
##   ..$ code        : chr "YAHOO/AS_IBMA"
##   ..$ description : chr "Exchange : Amersterdam Stock Exchange.  Currency: EUR"
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2007-12-27"
##   ..$ to_date     : chr "2015-09-11"
##  $ :List of 7
##   ..$ name        : chr "IBMC: IBM IDR - EuroNext Brussels Exchange"
##   ..$ code        : chr "YAHOO/BR_IBMC"
##   ..$ description : chr "Exchange : EuroNext Brussels Exchange. Fundamental company data provided by Capital IQ. Historical chart data and daily updates"| __truncated__
##   ..$ frequency   : chr "daily"
##   ..$ column_names:List of 1
##   .. ..$ : chr [1:7] "Date" "Open" "High" "Low" ...
##   ..$ from_date   : chr "2000-01-04"
##   ..$ to_date     : chr "2014-07-01"
##  $ :List of 7
##   ..$ name        : chr NA
##   ..$ code        : chr "NA/NA"
##   ..$ description : chr NA
##   ..$ frequency   : chr NA
##   ..$ column_names:List of 1
##   .. ..$ : NULL
##   ..$ from_date   : chr NA
##   ..$ to_date     : chr NA
##  $ :List of 7
##   ..$ name        : chr NA
##   ..$ code        : chr "NA/NA"
##   ..$ description : chr NA
##   ..$ frequency   : chr NA
##   ..$ column_names:List of 1
##   .. ..$ : NULL
##   ..$ from_date   : chr NA
##   ..$ to_date     : chr NA
##  $ :List of 7
##   ..$ name        : chr NA
##   ..$ code        : chr "NA/NA"
##   ..$ description : chr NA
##   ..$ frequency   : chr NA
##   ..$ column_names:List of 1
##   .. ..$ : NULL
##   ..$ from_date   : chr NA
##   ..$ to_date     : chr NA
##  $ :List of 7
##   ..$ name        : chr NA
##   ..$ code        : chr "NA/NA"
##   ..$ description : chr NA
##   ..$ frequency   : chr NA
##   ..$ column_names:List of 1
##   .. ..$ : NULL
##   ..$ from_date   : chr NA
##   ..$ to_date     : chr NA
```
