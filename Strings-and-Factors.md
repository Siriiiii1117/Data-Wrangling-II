Strings and factors
================
2025-10-09

Load important packages

``` r
library(rvest)
```

    ## 
    ## Attaching package: 'rvest'

    ## The following object is masked from 'package:readr':
    ## 
    ##     guess_encoding

Import NDSUH data from the web

``` r
url = "https://samhda.s3-us-gov-west-1.amazonaws.com/s3fs-public/field-uploads/2k15StateFiles/NSDUHsaeShortTermCHG2015.htm"

drug_use_html = read_html(url)
```

This is an easy case

``` r
ndsuh_df = 
  drug_use_html |> 
  html_table() |> 
  first() |> 
  slice(-1)
```
