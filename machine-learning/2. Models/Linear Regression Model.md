Linear regression is a supervised [[Machine Learn Models|learning model]] used for regression tasks, where the goal is to predict a **continuous output** variable **based on input** features. It assumes a linear **relationship** between the input features and the target variable, seeking to find the best-fitting line that represents this relationship.

The model learns to fit a straight line that best represents the relationship between the input variables and the continuous target variable.

##### Example
Suppose we have to train a model that predicts the tax percentage based on a given salary. In this scenario, we expect the model to yield a tax rate of **30%** for a salary of **$90,000**.

Here's an example of how to create a simple linear regression model using Python and the popular [scikit-learn](https://scikit-learn.org/stable/index.html) library:

```python
# Import the necessary libraries
import numpy as np
from sklearn.linear_model import LinearRegression

# Sample data
salary = np.array([50000, 60000, 70000, 80000, 100000]).reshape(-1, 1) # Input feature

tax_percent = np.array([20, 22, 25, 28, 32])  # Target variable (tax percentage)

# Create a Linear Regression model
model = LinearRegression()

# Fit the model to the data
model.fit(salary, tax_percent)

# Make predictions using the trained model
salary_new = np.array([90000]).reshape(-1, 1)  # New data point
tax_percent_pred = model.predict(salary_new)

# Print the predicted tax percentage
print("Predicted tax percentage:", tax_percent_pred)
```
