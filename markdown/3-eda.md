# Exploratory data analysis

<!--Intro about EDA-->



## Numerical features

<!--summary of basic stats  -->

We present the descriptive statistics of variables in Table \ref{tab:descriptive-statistic}

### Price

==*Question: what is the overall distribution of prices?*==

The nightly advertised prices range from \$0 to \$10,000. The range is so broad because hosts do not understand how to set Airbnb advertised prices.
Figure \ref{fig:price-distribution} shows the distributions of price. While the price's range is extensive, most of its values concentrate on the range \$10 to \$1000. Hence, for minimal values under \$ 10, we will increase them to £10, and values above \$ 1,000 will be reduced to \$ 1,000.



<!--<!--The reason why reduce the value above 1000 to 1000  -->-->

<!--There are notable drop-offs in nightly prices at £200 (first graph, orange line), £500 (second graph, orange line) and £1,000 (second graph, red line). Values above £1,000 will be reduced to £1,000.-->



#### Host listings count

*==Question: how many listings do hosts have on average? How many multi-listing hosts are there?==*

The median number of listings that the host of each listing has is 1. The mean is higher (8 in total) due to some hosts running many listings. About 55% of listings are from hosts with one listing, and 45% are from multi-listing hosts

<!--Two difficulties in discerning how many listings hosts have on average are:-->

- <!--this number is only known on the level of the listing, so hosts with more listings are represented more frequently (e.g a host with 10 listings may be represented up to 10 times in the dataset)-->
- <!--a host's other listings may not be in London, so some multi-listing hosts may appear multiple times in the dataset, and others may appear only once-->



#### Number of people accommodated, bathrooms, bedrooms and beds

==*Question: what are the average number of people accommodated, bathrooms, bedrooms and beds in Airbnb listings in London, and how do prices differ?*==



Figure 123 reveals that the most common listing type accommodates two people in one bed in one bedroom with one bathroom. Figure 123 shows that the more people a listing accommodates, the higher the price they can charge their customers.

<!--the most common property setup sleeps two people in one bed in one bedroom, with one bathroom.-->

<!--Figure shows that the more the number of people a listing accommodate , the higher the price they can charge their customers-->

<!--Some properties have very high looking values for some features (e.g. one property claims to have 17 bathrooms), but these will be left for now in the interests of time (as double-checking them would be time-consuming).-->



## Categorical features

Our main EDA objective for categorical data is to know the unique values and their corresponding count.



### Geographical Analysis

==*Question: which areas have the most Airbnb properties, and which are the most expensive?*==







![image-20201013155718600](/Users/macbook/Library/Application Support/typora-user-images/image-20201013155718600.png)





Manhattan and Brooklyn have the most Airbnb properties, followed by Queens.





![image-20201013145322516](/Users/macbook/Library/Application Support/typora-user-images/image-20201013145322516.png)



As shown in Figure ABC and Figure DEF, Unsurprisingly, Manhattan is the most expensive borough - this is a famously expensive area to live, with some of the world's highest house prices. The second most expensive area is in Brooklyn, followed by Queens. Staten Island is the least expensive area to rent Airbnb accommodation.

#### **Property and room types**

==*Question: what are the most common property and room types?*==

About 80% properties are apartments. The remainder are houses or more uncommon property types (e.g. 'bed and breakfast' or 'yurt').

About 52% of listings are entire homes (i.e. you are renting the entire property on your own). Most of the remainder are private rooms (i.e. you are renting a bedroom and possibly also a bathroom, but there will be other people in the property). Fewer than 3% are shared rooms (i.e. you are sharing a room with either the property owner or other guests).



#### Reviews

*==Question: what is the distribution of reviews like?==*

<!--Just write about overall listing rating!-->

From Figure   \ref{fig:overall-listing}, we see that, while few listings receive review ratings of 80 or below, most listings with a review have received a 95-100/100 overall,  indicating that the customers adore their Airbnbs.

#### First and last reviews

*==Question: how long have listings been on the site, and how many listings have been reviewed recently?==*

As can be seen from the Figure \ref{fig:time_since_first_review}, the most common period in which  Airbnb listings had their first review is 2-3 years, which means that many listings on the site have been active for at least a couple of years. However,  fewer listings have been on Airbnb for more than four years.

The bar plot \ref{fig:time_since_last_review} reveals that the most common period since a listing received its last review is 2-8 weeks, which means that many listings have been reviewed relatively recently.

What stands out in the figure is that over 10,000 listings have not had a review for more than a year, which means they exist on the site, but they do not have their calendars open and are not available to reserve.



## Boolean features

Many features (e.g. for amenities) can be true or false. This section compares the proportions of these features that are true or false (to explore the data and also to ascertain whether the feature is worth retaining), and the median price of each category (to explore the relationship between the category and price).



#### Superhosts

==*Question: what proportion of Airbnb hosts are superhosts, and is it worth being one? (a question often asked by hosts)*==

Answer: about 23% of hosts are "superhosts". As expect that being a superhost (a mark of quality, requiring various conditions to be met)  improve the median price of Airbnb listing.



#### Host verification

*==Question: how many hosts are verified, and is it worth it? (a question often asked by hosts)==*

About 49% of hosts are verified .As with superhost, verifying host's profile (e.g. by providing ID and verifying your phone number and email address) can lead to a price premium. The reason for this may have something to do with the fact that providing host's verification increases the trustworthiness of the host (Ert)



Ert, E., Fleischer, A., & Magen, N. (2016). Trust and reputation in the sharing economy: The role of personal photos in Airbnb. Tourism Management, 55, 62–73. doi:
https://10.1016/j.tourman.2016.01.013

#### Instant booking

*==Question: how many properties are instant bookable (i.e. able to be booked without messaging the host first), and is it worth it?==*

Answer: only about 40% of properties are instant bookable. However, the added convenience does not seem to have any effect on the median price per night. This negative link can be explained by both emotional (Wang & Nicolau 2017) and economic (Benitez-Aurioles, 2018)



Benítez-Aurioles, B. (2018). Why are flexible booking policies priced negatively? Tourism Management, 67, 312–doi: https://doi.org/10.1016/j.tourman.2018.02.008

<!--While this is a positive amenity that helps the guests plan their trip in an easier way, it-->
<!--is linked to lower prices because hosts that seem to look for high-->
<!--occupancy tend to combine both strategies: lower prices to be more-->
<!--attractive and instant booking to be easier to be reserved. This is-->
<!--especially noticeable in listings priced above average, as the 50th,-->
<!--75th and 90th quantiles are significantly lower (more negative)-->
<!--than the 10th and 25th quantiles-->

#### Amenities

*==Question: which amenities are common, and which increase the price of an Airbnb listing?==*

Our goal is to identify which amenities are common and which increase the price of an Airbnb listing.
In Figure ABC, we plot the count plot and each amenity's median price to explore the relationship between the amenity and price.

Amenities then can be split into three groups:

The first group contains uncommon amenity, but listings with it have a higher median price:

- [x] Bed linen
- [x] Coffee machine
- [x] Basic cooking equipment
- [x] Elevator
- [x] Child friendly
- [x] Long term stays allowed
- [x] Private entrance
- [x] Self check-in
- [x] Pets allowed
- [x] Air conditioner

The second group includes common amenities and listings with it have a higher median price:

- [x] TV
- [x] Washer, dryer and/or dishwasher (white goods)
- [x] Internet


The third group comprises uncommon amenities, and listings with it have a lower median price:

- [x] Parking (presumably because these are less likely to be central properties)
- [x] Greeted by host (surprisingly!)

<!--The takeaway from this is that there are some things that Airbnb hosts can do to try and improve their listing's price, although there is often not a simple causative relationship (e.g. having a parking space might improve your price, but listings with parking spaces are cheaper on average because they are less likely to be in central London, and location is a more important factor than parking space):-->

- <!--**Make sure you have the necessities that your competitors also have**, e.g. internet, a TV and white goods (a washer, dryer and/or dishwasher).-->
- <!--If you can, **include some extras to make your property stand out and achieve a higher price**. For example, you could buy a coffee machine, allow self check-in and long-term stays, and make your property child-friendly.-->
- <!--**Avoid pets** as the additional wear and tear to your property might harm its financial performance.-->




## Time series EDA

Lastly, we also plotted time series charts to check for trends and seasonality.

==*Question: how long have hosts been listing properties on Airbnb in London?*==

First, we examine how long hosts have been listing properties on Airbnb in New York.Of the Airbnb hosts that are active on the site, the first joined on 22 August 2008, and the most recent joined on 03 December 2019.


From 2011 onwards, the number of listings started growing considerably. However, growth in the number of new hosts (of those currently listed on the site) has decreased since mid-2014.

Strong evidence of seasonality was found in Figure ABC. The number of hosts joining Airbnb peaked in the summer because people put properties online to utilize the increased number of tourists in the summer holidays.



==*Question: are the different patterns in the growth in the number of hosts and the number of listings due to hosts increasingly owning multiple properties?*==

Moving on now to consider whether there are different patterns in the increase in the number of hosts and the number of listings caused by hosts increasingly possess multiple properties.

Several professional Airbnb management companies own many listings under a single host profile, particularly from 2014 onwards. The largest manages 1767 listings, while the second-largest is managing 1717 listings. However, the average number of properties managed by each host shows no steady upwards trend. (Figure 3.19)

      host_since  host_listings_count
20445 2016-06-06                435.0
14661 2016-09-16                492.0
6498  2015-04-07                653.0
12909 2015-03-30                677.0
31994 2014-12-14                681.0
23521 2014-02-14                844.0
38918 2018-06-11                975.0
29366 2016-12-16               1068.0
35568 2014-01-03               1717.0
37270 2015-11-02               1767.0



==*Question: how have prices changed over time?*==

In terms of how prices changed over time, Figure ABC shows that the average price per night for Airbnb listings in New York has increased slightly over the last ten years. Particularly, the top-tier property prices have increased, resulting in a more substantial increase in the mean price than the median. 



![image-20201014094338140](/Users/macbook/Library/Application Support/typora-user-images/image-20201014094338140.png)



Mean

first_review
2008-01-01     95.60
2009-01-01    144.09
2010-01-01    150.06
2011-01-01    170.55
2012-01-01    151.01
2013-01-01    149.61
2014-01-01    139.56
2015-01-01    129.14
2016-01-01    131.18
2017-01-01    127.89
2018-01-01    138.60
2019-01-01    183.47



Median 

first_review
2008-01-01     95
2009-01-01    125
2010-01-01    125
2011-01-01    125
2012-01-01    120
2013-01-01    118
2014-01-01    106
2015-01-01    100
2016-01-01     99
2017-01-01     90
2018-01-01     99
2019-01-01    100





## Multivariate Exploration



The goal of this section is to investigate the relationships between pairs of our features. A primary concern when analyzing the relationship between various variables is multicollinearity, a phenomenon in which two or more independent variables substantially correlate(\textcite{cohen2013applied}).

While multicollinearity does not hurt the model's predictive power(\textcite{kutner2005applied}), collinearity can pose problems in the regression context. In particular,  it can be challenging to separate the individual effects of collinear independent variables on the outcome variable.  

A straightforward way to detect collinearity is to construct a correlation matrix among predictors.  An element of this matrix that is large in absolute value indicates a pair of highly correlated variables and are indicative of collinearity issues.



As shown in Figure ~\ref{fig:correlation-matrix} shows the correlation matrix, areas of multicollinearity are:

- Beds, bedrooms, guests included, and the number of people that property accommodates are highly correlated. 
- There are strong negative correlations between houses and apartments and between private rooms and entire homes.



Providing a full remedy for the multicollinearity issue is beyond the scope of this thesis. However, we employ two  simple approaches as followed:

1. The first approach is to drop problematic variables from the regression. 
2. The second method is to employ regularization techniques, which combat collinearity by using biased models(\ref{sec:penalized_regression_models} ), which reduce the error variance of estimators.



### Phrases



These large values are indicative of collinearity issues

In the training set, these two predictors are highly correlated (0.96). We would expect severe collinearity as a result

### Correlation Matrix

