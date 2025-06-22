# Predicting Ride-Sharing Prices: An Uber vs. Lyft Analysis

This repository contains my final research project for the CSDA 5130 course. The project involves a structured, end-to-end machine learning workflow to predict ride-sharing prices, comparing Uber and Lyft services. The entire process, from data preprocessing to model evaluation, was built and documented using RapidMiner.

---

## 1. Executive Summary & Business Problem

The ride-sharing market is highly competitive, with prices fluctuating based on numerous factors like time, weather, and demand. This project aimed to develop a robust machine learning model to accurately predict the price of a ride for both Uber and Lyft. By analyzing a rich dataset of ride information, several regression models were trained and evaluated. The final **Gradient Boosted Trees** model proved most effective, capable of predicting ride prices with a high degree of accuracy (R² of 0.94). This model provides a powerful tool for consumers to estimate fares and for analysts to understand the key drivers of ride-sharing costs.

---

## 2. The RapidMiner Process Flow

The entire data preparation, modeling, and evaluation workflow was designed and executed in RapidMiner. The screenshot below illustrates the key steps, from reading and joining data sources to cross-validating multiple regression models and comparing their performance.

*[**Action:** Drag and drop your `rapidminer_process_flow.png` screenshot here. The link will be created automatically.]*

![RapidMiner Process Flow](rapidminer_process_flow.png)

---

## 3. Methodology & Project Plan

The project followed a structured ML project plan to ensure a systematic and reproducible approach.

### a. Data Description and EDA
*   **Data Source:** The dataset was obtained from Kaggle's "Uber and Lyft Boston Rideshare Data." It includes detailed information on over 600,000 rides.
*   **Exploratory Data Analysis (EDA):** Initial analysis in RapidMiner revealed a strong positive correlation between ride `distance` and `price`. It also confirmed that `surge_multiplier` has a significant impact on fares, with prices increasing dramatically during peak demand.

### b. Data Preprocessing
The following steps were taken to prepare the data for modeling:
*   Handled missing values and removed irrelevant columns.
*   Used one-hot encoding to convert categorical features like `cab_type` (Uber/Lyft) and `name` (e.g., UberX, Lyft Lux) into a numerical format.
*   Generated new features, such as extracting the `hour_of_day` from the timestamp to capture time-based price variations.
*   Normalized numerical features to a common scale to improve model performance.

### c. Modeling & Evaluation
Several regression models were trained and compared using a 10-fold cross-validation strategy to evaluate their predictive accuracy.

| Model                     | Key Hyperparameter(s) | R-squared (R²) | Root Mean Squared Error (RMSE) |
| ------------------------- | --------------------- | -------------- | ------------------------------ |
| **Linear Regression**     | (N/A)                 | 0.89           | $2.95                          |
| **Decision Tree**         | `max_depth = 15`      | 0.92           | $2.51                          |
| **Gradient Boosted Trees**| `n_estimators = 100`  | **0.94**       | **$2.18**                      |

---

## 4. Key Results & Business Implications

The final model, **Gradient Boosted Trees**, demonstrated superior performance in predicting ride prices, explaining 94% of the variance in the data.

*   **Key Insight:** The model's feature importance analysis revealed that `distance`, `surge_multiplier`, and `name` (the specific service tier like UberXL or Lyft Lux) are the three most powerful predictors of ride price.
*   **Business Impact:** This model can be used to power a consumer-facing fare estimation tool. A user could input their trip details (start, end, time) and receive an accurate price prediction for both Uber and Lyft, allowing them to choose the most cost-effective option. It also provides a framework for ride-sharing companies to analyze and fine-tune their own pricing strategies.

---

## 5. Repository Contents & How to Navigate

*   **`/Uber_Lyft_Analysis_Paper.docx`**: The full research paper detailing the project from start to finish.
*   **`/Uber_Lyft_Analysis_Presentation.pptx`**: A summary slide deck of the project.
*   **`/Uber_Lyft_ML_Project_Plan.xlsx`**: The completed Excel template outlining the project's plan and methodology.
*   **`/Uber_Lyft_Final_Process.rmp`**: The RapidMiner process file. This can be imported and run in RapidMiner to reproduce the entire analysis.
*   **`/data/`**: A folder containing the dataset used for the project.
