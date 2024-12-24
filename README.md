# BikeSharingAssignment
 build a multiple linear regression model for the prediction of demand for shared bikes. 


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

# Bike Sharing Demand Prediction

# General Information

## Problem Statement

A bike-sharing system provides bicycles for shared use on a short-term basis, either for a fee or free of charge. Many such systems utilize computer-controlled "docks," where users input payment information to unlock a bike. The bike can then be returned to any dock within the same system.

BoomBikes, a US-based bike-sharing provider, has faced significant revenue declines due to the COVID-19 pandemic. To recover quickly and thrive once the lockdown is lifted and the economy stabilizes, BoomBikes aims to devise a strategic business plan. 

The company is focused on understanding the factors influencing the demand for shared bikes post-pandemic. By doing so, they aim to anticipate customer needs, outpace competitors, and maximize profits. BoomBikes has partnered with a consulting firm to analyze these factors.

### Key Questions

1. Which variables significantly influence the demand for shared bikes?  
2. How effectively do these variables explain variations in bike demand?  

Using data gathered from meteorological surveys and customer behavior trends, BoomBikes has compiled a dataset of daily bike demand across the American market. This dataset serves as the foundation for analysis and strategy development.

---

## Business Goal

The objective is to model the demand for shared bikes using the provided independent variables. This model will help management understand how bike demand varies with different factors. Consequently, BoomBikes can manipulate business strategies to meet demand levels and customer expectations. The model will also aid in understanding demand dynamics in new markets.

---

## Dataset Information

- **casual**: Number of casual users making rentals.  
- **registered**: Number of registered users making rentals.  
- **cnt**: Total number of bike rentals (target variable), including both casual and registered users.  

---

## Steps Taken

1. **Data Understanding and Cleaning**
   - Read and explored the dataset.

2. **Exploratory Data Analysis (EDA)**
   - Univariate analysis
   - Bivariate analysis
   - Multivariate analysis

3. **Data Preparation**
   - Train-test split
   - Rescaling variables
   - Checking Variance Inflation Factor (VIF)
   - One-hot encoding

4. **Model Building**
   - Feature scaling
   - Training the model using `LinearRegression` from `sklearn.linear_model`

5. **Residual Analysis**
   - Homoscedasticity
   - Linearity validation

6. **Model Evaluation**
   - R² and Adjusted R² calculation
   - Visualizing the model
   - Deriving the equation for the best-fit line

---

## Key Insights

### Positive Factors:
1. **Temperature (temp):**  
   - A unit increase in temperature results in a **+4122.11** increase in bike bookings.  
   - Warmer temperatures have a strong positive correlation with bike usage.  

2. **Year (yr):**  
   - A unit increase in year results in a **+2044.85** increase in bike bookings.  
   - Reflects a positive trend in bike rental popularity over time.  

3. **September:**  
   - September shows a strong positive correlation with bike bookings, likely due to favorable weather and increased popularity.  

### Negative Factors:
1. **Bad Weather (3):**  
   - Bad weather conditions (e.g., heavy rain, thunderstorms, snow) lead to a **-2491.068** decrease in bike bookings.  

2. **Winter:**  
   - Holidays and colder months see decreased demand due to unfavorable weather conditions.  

---

## Model Equation

The final model for predicting bike demand:

cnt = 1858.811 + (yr * 2044.850) - (holiday * 816.386) + (temp * 4122.114) - (windspeed * 1363.530) - (spring * 531.807) + (summer * 380.496) + (winter * 668.806) - (january * 333.645) - (july * 443.581) + (september * 660.234) + (sunday * 172.032) - (2 * 694.085) - (3 * 2491.068)


---

## Overall Analysis

Bike demand is influenced by the following factors:

- **Positive Influences:**
  - Warmer temperatures during summer.
  - The month of September.
  - Increasing popularity of bike rentals over time.

- **Negative Influences:**
  - Bad weather (e.g., rain, thunderstorms, snow).
  - Winter holidays and colder months.

By leveraging these insights, BoomBikes can adjust its strategies to meet customer demands effectively and maximize revenue.



## Model Visualization

The graph below shows the predicted bike demand vs. the actual bike demand:

![Model Visualization](./image.png)
