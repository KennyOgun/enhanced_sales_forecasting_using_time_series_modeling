# Enhanced Sales Forecasting Using Time Series Modeling

<img width="577" alt="image" src="https://github.com/user-attachments/assets/64a537ac-6405-4521-90a6-b321c9d0dd51" />

# Project Overview

This repository contains the complete workflow, analysis, and results of forecasting sales using time series models. The project leverages advanced statistical techniques and machine learning models to predict future sales and support strategic decision-making in the industry.  

# Business Introduction:

The focal company is a renowned 'Video Game Developer and Re-Saler', offering a diverse catalog of games and accessories. Known for its innovative gaming experiences, the company has won multiple industry awards. Its unique selling proposition lies in its customer-centric approach, ensuring high-quality products and engaging marketing campaigns. With strong online presence, the company has established itself as a leader in competitive gaming
market.

# Business Challenge:

The company faces difficulty in aligning its inventory with fluctuating customer demand. An overestimation of demand results in excessive inventory holding costs, while underestimation leads to lost sales opportunities and dissatisfied customers.

Specific Obstacles:
1. Seasonal Demand: Sales spikes during holidays and game releases.
2. Market Competition: Rapid shifts in customer preferences due to competing products.
3. Inventory Costs: High storage costs and potential write-offs for unsold inventory.
4. Uncertainty: Variability in customer behavior and external factors (e.g., economic conditions).

# Project objectives

1. Build a time series forecasting model to predict monthly sales for the next four months.
2. Reduce inventory holding costs by improving demand forecasts.
3. Increase customer satisfaction by minimizing stockouts and overstock scenarios.
4. Provide actionable insights for supply chain and marketing teams.
5. Create a scalable solution for ongoing sales forecasting.


# 📊 Data Description

The dataset has 264 rows and 8 features and include:

● Month: Monthly sales timestamps.

● Monthly Sales: The total sales for the month in units or revenue.

● Product Categories: The genre of the video game (e.g., RPG, FPS, Adventure)

● Year: Year of Sales.

● Holiday: A binary indicator (1/0) representing whether the month includes major holidays(December/January)

● Promotion: A binary indicator (1/0) representing whether a promotion was active during the month.

● Platform: The platform the game was sold on (e.g., PC,PlayStation, Xbox).

● DayOfWeek: The day of the week for the recorded month.

## 🛠️ **Design Methodology**  

1. **Exploratory Data Analysis (EDA)**: Visualizations and statistical summaries.  
2. **Data Stationarity Checks**: Applied ADF and KPSS tests to ensure suitability for time series models.  
3. **Model Development**: Built and evaluated ARIMA, ETS, and FB Prophet models.  


## Data Preprocessing & Exploratory Data Analysis (EDA)

### Data Preprocessing 

The dataset had no missing or duplicate values, ensuring reliability in analysis.

### Exploratory Data Analysis (EDA)

**1.0 Category By Platform Sales**

<img width="539" alt="image" src="https://github.com/user-attachments/assets/ccdd3a2f-51de-4e95-95a8-97806c90e329" />

Comments:
  * Highest Sales by Category and Platform: For the "Sports" category, the Nintendo platform has the 
    highest sales, followed closely by the Xbox platform.

  * Second-Highest Sales by Category and Platform: In the "RPG" category, Xbox records the highest sales, followed by the Nintendo platform.

  * Third-Highest Sales by Category and Platform:

       * For the "Simulation" category, both Nintendo and Xbox have the highest sales.

       * For the "Adventure" category, PlayStation and Xbox lead in sales.

**2. Overall Sales Trend**

<img width="546" alt="image" src="https://github.com/user-attachments/assets/757fe5e4-8832-4217-8967-c6292948a747" />

As evident in the chart above, the business suffered a major drop in sales in 2008 and 2016 but shows a cumulative sales increase recording its highest sales in 2015.

# Data Stationality and Seasonality Check

To determine whether the data is suitable to use for time series models, these methods can be perform:

   * Visual Inspection
   * Global vs Local Check
   * ADG(Augmented Dickney Fuller) Test -Statistical Tests
   * KPPS Test - Statistical Test


<img width="568" alt="image" src="https://github.com/user-attachments/assets/f3c33d6e-5a9b-4b38-8158-f8c4ba91598f" />


Based on the the ADF and KPSS test Result, the data is stationary. 

# 🤖 Model Building

Three models were implemented and trained on the dataset:

1.**ARIMA (Auto-Regressive Integrated Moving Average):** Captures trends, seasonality, and noise through a combination of auto-regression and moving average techniques. 

2.**ETS (Exponential Smoothing):** Ideal for data with clear seasonal patterns. The additive seasonal method was selected due to the monthly sales periodicity.

3.**FB Prophet:** Utilizes robust trend and seasonality modeling, designed for irregular time series data. Its flexibility in handling external regressors (like holidays and promotions) was an advantage.

# Evaluation Metrics and Results

- **RMSE (Root Mean Squared Error)**: Evaluates overall prediction accuracy.
  
- **MAE (Mean Absolute Error)**: Measures average error in predictions.
  

| **Model**      | **RMSE**       | **MAE**        |  
|-----------------|----------------|----------------|  
| **ARIMA**      | 28,417.86      | 25,671.61      |  
| **FB Prophet** | 33,386.69      | 28,144.94      |  
| **ETS**        | 42,299.89      | 38,481.15      | 

Best Model:

**ARIMA** achieved the lowest RMSE and MAE, making it the most accurate model for forecasting future sales.


# 📅 Final Forecast Results

Using ARIMA, the forecasted sales for **January-April 2024** are as follows:  

<img width="557" alt="image" src="https://github.com/user-attachments/assets/a96c990f-f3f9-4368-95d2-d1edb1982940" />


    | **Date**       | **Forecast** |  
    |-----------------|--------------|  
    | 2024-01-01     | 116,317.28   |  
    | 2024-02-01     | 116,682.89   |  
    | 2024-03-01     | 113,380.77   |  
    | 2024-04-01     | 115,998.18   | 


# 🧠 **Conclusion and Recommendations**

This project demonstrates how robust time series models can accurately forecast sales, helping businesses make informed decisions.  Based on the EDA findings and the ARIMA forecast for January to April 2024, here are targeted recommendations to address the company's goals:

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
 * Include external features like game launches, global events, and marketing campaigns to refine forecasts.  
 *  Explore additional machine learning models such as XGBoost or LSTM for improved accuracy.  



## 🚀 **How to Use This Repository**  

### **Tools and Libraries**  
- **Python Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, scikit-learn, FB Prophet.  
- **Time Series Modeling**: ARIMA, Exponential Smoothing, and FB Prophet.  
- **Visualization**: Matplotlib and Seaborn for trend analysis and insights.  


1. Clone the repository:  
   ```bash
   git clone https://github.com/YourUsername/VideoGameSalesForecasting.git

2. pip install -r requirements.txt
3. Explore the notebooks and run models to experiment with forecasts.

