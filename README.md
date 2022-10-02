
# Insurance Price Prediction

The prediction for Insurance premium works as follows. You have some features/input (age, gender, smoking, etc.) which go into the training process. These features can determine how high or low is the premium amount. For example, the younger people are less likely to need medical care, so their premiums are generally cheaper, and the premium is higher for smokers. The Label/Output is the Premium/Price that you want to predict, which is the outcome of calling the Machine Learning Model.

---

## Authors
- [@roshan2600](https://github.com/roshan2600)

---

## Learning Objectives:
1. Getting practical hands-on on assumptions.

---

## Dataset Information
- The Dataset can be found [here](https://www.kaggle.com/datasets/mirichoi0218/insurance).
- The dataset contained 1338 observations and 7 features (including target variable).
  ### Attribute Information:
  - **age:** age of primary beneficiary
  - **sex:** insurance contractor gender, female, male
  - **bmi:** Body mass index, providing an understanding of body, weights that are relatively high or low relative to height, objective index of body weight (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9
  - **children:** Number of children covered by health insurance / Number of dependents
  - **smoker:** Smoking
  - **region:** the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.
  - **charges:** Individual medical costs billed by health insurance

---

## Feature Engineering:
- Applied custom mapping on *smoker* feature.
  ### OneHotEncoding:
  - Here we are Encoding the categorical variables: **sex** & **region**.
  - One major mistake to avoid while OneHotEncoding is that we should not use **fit_transform** on our data. The correct method invloves: **fit**, **save the model** & **transform**.
  - In OneHotEncoding we should drop the one of the dummy variables for each categories to avoid **Dummy Variable Trap**.
  
  ### Standardization:
  - Before assumptions we apply feature scalling.
  - I have applied StandardScaler.
  
---

## Linear Regression Assumptions:
#### 1. Linearity
#### 2. Multicollinearity:
  -  Multicollinearity is the occurrence of high intercorrelations among two or more independent variables in a multiple regression model.
  - To measure multicollinearity among the independent features, we use VIF (Variance Inflation Factor).
#### 3. Autocorrelation:
  - Autocorrelation represents the degree of similarity between a given time series and a lagged version of itself over successive time intervals.
  - Autocorrelation measures the relationship between a variable's current value and its past values.
  - We use Durbin Watson test to measure the degree of autocorrelation.
  - The Durbin Watson test reports a test statistic, with a value from 0 to 4, where:
    - 2 is no autocorrelation.
    - Less than 2 is positive autocorrelation (common in time series data).
    - Greater than 2 is negative autocorrelation (less common in time series data).
  - A residual vs fitted plot can also be used to assess the autocorrelation in the data.
#### 4. Normaility of Residuals:
  - Normality is the assumption that the underlying residuals are normally distributed, or approximately so.
  - We can use a Q-Q Plot to see whether our data is normally distributed.
#### 5. Homoscedasticity:
  - Heteroskedasticity refers to situations where the variance of the residuals is unequal over a range of measured values.
  - When running a regression analysis, heteroskedasticity results in an unequal scatter of the residuals.
  - A residual vs fitted plot can be used to assess whether data is homoscedatic in nature or not.
  - Goldfeld-Quandt Test can also be used to assess the same.
