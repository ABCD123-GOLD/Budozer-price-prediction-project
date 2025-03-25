# Predicting the Price of Bulldozers using Machine Learning

## 1. Problem Definition

**Goal:** Develop a machine learning model to predict the auction sales price of heavy equipment (bulldozers), effectively creating a "blue book" for these machines.

**Question:** How accurately can we predict the future sale price of a bulldozer, given its characteristics and historical data on similar bulldozer sales?

## 2. Data

**Source:** The data for this project is sourced from the Kaggle "Blue Book for Bulldozers" competition.

**Datasets:**
  - Train.csv: The training dataset, containing sales data up to the end of 2011.
  - Valid.csv: The validation dataset, containing sales data from January 1, 2012, to April 30, 2012. This dataset is used for model evaluation during the competition and contributes to the public leaderboard.
  - Test.csv: The test dataset, released in the final week of the competition. It contains sales data from May 1, 2012. The model's performance on this dataset determines the final ranking in the competition.


## 3. Evaluation

**Metric:** The evaluation metric for this competition is the Root Mean Squared Logarithmic Error (RMSLE).

**Note:** The objective in most regression evaluation metrics is to minimize the error. Therefore, the goal of this project is to build a machine learning model that minimizes the RMSLE.

## 4. Features

**Data Dictionary:** Kaggle provides a data dictionary detailing the features of the dataset.

**Key Features:**
  - SalesID: Unique identifier for each machine sale at auction.
  - MachineID: Identifier for a specific machine; a machine may have multiple sales.
  - ModelID: Identifier for a unique machine model (e.g., fiModelDesc).
  - datasource: Source of the sale record; reporting accuracy varies across sources.
  - ... (refer to the data dictionary for a complete list)

## 5. Methodology

- **Data Preprocessing:**
  - Handling missing values: Numerical features were filled with the median, and categorical features were filled with the mode. Categorical features were then converted to numerical using pandas categories.
  - Feature engineering: New features were created from the date column to capture temporal information.
- **Model Selection:** Random Forest Regressor was chosen for its ability to handle complex relationships and its robustness to outliers.
- **Model Training:** The model was trained on the training dataset using cross-validation to optimize hyperparameters.
- **Model Evaluation:** The model was evaluated on the validation dataset using RMSLE as the primary metric. Other metrics, such as Mean Absolute Error (MAE) and R-squared, were also used for a comprehensive evaluation.

## 6. Visualization

**Highlight Visualization**
**Visualization Output:**

[![Distribution of Sale Prices by State](./sale_price_by_state.png)](./sale_price_by_state.png)

[![Sale Price vs. Machine Hours](./sale_price_vs_machine_hours.png)](./sale_price_vs_machine_hours.png)


## 7. Results and Conclusion

- **Model Performance:** The Random Forest Regressor model achieved a high R-squared value on the training data, indicating a good fit. However, the performance on the validation set was slightly lower, suggesting a potential for overfitting.
- **RMSLE:** The model achieved a relatively low RMSLE score on both the training and validation sets, indicating reasonable accuracy in predicting bulldozer prices.
- **Key Features:** Feature importance analysis revealed that features like 'YearMade', 'ProductSize', 'Enclosure', and 'state' were among the most influential in predicting sale prices. This suggests that the age, size, type, and location of a bulldozer play a significant role in determining its value.
- **Overall:** The developed machine learning model demonstrates the potential for accurately predicting bulldozer prices based on historical data and machine characteristics.

## 8. Future Improvements

- **Hyperparameter Tuning:** Further exploration of hyperparameter tuning techniques, such as GridSearchCV or Bayesian optimization, could potentially improve model performance.
- **Feature Engineering:** Experimenting with different feature engineering strategies, such as creating interaction terms or using domain expertise to engineer new features, might enhance the model's ability to capture complex relationships in the data.
- **Data Augmentation:** Consider augmenting the dataset with external data sources to increase the sample size and improve the model's generalization ability.
- **Model Selection:** Evaluating other machine learning models, such as XGBoost or CatBoost, might lead to better predictive performance.
- **Deployment:** Develop a user-friendly interface or API to make the model accessible to end-users, allowing for real-time price predictions.
- **Address Overfitting:** Implement techniques such as regularization, cross-validation, or early stopping to mitigate overfitting and improve model generalization.
- **Error Analysis:** Conduct a detailed analysis of prediction errors to identify potential areas for improvement and refine the model's understanding of the underlying patterns.
