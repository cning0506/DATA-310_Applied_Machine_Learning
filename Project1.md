# DATA 310 Applied Machine Learning - Project 1 - Good or Bad Housing Deals

#### In this project, we will scrape 400 houses from a city of our choice via Zillow, as we extract some usable predictors including the number of beds, number of bathrooms, and total square footage. We will train a new model with our 400 observations, with the goal of predicting the reasonable housing prices of each house and assess if it is a good deal or not with the price difference. At the end of this project, with the help of some plots, we will analyze the model and evaluate each predictor. Moreover, we will rank all homes from best to worst deals.


#### To start off, let’s talk about the housing data that are collected from Zillow. I chose Phoenix, Arizona as the city to collect information on houses. We first created the data frame with the variables as we add the content to the corresponding variables. We cleaned the data by removing the Html tags that wrap around the information that we want. With all the preprocessing, we generate a CSV file that contains the data for the response variable - price(in thousand) and three independent variables/ predictors.  Figure 1 displays the descriptive statistics of the 400 houses in Phoenix. We can see that the average price of housing in Phoenix is $465,706, the median is $356,000. This difference reflects the existence of luxurious and more expensive houses in the city, which raises the average price of the housing. We will take a closer look at these expensive houses and see if they worth the price. Interestingly, the data also shows that most of the houses from the sample tend to have 4 bedrooms. 

#### To analyze the data, we load the dataset that we exported earlier and utilize the TensorFlow module to train the model. With the Keras function, we are able to compile the three layers, which are the three predictors into the training model. After we train the model, we predict the housing prices and insert the predicted price as a new column in the data frame, as well as the price difference, which is calculated as predicted price subtract by the original price. To get the good deals and bad deals, I subset the data frame into two data frames, one with the price difference greater than 0, which are the good deals. There are 298 houses belongs to this subset. The other 102 houses have a price difference smaller than 0, which are generally bad deals or at least overprice.


#### Assuming that price difference is the only indicator to determine a good deal or not, we can generalize some characteristics of the predictors based on the top 100 good deals in Phoenix. The house typically has four bedrooms, three bathrooms, and approximately 2,950 square footage, which has a predicted price of around $600,000. If someone is looking for a house that has similar dimensions, anything less than $600,000 should be prioritized or at least worth a second thought. In conclusion, this model provides a broad prediction on housing prices for the datasets we collected. There are different approaches to improving the model. It can be more practical and accurate if we scrape more data and perhaps change up the sequence of the layer to determine the strength of each predictor. In fact, there might be some typos or errors from the website that needs to be addressed. In addition, we should also examine more predictors to avoid any systematic bias. 

  
## Appendix 

### *Figure 1: Descriptive statistics of the 400 houses in Phoenix, AZ*

![Figure 1: Descriptive Statistics table](https://cning0506.github.io/DATA-310_Applied_Machine_Learning/DescriptiveStat.PNG)


### *Figure 2: Price Comparison of the 400 Houses in Phoenix, AZ*

![Figure 2: Price Comparison](https://cning0506.github.io/DATA-310_Applied_Machine_Learning/PriceComparison.png)



### *Figure 3: Best Deal to Worst Deals in Phoenix, AZ* 



|     |   prices | address                                              |   no_beds |   baths |   sqft |   predicted_price |   price_diff |
|----:|---------:|:-----------------------------------------------------|----------:|--------:|-------:|------------------:|-------------:|
|   0 |   24.99  | 205 W Bell Rd #85 Phoenix AZ 85023                   |         5 |       6 |  5.237 |           735.712 |   710.722    |
|   1 |   75     | 6834 N 23rd Dr LOT 3 Phoenix AZ 85015                |         5 |       5 |  4.511 |           693.697 |   618.697    |
|   2 |   99     | 616 E Old West Way #0 Phoenix AZ 85085               |         4 |       4 |  4.178 |           708.803 |   609.803    |
|   3 |  129.9   | 4750 N Central Ave UNIT 4C Phoenix AZ 85012          |         5 |       6 |  5.237 |           735.712 |   605.812    |
|   4 |  130     | 2132 W Glenrosa Ave #B78 Phoenix AZ 85015            |         5 |       6 |  5.028 |           711.255 |   581.255    |
|   5 |  167     | 2625 E Indian School Rd UNIT 220 Phoenix AZ 85016    |         5 |       6 |  5.237 |           735.712 |   568.712    |
|   6 |   20     | 799 E Cobble Ln Phoenix AZ 85018                     |         3 |       2 |  2.152 |           568.734 |   548.734    |
|   7 |  120     | 6565 N 19th Ave APT 3 Phoenix AZ 85015               |         5 |       3 |  3.389 |           648.283 |   528.283    |
|   8 |   16.5   | 6512 W Van Buren St #26 Phoenix AZ 85043             |         1 |       2 |  1.652 |           532.487 |   515.987    |
|   9 |  145.997 | 6817 N 19th Dr Phoenix AZ 85015                      |         5 |       3 |  3.389 |           648.283 |   502.286    |
|  10 |  150     | 1734 E Harvard St Phoenix AZ 85006                   |         4 |       3 |  3.055 |           620.33  |   470.33     |
|  11 |   12     | 20592 E Ash Creek Rd Scottsdale AZ 85254             |         4 |       2 |  1.508 |           482.24  |   470.24     |
|  12 |   25.5   | 2233 E Behrend Dr #128 Phoenix AZ 85024              |         2 |       2 |  1.344 |           485.313 |   459.813    |
|  13 |  239     | 3022 N 32nd St UNIT 45 Phoenix AZ 85018              |         5 |       5 |  4.511 |           693.697 |   454.697    |
|  14 |  159.9   | 4750 N Central Ave UNIT 6A Phoenix AZ 85012          |         3 |       3 |  2.908 |           614.26  |   454.36     |
|  15 |   30     | 5201 W Camelback Rd #F304 Phoenix AZ 85031           |         4 |       3 |  1.862 |           480.724 |   450.724    |
|  16 |   16     | 20125 E Sierra Dr Scottsdale AZ 85254                |         3 |       2 |  1.26  |           464.351 |   448.351    |
|  17 |   42     | 501 E Ray Rd #231 Chandler AZ 85225                  |         2 |       1 |  1     |           487.999 |   445.999    |
|  18 |   36     | 1018 W Welland Rd Phoenix AZ 85041                   |         4 |       3 |  1.862 |           480.724 |   444.724    |
|  19 |   49.9   | 1496 Shade Tree Dr Heber AZ 85928                    |         2 |       1 |  1     |           487.999 |   438.099    |
|  20 |  213     | 7223 N 25th Dr Phoenix AZ 85051                      |         5 |       3 |  3.389 |           648.283 |   435.283    |
|  21 |   18.9   | 1705 E Charleston Ave Phoenix AZ 85022               |         4 |       2 |  1.248 |           451.815 |   432.915    |
|  22 |   46     | 16005 N 32nd St #157 Phoenix AZ 85032                |         4 |       2 |  1.456 |           476.155 |   430.155    |
|  23 |   59     | 19602 N 32nd St LOT 91 Phoenix AZ 85050              |         2 |       1 |  1     |           487.999 |   428.999    |
|  24 |  239     | 7414 W Sells Dr Phoenix AZ 85033                     |         5 |       4 |  3.887 |           663.618 |   424.618    |
|  25 |  349.9   | 2413 W Coolidge St Phoenix AZ 85015                  |         4 |       4 |  4.655 |           764.621 |   414.722    |
|  26 |  185     | 18811 N 19th Ave APT 1019 Phoenix AZ 85027           |         4 |       2 |  2.477 |           595.633 |   410.633    |
|  27 |  150     | 3162 E Roeser Rd Phoenix AZ 85040                    |         4 |       3 |  2.502 |           555.617 |   405.617    |
|  28 |  209.9   | 17017 N 12th St UNIT 1099 Phoenix AZ 85022           |         5 |       3 |  3.083 |           612.475 |   402.574    |
|  29 |  315     | 9369 W Eaton Rd Phoenix AZ 85037                     |         4 |       4 |  4.178 |           708.803 |   393.803    |
|  30 |  139.9   | 7117 W Minnezona Ave Phoenix AZ 85033                |         4 |       2 |  1.922 |           530.687 |   390.787    |
|  31 |  260     | 8747 W Hazelwood St Phoenix AZ 85037                 |         5 |       2 |  3.041 |           650.501 |   390.501    |
|  32 |  319.9   | 4837 W Leodra Ln Laveen AZ 85339                     |         4 |       4 |  4.178 |           708.803 |   388.903    |
|  33 |  235     | 2702 E Roeser Rd Phoenix AZ 85040                    |         4 |       3 |  3.055 |           620.33  |   385.33     |
|  34 |  323.99  | Leslie Plan Sunset Place                             |         4 |       4 |  4.178 |           708.803 |   384.813    |
|  35 |  330     | 351 E Thomas Rd UNIT D508 Phoenix AZ 85012           |         5 |       6 |  5.028 |           711.255 |   381.255    |
|  36 |  147.9   | 4750 N Central Ave UNIT 5N Phoenix AZ 85012          |         3 |       2 |  1.777 |           524.851 |   376.951    |
|  37 |  332.99  | Palo Verde Plan Prior Ridge                          |         4 |       4 |  4.178 |           708.803 |   375.813    |
|  38 |  171.95  | 3405 W Danbury Dr APT D224 Phoenix AZ 85053          |         4 |       4 |  2.798 |           547.314 |   375.364    |
|  39 |   80     | 2664 N 43rd Ave APT B Phoenix AZ 85009               |         4 |       2 |  1.248 |           451.815 |   371.815    |
|  40 |  140     | 4001 S 45th St Phoenix AZ 85040                      |         2 |       2 |  1.558 |           510.355 |   370.355    |
|  41 |  167.9   | 2021 E Osborn Rd APT 2 Phoenix AZ 85016              |         4 |       3 |  2.346 |           537.362 |   369.462    |
|  42 |  254     | 1271 E Maryland Ave UNIT A Phoenix AZ 85014          |         4 |       3 |  3.055 |           620.33  |   366.33     |
|  43 |  215     | 1805 E Libby St Phoenix AZ 85022                     |         4 |       4 |  3.083 |           580.665 |   365.665    |
|  44 |  375     | 914 W Hononegh Dr Phoenix AZ 85027                   |         5 |       6 |  5.237 |           735.712 |   360.712    |
|  45 |  289.9   | 2218 W Dahlia Dr Phoenix AZ 85029                    |         5 |       3 |  3.389 |           648.283 |   358.383    |
|  46 |  170     | 2802 E Beck Ln UNIT 1 Phoenix AZ 85032               |         4 |       3 |  2.228 |           523.554 |   353.554    |
|  47 |  315     | 14451 N 27th Dr Phoenix AZ 85053                     |         5 |       4 |  3.887 |           663.618 |   348.618    |
|  48 |  128.9   | 743 W Pima St Phoenix AZ 85007                       |         4 |       2 |  1.456 |           476.155 |   347.255    |
|  49 |  174.9   | 1916 W Tonto St Phoenix AZ 85009                     |         3 |       2 |  1.741 |           520.638 |   345.738    |
|  50 |  160     | 15402 N 28th St UNIT 129 Phoenix AZ 85032            |         3 |       2 |  1.6   |           504.138 |   344.138    |
|  51 |  153.5   | 7129 W Highland Ave Phoenix AZ 85033                 |         4 |       3 |  2     |           496.873 |   343.373    |
|  52 |  195     | 2250 E Garfield St Phoenix AZ 85006                  |         4 |       3 |  2.346 |           537.362 |   342.362    |
|  53 |  239.9   | 4111 E Saint Catherine Ave Phoenix AZ 85042          |         4 |       4 |  3.083 |           580.665 |   340.765    |
|  54 |  309.9   | 2930 W Cavalier Dr Phoenix AZ 85017                  |         5 |       3 |  3.389 |           648.283 |   338.383    |
|  55 |  398.9   | 2002 W Carson Rd Phoenix AZ 85041                    |         5 |       6 |  5.237 |           735.712 |   336.812    |
|  56 |  359.9   | 13425 N 41st St Phoenix AZ 85032                     |         5 |       5 |  4.511 |           693.697 |   333.797    |
|  57 |  190     | 843 E Joan D Arc Ave Phoenix AZ 85022                |         3 |       1 |  1.392 |           522.739 |   332.739    |
|  58 |  125     | 3520 W Dunlap Ave #106 Phoenix AZ 85051              |         2 |       2 |  1.108 |           457.696 |   332.696    |
|  59 |  379.9   | 9802 S 29th Dr Laveen AZ 85339                       |         5 |       6 |  5.028 |           711.255 |   331.355    |
|  60 |  125     | 9228 N 7th Ave APT 3 Phoenix AZ 85021                |         4 |       3 |  1.652 |           456.15  |   331.15     |
|  61 |  289.9   | 5215 N 24th St APT 104 Phoenix AZ 85016              |         4 |       3 |  3.053 |           620.096 |   330.196    |
|  62 |  250     | 7108 W Almeria Rd Phoenix AZ 85035                   |         3 |       2 |  2.152 |           568.734 |   318.734    |
|  63 |  302.99  | Gull Plan Tuscano                                    |         4 |       3 |  3.053 |           620.096 |   317.106    |
|  64 |  189     | 1217 S 14th Ave Phoenix AZ 85007                     |         3 |       2 |  1.6   |           504.138 |   315.138    |
|  65 |  399.9   | 4536 N 18th Dr Phoenix AZ 85015                      |         4 |       4 |  4.178 |           708.803 |   308.903    |
|  66 |  179.5   | 1701 E Colter St UNIT 142 Phoenix AZ 85016           |         2 |       1 |  1     |           487.999 |   308.499    |
|  67 |  219     | 712 E Eugie Ave Phoenix AZ 85022                     |         4 |       2 |  1.871 |           524.719 |   305.719    |
|  68 |  219     | 4835 S 36th Dr Phoenix AZ 85041                      |         4 |       3 |  2.228 |           523.554 |   304.554    |
|  69 |  135     | 7101 N 36th Ave APT 129 Phoenix AZ 85051             |         3 |       2 |  1.024 |           436.734 |   301.734    |
|  70 |  179.999 | 1620 E Cambridge Ave APT 5 Phoenix AZ 85006          |         3 |       3 |  1.676 |           470.09  |   290.091    |
|  71 |  175     | 4901 E Kelton Ln UNIT 1040 Scottsdale AZ 85254       |         3 |       2 |  1.26  |           464.351 |   289.351    |
|  72 |  324.9   | 4022 W Thunderbird Rd Phoenix AZ 85053               |         5 |       3 |  3.083 |           612.475 |   287.574    |
|  73 |  269.5   | 1745 W Pershing Ave Phoenix AZ 85029                 |         4 |       2 |  2.124 |           554.325 |   284.825    |
|  74 |  330     | 1217 E Hess Ave Phoenix AZ 85034                     |         3 |       3 |  2.908 |           614.26  |   284.26     |
|  75 |  250     | 5820 N 35th Ave Phoenix AZ 85017                     |         1 |       2 |  1.652 |           532.487 |   282.487    |
|  76 |  240     | 10254 W Windsor Blvd Glendale AZ 85307               |         3 |       2 |  1.741 |           520.638 |   280.638    |
|  77 |  199     | 2450 W Glenrosa Ave UNIT 47 Phoenix AZ 85015         |         4 |       2 |  1.456 |           476.155 |   277.155    |
|  78 |  280     | 1334 E Cinnabar Ave Phoenix AZ 85020                 |         4 |       3 |  2.502 |           555.617 |   275.617    |
|  79 |  257     | 115 E Palm Ln UNIT D Phoenix AZ 85004                |         4 |       2 |  1.922 |           530.687 |   273.687    |
|  80 |  437.99  | Dove Plan Stone Butte                                |         5 |       6 |  5.028 |           711.255 |   273.265    |
|  81 |  250     | 7956 W Clayton Dr Phoenix AZ 85033                   |         3 |       1 |  1.392 |           522.739 |   272.739    |
|  82 |  192.1   | 3830 E Lakewood Pkwy E APT 3098 Phoenix AZ 85048     |         1 |       1 |  0.693 |           463.206 |   271.106    |
|  83 |  325     | 17624 N 14th Ave Phoenix AZ 85023                    |         4 |       2 |  2.477 |           595.633 |   270.633    |
|  84 |  299     | 5621 S 10th Dr Phoenix AZ 85041                      |         5 |       4 |  3.06  |           566.841 |   267.841    |
|  85 |  315     | 2921 W El Caminito Dr Phoenix AZ 85051               |         4 |       4 |  3.083 |           580.665 |   265.665    |
|  86 |  191     | 1542 W Carson Rd Phoenix AZ 85041                    |         4 |       3 |  1.652 |           456.15  |   265.15     |
|  87 |  349.5   | 6119 N 19th Ave Phoenix AZ 85015                     |         5 |       3 |  3.083 |           612.475 |   262.974    |
|  88 |  310     | 4062 E Danbury Rd Phoenix AZ 85032                   |         4 |       3 |  2.624 |           569.894 |   259.894    |
|  89 |  283     | 6316 N 23rd Ave Phoenix AZ 85015                     |         4 |       2 |  2.014 |           541.453 |   258.453    |
|  90 |  235     | 5846 W Cheery Lynn Rd Phoenix AZ 85031               |         2 |       2 |  1.401 |           491.983 |   256.983    |
|  91 |  265     | 1344 E Sahuaro Dr Phoenix AZ 85020                   |         3 |       2 |  1.741 |           520.638 |   255.638    |
|  92 |  299.999 | 1913 W Holly St Phoenix AZ 85009                     |         4 |       3 |  2.502 |           555.617 |   255.618    |
|  93 |  357     | 3825 W Carver Rd Laveen AZ 85339                     |         5 |       3 |  3.083 |           612.475 |   255.474    |
|  94 |  358.99  | Jubilee Plan Sunset Place                            |         3 |       3 |  2.908 |           614.26  |   255.27     |
|  95 |  364.9   | 4941 W Phelps Rd Glendale AZ 85306                   |         4 |       3 |  3.053 |           620.096 |   255.196    |
|  96 |  199.5   | 4211 N 51st Ave Phoenix AZ 85031                     |         3 |       2 |  1.177 |           454.638 |   255.138    |
|  97 |  269.9   | 1742 W North Ln Phoenix AZ 85021                     |         3 |       2 |  1.777 |           524.851 |   254.951    |
|  98 |  439.9   | 1802 W Rovey Ave Phoenix AZ 85015                    |         5 |       5 |  4.511 |           693.697 |   253.797    |
|  99 |  270     | 2944 N 79th Ln Phoenix AZ 85033                      |         4 |       3 |  2.228 |           523.554 |   253.554    |
| 100 |  219.9   | 1032 N 27th Dr Phoenix AZ 85009                      |         3 |       3 |  1.676 |           470.09  |   250.19     |
| 101 |  257.5   | 7323 W Sells Dr Phoenix AZ 85033                     |         3 |       2 |  1.63  |           507.649 |   250.149    |
| 102 |  399.9   | 1406 W Clarendon Ave Phoenix AZ 85013                |         5 |       3 |  3.389 |           648.283 |   248.383    |
| 103 |  189     | 17435 N 15th Pl Phoenix AZ 85022                     |         3 |       2 |  1.024 |           436.734 |   247.734    |
| 104 |  210     | 2211 W Medlock Dr Phoenix AZ 85015                   |         2 |       2 |  1.108 |           457.696 |   247.696    |
| 105 |  293.99  | Mayfair Plan Ellison Trails                          |         4 |       2 |  2.014 |           541.453 |   247.463    |
| 106 |  292     | 4907 E Hopi St Phoenix AZ 85044                      |         3 |       2 |  1.881 |           537.021 |   245.021    |
| 107 |  250     | 4510 W Weldon Ave Phoenix AZ 85031                   |         6 |       2 |  1.798 |           493.912 |   243.912    |
| 108 |  450     | 2605 W Luce Dr Phoenix AZ 85086                      |         5 |       5 |  4.511 |           693.697 |   243.697    |
| 109 |  320     | 2934 W Carson Rd Phoenix AZ 85041                    |         4 |       2 |  2.203 |           563.57  |   243.57     |
| 110 |  278     | 4925 E Desert Cove Ave UNIT 142 Scottsdale AZ 85254  |         3 |       2 |  1.741 |           520.638 |   242.638    |
| 111 |  234     | 2436 W Caribbean Ln UNIT 9 Phoenix AZ 85023          |         4 |       2 |  1.456 |           476.155 |   242.155    |
| 112 |  209.9   | 5525 E Thomas Rd UNIT N6 Phoenix AZ 85018            |         3 |       2 |  1.136 |           449.84  |   239.94     |
| 113 |  284.9   | 3961 W Culver St Phoenix AZ 85009                    |         4 |       2 |  1.872 |           524.836 |   239.936    |
| 114 |  292     | 310 S 4th St UNIT 907 Phoenix AZ 85004               |         4 |       2 |  1.922 |           530.687 |   238.687    |
| 115 |  225     | 2068 W Wayland Rd Phoenix AZ 85041                   |         1 |       1 |  0.693 |           463.206 |   238.206    |
| 116 |  382     | 2021 W Palmaire Ave Phoenix AZ 85021                 |         4 |       3 |  3.053 |           620.096 |   238.096    |
| 117 |  250     | 2913 W Orangewood Ave Phoenix AZ 85051               |         2 |       1 |  1     |           487.999 |   237.999    |
| 118 |  285     | 3722 W Caron St Phoenix AZ 85051                     |         3 |       1 |  1.392 |           522.739 |   237.739    |
| 119 |  299.9   | 6900 E Princess Dr UNIT 1215 Phoenix AZ 85054        |         4 |       3 |  2.346 |           537.362 |   237.462    |
| 120 |  299.9   | 3632 N 88th Dr Phoenix AZ 85037                      |         4 |       3 |  2.346 |           537.362 |   237.462    |
| 121 |  245     | 4644 N 22nd St UNIT 1008 Phoenix AZ 85016            |         1 |       1 |  0.85  |           481.578 |   236.578    |
| 122 |  320     | 4536 N 17th Dr Phoenix AZ 85015                      |         4 |       3 |  2.502 |           555.617 |   235.617    |
| 123 |  280     | 6535 W Heatherbrae Dr Phoenix AZ 85033               |         3 |       3 |  2.055 |           514.441 |   234.441    |
| 124 |  270     | 3048 W Chanute Pass Phoenix AZ 85041                 |         3 |       2 |  1.6   |           504.138 |   234.138    |
| 125 |  289.9   | 8602 W Kingman St Tolleson AZ 85353                  |         4 |       3 |  2.228 |           523.554 |   233.654    |
| 126 |  290.99  | Vela Plan 23 North                                   |         4 |       3 |  2.228 |           523.554 |   232.564    |
| 127 |  250     | 5061 W Avalon Dr Phoenix AZ 85031                    |         4 |       2 |  1.508 |           482.24  |   232.24     |
| 128 |  465     | 3610 W Aster Dr Phoenix AZ 85029                     |         5 |       5 |  4.511 |           693.697 |   228.697    |
| 129 |  229.9   | 2520 W Diana Ave Phoenix AZ 85021                    |         4 |       2 |  1.302 |           458.134 |   228.234    |
| 130 |  249.9   | 4049 W Earll Dr Phoenix AZ 85019                     |         4 |       3 |  1.82  |           475.809 |   225.909    |
| 131 |  225     | 2301 E Taylor St Phoenix AZ 85006                    |         3 |       2 |  1.136 |           449.84  |   224.84     |
| 132 |  232     | 2534 N 48th Dr Phoenix AZ 85035                      |         4 |       3 |  1.652 |           456.15  |   224.15     |
| 133 |  257.5   | 6031 W Illini St Phoenix AZ 85043                    |         4 |       3 |  1.862 |           480.724 |   223.224    |
| 134 |  310     | 4923 W Rosewood Dr Glendale AZ 85304                 |         1 |       2 |  1.652 |           532.487 |   222.487    |
| 135 |  349.9   | 3931 W Charter Oak Rd Phoenix AZ 85029               |         4 |       2 |  2.272 |           571.644 |   221.744    |
| 136 |  303     | 19408 N 13th Ave Phoenix AZ 85027                    |         4 |       3 |  2.228 |           523.554 |   220.554    |
| 137 |  275     | 4031 W Glenn Dr Phoenix AZ 85051                     |         4 |       2 |  1.619 |           495.23  |   220.23     |
| 138 |  399.9   | 530 W Cypress St Phoenix AZ 85003                    |         4 |       3 |  3.053 |           620.096 |   220.196    |
| 139 |  295     | 2331 W Darrel Rd Phoenix AZ 85041                    |         3 |       3 |  2.055 |           514.441 |   219.441    |
| 140 |  337.2   | 6606 S 57th Ave Laveen AZ 85339                      |         4 |       3 |  2.503 |           555.734 |   218.534    |
| 141 |  256     | 125 E Campo Bello Dr Phoenix AZ 85022                |         3 |       2 |  1.322 |           471.606 |   215.606    |
| 142 |  280     | 4215 W Pershing Ave Phoenix AZ 85029                 |         2 |       2 |  1.401 |           491.983 |   211.983    |
| 143 |  330     | 2707 E Atlanta Ave Phoenix AZ 85040                  |         4 |       2 |  2.014 |           541.453 |   211.453    |
| 144 |  315     | 1608 W Rockwood Dr Phoenix AZ 85027                  |         3 |       2 |  1.777 |           524.851 |   209.851    |
| 145 |  260     | 3442 N 39th Dr Phoenix AZ 85019                      |         4 |       2 |  1.4   |           469.602 |   209.602    |
| 146 |  250     | 5008 W Virginia Ave Phoenix AZ 85035                 |         2 |       2 |  1.108 |           457.696 |   207.696    |
| 147 |  325     | 914 E Osborn Rd UNIT 212 Phoenix AZ 85014            |         1 |       2 |  1.652 |           532.487 |   207.487    |
| 148 |  346.9   | 5811 W Pedro Ln Laveen AZ 85339                      |         4 |       2 |  2.124 |           554.325 |   207.425    |
| 149 |  349.9   | 101 W Oraibi Dr Phoenix AZ 85027                     |         4 |       3 |  2.502 |           555.617 |   205.717    |
| 150 |  374.99  | Erikson Plan Tierra Montana Discovery Collection     |         4 |       4 |  3.083 |           580.665 |   205.675    |
| 151 |  340     | 3155 W Altadena Ave Phoenix AZ 85029                 |         4 |       2 |  2.05  |           545.665 |   205.665    |
| 152 |  284.9   | 2219 S 101st Dr Tolleson AZ 85353                    |         3 |       2 |  1.475 |           489.51  |   204.61     |
| 153 |  290     | 1342 E Burgess Ln Phoenix AZ 85042                   |         6 |       2 |  1.798 |           493.912 |   203.912    |
| 154 |  352     | 15214 N 25th St Phoenix AZ 85032                     |         4 |       3 |  2.502 |           555.617 |   203.617    |
| 155 |  329     | 6416 W Berkeley Rd Phoenix AZ 85035                  |         1 |       2 |  1.652 |           532.487 |   203.487    |
| 156 |  280     | 3836 W Becker Ln Phoenix AZ 85029                    |         3 |       2 |  1.419 |           482.957 |   202.957    |
| 157 |  334.99  | Pelican Plan Prior Ridge                             |         3 |       2 |  1.881 |           537.021 |   202.031    |
| 158 |  325     | 11014 N 40th Dr Phoenix AZ 85029                     |         4 |       2 |  1.871 |           524.719 |   199.719    |
| 159 |  269.995 | 2929 W Mckinley St Phoenix AZ 85009                  |         4 |       2 |  1.4   |           469.602 |   199.607    |
| 160 |  269.995 | 720 E Desert Ln Phoenix AZ 85042                     |         4 |       2 |  1.4   |           469.602 |   199.607    |
| 161 |  238     | 3926 S 3rd Ave Phoenix AZ 85041                      |         3 |       2 |  1.024 |           436.734 |   198.734    |
| 162 |  339.9   | 207 E Valley View Dr Phoenix AZ 85042                |         4 |       3 |  2.346 |           537.362 |   197.462    |
| 163 |  329     | 8614 N 26th Ave Phoenix AZ 85021                     |         4 |       2 |  1.872 |           524.836 |   195.836    |
| 164 |  325     | 6512 N Maryland Cir Phoenix AZ 85013                 |         3 |       2 |  1.741 |           520.638 |   195.638    |
| 165 |  344.99  | Carefree Plan Alara                                  |         3 |       2 |  1.888 |           537.84  |   192.85     |
| 166 |  290     | 3017 W Stella Ln Phoenix AZ 85017                    |         3 |       2 |  1.411 |           482.021 |   192.021    |
| 167 |  429     | 2034 N Dayton St Phoenix AZ 85006                    |         4 |       3 |  3.055 |           620.33  |   191.33     |
| 168 |  330     | 9227 W Raymond St Tolleson AZ 85353                  |         3 |       2 |  1.741 |           520.638 |   190.638    |
| 169 |  335     | 1939 W Amelia Ave Phoenix AZ 85015                   |         3 |       2 |  1.777 |           524.851 |   189.851    |
| 170 |  475     | 2223 W Calle Del Sol Phoenix AZ 85085                |         5 |       4 |  3.887 |           663.618 |   188.618    |
| 171 |  309.9   | 10344 W Yuma St Tolleson AZ 85353                    |         4 |       3 |  2     |           496.873 |   186.973    |
| 172 |  249.9   | 6900 E Princess Dr UNIT 1128 Phoenix AZ 85054        |         3 |       2 |  1.024 |           436.734 |   186.834    |
| 173 |  265     | 395 N 21st Ave Phoenix AZ 85009                      |         4 |       2 |  1.248 |           451.815 |   186.815    |
| 174 |  290     | 7321 W Wolf St Phoenix AZ 85033                      |         4 |       3 |  1.82  |           475.809 |   185.809    |
| 175 |  359.995 | 4102 W Cholla St Phoenix AZ 85029                    |         4 |       2 |  2.05  |           545.665 |   185.67     |
| 176 |  319.5   | 4420 W Shangri La Rd Glendale AZ 85304               |         3 |       2 |  1.6   |           504.138 |   184.638    |
| 177 |  427.99  | Darius Plan The Preserve at Tuscano                  |         5 |       3 |  3.083 |           612.475 |   184.484    |
| 178 |  300     | 6505 S 15th Dr Phoenix AZ 85041                      |         3 |       3 |  1.798 |           484.367 |   184.367    |
| 179 |  324.9   | 4223 W Eva St Phoenix AZ 85051                       |         3 |       2 |  1.63  |           507.649 |   182.749    |
| 180 |  324.9   | 3731 W Marlette Ave Phoenix AZ 85019                 |         5 |       3 |  2.17  |           505.635 |   180.734    |
| 181 |  345     | 8022 W Williams St Phoenix AZ 85043                  |         3 |       2 |  1.777 |           524.851 |   179.851    |
| 182 |  324.99  | Goose Plan Alara                                     |         3 |       2 |  1.6   |           504.138 |   179.148    |
| 183 |  419.5   | 16201 S 42nd St Phoenix AZ 85048                     |         4 |       2 |  2.477 |           595.633 |   176.133    |
| 184 |  355     | 4808 N 24th St UNIT 925 Phoenix AZ 85016             |         4 |       2 |  1.922 |           530.687 |   175.687    |
| 185 |  299.9   | 15814 N 38th Dr Phoenix AZ 85053                     |         3 |       2 |  1.355 |           475.468 |   175.568    |
| 186 |  281     | 3236 E Chandler Blvd UNIT 1036 Phoenix AZ 85048      |         4 |       3 |  1.652 |           456.15  |   175.15     |
| 187 |  445     | 2446 E Glass Ln Phoenix AZ 85042                     |         4 |       3 |  3.053 |           620.096 |   175.096    |
| 188 |  319.9   | 3043 W Tuckey Ln Phoenix AZ 85017                    |         6 |       2 |  1.798 |           493.912 |   174.012    |
| 189 |  405     | 2423 W Crimson Ter Phoenix AZ 85085                  |         4 |       2 |  2.332 |           578.665 |   173.665    |
| 190 |  289.9   | 3505 E Helena Dr Phoenix AZ 85032                    |         3 |       1 |  0.882 |           463.059 |   173.159    |
| 191 |  375     | 1932 E Alta Vista Rd Phoenix AZ 85042                |         4 |       2 |  2.07  |           548.006 |   173.006    |
| 192 |  265     | 20835 N 34th Dr Phoenix AZ 85027                     |         3 |       2 |  1.024 |           436.734 |   171.734    |
| 193 |  338.9   | 15211 N 28th Pl Phoenix AZ 85032                     |         2 |       2 |  1.558 |           510.355 |   171.455    |
| 194 |  299.9   | 223 W Darrow St Phoenix AZ 85041                     |         3 |       2 |  1.309 |           470.085 |   170.185    |
| 195 |  367.5   | 2718 E Victor Hugo Ave Phoenix AZ 85032              |         4 |       3 |  2.346 |           537.362 |   169.862    |
| 196 |  325     | 207 W Clarendon Ave UNIT 6E Phoenix AZ 85013         |         6 |       2 |  1.798 |           493.912 |   168.912    |
| 197 |  374.9   | 13838 N 36th Ave Phoenix AZ 85053                    |         4 |       2 |  2.014 |           541.453 |   166.553    |
| 198 |  375     | 4124 E Barwick Dr Cave Creek AZ 85331                |         4 |       2 |  2.014 |           541.453 |   166.453    |
| 199 |  499     | 5638 N 14th Dr Phoenix AZ 85013                      |         5 |       4 |  3.887 |           663.618 |   164.618    |
| 200 |  385     | 15216 N La Paz Ct Phoenix AZ 85053                   |         4 |       4 |  2.798 |           547.314 |   162.314    |
| 201 |  460     | 8623 S 45th Gln Laveen AZ 85339                      |         4 |       3 |  3.055 |           620.33  |   160.33     |
| 202 |  285     | 6254 W Mcdowell Rd Phoenix AZ 85035                  |         2 |       2 |  1.002 |           445.291 |   160.292    |
| 203 |  339     | 15222 N 28th Pl Phoenix AZ 85032                     |         4 |       3 |  2     |           496.873 |   157.873    |
| 204 |  339     | 3914 W Berridge Ln Phoenix AZ 85019                  |         4 |       3 |  2     |           496.873 |   157.873    |
| 205 |  300     | 4149 W Wethersfield Rd Phoenix AZ 85029              |         3 |       3 |  1.567 |           457.335 |   157.335    |
| 206 |  369     | 4026 N 9th St Phoenix AZ 85014                       |         3 |       2 |  1.777 |           524.851 |   155.851    |
| 207 |  350     | 16232 S 41st St Phoenix AZ 85048                     |         5 |       3 |  2.17  |           505.635 |   155.634    |
| 208 |  380     | 22025 N 34th Ave Phoenix AZ 85027                    |         1 |       2 |  1.652 |           532.487 |   152.487    |
| 209 |  325     | 2007 W Dahlia Dr Phoenix AZ 85029                    |         3 |       2 |  1.322 |           471.606 |   146.606    |
| 210 |  374.9   | 4016 W Dailey St Phoenix AZ 85053                    |         3 |       2 |  1.741 |           520.638 |   145.738    |
| 211 |  325     | 1440 E Mckinley St Phoenix AZ 85006                  |         4 |       2 |  1.4   |           469.602 |   144.602    |
| 212 |  325     | 18050 N 24th Ave Phoenix AZ 85023                    |         4 |       2 |  1.4   |           469.602 |   144.602    |
| 213 |  365     | 3024 E Rockwood Dr Phoenix AZ 85050                  |         3 |       2 |  1.64  |           508.819 |   143.819    |
| 214 |  360.99  | Canyon Plan Landmark in Santolina at South Mountain  |         3 |       2 |  1.6   |           504.138 |   143.148    |
| 215 |  310     | 20016 N 8th Pl Phoenix AZ 85024                      |         3 |       2 |  1.136 |           449.84  |   139.84     |
| 216 |  345.9   | 1927 W Mitchell Dr Phoenix AZ 85015                  |         2 |       2 |  1.344 |           485.313 |   139.413    |
| 217 |  335     | 4560 W Morrow Dr Glendale AZ 85308                   |         3 |       3 |  1.676 |           470.09  |   135.09     |
| 218 |  354.9   | 9409 N 11th Pl Phoenix AZ 85020                      |         2 |       1 |  1     |           487.999 |   133.099    |
| 219 |  350     | 2420 W Dusty Wren Dr Phoenix AZ 85085                |         3 |       2 |  1.419 |           482.957 |   132.957    |
| 220 |  319.99  | 17844 N 29th Ave Phoenix AZ 85053                    |         4 |       2 |  1.248 |           451.815 |   131.825    |
| 221 |  389.9   | 3511 E Willow Ave Phoenix AZ 85032                   |         3 |       2 |  1.741 |           520.638 |   130.738    |
| 222 |  355     | 19666 N 9th St Phoenix AZ 85024                      |         3 |       2 |  1.411 |           482.021 |   127.021    |
| 223 |  429     | 1745 E San Juan Ave Phoenix AZ 85016                 |         4 |       3 |  2.502 |           555.617 |   126.617    |
| 224 |  325     | 1501 E Brill St Phoenix AZ 85006                     |         3 |       2 |  1.136 |           449.84  |   124.84     |
| 225 |  370     | 4301 N 21st St UNIT 18 Phoenix AZ 85016              |         6 |       2 |  1.798 |           493.912 |   123.912    |
| 226 |  375     | 305 E Roeser Rd APT B Phoenix AZ 85040               |         4 |       3 |  2     |           496.873 |   121.873    |
| 227 |  330     | 3325 W Shaw Butte Dr Phoenix AZ 85029                |         4 |       2 |  1.248 |           451.815 |   121.815    |
| 228 |  355     | 3928 E Branham Ln Phoenix AZ 85042                   |         4 |       2 |  1.456 |           476.155 |   121.155    |
| 229 |  359.999 | 17629 N 36th St Phoenix AZ 85032                     |         4 |       3 |  1.862 |           480.724 |   120.725    |
| 230 |  350     | 4431 W Mcrae Way Glendale AZ 85308                   |         3 |       2 |  1.309 |           470.085 |   120.085    |
| 231 |  375     | 17837 N 47th St Phoenix AZ 85032                     |         3 |       2 |  1.488 |           491.032 |   116.032    |
| 232 |  499     | 5118 N 18th Pl Phoenix AZ 85016                      |         3 |       3 |  2.908 |           614.26  |   115.26     |
| 233 |  350     | 2529 N 30th St Phoenix AZ 85008                      |         3 |       2 |  1.26  |           464.351 |   114.351    |
| 234 |  370.99  | Phoenix Plan Alara                                   |         2 |       2 |  1.344 |           485.313 |   114.323    |
| 235 |  349.888 | 3401 N 84th Ln Phoenix AZ 85037                      |         3 |       1 |  0.882 |           463.059 |   113.171    |
| 236 |  339     | 5350 E Deer Valley Dr UNIT 1427 Phoenix AZ 85054     |         4 |       2 |  1.248 |           451.815 |   112.815    |
| 237 |  439.5   | 4502 W Paradise Ln Glendale AZ 85306                 |         4 |       2 |  2.07  |           548.006 |   108.506    |
| 238 |  349     | 17049 N 39th Ave Glendale AZ 85308                   |         4 |       3 |  1.652 |           456.15  |   107.15     |
| 239 |  399     | 16828 S 13th Way Phoenix AZ 85048                    |         3 |       2 |  1.6   |           504.138 |   105.138    |
| 240 |  399.945 | 5739 N 16th St Phoenix AZ 85016                      |         4 |       2 |  1.703 |           505.059 |   105.114    |
| 241 |  335     | 2202 E Delgado St Phoenix AZ 85022                   |         3 |       3 |  1.419 |           440.016 |   105.016    |
| 242 |  491.99  | Powell Plan Tierra Montana Passage Collection        |         4 |       2 |  2.477 |           595.633 |   103.643    |
| 243 |  430     | 7 E Piping Rock Rd Phoenix AZ 85022                  |         4 |       2 |  1.922 |           530.687 |   100.687    |
| 244 |  339.9   | 1513 E Wescott Dr Phoenix AZ 85024                   |         3 |       3 |  1.419 |           440.016 |   100.116    |
| 245 |  370     | 1719 W Fairmount Ave Phoenix AZ 85015                |         3 |       3 |  1.676 |           470.09  |   100.09     |
| 246 |  425     | 3122 N 34th Pl Phoenix AZ 85018                      |         3 |       1 |  1.392 |           522.739 |    97.7393   |
| 247 |  342.99  | Omni Plan Prior Ridge                                |         3 |       3 |  1.419 |           440.016 |    97.0257   |
| 248 |  360     | 11640 N Tatum Blvd UNIT 3023 Phoenix AZ 85028        |         4 |       3 |  1.652 |           456.15  |    96.1496   |
| 249 |  360     | 5623 S 36th Dr Phoenix AZ 85041                      |         3 |       2 |  1.177 |           454.638 |    94.6382   |
| 250 |  519.9   | 121 E Tam Oshanter Dr Phoenix AZ 85022               |         3 |       3 |  2.908 |           614.26  |    94.3596   |
| 251 |  370     | 3202 E Captain Dreyfus Ave Phoenix AZ 85032          |         3 |       2 |  1.26  |           464.351 |    94.351    |
| 252 |  381.99  | Liberty Plan Landmark in Santolina at South Mountain |         4 |       2 |  1.456 |           476.155 |    94.1652   |
| 253 |  400     | 20032 N 44th Ave Glendale AZ 85308                   |         6 |       2 |  1.798 |           493.912 |    93.9124   |
| 254 |  350     | 3030 N 15th Ave Phoenix AZ 85015                     |         3 |       3 |  1.419 |           440.016 |    90.0157   |
| 255 |  480     | 2214 N 12th St Phoenix AZ 85006                      |         3 |       2 |  2.152 |           568.734 |    88.7335   |
| 256 |  484.9   | 5235 S 22nd St Phoenix AZ 85040                      |         4 |       2 |  2.272 |           571.644 |    86.7441   |
| 257 |  367     | 2618 N Dayton St Phoenix AZ 85006                    |         4 |       2 |  1.248 |           451.815 |    84.8148   |
| 258 |  353     | 9016 S 4th St Phoenix AZ 85042                       |         3 |       2 |  1.024 |           436.734 |    83.7341   |
| 259 |  415     | 917 W Turney Ave Phoenix AZ 85013                    |         4 |       3 |  2     |           496.873 |    81.8729   |
| 260 |  486.99  | Jordan Plan Stone Butte                              |         3 |       2 |  2.152 |           568.734 |    81.7435   |
| 261 |  450     | 917 W Mcdowell Rd Phoenix AZ 85007                   |         4 |       2 |  1.922 |           530.687 |    80.6868   |
| 262 |  489     | 6434 S 12th St Phoenix AZ 85042                      |         5 |       4 |  3.06  |           566.841 |    77.8414   |
| 263 |  379.999 | 3861 W Caribbean Ln Phoenix AZ 85053                 |         4 |       3 |  1.652 |           456.15  |    76.1506   |
| 264 |  394.8   | 4808 N 24th St UNIT 427 Phoenix AZ 85016             |         3 |       3 |  1.676 |           470.09  |    75.29     |
| 265 |  450     | 2725 N 27th St Phoenix AZ 85008                      |         4 |       2 |  1.872 |           524.836 |    74.8358   |
| 266 |  450     | 1426 W Missouri Ave Phoenix AZ 85013                 |         3 |       1 |  1.392 |           522.739 |    72.7393   |
| 267 |  374.9   | 1632 E Harvard St Phoenix AZ 85006                   |         2 |       2 |  1.002 |           445.291 |    70.3915   |
| 268 |  400     | 1010 E Southern Ave Phoenix AZ 85040                 |         3 |       3 |  1.676 |           470.09  |    70.09     |
| 269 |  375     | 4124 E Barwick Dr Cave Creek AZ 85331                |         3 |       3 |  1.419 |           440.016 |    65.0157   |
| 270 |  400     | 9027 N 11th St Phoenix AZ 85020                      |         3 |       2 |  1.26  |           464.351 |    64.351    |
| 271 |  395     | 14652 N 44th Pl Phoenix AZ 85032                     |         4 |       2 |  1.302 |           458.134 |    63.1339   |
| 272 |  469.9   | 702 E Coral Gables Dr Phoenix AZ 85022               |         4 |       2 |  1.922 |           530.687 |    60.7868   |
| 273 |  495     | 3903 E Mountain Vista Dr Phoenix AZ 85048            |         4 |       3 |  2.502 |           555.617 |    60.6173   |
| 274 |  650     | 35313 N 26th Ave Phoenix AZ 85086                    |         4 |       4 |  4.178 |           708.803 |    58.8026   |
| 275 |  555     | 4114 E Liberty Ln Phoenix AZ 85048                   |         5 |       3 |  3.083 |           612.475 |    57.4745   |
| 276 |  379.9   | 814 S 1st Ave Phoenix AZ 85003                       |         3 |       2 |  1.024 |           436.734 |    56.8341   |
| 277 |  425     | 1142 E Garfield St Phoenix AZ 85006                  |         4 |       3 |  1.862 |           480.724 |    55.724    |
| 278 |  389.9   | 2238 E Osborn Rd Phoenix AZ 85016                    |         3 |       3 |  1.419 |           440.016 |    50.1157   |
| 279 |  489.999 | 719 W Marshall Ave Phoenix AZ 85013                  |         4 |       3 |  2.346 |           537.362 |    47.3631   |
| 280 |  650     | 2729 E Purdue Ave Phoenix AZ 85028                   |         5 |       5 |  4.511 |           693.697 |    43.697    |
| 281 |  399     | 3101 E Roosevelt St Phoenix AZ 85008                 |         3 |       3 |  1.419 |           440.016 |    41.0157   |
| 282 |  695     | 2626 E Arizona Biltmore Cir UNIT 2 Phoenix AZ 85016  |         5 |       6 |  5.237 |           735.712 |    40.7125   |
| 283 |  487.99  | Oriole Plan Copperhead                               |         4 |       2 |  1.872 |           524.836 |    36.8458   |
| 284 |  590     | 1936 E Missouri Ave Phoenix AZ 85016                 |         4 |       3 |  3.053 |           620.096 |    30.0958   |
| 285 |  439     | 2712 E Highland Ave Phoenix AZ 85016                 |         3 |       1 |  0.882 |           463.059 |    24.0587   |
| 286 |  535     | 2218 E Virginia Ave Phoenix AZ 85006                 |         4 |       3 |  2.503 |           555.734 |    20.7343   |
| 287 |  559.9   | 15020 N 7th Dr Phoenix AZ 85023                      |         4 |       2 |  2.332 |           578.665 |    18.7653   |
| 288 |  550     | 27601 N 47th St Cave Creek AZ 85331                  |         3 |       2 |  2.152 |           568.734 |    18.7335   |
| 289 |  480     | 9818 S 26th Ln Phoenix AZ 85041                      |         4 |       2 |  1.619 |           495.23  |    15.2295   |
| 290 |  450     | 4749 E Amber Sun Dr Cave Creek AZ 85331              |         3 |       1 |  0.882 |           463.059 |    13.0587   |
| 291 |  569.9   | 3419 E Rosemonte Dr Phoenix AZ 85050                 |         4 |       4 |  3.083 |           580.665 |    10.7648   |
| 292 |  699     | 2315 N 54th St Phoenix AZ 85008                      |         4 |       4 |  4.178 |           708.803 |     9.80261  |
| 293 |  639     | 1346 E Thistle Landing Dr Phoenix AZ 85048           |         5 |       3 |  3.389 |           648.283 |     9.28284  |
| 294 |  485     | 2304 E Monterosa St Phoenix AZ 85016                 |         6 |       2 |  1.798 |           493.912 |     8.91245  |
| 295 |  515     | 702 W Wilshire Dr Phoenix AZ 85007                   |         3 |       1 |  1.392 |           522.739 |     7.73932  |
| 296 |  530     | 5332 E Oak St Phoenix AZ 85008                       |         4 |       2 |  1.922 |           530.687 |     0.686829 |
| 297 |  485     | 14015 N Medinan Dr Phoenix AZ 85022                  |         2 |       2 |  1.344 |           485.313 |     0.312622 |
| 298 |  454.8   | 4235 E Desert Marigold Dr Cave Creek AZ 85331        |         4 |       2 |  1.248 |           451.815 |    -2.98518  |
| 299 |  469.999 | 33618 N 24th Ln Phoenix AZ 85085                     |         3 |       2 |  1.26  |           464.351 |    -5.64805  |
| 300 |  530     | 1509 E Rancho Dr Phoenix AZ 85014                    |         4 |       3 |  2.228 |           523.554 |    -6.44641  |
| 301 |  499     | 2236 N 37th St Phoenix AZ 85008                      |         3 |       2 |  1.475 |           489.51  |    -9.48956  |
| 302 |  550.99  | Lexington Plan Arabella                              |         4 |       2 |  2.014 |           541.453 |    -9.53724  |
| 303 |  482.99  | Hampton Plan Tierra Montana Passage Collection       |         4 |       2 |  1.4   |           469.602 |   -13.388    |
| 304 |  485     | 736 W Beverly Ln Phoenix AZ 85023                    |         3 |       3 |  1.676 |           470.09  |   -14.91     |
| 305 |  540     | 3302 E Turquoise Ave Phoenix AZ 85028                |         3 |       2 |  1.777 |           524.851 |   -15.1493   |
| 306 |  475     | 1843 E Turney Ave Phoenix AZ 85016                   |         4 |       3 |  1.652 |           456.15  |   -18.8504   |
| 307 |  496     | 1003 E Bethany Home Rd Phoenix AZ 85014              |         4 |       2 |  1.4   |           469.602 |   -26.398    |
| 308 |  484.99  | 4452 E Redwood Ln Phoenix AZ 85048                   |         2 |       2 |  1.108 |           457.696 |   -27.2943   |
| 309 |  630     | 29233 N 46th St Cave Creek AZ 85331                  |         4 |       2 |  2.477 |           595.633 |   -34.3666   |
| 310 |  500     | 1512 W Dunlap Ave Phoenix AZ 85021                   |         3 |       2 |  1.26  |           464.351 |   -35.649    |
| 311 |  699.9   | 15215 S 20th Pl Phoenix AZ 85048                     |         5 |       4 |  3.887 |           663.618 |   -36.2823   |
| 312 |  689     | 1929 E Seminole Dr Phoenix AZ 85022                  |         5 |       2 |  3.041 |           650.501 |   -38.4988   |
| 313 |  515     | 7355 N Black Canyon Hwy Phoenix AZ 85021             |         3 |       3 |  1.676 |           470.09  |   -44.91     |
| 314 |  713     | Alta Plan 1 Plan Alta at Avance                      |         5 |       4 |  3.887 |           663.618 |   -49.3823   |
| 315 |  575     | 3711 E Glenrosa Ave Phoenix AZ 85018                 |         3 |       2 |  1.777 |           524.851 |   -50.1493   |
| 316 |  595     | 34022 N 13th Pl Phoenix AZ 85085                     |         4 |       2 |  2.014 |           541.453 |   -53.5472   |
| 317 |  529.9   | 2107 W Caleb Rd Phoenix AZ 85085                     |         3 |       2 |  1.355 |           475.468 |   -54.4321   |
| 318 |  625     | 6511 W Silver Sage Ln Phoenix AZ 85083               |         4 |       3 |  2.624 |           569.894 |   -55.1062   |
| 319 |  500     | 4386 E Selena Dr Phoenix AZ 85050                    |         3 |       3 |  1.419 |           440.016 |   -59.9843   |
| 320 |  499.9   | 3115 W Languid Ln Phoenix AZ 85086                   |         3 |       2 |  1.024 |           436.734 |   -63.1659   |
| 321 |  550     | 4539 E Rancho Laredo Dr Cave Creek AZ 85331          |         3 |       3 |  1.798 |           484.367 |   -65.6335   |
| 322 |  551     | 5534 E Shaw Butte Dr Scottsdale AZ 85254             |         2 |       2 |  1.344 |           485.313 |   -65.6874   |
| 323 |  575     | 2307 W Coyote Wash Dr Phoenix AZ 85085               |         4 |       2 |  1.703 |           505.059 |   -69.9407   |
| 324 |  549.9   | 3025 W Leisure Ln Phoenix AZ 85086                   |         3 |       1 |  0.882 |           463.059 |   -86.8413   |
| 325 |  575     | 11016 N 10th St Phoenix AZ 85020                     |         2 |       1 |  1     |           487.999 |   -87.0009   |
| 326 |  555.9   | 6036 N 10th Way Phoenix AZ 85014                     |         3 |       1 |  0.882 |           463.059 |   -92.8413   |
| 327 |  558.5   | Ranger Plan 4 Plan Ranger at Avance                  |         3 |       2 |  1.26  |           464.351 |   -94.149    |
| 328 |  629.9   | 312 E Joan D Arc Ave Phoenix AZ 85022                |         1 |       2 |  1.652 |           532.487 |   -97.4131   |
| 329 |  599.999 | 24514 N 44th Ln Glendale AZ 85310                    |         6 |       2 |  1.798 |           493.912 |  -106.087    |
| 330 |  631     | 16629 S 38th Pl Phoenix AZ 85048                     |         4 |       2 |  1.872 |           524.836 |  -106.164    |
| 331 |  577.5   | 3839 E Glenhaven Dr Phoenix AZ 85048                 |         4 |       2 |  1.4   |           469.602 |  -107.898    |
| 332 |  775     | 3800 E Lincoln Dr UNIT 6 Phoenix AZ 85018            |         5 |       4 |  3.887 |           663.618 |  -111.382    |
| 333 |  575     | 4327 W Acoma Dr Glendale AZ 85306                    |         3 |       1 |  0.882 |           463.059 |  -111.941    |
| 334 |  878     | 10829 S 25th Dr Phoenix AZ 85041                     |         4 |       4 |  4.655 |           764.621 |  -113.378    |
| 335 |  850     | 9210 S 19th Ave Phoenix AZ 85041                     |         5 |       6 |  5.237 |           735.712 |  -114.288    |
| 336 |  739.9   | 1037 E Fairmount Ave Phoenix AZ 85014                |         4 |       3 |  3.055 |           620.33  |  -119.57     |
| 337 |  660     | 4967 E Evans Dr Scottsdale AZ 85254                  |         3 |       2 |  1.888 |           537.84  |  -122.16     |
| 338 |  659     | 91 W Willetta St Phoenix AZ 85003                    |         1 |       2 |  1.652 |           532.487 |  -126.513    |
| 339 |  742     | Alta Plan 2 Plan Alta at Avance                      |         5 |       3 |  3.083 |           612.475 |  -129.526    |
| 340 |  655     | 14350 N Medinan Dr Phoenix AZ 85022                  |         3 |       1 |  1.392 |           522.739 |  -132.261    |
| 341 |  659     | 3820 E Matthew Dr Phoenix AZ 85050                   |         4 |       3 |  2.228 |           523.554 |  -135.446    |
| 342 |  629     | 3038 N Evergreen St Phoenix AZ 85014                 |         3 |       2 |  1.488 |           491.032 |  -137.968    |
| 343 |  589     | 14404 N 14th Pl Phoenix AZ 85022                     |         3 |       2 |  1.136 |           449.84  |  -139.16     |
| 344 |  625     | 1832 N 7th Ave Phoenix AZ 85007                      |         4 |       3 |  1.862 |           480.724 |  -144.276    |
| 345 |  695     | 315 W Edgemont Ave Phoenix AZ 85003                  |         4 |       2 |  2.014 |           541.453 |  -153.547    |
| 346 |  749.9   | 2336 N 11th St Phoenix AZ 85006                      |         4 |       2 |  2.477 |           595.633 |  -154.267    |
| 347 |  779     | 5426 E Oak St Phoenix AZ 85008                       |         3 |       3 |  2.908 |           614.26  |  -164.74     |
| 348 |  737     | 341 W Edgemont Ave Phoenix AZ 85003                  |         3 |       2 |  2.152 |           568.734 |  -168.266    |
| 349 |  650     | 16625 S 27th Ln Phoenix AZ 85045                     |         1 |       1 |  0.85  |           481.578 |  -168.422    |
| 350 |  650     | 3043 N 34th St Phoenix AZ 85018                      |         4 |       3 |  1.862 |           480.724 |  -169.276    |
| 351 |  664.999 | 15243 N 10th St Phoenix AZ 85022                     |         2 |       2 |  1.108 |           457.696 |  -207.303    |
| 352 |  699     | 2835 W Belmont Ave Phoenix AZ 85051                  |         2 |       2 |  1.344 |           485.313 |  -213.687    |
| 353 |  719     | 1927 E Betty Elyse Ln Phoenix AZ 85022               |         4 |       3 |  2     |           496.873 |  -222.127    |
| 354 |  850     | 2332 E Lincoln Dr Phoenix AZ 85016                   |         4 |       3 |  3.055 |           620.33  |  -229.67     |
| 355 |  849     | 15856 S 38th St Phoenix AZ 85048                     |         5 |       3 |  3.083 |           612.475 |  -236.526    |
| 356 |  725     | 15035 N 54th Way Scottsdale AZ 85254                 |         2 |       2 |  1.344 |           485.313 |  -239.687    |
| 357 |  765     | 5852 E Nisbet Rd Scottsdale AZ 85254                 |         4 |       2 |  1.872 |           524.836 |  -240.164    |
| 358 |  899     | 6640 E Dreyfus Ave Scottsdale AZ 85254               |         5 |       3 |  3.389 |           648.283 |  -250.717    |
| 359 |  724.4   | 13451 N 50th St Scottsdale AZ 85254                  |         4 |       2 |  1.4   |           469.602 |  -254.798    |
| 360 |  725     | 18840 N 30th St Phoenix AZ 85050                     |         2 |       2 |  1.108 |           457.696 |  -267.304    |
| 361 |  739.9   | 4121 E Catalina Dr Phoenix AZ 85018                  |         4 |       2 |  1.4   |           469.602 |  -270.298    |
| 362 |  724.9   | 3206 E Desert Flower Ln Phoenix AZ 85044             |         3 |       2 |  1.136 |           449.84  |  -275.06     |
| 363 |  775     | 31013 N 1st Pl Phoenix AZ 85085                      |         2 |       1 |  1     |           487.999 |  -287.001    |
| 364 |  750     | 3826 E Saint Catherine Ave Phoenix AZ 85042          |         2 |       2 |  1.108 |           457.696 |  -292.304    |
| 365 |  760     | 501 W Encanto Blvd Phoenix AZ 85003                  |         3 |       3 |  1.567 |           457.335 |  -302.665    |
| 366 |  785     | 31312 N 1st St Phoenix AZ 85085                      |         4 |       3 |  1.862 |           480.724 |  -304.276    |
| 367 |  799.9   | 14617 N Coral Gables Dr Phoenix AZ 85023             |         2 |       2 |  1.344 |           485.313 |  -314.587    |
| 368 |  890     | 5410 E Cactus Rd Scottsdale AZ 85254                 |         3 |       2 |  2.152 |           568.734 |  -321.266    |
| 369 |  779     | 1802 E Brookwood Ct Phoenix AZ 85048                 |         3 |       2 |  1.136 |           449.84  |  -329.16     |
| 370 |  899     | 5002 N 38th Pl Phoenix AZ 85018                      |         3 |       2 |  2.152 |           568.734 |  -330.266    |
| 371 |  820     | 3039 E Rock Wren Rd Phoenix AZ 85048                 |         4 |       2 |  1.456 |           476.155 |  -343.845    |
| 372 |  975     | 5011 E Bluefield Ave Scottsdale AZ 85254             |         4 |       3 |  3.053 |           620.096 |  -354.904    |
| 373 |  995     | 1807 E Campbell Ave Phoenix AZ 85016                 |         3 |       3 |  2.908 |           614.26  |  -380.74     |
| 374 | 1100     | 4010 E San Juan Ave Phoenix AZ 85018                 |         5 |       6 |  5.028 |           711.255 |  -388.745    |
| 375 |  943     | 4701 W Electra Ln Glendale AZ 85310                  |         4 |       2 |  1.872 |           524.836 |  -418.164    |
| 376 | 1199     | 6047 E Calle De Pompas Cave Creek AZ 85331           |         5 |       6 |  5.237 |           735.712 |  -463.288    |
| 377 |  999     | 31912 N 19th Ave Phoenix AZ 85085                    |         3 |       2 |  1.6   |           504.138 |  -494.862    |
| 378 | 1020     | 3023 E Sierra Vista Dr Phoenix AZ 85016              |         4 |       2 |  1.872 |           524.836 |  -495.164    |
| 379 |  990     | 5713 W Pinnacle Hill Dr Glendale AZ 85310            |         3 |       1 |  0.882 |           463.059 |  -526.941    |
| 380 | 1050     | 415 E Quartz Rock Rd Phoenix AZ 85085                |         4 |       3 |  2     |           496.873 |  -553.127    |
| 381 | 1249.9   | 3604 E Tano Ct Phoenix AZ 85044                      |         5 |       5 |  4.511 |           693.697 |  -556.203    |
| 382 | 1194.5   | 622 W Palmaire Ave Phoenix AZ 85021                  |         3 |       3 |  2.908 |           614.26  |  -580.24     |
| 383 | 1250     | 404 E Briles Rd Phoenix AZ 85085                     |         5 |       4 |  3.887 |           663.618 |  -586.382    |
| 384 | 1050     | 3107 E Maryland Ave Phoenix AZ 85016                 |         3 |       2 |  1.136 |           449.84  |  -600.16     |
| 385 | 1339     | 3038 W Briarwood Ter Phoenix AZ 85045                |         5 |       6 |  5.028 |           711.255 |  -627.745    |
| 386 | 1250     | 3117 E Campbell Ave Phoenix AZ 85016                 |         4 |       3 |  2.346 |           537.362 |  -712.638    |
| 387 | 1349.9   | 14613 S 1st St Phoenix AZ 85048                      |         4 |       4 |  3.083 |           580.665 |  -769.235    |
| 388 | 1495     | 3122 N 47th St Phoenix AZ 85018                      |         5 |       6 |  5.028 |           711.255 |  -783.745    |
| 389 | 1399     | 3331 E Kachina Dr Phoenix AZ 85044                   |         4 |       2 |  2.477 |           595.633 |  -803.367    |
| 390 | 1399     | 14828 N 15th Ave Phoenix AZ 85023                    |         4 |       4 |  3.083 |           580.665 |  -818.335    |
| 391 | 1400     | 3427 E Mariposa St Phoenix AZ 85018                  |         4 |       4 |  3.083 |           580.665 |  -819.335    |
| 392 | 1350     | 9409 N 47th St Phoenix AZ 85028                      |         3 |       1 |  1.392 |           522.739 |  -827.261    |
| 393 | 1850     | 10819 N 52nd St Scottsdale AZ 85254                  |         5 |       6 |  5.028 |           711.255 | -1138.74     |
| 394 | 1799.99  | 4535 N 39th St Phoenix AZ 85018                      |         4 |       2 |  1.456 |           476.155 | -1323.83     |
| 395 | 1950     | 336 E Orangewood Ave Phoenix AZ 85020                |         4 |       3 |  3.055 |           620.33  | -1329.67     |
| 396 | 1900     | 5537 W Alameda Rd Glendale AZ 85310                  |         4 |       2 |  2.203 |           563.57  | -1336.43     |
| 397 | 2550     | 3208 W Redwood Ln Phoenix AZ 85045                   |         2 |       2 |  1.108 |           457.696 | -2092.3      |
| 398 | 3500     | 14004 S Rockhill Rd Phoenix AZ 85048                 |         4 |       2 |  2.477 |           595.633 | -2904.37     |
| 399 | 5495     | 5212 E Red Rock Dr Phoenix AZ 85018                  |         3 |       2 |  1.64  |           508.819 | -4986.18     |

