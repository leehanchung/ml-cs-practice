## Ridge Regression

![Ridge Regression](/machine-learning/elliot/Ridge_Regression_print.png)
Source: Chris Albon's flashcards

- The main idea behind ridge regression is we introduce a small amount of bias when fitting the data, so we have a drop in variance (don’t over-fit)
- The model generalizes better
-	With a worse fit, ridge regression can provide better long-term predictions
-	How does it do this?
  - OLS minimizes sum of squared residuals
  - Ridge minimizes that and [lambda x slope^2]
  - [lambda x slope^2] is a penalty applied to the traditional OLS method. This is the small amount of bias introduced
-	How do we determine lambda?
  - A larger lambda means a less sensitive ridge regression (slope is flatter)
  - When lambda is 0, you get OLS
  - We just try a bunch of lambda values and use cross validation to determine the one with lowest variance
-	Does this work with discrete variables??
  - Yes, a little trickier…
-	We can also apply this to logistic regression: it optimizes the sum of the likelihoods instead of SSRs because logistic regression is solved using maximum likelihood
-	Ridge regression is also great in datasets where the # of parameters exceeds data points (e.g. 10,000 parameters, 500 data points)
  - Again, it will be able to do this with cross validation and the ridge penalty that optimizes for smaller parameter values
  - It is able to work well on smaller sample sizes as it makes the predictions less sensitive to the training data
- In sum:
    - Lasso & ridge are two ways to add penalization (aka regularization: increase bias, reduce variance)
    - Ridge penalizes by the sum of squares
    - Use ridge when you're worried about the features overfitting
    - Make sure to normalize/standardize the data first
    - Cons:
      - Cannot perform variable selection

Notes from:  
[StatQuest: Ridge Regression]( https://www.youtube.com/watch?v=Q81RR3yKn30)

[ryxcommar](https://ryxcommar.com/2019/09/06/some-things-you-maybe-didnt-know-about-linear-regression/)


Code example:  
[Chris Albon](https://chrisalbon.com/machine_learning/linear_regression/ridge_regression/)
