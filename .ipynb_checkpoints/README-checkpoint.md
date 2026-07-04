# 🚗 Car Price Prediction

Ever wondered what your car is actually worth? This project builds a machine learning model to predict car selling prices based on various features like the car's age, mileage, fuel type, and more.

# New concepts you now own:

* Regression vs classification — predicting numbers not categories
* Feature engineering — converting Year → Car_Age
* One-hot encoding — converting text categories to binary columns
* Log transformation — fixing skewed target distributions
* expm1 — reversing log transformation on predictions
* MAE, RMSE, R² — regression evaluation metrics
* Actual vs Predicted plot — visual regression evaluation
* Feature importance — understanding what the model actually learned
* Random Forest — ensemble learning, why it beats a single tree
* Multicollinearity — seeing it in the dummy variable columns

## What This Does

Given information about a car (how old it is, how many kilometers it has driven, its current market price, etc.), this model predicts what price it would sell for. Super useful for:
- Car dealerships pricing their inventory
- Individuals selling their used cars
- Anyone curious about car valuations

## The Dataset

We've got 301 car records with these features:
- **Car_Name** – the car's model name
- **Year** – when it was manufactured
- **Selling_Price** – the price at which it was sold (our target variable!)
- **Present_Price** – current ex-showroom price
- **Driven_kms** – total kilometers driven
- **Fuel_Type** – Petrol, Diesel, or CNG
- **Selling_type** – Dealer or Individual seller
- **Transmission** – Manual or Automatic
- **Owner** – how many previous owners

## Approach

1. **Data Cleaning & Prep**
   - Converted "Year" to "Car_Age" (much more meaningful!)
   - Dropped the car name (too many unique values to be useful)
   - One-hot encoded categorical variables (Fuel_Type, Selling_type, Transmission)

2. **Feature Engineering**
   - Applied log transformation to the target variable (prices are often skewed)

3. **Model**
   - Random Forest Regressor with 100 trees
   - 80/20 train-test split

4. **Results**
   - **R² Score: 0.956** – The model explains 95.6% of the variance in car prices! 🎯
   - **MAE: 0.63 lakhs** – On average, predictions are off by about 63,000 INR
   - **RMSE: 1.01 lakhs**

5. **Key Insights**
   - Present Price is the most important factor (makes sense!)
   - Car Age comes second – older cars are cheaper
   - Kilometers driven matters too

## Running It

This is a Jupyter notebook. Just open it in Jupyter or VS Code and run the cells:

```bash
jupyter notebook Car_Price_Prediction.ipynb
```

Or open directly in VS Code – it should detect the notebook automatically.

## Dependencies

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

Install everything with:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Files

```
├── Car_Price_Prediction.ipynb   # The main notebook
└── Datasets/
    └── car data.csv             # The dataset
```

## Future Improvements

Some ideas if you want to take this further:
- Try other models (XGBoost, LightGBM)
- Add more features (car brand, model specifics)
- Tune hyperparameters
- Build a simple web app for predictions

---

Made with ☕ and curiosity