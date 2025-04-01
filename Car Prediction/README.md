# **Car Price Prediction**

## **Context**
Geely Auto, a Chinese automobile company, is entering the U.S. market and aims to understand the key factors influencing car prices. This dataset provides various attributes of cars sold in the American market to predict car prices based on their features.

## **Dataset Description**
The dataset includes various features that can influence the price of a car:

### **Columns**:
- **CarID**: Unique Identifier for each car
- **CarName**: Name of the Car Model
- **FuelType**: Type of fuel used (Gasoline, Diesel, Electric, etc.)
- **Aspiration**: Type of aspiration (Standard or Turbocharged)
- **NumDoors**: Number of doors on the car
- **BodyStyle**: Body style (Sedan, Coupe, SUV, etc.)
- **DriveWheelType**: Type of drive wheel (Front, Rear, All)
- **EngineLocation**: Location of engine (Front or Rear)
- **Wheelbase**: Length of the wheelbase
- **CarLength**: Length of the car
- **CarWidth**: Width of the car
- **CarHeight**: Height of the car
- **CurbWeight**: Weight of the car without passengers or cargo
- **EngineType**: Type of engine (Gas, Diesel, Electric, etc.)
- **Horsepower**: Engine power
- **Torque**: Important for acceleration and towing capacity
- **Mileage**: Fuel efficiency or energy consumption (MPG or kWh/mile)
- **TransmissionType**: Automatic vs. Manual
- **Price**: Target variable (Price of the car)

## **Objective**
The goal of this project is to predict car prices based on various features and to understand the key factors influencing these prices.

## **Technologies Used**
- Python
- Pandas for data manipulation
- Seaborn & Matplotlib for data visualization
- Scikit-learn for machine learning models and evaluation

## **Steps Taken in the Project**

### **1. Data Preprocessing**
- **Exploration**: The dataset was explored using summary statistics and visualizations for numerical and categorical variables.
- **Categorical Variables Encoding**: Categorical variables like fuel type, aspiration, etc., were encoded using label encoding.
- **Feature Engineering**: A new feature, `power_to_weight_ratio`, was created by dividing horsepower by curb weight.

### **2. Feature Scaling**
- The features were scaled using `StandardScaler` for better model performance.

### **3. Model Building and Evaluation**
- Various regression models were applied to predict car prices:
  - **Linear Regression**
  - **Random Forest Regressor**
  - **Gradient Boosting Regressor**
  - **Support Vector Regressor (SVR)**
  - **K-Nearest Neighbors (KNN)**
  - **Decision Tree Regressor**
  - **Ridge Regression**
  - **Lasso Regression**
  - **AdaBoost Regressor**
- Each model's performance was evaluated using **Mean Squared Error (MSE)** and **R² score**.

### **4. Model Performance**
- The best performing model was selected based on the **R² score**, and its predictions were used to estimate car prices.

### **5. Results**
- The final model's predictions were compared with actual prices, and a DataFrame displaying the actual and predicted values, along with the difference, was created.

## **How to Run the Project**

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/car-price-prediction.git
    cd car-price-prediction
    ```

2. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Download the dataset and place it in the project directory.

4. Run the script:

    ```bash
    python car_price_prediction.py
    ```

## **Expected Output**
The script will output the evaluation results of each model, and the best model will be chosen. It will also display a DataFrame with the actual and predicted car prices.

## **Results**

Here is a sample output of the results:

| **Actual Value** | **Predicted Value** | **Difference** |
|-------------------|---------------------|----------------|
| 25000             | 24500               | -500           |
| 35000             | 36000               | 1000           |
| 20000             | 19000               | -1000          |

## **License**
None
