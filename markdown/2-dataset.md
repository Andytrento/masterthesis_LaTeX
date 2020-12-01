# Data

<!--suggested structure-->

1. Data Acquisition
2. Data Cleaning and Pre-processiong
    1. Five categories (according to Wang and Nicolau)
    2. Filtering active data (number of review at least 1) (Wang and Nicolau)
    3. Then cleaning each category (See Lewis)



<!--After this step, we got a data ready for exploring and modelling-->


## Data Acquisiton



<!--Where do I get the data?-->



The dataset used for this study comes from the Inside Airbnb website \textcite{}. This independent initiative collects Airbnb data for more than 30 major cities around the world that scrapes Airbnb listings, reviews, and calendar data from multiple cities worldwide. The dataset  was scraped on December 4, 2019, contains information about the location (latitude and longitude coordinates) of all Airbnb listings in New York City and data about the hostname and ID, room type, price, minimum nights, number of reviews listings per host, and availability.  . A GeoJSON file of New York borough boundaries was also downloaded from the same site.



Following \textcite{wang2017price}, this study filtered the listings with at least one online customer review to guarantee that our sample listings were "active." This view is supported by Ye et al. (2009), which confirms that online review ratings are associated with hotel-room sales, indicating that reviews suggest real transactions.



<!--Overview of data like pros and cons-->

- [x] Paraphase

<!--The data is quite messy, and has some limitations. The major one is that it only includes the advertised price (sometimes called the ‘sticker’ price). The sticker price is the overall nightly price that is advertised to potential guests, rather than the actual average amount paid per night by previous guests. The advertised prices can be set to any arbitrary amount by the host, and hosts that are less experienced with Airbnb will often set these to very low (e.g. $0) or very high (e.g \$10,000) amounts.-->

The raw data is quite untidy and has some weaknesses. The major one is that it
only includes the advertised price (sometimes called the ‘sticker’ price). The
sticker price is the overall nightly price advertised to potential renters,
rather than the actual average amount paid per night by previous guests. A host
can set the advertised prices to any arbitrary amount, and those that do not
have much experience with Airbnb will often set these to unreasonable prices,
such as too low (e.g., \$0) or very high (e.g., \$10,000) amounts.

- [ ] Have a plot of Airbnb in New York





<!--What is the pros and cons of the dataset-->



## Data Pre-processing

- [ ] Paraphrase

    <!--What is data pre-processing-->



Real-world data is often dirty; that is, it is in need of being cleaned up
before it can be used for the desired purpose such as visualization, model
building. This is often called data pre-processing.



![image-20200924143022620](/Users/macbook/Library/Application Support/typora-user-images/image-20200924143022620.png)



### Data Cleaning



- [ ] paraphrase

Since there are several reasons why data could be “dirty,” there are just as various techniques to “clean” it.
For this analysis, we will take a look at three key methods that illustrate ways in which data may be “cleaned,” or better organized, or scrubbed of potentially incorrect, incomplete, or duplicated data.

#### Data Mungling

<!--Data set is already in the right format => No need-->

#### Handling Missing Data



- [ ] parapharse + find another example

Missing data is a common issue in many data analysis applications.
A missing value in a variable occurs when an actual value exists but was omitted in the course of data entering. An empty value in a variable is one for which no real-world value exists or can be obtained. These values are expected to be corrected before we perform the Exploratory Data Analysis and model building.



- [x] paraphrase

    <!--Strategy for combat missing data-->



So, what to do when we encounter missing data? There is no single right answer. One method to combat missing data is to perform data imputation, a statistical technique for substituting missing or inconsistent data items with an estimated value based on other available information.
We need to find a proper strategy based on the situation.


<!--Insert a table of description of missing datatreatment-->




 #### Smoothing Noisy Data



### Data Transformation

- [ ] paraphrase

    Data must be transformed so it is consistent and readable (by a system). The following five processes may be used for data transformation. For the time being, do not worry if these seem too abstract

### Data Reduction

Data reduction is a key process in which a reduced representation of a dataset that produces the same or similar analytical results is obtained.

### Data Discretization and Binning





### Dropping initial columns

- [ ] Shorten, paraphrase

<!--NLP will not be used in the creation of an initial model (although they could be used to augment the model later, e.g. through sentiment analysis). Therefore, free text columns will be dropped for now, as will other columns which are not useful for predicting price (e.g. url, host name and other host-related features that are unrelated to the property).-->



It is beyond the scope of this study to explore the natural language process for predictive modeling.  Therefore,  we will drop free-text columns for now, as will other columns that are not useful for predicting price (e.g., URL, hostname, and other host-related features unrelated to the property).

- [ ] Parapharse



### Handling Missing Data

- [ ] Paraphrase



A missing value in a variable occurs when an actual value exists but was omitted in the course of data entering. An empty value in a variable is one for which no real-world value exists or can be obtained. These values are expected to be corrected before we perform Exploratory Data Analysis.



<!--Method to deal with missing data-->

One method to deal with missing data is to perform data imputation. Data imputation is the statistical technique for substituting missing or inconsistent data items with an estimated value based on other available information.



In our dataset the imputation was performed on a few columns such as

<!--Table of missing value here-->

Other columns can be dropped because they contain a majority of null entries.









<!--How to write about handling messy data?-->

<!--Drop similar columns-->

<!--duplicate data-->

host_listings_count and host_total_listings_count are the same in all but 248 cases. These cases are those where the value is NaN. Therefore one of these columns can be dropped. Other columns which split these into type of property will also be dropped, as they will be highly correlated (one will be the total of the others).



- [ ] Paraphrase

    <!--location columns-->

There are multiple columns for property location, including an attempt by the site that originally scraped the data to clean up the neighbourhood locations. Some of these columns can be dropped. Because all of the listings are in London, columns relating to city and country can be dropped. One columns for area (borough) will be kept - 'neighboorhood_cleansed'. Latitude and longitude will be saved in a dataframe for later use (see modelling section below).



- [ ] paraphrase

There are multiple columns for minimum and maximum night stays, but the two main ones will be used as there are few differences between e.g. minimum_nights and minimum_minimum_nights. The latter presumably refers to the fact that min/max night stays can vary over the year. The default (i.e. most frequently applied) min/max night stay values will be used instead.



<!-- plot histogram and Drop columns only contain one category-->

From the above, it can be seen that several columns only contain one category and can be dropped:





```python
df.drop(['has_availability', 'host_has_profile_pic', 'is_business_travel_ready', 'require_guest_phone_verification', 'require_guest_profile_picture', 'requires_license'], axis=1, inplace=True)
```



- [ ] Give a description of each column



![image-20200924204733102](/Users/macbook/Library/Application Support/typora-user-images/image-20200924204733102.png)



- [ ] paraphrase

From the above, it can be seen that several columns only contain one category and can be dropped:        [
            "has_availability",
            "host_has_profile_pic",
            "is_business_travel_ready",
            "require_guest_phone_verification",
            "require_guest_profile_picture",
            "requires_license",
        ]





data shape (40379, 42)

### Cleaning individual columns

<!--In each column describe it, give the hypothesis and literature review (if have any)-->

- [ ] Paraphrase



#### experiences_offered

<!--contain just one categor-->

<!--Drop -->

Most listings offer no experiences so this feature can be dropped.

####  bed_type

We drop this feature because it  has the same bed type (Real Bed)

<!--Most listings in these columns have the same bed type so this feature can be drop-->



<!--none    40379-->
<!--Name: experiences_offered, dtype: int64-->

#### host_since

- [ ] paraphrase

<!--Convert to number of active days-->

This is a DateTime column and will be transformed into a feature that measures the number of days that a host has been on the Airbnb, measured from the date that the data was obtained (4 December 2019). The mean and median days as hosts are 1654 days and 1662 days, respectively.

<!--This is a datetime column, and will be converted into a measure of the number of days that a host has been on the platform, measured from the date that the data was scraped (4 December 2019). The original column will be left in initially for EDA, and dropped later.-->

<!--Mean days as host:  1654.0-->

<!--Median days as host:  1662.0-->

#### host_response_time

- [ ] paraphrase

About a third of rows don't have a value for host_response_time, and the majority of these have also not yet been reviewed. Therefore this section of the dataset consists primarily of properties which have not yet had a completed stay (most likely properties which have not yet had a booking, although may also include properties that have a booking currently occuring). Although this is a considerable proportion of the dataset, these listings will be retained in the data because they are still legitimate properties with advertised prices, and are still part of the comparative market when considering the price for which to advertise your Airbnb listing. However, if the dataset being used had the actual average price paid as its target, it would be necessary to drop these rows because they would not have a value, as they have not yet been booked.

It is worth noting, however, that this group of listings probably also contains a large number of 'inactive' listings. These are properties which have been speculatively listed on Airbnb but either have their calendars closed (so no stays can be booked), or have prices which are notably higher than other properties in their area. The latter occurs in some cases when people who regularly live in a property put their property on Airbnb at a high price just to see if anyone is willing to book at that price (some Airbnb listings are indeed booked at very high prices). Then if their property is booked, they will decamp to a cheaper hotel for those dates, and pocket the difference in price.

Because host_response_time is unknown for so many listings, it will be retained as its own category, 'unknown'.



Null values:  12270

Proportion: 30.4%

<!--talk about data imputation fill nan with value "unknown"-->



    df.host_response_time.fillna(
        "unknown", inplace=True
    )  # fill NaN value with 'unknow'


<!--value_counts-->

within an hour        0.625849
within a few hours    0.219254
within a day          0.132804
a few days or more    0.022093



#### host_response_rate

- [ ] paraphrase

A similar story is true for host_response_rate, with about a third of values being null. This will also be kept as its own category, after grouping other values into meaningful groups (i.e. transforming this into a categorical feature, rather than a numerical one). Because about 70% of hosts respond 100% of the time, this will be kept as its own category, and other values will be grouped into bins.



Null values: 12270

Proportion: 30.4%

Mean host response rate:  94.0

Median host response rate:  100.0



Proportion of 100% host response rates: 70.5%



<!--Talk about binning this column into 5 bins-->

<!--Talk about the reason why i did that-->

100%       19809
unknown    12270
50-89%      4709
90-99%      2608
0-49%        983

#### host_is_superhost



#### property_type

- [ ] paraphase

Some cleaning of property types is required as there are a large number of categories with only a few listings. The categories 'apartment', 'house' and 'other' will be used, as most properties can be classified as either apartments or houses.

<!--Talk about grouping similar categories-->


Apartment    32553
House         5053
Other         2301

#### bathrooms, bedrooms and beds

<!--Why?-->

Missing values will be replaced with the median (to avoid strange fractions).



#### bed_type

Most listings have the same bed type so this feature can be dropped.

Real Bed         39296
Futon              236
Pull-out Sofa      202
Airbed             123
Couch               50

#### amentities

<!--See Wang and Nicolau for literature reviews -->



<!--Fill missing value with zero-->

- [ ] paraphrase

Amenities is a list of additional features in the property, e.g. whether it has a TV or parking. Examples are below:

In the list above, some amenities are more important than others (e.g. a balcony is more likely to increase price than a fax machine), and some are likely to be fairly uncommon (e.g. 'Electric profiling bed'). Based on previous experience working in the Airbnb property management industry, and research into which amenities are considered by guests to be more important, a selection of the more important amenities will be extracted. These will be further investigated in the EDA section. For example, if it turns out that almost all properties have/do not have a particular amenity, that feature will not be very useful in helping explain differences in prices.



One way to reduce the number of features (to avoid the curse of dimensionality) is to remove the amenities which add relatively little information, or are relatively unhelpful in differentiating between different listings. Amenity features where either the true or the false category contains fewer than 10% of listings will be removed.



#### price

 convert price to an integer

#### security_deposit, cleaning_fee, extra_people

<!--these columns will be converted from string with curency sign to integer-->

<!--missing value will be replace with zero-->



#### calendar_updated

<!--Drop because i think it's not clear how importance this feature is-->

#### availability

<!--Keep 1 feature availability_90 not clear why-->

#### first_review and last_review

<!--turn these columns into time_since_first_review and time_since_last_review. Then Bin them into different categories-->

#### review ratings columns

Keep just one column: reviews_score_rating. then bin it scored out of 100



#### cancellation_policy

Some cleaning of cancellation policy types is required, in order to categorise the four very small categories into the three larger categories (e.g. the super strict options are only available to long-term Airbnb hosts, and is invitation only).

<!--replace values -->

strict_14_with_grace_period    19864
moderate                       10222
flexible                        9821

#### number_of_reviews and reviews_per_month

These will be highly correlated with number_of_reviews and so will be dropped.



- [ ] Comments about data after cleaning







### Data Transformation

<!--Data Transformation for Multiple Predictors-->



<!--Categorical Feature-->





<!--Numerical Feature-->



<!--Feature Encoding-->



<!--Train/Test Split-->



<!--Library used -->



<!--Brief introduction of pandas, numpy?-->





For the initial prepossessing, the authors inspected each feature of the dataset to (i) remove features
with frequent and irreparable missing ﬁelds or set the missing values to zero where appropriate, (ii)
convert some features into ﬂoats (e.g. by removing the dollar sign in prices), (iii) change boolean
features to binaries, (iv) remove irrelevant or uninformative features, e.g. host picture url, constant-
valued ﬁelds or duplicate features, and (v) convert the 10 categorical features in the ﬁnal set, e.g.
‘neighborhood name’ and ‘cancellation policy,’ into "one-hot vectors." In addition, the features were
normalized and the labels were converted into logarithm of the prices to mitigate the impact of the
outliers in the dataset. The data was split into three sets; namely, train set (comprising 90% of the
original data), validation set, and test set (both comprising 5% of original data). Since the dataset was
relatively large, 10% of the data was deemed sufﬁcient for the accumulated testing and validation
sets. The following explains the sentiment analysis conducted on the reviews and the steps taken for
selecting the most important features among the available set of features.



In the dataset from Insiderairbnb.com, amenities were stored as one big block of text

In order to figure out what the various options were and which listings had them, I first made a giant string of all the amenities values, tidied it up a bit, split out the individual amenities separated by commas, and created a set of the resultant list (fortunately the dataset was small enough to allow this, but I would have needed a more efficient way to do this with a much larger dataset):

In the list above, some amenities are more important than others (e.g. a balcony is more likely to increase price than a fax machine), and some are likely to be fairly uncommon (e.g. ‘Electric profiling bed’). Based on previous experience in the industry, and furtherresearch into which amenities are considered by guests to be more important, a selection of the more important amenities were extracted. These were then selected from for inclusion in the final model depending on how sparse the data was. For example, if it turns out that almost all properties have/do not have a particular amenity, that feature will not be very useful in differentiating between listings or helping explain differences in prices.

- The whole convoluted code for this can be found on [GitHub](https://github.com/L-Lewis/Airbnb-neural-network-price-prediction), but this is the final section where I removed columns where over 90% of the listings either had or did not have a particular amenity:

These are the amenities that I ended up keeping:

- Balcony
- Bed linen
- Breakfast
- TV
- Coffee machine
- Basic cooking equipment
- White goods (specifically a washer, dryer and/or dishwasher)
- Child-friendly
- Parking
- Outdoor space
- Greeted by host
- Internet
- Long term stays allowed
- Pets allowed
- Private entrance
- Safe or security system
- Self check-in
- 





After cleaning and dropping collinear columns, the features in the model were:



- experiences_offered - slightly unclear as it does not appear to directly relate to Airbnb Experiences, but this seems to be the main recommended category of travel type, e.g. business
- host\_since & \_ date that the host first joined Airbnb
- host\_response_time & average amount of time the host takes to reply to messages \\
- host\_response\_rate & proportion of messages that the host replies to \\
- host\_is\_superhost & whether or not the host is a superhost, which is a mark of quality for the top-rated and most experienced hosts, and can increase your search ranking on Airbnb \\
- host_listings_count - how many listings the host has in total
- host_identity_verified - whether or not the host has been verified with id
- neighbourhood_cleansed - the London borough the property is in
- property_type - type of property, e.g. house or flat
- room_type - type of listing, e.g. entire home, private room or shared room
- accommodates - how many people the property accommodates
- bathrooms - number of bathrooms
- bedrooms - number of bedrooms
- beds - number of beds
- bed_type - type of bed, e.g. real bed or sofa-bed
- amenities - list of amenities
- price - nightly advertised price (the target variable)
- security_deposit - the amount required as a security deposit
- cleaning_fee - the amount of the cleaning fee (a fixed amount paid per booking)
- guests_included - the number of guests included in the booking fee
- extra_people - the price per additional guest above the guests_included price
- minimum_nights - the minimum length of stay
- maximum_nights - the maximum length of stay
- calendar_updated - when the host last updated the calendar
- availability_30 - how many nights are available to be booked in the next 30 days
- availability_60 - how many nights are available to be booked in the next 60 days
- availability_90 - how many nights are available to be booked in the next 90 days
- availability_365 - how many nights are available to be booked in the next 365 days
- number_of_reviews - the number of reviews left for the property
- number_of_reviews_ltm - the number of reviews left for the property in the last twelve months
- first_review - the date of the first review
- last_review - the date of the most recent review
- review_scores_rating - guests can score properties overall from 1 to 5 stars
- review_scores_accuracy - guests can score the accuracy of a property's description from 1 to 5 stars
- review_scores_cleanliness - guests can score a property's cleanliness from 1 to 5 stars
- review_scores_checkin - guests can score their check-in from 1 to 5 stars
- review_scores_communication - guests can score a host's communication from 1 to 5 stars
- review_scores_location - guests can score a property's location from 1 to 5 stars
- review_scores_value - guests can score a booking's value for money from 1 to 5 stars
- instant_bookable - whether or not the property can be instant booked (i.e. booked straight away, without having to message the host first and wait to be accepted)
- cancellation_policy - the type of cancellation policy, e.g. strict or moderate
- reviews_per_month - calculated field of the average number of reviews left by guest each month















### Removing predictors

There are potential advantages to removing predictors prior to modeling.
First, fewer predictors means decreased computational time and complexity.
Second, if two predictors are highly correlated, this implies that they are 

measuring the same underlying information. Removing one should not compromise the performance of the model and might lead to a more parsimonious
and interpretable model. Third, some models can be crippled by predictors
with degenerate distributions. In these cases, there can be a significant improvement in model performance and/or stability without the problematic
variables.



Consider a predictor variable that has a single unique value; we refer to this type of data as a zero variance predictor. For some models, such an uninformative variable may have little effect on the calculations.





- [ ] Add a snapshot of dataframe like



![image-20201019165625770](/Users/macbook/Library/Application Support/typora-user-images/image-20201019165625770.png)



