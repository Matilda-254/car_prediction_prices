CarDekho Used Cars Price Prediction
This project analyzes and predicts the selling price of used cars using the CarDekho dataset. The workflow covers data cleaning, exploratory data analysis (EDA), feature engineering, and training regression models
to understand the factors that affect car prices.
Dataset Description

The dataset contains details of used cars listed for sale.

Columns Explanation:

name: Brand, model, and variant of the car (e.g., Maruti Swift Dzire VDI)

year: Year of manufacture

selling_price: Target variable, price of the car to be sold

km_driven: Distance traveled in kilometers

fuel: Fuel type (Petrol, Diesel, LPG, CNG, etc.)

seller_type: Type of seller (Individual, Dealer, Trustmark Dealer)

transmission: Transmission type (Manual, Automatic)

owner: Ownership details (First Owner, Second Owner, etc.)

mileage: Mileage in kmpl or km/kg

engine: Engine capacity in cc

max_power: Maximum power output (bhp)

seats: Seating capacity

car_age: Derived feature → Current year minus manufacturing year

price_per_km: Derived feature → Selling Price divided by Mileage

brand: Extracted from car name
Data Preprocessing

Checked for missing values and handled them using imputation (mean or most frequent strategy).

Dropped rows with missing target variable (selling_price).

Removed duplicates to prevent bias.

Converted categorical values and inconsistent text into numeric formats.

Engineered new features such as car_age, price_per_km, brand.

Handled outliers by removing cars priced below 10,000 or above 5,000,000.

Standardized column names for consistency.
Exploratory Data Analysis (EDA)

Some insights obtained from the dataset:

Most common fuel type: Petrol.

Automatic cars tend to be more expensive on average compared to manual cars.

Car age is negatively correlated with price (older cars sell for less).

Outliers affect regression performance, so extreme prices were removed.

Distribution of selling prices is right-skewed (more budget cars than luxury ones).

Visualizations include:

Boxplots and histograms of selling prices.

Scatterplots showing relationships (Car Age vs Selling Price, Mileage vs Price).

Correlation heatmap for numeric features.

Bar charts for categorical variables (Fuel, Transmission, Brand).
Machine Learning Models

Models were trained to predict Selling Price.

Baseline Models

Linear Regression

Lasso Regression (L1 regularization → shrinks irrelevant features)

Ridge Regression (L2 regularization → controls multicollinearity)

Key Results:

Linear Regression: R² ≈ 0.70, moderate performance.

Lasso Regression: R² ≈ 0.75, lower MSE than Linear Regression.

Ridge Regression: R² ≈ 0.75, performed slightly better after tuning.

GridSearchCV was applied for Ridge to optimize the regularization parameter alpha.

Why Regularization?
Prevents overfitting.

Handles multicollinearity.

Improves generalization to unseen data.
Results Summary

Best model: Ridge Regression with tuned alpha (0.1).

Performance: R² ≈ 0.75 → Model explains ~75% of the variance in car prices.

Insights:

Newer cars with automatic transmission and higher engine power sell at higher prices.

Mileage has only a weak negative effect on price.

Brand and fuel type significantly influence price.
Tech Stack

Python

Pandas → Data cleaning & preprocessing

Matplotlib, Seaborn → Data visualization

Scikit-learn → Model training & evaluation

Statsmodels → Regression diagnostics

NumPy → Numerical operations
