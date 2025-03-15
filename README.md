# COVID-19 Case Growth Analysis using Multi-Regressors

This project analyzes the growth of COVID-19 cases using multiple regression models, including:
- Linear Regression
- Polynomial Regression
- Support Vector Regression (SVR)
- Decision Tree Regression
- Random Forest Regression
- Voting Regressor (Ensemble Model)

## 📊 Dataset Source
The dataset is sourced from the **Johns Hopkins University COVID-19 Dataset**, which provides daily case counts worldwide.

## 🔧 Installation & Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn
```

## 🚀 Usage Guide

To run the analysis, execute the provided Jupyter Notebook.

## 📌 Models Used

Importing Libraries

Loading the dataset

Preprocessing the Dataset

Fit various regression models

Train and compare Different Regression models

## 📈 Results & Visualization
The results are plotted to compare different regression models.

## 🛠 Code Overview

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import PolynomialFeatures, StandardScaler
from sklearn.linear_model import LinearRegression
from sklearn.svm import SVR
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_squared_error, r2_score
```

```python
# Load COVID-19 confirmed cases dataset
url = "https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv"
df = pd.read_csv(url)

# Display first few rows
df.head()
```

```python
#Selecting data for a specific country in this case we'll use Kenya
country = "Kenya"
df_country = df[df['Country/Region'] == country].drop(columns=['Province/State','Lat','Long']).sum()

#Converting date column into a time series
df_country = df_country.iloc[1:] #Removes the 'Country/Region' row
df_country.index = pd.to_datetime(df_country.index)
df_country = df_country.reset_index()
df_country.columns = ["Date","Confirmed"]

#Add Days since first column
df_country["Days"] = (df_country["Date"]
```

## 🤝 Contributing
Feel free to fork, modify, and improve the project!

## 📜 License
This project is open-source under the MIT License.
