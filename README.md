README
================

## Loading Data

``` r
# Define the URL of the dataset
url <- "https://www.kaggle.com/api/v1/datasets/download/fratzcan/usa-house-prices"

# Define the destination file path 
USA_housing_dataset <- "usa-house-prices.zip"

# Extract the dataset
unzip(USA_housing_dataset, exdir = "usa-house-prices")

# List extracted files 
list.files("usa-house-prices")
```

    ## [1] "USA Housing Dataset.csv"

``` r
# Import dataset 
housing_data <- read.csv ("USA Housing Dataset.csv", stringsAsFactors = FALSE)

getwd()
```

    ## [1] "/Users/isabel_choma/Documents/GitHub/Getting_into_Business"

## PART 1: Understanding the Data

### When was the data acquired?

The data was acquired from May 2, 2014 to July 10, 2014. The data was
uploaded to Kaggle and was first accessed for this analysis on February
12, 2025.

### Where was the data acquired? (geographical location)

The data consists of housing prices from various cities in Washington,
US. The cities are shown in the frequency table below:

| City               | Frequency |
|:-------------------|----------:|
| Algona             |         1 |
| Auburn             |       162 |
| Beaux Arts Village |         1 |
| Bellevue           |       260 |
| Black Diamond      |         7 |
| Bothell            |        30 |
| Burien             |        64 |
| Carnation          |        18 |
| Clyde Hill         |        10 |
| Covington          |        39 |
| Des Moines         |        52 |
| Duvall             |        39 |
| Enumclaw           |        28 |
| Fall City          |         9 |
| Federal Way        |       131 |
| Issaquah           |       162 |
| Kenmore            |        58 |
| Kent               |       167 |
| Kirkland           |       166 |
| Lake Forest Park   |        33 |
| Maple Valley       |        90 |
| Medina             |        11 |
| Mercer Island      |        81 |
| Milton             |         2 |
| Newcastle          |        31 |
| Normandy Park      |        16 |
| North Bend         |        45 |
| Pacific            |         6 |
| Preston            |         2 |
| Ravensdale         |         4 |
| Redmond            |       209 |
| Renton             |       261 |
| Sammamish          |       158 |
| SeaTac             |        29 |
| Seattle            |      1415 |
| Shoreline          |       112 |
| Skykomish          |         2 |
| Snoqualmie         |        65 |
| Snoqualmie Pass    |         1 |
| Tukwila            |        28 |
| Vashon             |        28 |
| Woodinville        |       103 |
| Yarrow Point       |         4 |

### How was the data acquired?

This data was acquired from Kaggle. The page on Kaggle does not contain
any information about the source. There are no links to original
publications or projects from which the data was derived.

### What type of data do these attributes contain? (Categorical, numerical, ordinal, etc)

The dataset consists of 18 different attributes. The attributes of the
data and the data type of each attribute are shown in the table below:

<table class="table table-striped table-hover table-condensed table-responsive" style="width: auto !important; margin-left: auto; margin-right: auto;">
<caption>
📌 USA Housing Data
</caption>
<thead>
<tr>
<th style="text-align:left;font-weight: bold;color: white !important;background-color: black !important;">
Attribute
</th>
<th style="text-align:left;font-weight: bold;color: white !important;background-color: black !important;">
Description
</th>
<th style="text-align:left;font-weight: bold;color: white !important;background-color: black !important;">
Type
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
date
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Date when the house was sold
</td>
<td style="text-align:left;width: 40em; ">
character
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
price
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Sale price of the house
</td>
<td style="text-align:left;width: 40em; ">
double
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
bedrooms
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Number of bedrooms
</td>
<td style="text-align:left;width: 40em; ">
double
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
bathrooms
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Number of bathrooms
</td>
<td style="text-align:left;width: 40em; ">
double
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
sqft_living
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Living area in square feet
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
sqft_lot
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Lot area in square feet
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
floors
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Number of floors
</td>
<td style="text-align:left;width: 40em; ">
double
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
waterfront
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Whether the house is waterfront (1: Yes, 0: No)
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
view
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Number of times the house has been viewed
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
condition
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Condition of the house (1-5 scale)
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
sqft_above
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Square footage of the house above ground
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
sqft_basement
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Square footage of the basement
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
yr_built
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Year the house was built
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
yr_renovated
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Year of renovation (0 if never renovated)
</td>
<td style="text-align:left;width: 40em; ">
integer
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
street
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Street address of house
</td>
<td style="text-align:left;width: 40em; ">
character
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
city
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
City of the house location
</td>
<td style="text-align:left;width: 40em; ">
character
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
statezip
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Zip code of the house location
</td>
<td style="text-align:left;width: 40em; ">
character
</td>
</tr>
<tr>
<td style="text-align:left;font-weight: bold;color: black !important;">
country
</td>
<td style="text-align:left;font-style: italic;color: blue !important;">
Country of the house location
</td>
<td style="text-align:left;width: 40em; ">
character
</td>
</tr>
</tbody>
</table>

## PART 2: Data Summary & Initial Insights

Here is a table that shows the code that corresponds with each
attribute. These codes are useful for calculating summary statistics.

<table class="table" style="margin-left: auto; margin-right: auto;">
<caption>
Attribute Codes for Housing Data
</caption>
<thead>
<tr>
<th style="text-align:right;font-weight: bold;">
Code
</th>
<th style="text-align:left;font-weight: bold;">
Attribute
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;font-weight: bold;">
1
</td>
<td style="text-align:left;">
date
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
2
</td>
<td style="text-align:left;">
price
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
3
</td>
<td style="text-align:left;">
bedrooms
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
4
</td>
<td style="text-align:left;">
bathrooms
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
5
</td>
<td style="text-align:left;">
sqft_living
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
6
</td>
<td style="text-align:left;">
sqft_lot
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
7
</td>
<td style="text-align:left;">
floors
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
8
</td>
<td style="text-align:left;">
waterfront
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
9
</td>
<td style="text-align:left;">
view
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
10
</td>
<td style="text-align:left;">
condition
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
11
</td>
<td style="text-align:left;">
sqft_above
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
12
</td>
<td style="text-align:left;">
sqft_basement
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
13
</td>
<td style="text-align:left;">
yr_built
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
14
</td>
<td style="text-align:left;">
yr_renovated
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
15
</td>
<td style="text-align:left;">
street
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
16
</td>
<td style="text-align:left;">
city
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
17
</td>
<td style="text-align:left;">
statezip
</td>
</tr>
<tr>
<td style="text-align:right;font-weight: bold;">
18
</td>
<td style="text-align:left;">
country
</td>
</tr>
</tbody>
</table>
The table below shows summary statistics for the attributes:
<table class="table" style="margin-left: auto; margin-right: auto;">
<caption>
Summary Statistics for Housing Data
</caption>
<thead>
<tr>
<th style="text-align:center;font-weight: bold;">
Statistic
</th>
<th style="text-align:center;font-weight: bold;">
X2
</th>
<th style="text-align:center;font-weight: bold;">
X3
</th>
<th style="text-align:center;font-weight: bold;">
X4
</th>
<th style="text-align:center;font-weight: bold;">
X5
</th>
<th style="text-align:center;font-weight: bold;">
X6
</th>
<th style="text-align:center;font-weight: bold;">
X7
</th>
<th style="text-align:center;font-weight: bold;">
X8
</th>
<th style="text-align:center;font-weight: bold;">
X9
</th>
<th style="text-align:center;font-weight: bold;">
X10
</th>
<th style="text-align:center;font-weight: bold;">
X11
</th>
<th style="text-align:center;font-weight: bold;">
X12
</th>
<th style="text-align:center;font-weight: bold;">
X13
</th>
<th style="text-align:center;font-weight: bold;">
X14
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Min
</td>
<td style="text-align:center;font-size: 12px;">
0.0
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Q1
</td>
<td style="text-align:center;font-size: 12px;">
115000.0
</td>
<td style="text-align:center;font-size: 12px;">
0.23
</td>
<td style="text-align:center;font-size: 12px;">
0.20
</td>
<td style="text-align:center;font-size: 12px;">
516.87
</td>
<td style="text-align:center;font-size: 12px;">
2397.50
</td>
<td style="text-align:center;font-size: 12px;">
0.65
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.76
</td>
<td style="text-align:center;font-size: 12px;">
492.85
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
497.36
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Median
</td>
<td style="text-align:center;font-size: 12px;">
506531.4
</td>
<td style="text-align:center;font-size: 12px;">
1.95
</td>
<td style="text-align:center;font-size: 12px;">
1.47
</td>
<td style="text-align:center;font-size: 12px;">
1468.74
</td>
<td style="text-align:center;font-size: 12px;">
11186.82
</td>
<td style="text-align:center;font-size: 12px;">
1.25
</td>
<td style="text-align:center;font-size: 12px;">
0.00
</td>
<td style="text-align:center;font-size: 12px;">
0.12
</td>
<td style="text-align:center;font-size: 12px;">
2.00
</td>
<td style="text-align:center;font-size: 12px;">
1230.69
</td>
<td style="text-align:center;font-size: 12px;">
156.14
</td>
<td style="text-align:center;font-size: 12px;">
1935.41
</td>
<td style="text-align:center;font-size: 12px;">
404.18
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Mean
</td>
<td style="text-align:center;font-size: 12px;">
4697791.5
</td>
<td style="text-align:center;font-size: 12px;">
2.55
</td>
<td style="text-align:center;font-size: 12px;">
1.99
</td>
<td style="text-align:center;font-size: 12px;">
2581.85
</td>
<td style="text-align:center;font-size: 12px;">
188851.08
</td>
<td style="text-align:center;font-size: 12px;">
1.34
</td>
<td style="text-align:center;font-size: 12px;">
0.18
</td>
<td style="text-align:center;font-size: 12px;">
0.84
</td>
<td style="text-align:center;font-size: 12px;">
2.19
</td>
<td style="text-align:center;font-size: 12px;">
2113.79
</td>
<td style="text-align:center;font-size: 12px;">
932.77
</td>
<td style="text-align:center;font-size: 12px;">
1315.10
</td>
<td style="text-align:center;font-size: 12px;">
633.62
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Q3
</td>
<td style="text-align:center;font-size: 12px;">
576030.6
</td>
<td style="text-align:center;font-size: 12px;">
3.30
</td>
<td style="text-align:center;font-size: 12px;">
2.23
</td>
<td style="text-align:center;font-size: 12px;">
2102.73
</td>
<td style="text-align:center;font-size: 12px;">
30582.04
</td>
<td style="text-align:center;font-size: 12px;">
1.51
</td>
<td style="text-align:center;font-size: 12px;">
0.07
</td>
<td style="text-align:center;font-size: 12px;">
0.65
</td>
<td style="text-align:center;font-size: 12px;">
3.34
</td>
<td style="text-align:center;font-size: 12px;">
1773.51
</td>
<td style="text-align:center;font-size: 12px;">
426.33
</td>
<td style="text-align:center;font-size: 12px;">
1974.70
</td>
<td style="text-align:center;font-size: 12px;">
936.63
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
Max
</td>
<td style="text-align:center;font-size: 12px;">
26590000.0
</td>
<td style="text-align:center;font-size: 12px;">
8.00
</td>
<td style="text-align:center;font-size: 12px;">
6.75
</td>
<td style="text-align:center;font-size: 12px;">
10040.00
</td>
<td style="text-align:center;font-size: 12px;">
1074218.00
</td>
<td style="text-align:center;font-size: 12px;">
3.50
</td>
<td style="text-align:center;font-size: 12px;">
1.00
</td>
<td style="text-align:center;font-size: 12px;">
4.00
</td>
<td style="text-align:center;font-size: 12px;">
5.00
</td>
<td style="text-align:center;font-size: 12px;">
8020.00
</td>
<td style="text-align:center;font-size: 12px;">
4820.00
</td>
<td style="text-align:center;font-size: 12px;">
2014.00
</td>
<td style="text-align:center;font-size: 12px;">
2014.00
</td>
</tr>
<tr>
<td style="text-align:center;font-size: 12px;font-weight: bold;">
SD
</td>
<td style="text-align:center;font-size: 12px;">
10728194.6
</td>
<td style="text-align:center;font-size: 12px;">
3.04
</td>
<td style="text-align:center;font-size: 12px;">
2.53
</td>
<td style="text-align:center;font-size: 12px;">
3751.67
</td>
<td style="text-align:center;font-size: 12px;">
433939.73
</td>
<td style="text-align:center;font-size: 12px;">
1.21
</td>
<td style="text-align:center;font-size: 12px;">
0.40
</td>
<td style="text-align:center;font-size: 12px;">
1.58
</td>
<td style="text-align:center;font-size: 12px;">
1.93
</td>
<td style="text-align:center;font-size: 12px;">
2976.73
</td>
<td style="text-align:center;font-size: 12px;">
1914.43
</td>
<td style="text-align:center;font-size: 12px;">
1007.85
</td>
<td style="text-align:center;font-size: 12px;">
807.46
</td>
</tr>
</tbody>
</table>

### Identify any missing (NA) or empty values and discuss potential strategies to handle them.

When calculating summary statistics and creating our summary table, we
separated numeric data and non-numeric data. There are 5 attributes of
the character data type, so these attributes had empty values. We did
not include these categorical attributes in our analysis.

## PART 3: Expanding Your Investment Knowledge

### Why would this dataset be useful?

This additional dataset consists of the all-transactions house price
index for Washington, US from 1975 to present. House price index (HPI)
is an economic indicator that measures the change in average residential
property prices over time. It shows how much house prices are rising or
falling in a given region, usually calculated by tracking repeat sales
of the same properties over time. It is considered a key tool for
understanding housing market trends and affordability.

This dataset would be useful because our dataset consists of data from
Washington, US only from May-July 2014, so it would be useful to compare
the data with the HPI in Washington throughout the years to see whether
housing prices in the state were relatively low or high at that time.

### How could it complement the data you are currently analyzing?

This dataset could complement our dataset by showing the housing price
index in 2014. We could compare the change in HPI from Quarter 2 and
Quarter 3 to our own dataset. Our data was recorded from the months of
May to August, which covers both quarters 2 and 3, so this will help us
analyze the and compare the summary statistics of our data to the HPI of
Washington in 2014.

We could also use this dataset to compare the prices in our set to the
trends of housing prices over the years. The HPI data shows that average
residential property prices have risen over time in Washington. It shows
a decline following the 2008 recession, with the lowest peak being in
2012, then a gradual increase. The pricing data in the original set is
from 2014, so the data falls in a year of recovery from the recession,
which showcases a unique trend that is captured in our data. The HPI had
not yet hit the pre-recession high of 498.06 from 2007. It hit this high
again in 2016 and has continued to increase since then.

### Provide a link to the additional dataset.

[Additional dataset](https://fred.stlouisfed.org/series/WASTHPI)
