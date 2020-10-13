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

Answer: the oldest London listing that is currently live on Airbnb was first listed on the site in August 2008. From 2011 onwards, the number of listings started increasing considerably. However, growth in the number of new hosts (of those currently listing on the site) has been decreasing since 2015, when the UK government introduced a law in 2015 making it illegal to let short-term residential properties for more than 90 nights a year.

A high level of seasonality is evident, with notable peaks in the summer when people put properties online to take advantage of the increased number of tourists in the summer holidays.

There is a big peak in the number of hosts joining Airbnb in 2015. This could be a response to the government legislation, as existing hosts may have created new accounts in order to re-list their properties and get around the 90 day limit.



==*Question: are the different patterns in the growth in the number of hosts and the number of listings due to hosts increasingly owning multiple properties?*==

Answer: there are a number of professional Airbnb management companies which host a large number of listings under a single host profile, particularly from 2013 onwards. The largest manages 1654 listings and is aa management company based in Liverpool operating under the name 'Jp', while the second largest is the management company Veeve, managing 1304 listings.

However, there is no consistent upwards trend in the average number of properties managed by each host.



==*Question: how have prices changed over time?*==

Answer: the average price per night for Airbnb listings in London has increased slightly over the last 10 years. In particular, the top end of property prices has increased, resulting in a larger increase in the mean price compared to the median - e.g. the mean price in 2015 was £95.90, whereas the mean price in 2018 (the last complete year of data) was £111.14.



