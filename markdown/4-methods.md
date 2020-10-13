# XgBoost

<!--Introducing the problem facing the approach using a single model -->

All the approaches reviewed so far suffer from the fact that they use a single prediction model for the price. Hence the ability to choose a suitable model is crucial to have any chance to obtain good results. 

Machine Learning practitioners have to consider many factors such as the quantity of data, the dimensionality of the space, and distribution hypothesis to find a high predictive power model.

<!--Bias and variance tradeoff-->

Using this approach, we have to face the bias-variance tradeoff. On the one hand, we want our model to have enough degrees of freedom to resolve the underlying complexity of the data we are working with. On the other hand, we also want it to have not too many degrees of freedom to avoid high variance and be more robust.

Boosting, on the other hand, takes a more iterative approach. It is an ensemble technique in that several models are combined to achieve a better one.
In this study, XGBoost, an optimized implementation of Gradient Boosting, is employed to provide a baseline accuracy level and measure feature importance.

## Ensemble Learning 

<!--What is the ensemble learning -->

Imagine we want to buy a new laptop. We are unlikely to walk into a store and buy a laptop. You search the product on the internet, read reviews, compare models, prices. We ask for opinions from our family and friends. In brief, we investigate, seek the *wisdom of the crowd* before making an informed decision. 



Likewise, if we combine multiple learning algorithms, we will often obtain better predictions than the best individual algorithm. We call a group of predictors an *ensemble,* and the technique is called Ensemble Learning. The Ensemble Learning algorithm is called an Ensemble method.



In practice, two ensemble models have proven to be effective on a wide range of datasets for classification and regression, both of which use decision trees as their building blocks: random forests and gradient boosted decision trees.

<!--Motivation for choosing gradient boosted decison trees-->

In this study, we applying Extreme Gradient Boosting (XGBoost ), a gradient boosting approach to provide a baseline level of accuracy and measure feature importance. The reason for this choice is that  XGBoost has been shown to provide state-of-the-art results for diverse problems, including web text classification, customer behavior prediction, motion detection, and malware classification [7, 28].  Its superior performance has been widely recognized in many machine learning and data mining challenges on websites such as Kaggle [22].



## Boosting

While there are several boosting methods available, the two most popular are
AdaBoost (Adaptive Boosting) \parencite{freund1997decision} and Gradient
Boosting \parencite{friedman2001greedy}. In this study, we focus on Gradient
boosting trees and its high-performance implementation, XGBoost.

The Gradient boosting trees model uses a regression tree as the base learner.
\textcite{kuhn2013applied} suggests three reasons why trees make an
excellent base learner for boosting:
\begin{enumerate}
    \item By limiting their depth, they can be weak learners.
    \item We can add together separate trees easily.
    \item Trees can be created quickly.
\end{enumerate}

### Gradient Boosting Trees

<!--What is Gradient Boost?-->

The basic gradient boosting regression principles are: given mean squared error
( a loss function ) and regression trees (weak learners). The goal of Gradient
Boosting Trees is to find an additive model that minimizes the loss function.

![image-20201009093024984](/Users/macbook/Library/Application Support/typora-user-images/image-20201009093024984.png)

In his book, \textcite{kuhn2013applied} illustrate the Gradient Boosting for
Regression algorithm as followed:

\begin{algorithm}[H]
\setstretch{1.35}
\SetAlgoLined

\renewcommand{\labelenumi}{(\Roman{enumi})}
Select tree depth, D, and number of iterations, K

Compute the average response, \bar{y}, and use this as initial predicted value for each sample 


\For{$k\gets0$ \KwTo $K$ }{
    Compute the residual, the difference between observed value and the \textit{current} predicted value, for each sample
    
    Fit a regression tree of depth, D, using the residuals as the response
    
    Predict each sample using regression fit in the previous step 
    
    Update the predicted value of each sample by adding the previous iteration's predicted value to the predicted value generated in the previous step
    
    }
 \caption{Simple Gradient Boosting for Regression}
\end{algorithm}



(Insert Algoritm)
y

![image-20201009105631451](/Users/macbook/Library/Application Support/typora-user-images/image-20201009105631451.png)



```latex
\documentclass{article}

\usepackage{algorithm2e}
\pagestyle{empty}
\SetKw{KwBy}{by}
\begin{document}
\begin{algorithm}
  \For{$i\gets0$ \KwTo $8$ \KwBy $2$}{
    Do something
    }
\end{algorithm}
\end{document}
```

![image-20201010162726632](/Users/macbook/Library/Application Support/typora-user-images/image-20201010162726632.png)


### XGBoost

Extreme Gradient Boosting (XGBoost) is a variant of the gradient tree boosting. Gradient boosting and XGBoost follows the same principle. The key differences between them lie in implementation details. 

Specifically, features of XGBoost which make it stand out of from the rest of other gradient boosting algorithms, are

- Clever penalization of trees
- A proportional shrinking of leaf nodes
- Newton Boosting
- Extra randomization parameter
- Implementation on single, distributed systems and out-of-core computation

Besides these superior features, there are other reasons why XGBoost is getting popular in the machine learning community: 
\begin{enumerate}
    \item Can solve a wide range of applications such as regression,
        classification, ranking, and user-defined prediction problems.
    \item Portability: Runs smoothly on Windows, Linux, and OS X.
    \item Languages: Supports all major programming languages, including C++,
        Python, R, Java, Scala, and Julia.
    \item Cloud Integration: Supports AWS, Azure, and Yarn clusters and works
        well with Flink, Spark, and other ecosystems.
\end{enumerate}



Because of those difference, since its introduction, this algorithm has been credited with winning numerous Kaggle competitions and being the driving force under the hood for several cutting-edge industry applications. Futhermore, XGBoost has been shown to provide state-of-the-art results for diverse problems, including web text classification, customer behavior prediction, motion detection, and malware classification [7,28].  



<!--Write about disadvatage -->



<!--Compared to restrictive models such as Lasso or Least Squares model-->

While XGBoost is suitable for predicting, it does so at the expense of its interpretability. 
As shown in Figure, compared to restrictive models such as Lasso or Least Squares, Boosting is a highly flexible (complex) approach that is harder to interpret. 

![image-20201010201013124](/Users/macbook/Library/Application Support/typora-user-images/image-20201010201013124.png)



<!--Then all things considered -->

However, one of our main goals is making the best prediction, so we decide to use the XGBoost model to provide a baseline level of accuracy and measure feature importance. 

