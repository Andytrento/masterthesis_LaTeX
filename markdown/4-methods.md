# Boosting 

All the approaches reviewed so far suffer from the fact that they use a single
model for predicting the response variable. Hence the ability to choose a
suitable model is crucial to have any chance to obtain good results.
Machine Learning practitioners have to consider many factors such as
the quantity of data, the dimensionality of the space, and distribution
hypothesis to find a high predictive power model.

Boosting, on the other hand, is an an ensemble
technique in which several weak models such as decision trees  are combined to achieve a stronger one.The general idea of most boosting methods is to train predictors sequentially, each trying to correct its prede‐
cessor. 



## Regression Trees

Regression Tree is a type of decision trees  used to predict continuous
numeric values (e.g. the price of a house, or a patient's length of stay in a
hospital). In a regression tree, each leaf represenet a numeric value.

A regression tree is recursively constructed through a binary partitioning
process. We first select the predictor  and the cut point s such that splitting
the predictor space into the two regions (S1 = {${X|X_j <s}$} and S2 = {${X|X_j >s}$}) such that the overall sums of squares error are minimized:

<!--\begin{eqnarray}-->
  <!--\textrm{SSE} = \sum_{i\in S_1}^{n}(y-\bar{y_1})^2 + \sum_{i \in S_2}^{n}(y-\bar{y_2})^2-->
<!--\end{eqnarray}-->

where $\hat{y_1}$ and  $\hat{y_1}$ are the mean response for  training set within groups
S1 and S2, respectively.

We repeat the process, looking for the best predictor and best cutpoint to split
the data further to minimize the sums of squares errors within each group. The
recursive partitioning of the data continues until a stopping criterion reached
for instance, we may continue until no region contains more than 20
observations.
We predict the response for a given test data point using the average value of
the training observations in the group to which that test observation belongs.



<!--Pros and Cons of regression trees-->

While having an advantage of being easily be visualized and understood, the main downside of decision trees is that they tend to overfit and provide poor generalization performance. 
Therefore, in most applications, the ensemble methods such as boosting are usually used in place of a single decision tree.  Trees can make excellent base learners for boosting for the following reasons: 
\begin{enumerate}
  \item By limiting their depth, they can be weak learners.  
\item We can add together separate trees easily. 
 \item Trees can be created quickly. \end{enumerate}

## Gradient Boosting

While there are many boosting methods available, in this study, we focus on Gradient boosting trees and its high-performance implementation, XGBoost. In gradient boosting trees,  regression trees are choosen  as the base learners. 

We illustrate this approach in Figure ~\ref{fig:gradient-boosting-illustration}

\begin{figure}[H]\centering
    \includegraphics[width=\textwidth]{gradient-boosting-illustration.png}
    \caption{Gradient Boosting Approach}
    \label{fig:gradient-boosting-illustration}
\end{figure}

\textcite{kuhn2013applied} illustrate the Gradient Boosting for
Regression algorithm as followed:



## XGBoost

XGBoost is an decision-tree-based ensemble Machine Learning algorithm that uses a gradient boosting framework. Since its introduction in 2014, this algorithm has
been credited with winning numerous Kaggle competitions and being the driving
force under the hood for several cutting-edge industry applications. Futhermore,
XGBoost has been shown to provide state-of-the-art results for diverse problems,
including web text classification, customer behavior prediction, motion
detection, and malware classification \textcite{chen2016xgboost}
\textcite{nielsen2016tree}.



Some features of XGBoost that make it stand out of from the rest of
other gradient boosting algorithms, are
\begin{itemize}
    \item Clever penalization of trees
    \item A proportional shrinking of leaf nodes
    \item Newton Boosting
    \item Extra randomization parameter
    \item Implementation on single, distributed systems and out-of-core computation
\end{itemize}

Besides these superior features, there are other reasons why XGBoost is getting
popular in the machine learning community:
\begin{itemize}
    \item Can solve a wide range of applications such as regression,
        classification, ranking, and user-defined prediction problems.
    \item Portability: Runs smoothly on Windows, Linux, and OS X.
    \item Languages: Supports all major programming languages, including C++,
        Python, R, Java, Scala, and Julia.
    \item Cloud Integration: Supports AWS, Azure, and Yarn clusters and works
        well with Flink, Spark, and other ecosystems.
\end{itemize}



While XGBoost is suitable for predicting, it does so at the expense of its
interpretability.  As shown in Figure
\ref{fig:flexibility-interpretability-tradeoff}, compared to restrictive models
such as Lasso or Least Squares, Boosting is a highly flexible (complex) approach
that is harder to interpret.

\begin{figure}[H]\centering
    \includegraphics[width=\textwidth]{flexibility-interpretability-tradeoff.png}
    \caption{Interpretability and Flexibility Tradeoff}
    \label{fig:flexibility-interpretability-tradeoff}
    \source{\textcite{james2013introduction}}
\end{figure}

