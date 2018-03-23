Stedin Data Science Analytics Community
=======================================

### Code, images and data used for the Data Science Analytics Community 'Deep Dive Into SVMs' session. 

#### 1 - Binary Classification - Linear Kernel Example

The `basic_linear_kernel.R` code includes a simple classification example using the famous [iris dataset](https://archive.ics.uci.edu/ml/datasets/iris).
*Note* that the data is reduced by removing all the cases of 'versicolor' species so that the problem is reduced to binary classification.
The following plot shows a two dimensional plot of the iris data where the class separation is visible.

Linear Separation: ![new plot](https://github.com/idlirshkurti/StedinSVM/blob/master/iris_classes.png)

The data is separated into a train set (75% of the rows) and a test set (25% of rows). The following lines of code are used to build an SVM model using a linear kernel and make predictions for the test set.
```R
svm_model <- svm(xtrain, ytrain, scale = TRUE, kernel = "linear")
ypred <- predict(svm_model, xtest)
```
The confusion matrix below generated by `table(ypred, ytest)` shows a perfect separation in the test set predictions. 

| Confusion Matrix    |               |           |
| ------------------- |:-------------:| ---------:|
| Actuals\Predictions | setosa        | virginica |
| setosa              | 12            |   0       |
| virginica           | 0             |    13     |



#### 2 - Binary Classification - Gaussian Kernel Example

Artificial data was generated in R to simulate non linear separation in a two dimensional space as shown below.
Data points which are within the boundaries of the circle with equation `(x-1)^2 + (y-1)^2 = 1` are given a class 0 and the datapoints outside the circle (or on the boundaries) a class of 1.


![new plot](https://github.com/idlirshkurti/StedinSVM/blob/master/non_linear_plot.png)

Radial (Gaussian) Kernel Performance: ![new plot](https://github.com/idlirshkurti/StedinSVM/blob/master/test_non_linear.png)


| Confusion Matrix        |               |       |
| ----------------------- |:-------------:| -----:|
| Actuals\Predictions     | 0             |    1  |
| 0                       | 97            |    0  |
| 1                       | 4             |   149 |


#### 3 - More Complicated Example - Optimising parameters (Titanic Dataset)









