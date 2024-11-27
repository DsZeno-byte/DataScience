## **Project Summary**

<p align="center"> 
<img src="https://i.pinimg.com/originals/25/05/16/25051662be929d78194985190aeee50a.gif"  width="600" height="400" alt="GIF">
</p>

## <ins>Introduction</ins>
     Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is 
     important to make the rental bike available and accessible to the public at the right time as it lessens the
     waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern.
     The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.
## <ins>Dataset</ins>
     The dataset contains weather information Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, 
     Snowfall, Rainfall, the number of bikes rented per hour and date information.
     
     Attribute Information:
     Date : year-month-day
     Rented Bike count - Count of bikes rented at each hour.
     Hour - Hour of the day
     Temperature-Temperature in Celsius
     Humidity - %
     Windspeed - m/s
     Visibility - 10m
     Dew point temperature - Celsius
     Solar radiation - MJ/m2
     Rainfall - mm
     Snowfall - cm
     Seasons - Winter, Spring, Summer, Autumn
     Holiday - Holiday/No holiday
     Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)
## <ins>Data Cleaning and Data Preprocessing</ins>
     [1] Handling Duplicate Values
     - Dataset having 0 duplicated values.
     [2] Handling Null / Missing Values
     - Dataset having 0 null values.
     [3] Removing Outliers
     - Interquartile Range in the skew symmetric curve used to remove outliers found in the Rented Bike Count, Wind speed (m/s) and Solar Radiation (MJ/m2) variables.
     [3] Data Wrangling and Feature Engineering
     - The variables day, month, and year were created from the variable Date, and the original variables deleted.
     - Datatype of the variable Date was transformed from object datatype to datetime64.
     [4] Confirming Presumptions
     - Using log and square root transformation, the distribution of the features Rented Bike Count, Wind speed (m/s), Solar Radiation (MJ/m2), Visibility (10 m), Rainfall (mm), and Snowfall (cm) was returned to normal.
     - All numerical variables are correlated with the dependent variable Rented Bike Count, but Solar Radiation (MJ/m2), Dew Point Temperature (°C) and Temperature (°C) are highly correlated with the dependent variable, which is good for a linear machine learning model.
     - From above, variables 'year','Dew point temperature(°C)', and 'Humidity(%)' have a high variance inflation factor, so we can remove them to reduce VIF
     [5] Features encoding
     - Label encoding used to encoding variables Seasons, Holiday, and Functional Day.
     [6] Data Scaling
     - MinMaxScaler preserves the shape of the original distribution. It doesn't meaningfully change the information embedded in the original data. So we used MinMaxScaler for scaling the dataset.


1. **Dataset Overview**:
   - The dataset consists of **8760 rows and 14 columns** after initial inspection.
   - It includes weather conditions, temporal information, and bike rental counts to predict hourly bike demand.

2. **Categorical Variables**:
   - There are three categorical variables: **Seasons, Holiday, and Functioning Day**.
   - These variables provide insights into the temporal and functional context influencing bike rentals.

3. **Numerical Variables**:
   - There are **11 numerical variables**, including dependent and independent features such as "Rented Bike Count," "Temperature," and weather conditions.
   - The "Date" column was converted to a datetime format for further processing.

4. **Data Quality**:
   - The dataset contains **no missing or null values**.
   - Duplicate rows were **not present**, indicating clean data.

5. **Outliers**:
   - Outliers were detected in **Rented Bike Count, Wind Speed, and Solar Radiation**.
   - Outlier treatment was performed using the **Interquartile Range (IQR)** method, ensuring extreme values do not skew the model's performance.

6. **Irrelevant Variables**:
   - Columns like **Rainfall** and **Snowfall** were excluded due to their minimal variance and flat interquartile ranges, making them non-informative for predictive modeling.

7. **Next Steps**:
   - Proceed to feature engineering, exploratory data analysis (EDA), and model training.
   - Investigate feature importance and potential relationships between variables to improve prediction accuracy.
   