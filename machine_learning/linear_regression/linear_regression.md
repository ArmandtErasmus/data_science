# Linear Regression Analysis

Predictive analytics is a sub-field within statistics that aims to predict future events with reasonable accuracy by using data obtained from events in the past. A well-known and widely used model in predictive analytics is a regression model. Regression models use input data together with a well-defined function to produce an estimate value. Depending on the scenario, one might decide to use simple linear regression which is a regression technique used when dealing with a single input variable.

Simple linear regression aims to determine a linear relationship between two variables, namely the independent input variable, $x$, and the dependent output variable, $y$, commonly referred to as an estimate. If we have data consisting of two-dimensional sample points for a total of $n$ pairs, that is, our dataset looks like $\{(x_{i}, y_{i}) | i = 1, 2, ..., n\}$ then we can construct a linear model given by

$y_{i}=\omega x_{i} + \beta + \epsilon_{i}$

where $\epsilon_{i}$ is the error term, $\omega$ is the weight (also called slope) parameter and $\beta$ is the bias parameter. The aim of simple linear regression is then to find "good" estimates $\widehat\omega$, $\widehat\beta$ for $\omega$ and $\beta$ respectively in order to find a best fit through the data points. There are many different optimisation algorithms which can be used to find $\omega$ and $\beta$, including the method of least-squares and gradient descent.

The method of least-squares, as the name suggests, aims to minimize the sum of the squared residual terms given by $\widehat\epsilon_{i}$ which can be written as

$\widehat\epsilon_{i} = y_{i} - \omega x_{i} - \beta$

This leaves us with the minimization problem given by $(\widehat\omega, \widehat\beta)=\text{argmin}(Q(\omega,\beta))$ in which $Q(\omega,\beta)$ is called the objective (also called cost or loss) function defined as

$Q(\omega,\beta)=\sum_{i=1}^{n}\widehat\epsilon_{i}^{2}=\sum_{i=1}^{n}(y_{i} - \omega x_{i} - \beta)^{2}$
