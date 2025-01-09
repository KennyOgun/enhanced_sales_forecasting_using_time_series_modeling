# 🎮 Video Game Sales Forecasting Analysis  

Welcome to the **Video Game Sales Forecasting** project! This repository contains the complete workflow, analysis, and results of forecasting monthly video game sales 
using time series models. The project leverages advanced statistical techniques and machine learning models to predict future sales and support strategic decision-making
in the video game industry.  

---

## 📊 **Data Overview**  
The dataset includes 264 rows and 8 features, spanning video game sales data from **January 2002 to December 2023**.  

### **Features**  
- **Category**: Game genres (e.g., Sports, RPG, Simulation).  
- **Monthly_Sales**: Units sold per month.  
- **Year**: Year of sales.  
- **Platform**: Gaming platforms (Xbox, Nintendo, PC, PlayStation).  
- **Additional Contextual Features**:  
  - **DayOfWeek**  
  - **Holiday**  
  - **Promotion**  
  - **Month_Name**  

### **Key Observations**  
- **No Missing or Duplicate Values**: Data is clean and reliable.  
- **Category Insights**: Sports games dominate the data, appearing 59 times.  
- **Platform Insights**: Xbox leads with 76 entries.  
- **Statistics for Monthly Sales**:  
  - **Mean**: 112,349  
  - **Std**: 34,144.61  
  - **Min**: 10,469 | **Max**: 206,596  
  - **Median**: 112,947.50  
  - **75th Percentile**: 135,193.50  

---

## 🛠️ **Design Methodology and Tools**  

### **Methodology**  
1. **Exploratory Data Analysis (EDA)**: Visualizations and statistical summaries.  
2. **Data Stationarity Checks**: Applied ADF and KPSS tests to ensure suitability for time series models.  
3. **Model Development**: Built and evaluated ARIMA, ETS, and FB Prophet models.  

### **Tools and Libraries**  
- **Python Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, scikit-learn, FB Prophet.  
- **Time Series Modeling**: ARIMA, Exponential Smoothing, and FB Prophet.  
- **Visualization**: Matplotlib and Seaborn for trend analysis and insights.  

---

## 🤖 **Model Selection, Training & Evaluation**  

### **Models Built**  
1. **ARIMA**: Auto-Regressive Integrated Moving Average for trend and seasonality modeling.  
2. **ETS (Exponential Smoothing)**: Captures seasonal patterns in data.  
3. **FB Prophet**: Handles trends, seasonality, and external regressors like holidays.  

### **Model Evaluation Metrics**  
- **RMSE (Root Mean Squared Error)**: Evaluates overall prediction accuracy.  
- **MAE (Mean Absolute Error)**: Measures average error in predictions.  

| **Model**      | **RMSE**       | **MAE**        |  
|-----------------|----------------|----------------|  
| **ARIMA**      | 28,417.86      | 25,671.61      |  
| **FB Prophet** | 33,386.69      | 28,144.94      |  
| **ETS**        | 42,299.89      | 38,481.15      |  

**Best Model**: **ARIMA** achieved the lowest RMSE and MAE, making it the most accurate model.  

---

## 📅 **Final Forecast Results**  

Using ARIMA, the forecasted sales for **January-April 2024** are as follows:  

| **Date**       | **Forecast** |  
|-----------------|--------------|  
| 2024-01-01     | 116,317.28   |  
| 2024-02-01     | 116,682.89   |  
| 2024-03-01     | 113,380.77   |  
| 2024-04-01     | 115,998.18   |  

---

## 🧠 **Conclusion nd Recommendations for the Video Game Company**

This project demonstrates how robust time series models can accurately forecast sales, helping businesses make informed decisions.  
Based on the EDA findings and the ARIMA forecast for January to April 2024, here are targeted recommendations to address the company's goals:

**1. Demand Forecasting & Inventory Optimization**

  * Adjust inventory planning: Ensure adequate inventory for the forecasted sales of approximately 115,000–116,000 units per month from January to February. Scale back inventory slightly in March (~113,000 units) and ramp up again in April (~116,000 units) to minimize holding costs.
    
  * Implement a dynamic inventory model: Use the ARIMA forecasts as a baseline and incorporate real-time updates to fine-tune inventory levels, reducing overstock and stockouts.

**2. Marketing & Promotional Strategies**

  * Targeted promotions: Focus holiday-season campaigns on Simulation, RPG, and Adventure games, with an emphasis on Xbox and Nintendo platforms.
   
  * Leverage weekend trends: Run weekend-exclusive promotions or discounts to capitalize on higher sales during this period.
    
  * Seasonal campaigns: Since sales historically dip from February to October, introduce mid-year promotional events or bundle deals to maintain customer engagement.

**3. Product Focus by Category and Platform**

  * Expand offerings in Sports: Since Sports games consistently drive sales, prioritize new releases or updates in this category across Nintendo and Xbox platforms.
    
  * Platform-specific promotions:
      Highlight RPG games for Xbox and Nintendo users.
      Promote Adventure games for PlayStation and Xbox users.
    
  * Balanced portfolio: Invest in diversifying content within Adventure and Simulation categories, as they perform well during specific periods.



### **Key Takeaways**  
1. **Best Model**: ARIMA was the most reliable model based on RMSE and MAE.  
2. **Data Stationarity**: Stationarity was confirmed, enabling accurate time series modeling.  
3. **Seasonality Patterns**: Strong seasonal trends were observed, significantly influencing sales forecasts.  

### **Future Work**  
- Include external features like game launches, global events, and marketing campaigns to refine forecasts.  
- Explore additional machine learning models such as XGBoost or LSTM for improved accuracy.  

---

---

## 🚀 **How to Use This Repository**  
1. Clone the repository:  
   ```bash
   git clone https://github.com/YourUsername/VideoGameSalesForecasting.git

2. pip install -r requirements.txt
3. Explore the notebooks and run models to experiment with forecasts.

