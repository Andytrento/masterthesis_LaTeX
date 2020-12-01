# Introduction

## Motivation and goals



In recent years, the so-called sharing economy has spread all over the world. People share access to resources such as their homes, cars, and even personal time with other people in a peer-to-peer manner. In the travel and hospitality industry, Airbnb emerged as a company that pioneers in deploying this business model to let individuals' share' extra space in their homes with those who need temporary accommodation via the online marketplace. 
Airbnb's revenues come from service fees, which it charges to the host and guest. When an Airbnb guest books a property, the Airbnb host pays Airbnb a fee. Airbnb also charges service fees depending on the total cost of the guest's stay \cite{duckworth2018}.
One year after its foundation in 2018, it had over 2,500 listings and 10,000 Airbnb users. As of 2020, there are 2.9 million hosts on Airbnb with over 7 million accommodations in 100,000 cities worldwide \cite{airbnbfacts}. In 2017, Airbnb generated approximately \$93 million in profit out of \$2.6 billion in revenue \cite{zaleski2018}. 

<!--The business nececesity of finding an model to predict price--> 

Pricing is widely acknowledged to be one of the most critical determinants contributing to the accommodation industry's success. Therefore, examining Airbnb's price and finding a model to predict it may provide valuable insights for stakeholders to maximize their profits and develop their business.

<!--Airbnb in New York -->

While Airbnb has increasingly expanded globally, on the country level, the main markets are in the US, France, Italy, Spain, and the United Kingdom (\cite{airbnbstats2020}). Overall, the United States alone has 660,000 listings, the highest number of any country globally. New York City (NYC) is one of the most popular destinations on Airbnb with over 50,000 listings and ranked fourth in the most popular cities for booking experiences(\cite{airbnbstats2020}). With plenty of listing and booking activities, New York City serves as an excellent example for the study of Airbnb pricing.

<!--To explain or to Predict--> 

It's essential to understand whether you're dealing with an inferential question or a prediction question because the type of problem you're answering can significantly influence the modeling approach you pursue. For inferential questions, the objective is to measures an association between a predictor of interest and the outcome. For prediction problems, the goal is to identify a model that best predicts the outcome. We often do not worry about "how the model works" or describing a detailed story about the predictors. 

The focus of this study falls into answering the prediction problem. To be more specific, there are two primary aims of this study: 

1. *We want to build a model for the price of Airbnb listing* and make comparisons between different methods.
2. We identify the which features of an Airbnb listing were most important in predicting the price


## Related Works

As discussed in \ref{sec:motivation-and-goal}, our primary focus is to answer the prediction question. However, besides the literature on using machine learning techniques for price prediction, we first briefly review the related works on the inference side.



### Inference

While some research has been carried out on hotel price determinants, few empirical investigations into the price determinants of the non-hotel accommodation offer have been conducted. 
Furthermore, most researchers investigating the price determinant of sharing economy based accommodation have utilized the hedonic price model. 

\cite{monty2003hedonic} assessed the price determinants of bed and breakfast amenities and confirmed the positive effects of a hot tub, a private bath, and a larger room on room price. 
In an analysis of the impact of private tourist accommodation facilities on prices, \cite{portolan2013impact} found that the presence of free parking places and sea view could be associated with a higher room rate. 
Both of the above studies recognized that location has a vital influence on the price.

<!--Airbnb-->

In recent years, there has been an increasing amount of literature on the price determinants of Airbnb. 
Several studies (\cite{gutt2015sharing}; \cite{ikkala2014defining} ) have shown that hosts who offer accommodation to rent on Airbnb.com usually charge higher prices if their accommodation has received high star ratings.
Using a dataset from New York City, \cite{li2016pros,} showed that properties managed by professional hosts earn more in daily revenue, have higher occupancy rates, and are less likely to exit the market than properties owned by nonprofessional hosts.
\cite{kakar2016effects} measures the impact of information on hosts’ racial background on Airbnb listing prices in San Francisco and found that Hispanic hosts and Asian hosts, on average, have a lower list price relative to their white counterparts.
\cite{wang2017price} analyzed the Airbnb data from 33 countries and concluded that 24 out of 25 variables within five categories (host attributes, site, and property attributes, amenities and services, rental rules, and the number of online reviews and ratings) are good predictors of price. 
In a similar study, \cite{cai2019price} examines the impacts of five groups of explanatory variables on Airbnb price in Hong Kong.

### Prediction

 

To date, there is little published research on applying machine learning techniques to predict the price of Airbnb listing. 

\cite{tang2015neighborhood} work on the task of price prediction for San Francisco Airbnb listings by turning the regression problem into a binary classification problem.

\cite{li2016reasonable} has attempted to create a price prediction model for  Airbnb in different cities by using the clustering method with the distance of the property to the city landmarks as the clustering feature.

In more recent work, \cite{kalehbasti2019airbnb}  try to develop a reliable price prediction model using machine learning, deep learning, and natural language processing techniques. 



This study aims to contribute to this growing area of research by utilizes a holistic approach. In particular, the contribution is as followed:

- We rely on "domain knowledge" in the feature engineering process (as demonstrated in \ref{c:dataset}
- We make use of visualization techniques to gain insights from data.
- We introduce regularization techniques to improve the disadvantage of the traditional ordinary least square model.
- We present the Boosting modeling strategy, a machine learning approach that performs well when there are many predictors as a baseline model.

