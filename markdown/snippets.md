%\subsection{Boosting}
%All the approaches reviewed so far suffer from the fact that they use a single
%model for predicting the response variable. Hence the ability to choose a
%suitable model is crucial to have any chance to obtain good results.
%Machine Learning practitioners have to consider many factors such as
%the quantity of data, the dimensionality of the space, and distribution
%hypothesis to find a high predictive power model.

%Using this approach, we have to face the bias-variance tradeoff. On the one
%hand, we want our model to have enough degrees of freedom to resolve the
%underlying complexity of the data we are working with. On the other hand, we
%also want it to have not too many degrees of freedom to avoid high variance and
%be more robust.

%Boosting, on the other hand, takes a more iterative approach. It is an ensemble
%technique in which several models are combined to achieve a better one.

%\subsection{Ensemble Methods}

%Imagine we want to buy a new laptop. We are unlikely to walk into a store and
%buy a laptop. You search the product on the internet, read reviews, compare
%models, prices. We ask for opinions from our family and friends. In brief, we
%investigate, seek the \textit{wisdom of the crowd} before making an informed
%decision.\newline
%Likewise, if we combine multiple learning algorithms, we will often obtain
%better predictions than the best individual algorithm. We call a group of
%predictors an \textit{ensemble}, and the technique is called Ensemble Learning. The
%Ensemble Learning algorithm is called an Ensemble method.

%In practice, two ensemble models have proven to be effective on a wide range of
%datasets for classification and regression, both of which use decision trees as
%their building blocks: random forests and gradient boosted decision trees.

%\subsection{Gradient Boosting}

%While there are several boosting methods available, the two most popular are
%Adaptive Boosting \autocite{freund1997decision} and Gradient
%Boosting \autocite{friedman2001greedy}. In this study, we focus on Gradient
%boosting trees and its high-performance implementation, XGBoost.
%The Gradient boosting trees model uses a regression tree as the base learner.
%\citeauthor{kuhn2013applied} \parencite{kuhn2013applied} suggests three reasons
%why trees make an excellent base learner for boosting:
%\begin{enumerate}
    %\item By limiting their depth, they can be weak learners.
    %\item We can add together separate trees easily.
    %\item Trees can be created quickly.
%\end{enumerate}

%The basic gradient boosting regression principles are: given mean squared error
%( a loss function ) and regression trees (weak learners). The goal of Gradient
%Boosting Trees is to find an additive model that minimizes the loss function.





While having an advantage of being easily be visualized and understood, the main
downside of decision trees is that they tend to overfit and provide poor
generalization performance.  Therefore, in most applications, the ensemble
methods such as boosting are usually used in place of a single decision tree.



XGBoost is an  end-to-end tree boosting system developed by Chen that based on
agradient boosting framework. Since its introduction in 2014, this algorithm
has been credited with winning numerous Kaggle competitions and being the
driving force under the hood for several cutting-edge industry applications.
Futhermore, XGBoost has been shown to provide state-of-the-art results for
diverse problems, including web text classification, customer behavior
prediction, motion detection, and malware classification
\textcite{chen2016xgboost}.



\1. Introduction

[Lý Vũ](https://www.facebook.com/vuly16)đã gửi15 phút trước2. Background

[Lý Vũ](https://www.facebook.com/vuly16)đã gửi15 phút trước3. Methodology

[Lý Vũ](https://www.facebook.com/vuly16)đã gửi15 phút trước5. Findings

[Lý Vũ](https://www.facebook.com/vuly16)đã gửi15 phút trước6. Related works

[Lý Vũ](https://www.facebook.com/vuly16)đã gửi15 phút trước7. Conclusion and Future works





## Introduction

## Background 



## Methodology

### Dataset

### Data Preprocessing

### EDA

### Modelling Methods



## Findings



## Conclusions and Future Works 



## Related Works 