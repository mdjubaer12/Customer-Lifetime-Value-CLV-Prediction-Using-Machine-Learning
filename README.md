# Customer Lifetime Value (CLV) Prediction Using Machine Learning

## Project Overview
This project aims to predict **Customer Lifetime Value (CLV)** using machine learning techniques. CLV is a key metric for businesses to estimate the total revenue a customer will generate over their lifetime. The project involves data preprocessing, feature engineering, and the application of regression models to predict CLV based on customer transaction data.

**Note:** The CLV target variable has been **log-transformed** to stabilize variance and improve model performance.

## Dataset
The dataset contains the following columns:
- `InvoiceNo`: Invoice number of the transaction
- `StockCode`: Unique code of the product
- `Description`: Description of the product
- `Quantity`: Quantity of the product in the transaction
- `InvoiceDate`: Date and time of the transaction
- `UnitPrice`: Unit price of the product
- `CustomerID`: Unique identifier of the customer
- `Country`: Country where the transaction occurred

## Project Workflow
1. **Data Preprocessing**:
   - Removed missing `CustomerID` values.
   - Removed negative `Quantity` values and outliers in `Monetary` values.
   - Created **Recency**, **Frequency**, and **Monetary** (RFM) features from customer purchase history.
   
2. **Feature Engineering**:
   - Created additional features like **Average Order Value** and **Monetary per Recency**.
   - Target variable **CLV** was **log-transformed** using `log1p()` to handle large variance and improve regression performance.

3. **Model Building**:
   - Trained a **Random Forest Regressor** on the log-transformed CLV data.
   - Evaluated the model using **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)**.
   - Performed **hyperparameter tuning** to optimize model performance.
   
4. **Model Evaluation**:
   - Reversed the log transformation to predict actual CLV values.
   - **MAE**: 555.74  
   - **RMSE**: 3782.33

5. **Visualization and Deployment**:
   - Used **Streamlit** to build an interactive web application to predict CLV based on user input (Recency, Frequency, and Monetary).
   - Added visualizations to explore customer segmentation and CLV distribution.

## Key Technologies
- **Python**: Core language for data preprocessing, modeling, and feature engineering.
- **Pandas**: Data manipulation and processing.
- **Scikit-learn**: Machine learning models and evaluation metrics.
- **Matplotlib/Seaborn**: Data visualization for insights and analysis.
