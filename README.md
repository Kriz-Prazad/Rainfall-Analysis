# Rainfall-Analysis
### This project analyzes a historical weather dataset for various stations across India to understand the key patterns and drivers of rainfall. The analysis explores rainfall based on time (season, month), location (state, elevation), and relationships with other meteorological factors like temperature, air pressure, and wind speed.

#### Tools used
#### - Python, Jupyter notebook

<Details>
<summary>About the Data </summary>

#### This dataset consists of daily weather and geographical data for 458 weather stations across India over a span of more than 10 years, specifically from January 1, 2015, to February 10, 2025.

#### The dataset contain 970k+ records and includes the following features, crucial for building an accurate rainfall forecasting model:



---

###  **Weather and Climate Data Fields Explained**

| **Field**         | **Description** |
|------------------|-----------------|
| **date_of_record** | The specific calendar date when the weather data was recorded. |
| **month**          | The month of the year corresponding to the record. Useful for seasonal analysis. |
| **season**         | The meteorological or regional season (e.g., `Winter`, `Monsoon`, `Summer`). May vary by geography. |
| **station_name**   | The name of the weather station that collected the data. |
| **state**          | The state or province where the station is location. |
| **district**       | The administrative district within the state. |
| **avg_temp**       | The average temperature recorded on that day, typically in degrees Celsius. |
| **min_temp**       | The minimum temperature observed during the day. |
| **max_temp**       | The maximum temperature observed during the day. |
| **wind_speed**     | The average wind speed, usually measured in kilometers per hour (km/h) or meters per second (m/s). |
| **air_pressure**   | Atmospheric pressure at the station, typically in hectopascals (hPa) or millibars. |
| **elevation**      | The height of the station above sea level, usually in meters. Affects temperature and pressure readings. |
| **latitude**       | Geographic coordinate specifying north-south position . |
| **longitude**      | Geographic coordinate specifying east-west position. |
| **rainfall**       | Total precipitation recorded on that day, usually in millimeters (mm). |

---

</Details>

---

<details>
<summary>Preprocessing the data</summary>

### The percentage of null values are as follows:
---
* min_temp has 4.52% null value
* max_temp has 11.40% null values
* wind_speed has 28.28% null values
* air_pressure has 31.40% null values
* rainfall has 26.54% null values
---
We have to find a strategy to fill the null values. 
Since the **District** is not having null values, we can use it as a unique value to group and fill null values accordingly. 
But the data is prone to be inconsistent if we use only district name, because climate is different in different months / seasons. 
So we have to group the data with **District** and **Month**. We can fill the mean value at the null's place
  
- Group the dataset based on district,station name and month, then we have to find the mean to fill the null values
  
</details>

---

<details>
  <summary>
    The Data Analysis strategy/ Problem definition in this dataset
  </summary>
--- 

## 1. Time Series Analysis (Rainfall Over Time)
-	which month has the highest average rainfall
-	How does the frequency of rainy days in differs in different seasons (e.g., days with rainfall > 1 mm)?
-	Frequency of rainy days in each month (days with rainfall > 1 mm)
-	What is the average rainfall for each specific year in the dataset? Is there a noticeable upward or downward trend?
## 2. Geographical Analysis (Rainfall in Space) 
-	 Which are the top 5 states that has the highest average daily rainfall across all its stations? 
-	Which are the top 5 unique stations that has the most "rainy days" (days with rainfall > 1 mm) in a single year? 
-	 Is there a clear relationship between latitude and average rainfall? 
-	Which are the top 10 states that exhibits the most extreme rainfall events (rainfall > 100 mm)?
-	What is the average rainfall for stations above 1000m elevation compared to those below 100m?
-	the elevation of place with highest rainfall (top 10)

## 3. Distribution Analysis (Rainfall Frequency) 
-	 What percentage of all recorded that days had zero rainfall?
-	What percentage of the total, cumulative rainfall in the dataset comes from days with over 50 mm of rain?
-	Ignoring days with no rain, what is the most common range of rainfall (e.g., 1-10 mm, 10-20 mm, etc.)?
## 4. Correlative Analysis (Rainfall vs. Other Weather) 
-	What is the average air_pressure on days with heavy rain (> 50 mm) compared to dry days (0 mm)?
-	Is higher rainfall associated with a larger daily temperature range (max_temp - min_temp)?
-	 What is the maximum,minimum and average wind_speed during the top 5% of rainfall events?
-	Is there a specific avg_temp range where rainfall is most likely to occur?
-	How does the correlation between rainfall and air_pressure,windspeed and elevation differ between different seasons?
-	how does the correlation between rainfall and avg_temp,min_temp,max_temp differ between different seasons?
---
</details>
