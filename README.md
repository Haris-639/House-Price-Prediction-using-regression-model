# House Price Prediction

## Task Objective

The objective of this project is to build a regression model to predict house sale prices based on various property features. The goal is to analyze how well basic machine learning models can capture real estate price trends using structured data.

## Dataset Used

**Dataset**= https://www.kaggle.com/datasets/zafarali27/house-price-prediction-dataset
The dataset contains the following columns:

| Feature               | Description                                         |
|------------------------|-----------------------------------------------------|
| Area                 | Square footage of the house                         |
| Bedrooms             | Number of bedrooms                                  |
| Bathrooms            | Number of bathrooms                                 |
| Floors               | Number of floors in the house                       |
| YearBuilt            | Year the house was constructed                      |
| Location             | Categorical variable                                |
| Condition            | Categorical condition of the house                  |
| Garage               | Binary feature indicating garage availability       |
| Price                | Target variable representing house sale price       |

**Derived Feature**: A new feature, `HouseAge`, was created as `2025 - YearBuilt`.


## Models Applied

The following regression models were implemented using 'scikit-learn':

- **Linear Regression**
- **Gradient Boosting Regressor**

Preprocessing steps included:
- One-hot encoding for categorical features (`Location`, `Condition`, `Garage`)
- Feature scaling using *MinMaxScaler* on numerical columns (`Area`, `HouseAge`)
- Train-test split with 80% training and 20% testing

## Key Results and Findings

| Model                 | MAE (Mean Absolute Error) | RMSE (Root Mean Squared Error) |
|-----------------------|---------------------------|----------------------------------|
| Linear Regression     | ~244419.99901363705       | ~280587.6374016649              |
| Gradient Boosting     | ~244909.88652959638       | ~283523.8808127885              |

### Observations:
- The models produced relatively high errors, which suggests that:
  - The available features might not be sufficient to accurately predict price
  - Feature relationships with price are not purely linear
  - More advanced models or richer datasets may be required
- `Floors` showed stronger correlation with price than expected features like `Area`


## Conclusion

This project builds a baseline regression pipeline for predicting house prices. Although models were applied successfully, high prediction errors highlight the need for either:
- Additional feature engineering
- More complex models (e.g., XGBoost or Random Forest with tuning)
- Larger or more detailed datasets
