# Seoul Bike Sharing Demand Prediction - Advanced Modeling

## Project Overview

This project focuses on optimizing Seoul's bike-sharing system through advanced data analytics and predictive modeling. The goal is to address the challenge of fluctuating rental demand, enhance operational efficiency, improve user satisfaction, and promote sustainable urban mobility within the city. By leveraging data-driven insights, the system aims to ensure bike availability aligns with user needs, minimizing imbalances and maximizing resource utilization.

## Business Idea

The project is based on the idea of using predictive modeling to optimize the Seoul bike-sharing system. By accurately forecasting demand, the system can ensure that bikes are available where and when they are needed, improving user experience and resource allocation.

## Problem Statement

Bike-sharing systems face challenges in managing fluctuating demand due to factors like weather, time of day, seasons, and holidays. These fluctuations lead to inefficiencies in resource allocation, resulting in either overstocking or lack of bikes in high-demand areas. Accurate demand forecasting is critical for operational efficiency and customer satisfaction.

## SWOT Analysis

### Strengths
- Environmentally friendly.
- Cost-effective.
- Reduces traffic congestion.
- Promotes a healthy lifestyle.
- Aligns with Seoul's sustainability goals.

### Weaknesses
- High demand variability due to weather and seasonality.
- Potential inefficiencies in manual redistribution of bikes.

### Opportunities
- Growing environmental awareness.
- Leveraging data analytics and machine learning for resource optimization.
- Potential for mobile app integration to enhance user experience.

### Threats
- Competition from other micro-mobility options.
- Infrastructural limitations (e.g., weather, lack of bike lanes).
- Financial risks associated with advanced technology investments.

## Solution Approach & Recommendations

The project employs a combination of descriptive analytics to understand historical patterns and predictive modeling to forecast future demand. Key recommendations include:

- **Dynamic Resource Allocation:** Real-time redistribution of bikes based on predictive demand.
- **Weather-Sensitive Adjustments:** Adjusting bike availability based on weather conditions.
- **Technology Integration:** User engagement through mobile apps for real-time bike availability, reservations, and gamification.
- **User Feedback:** Continuous collection and analysis of user feedback for service improvement.

## Implementation Strategy

### Data Collection and Preprocessing
- Loaded the Seoul bike-sharing system dataset.
- Handled missing values and converted categorical variables to numerical.
- Extracted features like month, year, and day from the date column.
- Applied transformations (log1p, square root, cube root) to address skewness in numerical data.

### Descriptive Analysis
- Calculated basic statistics and visualized seasonal, monthly, and hourly rental trends.
- Analyzed the effects of weather variables on rental demand.
- Examined data distribution using histograms.
- Conducted specific analyses for seasonal variations, monthly trends, yearly changes, and the impact of holidays.
- Created a correlation matrix to analyze the impact of weather conditions on bike rentals.

### Feature Engineering
- Extracted month and day names from the date column and converted the date column to datetime format.
- Categorical features such as "Holiday, Seasons, Functioning_Day and Day_Name" were encoded.
- Removed unnecessary columns (e.g., 'Date', 'DPT').
- Identified high correlation between 'DPT' and 'Temperature', removed 'DPT' to avoid multicollinearity.
- Applied label encoding to categorical variables.
- Performed outlier analysis using boxplots.
- Transformed the target variable and windspeed column using square root and cube root transformations to approach normal distribution.

### Predictive Model Development
- Split the dataset into training and testing sets.
- Trained models: Linear Regression, Lasso Regression, Ridge Regression, Random Forest Regressor, and LightGBM (LGBM).
- Evaluated model performance using R² and RMSE.
- Implemented custom evaluation function for models, also calculates and prints Adjusted R².
- Visualized actual versus predicted values using a scatter plot.

## Results & Outcomes

### Model Performance
- **Linear Regression, Lasso, and Ridge:** R² values between 0.45 and 0.48, RMSE between 8.40 and 8.64
- **Random Forest Regressor:** Explained around 76% of the variance with an RMSE of 5.66.
- **LightGBM (LGBM):** Demonstrated the best performance, explaining 81% of the variance with the lowest RMSE of 5.12.

### Key Findings
- Summer and rush hours (5:00 PM - 7:00 PM) see peak bike rental demand.
- Bike rentals are significantly affected by weather conditions, with temperature and dew point temperature positively correlated to the number of rented bikes.
- Holiday bike rental is significantly lower than regular days and therefore requires special holiday planning.
- Monthly rental peaks are in May and June, dropping to a low in January.
- Significant usage increase was observed in 2018, compared to 2017.

## Follow-Up and Evaluation Plan

- **KPI Tracking:** Monitor bike utilization rates, user satisfaction scores, and operational efficiency metrics monthly.
- **User Feedback:** Collect feedback through surveys and mobile application reviews to identify areas for improvement.
- **Model Retraining:** Periodically retrain predictive models with updated data to maintain relevance and accuracy.
- **Annual Assessment:** Conduct an annual review to assess the impact of implemented strategies, address challenges, and plan further improvements.

## Conclusion

This project has developed a comprehensive framework for predicting bike-sharing demand in Seoul using data analysis, feature engineering, and predictive modeling. The insights and model outcomes will contribute to significant improvements in operational efficiency, customer satisfaction, and overall user experience of the bike-sharing system in Seoul. By using a data-driven approach, the system can ensure continuous improvement and long-term success.

## Repository Contents

- **`notebook.ipynb`**: Jupyter Notebook containing the complete data analysis, feature engineering, and modeling process.
- **`seoul_bike_sharing_demand_prediction.pdf`**: PDF version of the project report.
- **`data/`**: Directory containing the dataset used in the project (ensure the data file is uploaded).
- **`README.md`**: This file providing a project overview and instructions.

## Getting Started

1. Clone the repository to your local machine.
2. Install the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn lightgbm
