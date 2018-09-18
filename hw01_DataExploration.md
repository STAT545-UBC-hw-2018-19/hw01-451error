Data Exploration
================
Tom Peng

## **USArrests** Dataset

The `USArrests` dataset is built-in to `R` and it has arrests per
100,000 residents for various crimes in the US states in 1973. For more
details of the dataset, see the R Documentations page
[here](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/USArrests.html)

To help us have a better understanding of what the dataset looks like,
the `head` and `tail` commands lets us see the first and last six rows
of the data, respectively:

``` r
head(USArrests)
```

    ##            Murder Assault UrbanPop Rape
    ## Alabama      13.2     236       58 21.2
    ## Alaska       10.0     263       48 44.5
    ## Arizona       8.1     294       80 31.0
    ## Arkansas      8.8     190       50 19.5
    ## California    9.0     276       91 40.6
    ## Colorado      7.9     204       78 38.7

``` r
tail(USArrests)
```

    ##               Murder Assault UrbanPop Rape
    ## Vermont          2.2      48       32 11.2
    ## Virginia         8.5     156       63 20.7
    ## Washington       4.0     145       73 26.2
    ## West Virginia    5.7      81       39  9.3
    ## Wisconsin        2.6      53       66 10.8
    ## Wyoming          6.8     161       60 15.6

`R` has a built-in function `summary` which, as the function name
suggests, shows us summary information on each column of the dataframe:

``` r
summary(USArrests)
```

    ##      Murder          Assault         UrbanPop          Rape      
    ##  Min.   : 0.800   Min.   : 45.0   Min.   :32.00   Min.   : 7.30  
    ##  1st Qu.: 4.075   1st Qu.:109.0   1st Qu.:54.50   1st Qu.:15.07  
    ##  Median : 7.250   Median :159.0   Median :66.00   Median :20.10  
    ##  Mean   : 7.788   Mean   :170.8   Mean   :65.54   Mean   :21.23  
    ##  3rd Qu.:11.250   3rd Qu.:249.0   3rd Qu.:77.75   3rd Qu.:26.18  
    ##  Max.   :17.400   Max.   :337.0   Max.   :91.00   Max.   :46.00

If we want to look at one column of the dataframe, we can use square
brackets and the column name to extract it from the
    data:

``` r
USArrests$Assault
```

    ##  [1] 236 263 294 190 276 204 110 238 335 211  46 120 249 113  56 115 109
    ## [18] 249  83 300 149 255  72 259 178 109 102 252  57 159 285 254 337  45
    ## [35] 120 151 159 106 174 279  86 188 201 120  48 156 145  81  53 161

We can also use `R` functions to find, for example, which state has the
highest murder
rate:

``` r
row.names(USArrests[which(USArrests["Murder"]==max(USArrests["Murder"])),])
```

    ## [1] "Georgia"

## Visualization

We can plot the dataset to visualize the data. The `UrbanPop` column was
removed from the plot so we can compare the different arrest
rates.

![](hw01_DataExploration_files/figure-gfm/pressure-1.png)<!-- -->

<!---Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.--->
