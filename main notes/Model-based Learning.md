They system generalizes over new data by building a model from the training set and use that model to make prediction.
other words, the system creates a formula or notice pattern in the training and make prediction, unlike Instance-based learning which is rot learner


## Example
Given table, we are gonna predict life satisfaction based on GDP per capita
![[Pasted image 20250806145358.png]]

plot the graph and check the trend here and do **model selection**
![[Pasted image 20250806145432.png]]

we select a linear model of life satisfaction with just one attribute, GDP per capita
_A simple linear model_
$\text{life\_satisfaction} = \theta_0 + \theta_1 \times \text{GDP\_per\_capita}$


### selecting the best parameter for the model
![[Pasted image 20250806151630.png]]

You need to specify performance measure like 
**utility function(or fitness function):** that measure how good is your model
or
**cost function:** how bad is your model

for linear regression, people tend to choose the later and measure the distance between the linear model's predictions and the training examples; the objective is to minimize this distance.



**best option**
**linear regression algorithm:** you feed your training datasets and find the best parameter to your data. This is called **training** the model.
![[Pasted image 20250806152058.png]]



## Example
Predicting life satisfaction of Cyprus
GDP per capita of Cyprus is 37,655.2 (2020 data)

code to make prediction
```py
import matplotlib.pyplot as plt

import pandas as pd

import numpy as np

from sklearn.linear_model import LinearRegression

  

# Download and prepare the data

data_root = "https://github.com/ageron/data/raw/main/"

lifesat = pd.read_csv(data_root + "lifesat/lifesat.csv")

X = lifesat[["GDP per capita (USD)"]].values

y = lifesat[["Life satisfaction"]].values

  

# Visualize the data

lifesat.plot(kind='scatter', grid=True, x="GDP per capita (USD)", y="Life satisfaction")

plt.axis((23_500, 62_500, 4, 9))

plt.show()

  

# Select a linear model

model = LinearRegression()

  

# Train the model

model.fit(X, y)

  

X_new = [[37_655.2]]

print(model.predict(X_new)) # type: ignore
```