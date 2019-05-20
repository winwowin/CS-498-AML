library(MASS)
library(glmnet)

# Plot diagnosis plots of raw data
data(Boston)
fit1 <- lm(medv ~ crim + zn + indus + chas + nox + rm + age + dis + rad + tax + ptratio + black + lstat, data=Boston)
par(mfrow=c(2,2)) # Change the panel layout to 2 x 2
plot(fit1, id.n = 3)

# Plot diagnosis plots of outliers-removed data
Boston2 <- Boston[-c(381,419,406,411,365,369,373,372,366),]
fit2 <- lm(medv ~ crim + zn + indus + chas + nox + rm + age + dis + rad + tax + ptratio + black + lstat, data=Boston2)
par(mfrow=c(2,2))
plot(fit2, id.n = 3)

# Apply Box-Cox transformation
par(mfrow=c(1,1))
Box = boxcox(Boston2$medv ~ 1)
Cox = data.frame(Box$x, Box$y)            # Create a data frame with the results
Cox2 = Cox[with(Cox, order(-Cox$Box.y)),] # Order the new data frame by decreasing y
Cox2[1,]                                  # Display the lambda with the greatest log likelihood
lambda = Cox2[1, "Box.x"]                 # Extract that lambda
T_box = (Boston2$medv ^ lambda - 1)/lambda   # Transform the original data
Boston2$boxcox <- T_box

# Fit the Box-Cox transformed data
fit3 <- lm(boxcox ~ crim + zn + indus + chas + nox + rm + age + dis + rad + tax + ptratio + black + lstat, data=Boston2)
Boston2.stdres <- rstandard(fit3)
par(mfrow=c(1,1))

# Plot "Real values vs Prediction"
plot((((fit3$fitted.values)*0.2222222222)+1)^(1/0.2222222222), Boston2$medv, ylab = "Real Values", xlab = "Predictions", main = "Real values vs Prediction")

# Plot "Std Residuals values vs Prediction"
plot((((fit3$fitted.values)*0.2222222222)+1)^(1/0.2222222222), Boston2.stdres, ylab = "Std Residuals", xlab = "Predictions", main = "Std Residuals values vs Prediction")
