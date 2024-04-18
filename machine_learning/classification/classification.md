# Classification

In many cases we may encounter data which contain categorical variables instead of quantitative variables. An example of categorical data could be something like a dataset containing a coloumn of a variable called "Eye Colour" with entries such as "Blue" or "Brown" instead of numerical values. In some cases we could decide to convert categorical data to numerical data if the assignment is appropriate. For example if there are only two possible options we can map one choice to the number 1 and the alternative to the number 0. An example would be a column called "Passed" with entries being either "Yes" or "No", and we can map each "Yes" to 1 and each "No" to 0.

In general we use classification to predict qualitative responses for categorical data. To extract direct meaning from the term "Classification": We classify an observation and assign it to a category. There are many classification techniques, some of the more popular ones are logistic regression, linear and quadratic discriminant analysis, naive Bayes and K-nearest neighbours.

### 1. Logistic Regression
Let's go back to the example where we have a column called "Passed" which contains data labeled either "Yes" or "No". This could be a column containing data on whether a student has passed a course, and it is clear that a response can fall into one of two categories. Logistic regression is a reasonable model for a situation like this where we encounter a binary outcome. The logistic regression models the probability that the response $Y$ belongs to one of the categories based on some independent value. In this case the logistic regression model would return the probability of a pass based on a student's overall course grade, so we would have $Pr(\text{pass}|\text{grade})$.

So in general, the logistic regression model can be expressed as

$p(X)=Pr(Y=1|X)=\dfrac{e^{\beta_{0}+\beta_{1}X}}{1+e^{\beta_{0}+\beta_{1}X}}$

This model (i.e. the parameters $\beta_{0}, \beta_{1}$) can be fitted with the maximum likelihood method. The estimates $\widehat\beta_{0}$ and $\widehat\beta_{1}$ should maximise the likelihood function $l(\beta_{0}, \beta_{1})$ given by

$l(\beta_{0}, \beta_{1})=\displaystyle{\prod_{i:y_{i}=1}p(x_{i})\prod_{i':y_{i'}=0}(1-p(x_{i'}))}$

We can start making predictions once the coefficients have been estimated by using

$\widehat{p}(X)=\widehat{Pr}(Y=1|X)=\dfrac{e^{\widehat\beta_{0}+\widehat\beta_{1}X}}{1+e^{\widehat\beta_{0}+\widehat\beta_{1}X}}$

which returns a value between 0 and 1. Now suppose we add more predictors such as class attendance, hours studies etc, then we will have to use a multiple logistic regression model for $p$ predictors which is simply

$p(X)=Pr(Y=1|X)=\dfrac{e^{\beta_{0}+ \beta_{1}X_{1} + ... + \beta_{p}X_{p}}}{1+e^{\beta_{0}+ \beta_{1}X_{1} + ... + \beta_{p}X_{p}}}$


