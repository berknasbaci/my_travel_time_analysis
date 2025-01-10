# my_travel_time_analysis
## **Project Idea**
In this project, I will analyze how departure time and weather conditions impact the travel time between my home and campus, and how these factors together influence my stress levels. My goal is to maintain a positive mood by achieving better time management as a result of this analysis. Weather and departure time will have a considerable impact on travel time. In particular, rush hour and bad weather might significantly prolong travel time, potentially causing increased stress levels during the trip.


## **Description of Dataset**
-**Total duration of each trip**: I will record the travel time between home and campus using the data provided by Google Maps under “My Timeline”.

-**Stress levels**: I will track my stress levels by checking my mood before and after each trip using the Health Monitor app on my Samsung device. This will help to assess how stress levels correlate with the travel experience between my home and campus.

-**Route**: Recording the departure point(campus/home) and the arrival point(home/campus). 

-**Weather**: Weather information of that day will be gathered for each journey by OpenWeatherMap API.

-**Departure time**: The exact time of my departure to analyze its effect on the duration of the trip.

-**Day of the week including the date**: Information to distinguish whether the journey happened on a weekday or weekend.

## **Plan** 
#### **Data Collection** 
- Data will be collected throughout December, maintaining:
  	- A consistent route. 
	- The same vehicle. 
	- The same driver (myself). 
-  **Sources:**
  	- Travel time will be recorded from Google Maps under “My Timeline.” 
	- Weather data will be obtained using the OpenWeatherMap API. 
	- Stress levels will be monitored using the Samsung Health Monitor app. 
-  To ensure consistency and minimize bias:
  	- Information will be recorded immediately after each trip. 
	- Data will be systematically organized and accessible. 
	- Confounding variables and outliers will be carefully considered to ensure the accuracy and reliability of the analysis.
	





#### **Data Preparation and Analysis** 
- At the end of the data collection period: 
	- Data will be reviewed for completeness and consistency. 
- **Exploratory Data Analysis (EDA):** 
	- Trends will be identified using statistical methods and visualization techniques. 
- **Regression Analysis:** 
	- Statistical methods will be applied to investigate the impact of various factors such as departure time and weather on travel duration and stress levels.

# Report
## **Introduction**
The main objective of this project is to analyze the relationship between departure time, weather conditions, travel duration and stress levels for trips between home and campus. This study aims to determine how the factors which set to be both dependent and independent, influence stress levels before and after trip, as it is expected to improve time managament and reduce stress. Since patterns will be identified by it will be possible to make decisions to minimize both travel time and stress levels.

## **Hypothesis**
- Departure times during peak hours which are morning and evening commutes, correlate with longer travel durations.
- Unfavorable weather conditions such as rainy weathers increase travel duration and stress levels.
- Stress levels are higher after longer travel durations and or during unfavorable weather conditions.

 ## **Methods**
 #### **Data Collection** 

Throughout December 2024, data was collected using methods below:

	- Travel Duration: Recorded from Google Maps under "My Timeline"
 
 	- Stress Levels: Self-reported using Samsung Health Monitor app before and after each trip.
  
  	- Weather Data: At the beginning, intended to be collected via OpenWeatherMap API, instead it was manually recorded since subscription was needed to use OpenWeatherMap.
   
#### **Dataset** 
-**Date and day of the week**: Dates are recorded to assess everyday separately.

-**Route**: Recording the departure point(campus/home) and the arrival point(home/campus). 

-**Weather Condition**: Weather information of that day were gathered via manual logging technique.

-**Departure time**: The exact time of my departures were recored using the data provided by Google Maps under “My Timeline” to analyze its effect on the duration of the trip.

-**Total duration of each trip**: Travel time between home and campus will be recorded using the data provided by Google Maps under “My Timeline”.

-**Stress levels before and after the trip**: My stress levels were tracked by checking my mood before and after each trip using the Health Monitor app on my smart watch. This helped me assess how stress levels correlate with the travel experience between my home and campus.

-**Highest temperature and lowest temperature**: Highest temperature and lowest temperature on that day were recorded using weather forecast.


#### **Data Processing** 
- **Data Cleaning:**: 
	- Converted date and time into appropriate formats.
 
 - **Feature Engineering**: 
 	- New variable is created named "StressLevelDifference" to compute the difference between stress levels before and after the trip.
  	- DepartureTimeHour is extracted for time analysis.
   	- Applied one-hot encoding method to WeatherCondition and TimeCategory. WeatherCondition is separated into 4 groups: Cloudy, Rainy, Sunny, Partly Cloudy. TimeCategory is also seperated into 4 groups: Morning Commute, Work Hours, Evening Commute, Off Hours. 

#### **Visualization Techniques** 
- **Univariate Analysis:** 
	- Histogram for TravelDuration distribution.
 	- Boxplots for StressLevelBefore and StressLevelAfter.
  	- Count plot for WeatherCondition frequencies.

- **Bivariate Analysis:** 
 	-Scatter plots to analyze the relationship between departure time and travel duration.

- **Multivariate Analysis:**
	- Bar plots to study the interaction of day of the week, weather conditions, and stress levels.
 	- Correlation heatmap to explore relationships between variables.

  #### **Machine Learning Models**
  - **Regression Models**: 
  	- Linear Regression
   	- Ramdom Tree
      	- Decision Tree

## **Results of the analysis**
- **Univariate Analysis**
  	- **Travel Duration:**
  	  	- A histogram showed a right-skewed distribution, indicating a few trips with unusually long durations.
  	- **Stress Levels:**
  	  	- Boxplots showed higher stress levels after trips compared to before trips.
  	- **Weather Condition:**
  	  	- Count plots revealed that "Rainy" and "Cloudy" conditions were the most frequent weather types, however still this graph shpws us that variation in weather condition is enough to analyze the affect of weather condition.

- **Bivariate Analysis**
  	- **Departure Time and Travel Duration:**
  	  	- Scatter plots showed a clear increase in travel durations during peak hours which is said to be morning and evening commutes.
  	 
- **Multivariate Analysis**
  	- **Correlation Heatmap:**
  	  	- Strong Correlations:
  	  		- TravelDuration and StressLevelDifference : 0.79
  	  		- TravelDuration and StressLevelAfter : 0.6
  	- **Bar Plots:**
  	  	- Stress level rises were highhest on rainy days during morning and evening commutes.
  	  	- Weekend trips were less stressful.
  	 
- **Machine Learning Results**
  	 
  |**Model**                |**Mean Squared Error(MSE)**   	|**R^2**      |
  |-------------------------|-----------------------------------|-------------|
  |Linear Regression        | 0.26 				| 0.62        |
  |Decision Tree	    | 0.38 				| 0.43        |
  |Linear Regression        | 0.30 				| 0.56        |

	- **Linear Regression** model is the best model to use as R^2 is 0.62 which is satisfactory for a project data that as we have limited data.
   
## **Findings**
- Departure Time:
 	- Morning and evening commutes significantly increased travel duration.
   	- Trips during off-hours were quicker and less stressful.
- Weather Conditions:
  	- Rainy conditions were associated with longer travel times and higher stress levels.
	- Sunny and partly cloudy conditions had minimal impact on travel duration or stress.
- Stress Levels:
   	- Longer travel durations and rainy conditions consistently increased stress levels.
  	- Stress level differences were highest during the evening commute on rainy days.

## **Limitations**
- Weather Data:
 	- Intended to get from OpenWeatherMap API, however it required a subscription, so weather data was manually recorded.
   
- Sample Size: 

  	- Since we had a limited amount of time to get data, the dataset was limited to one month of data, reducing the ability to generalize findings.

## **Future Work**
- Adding automated weather data collection using APIs.
 
- Collect data over multiple months for improved generalizability.
  
- Explore additional features such as traffic density and exact route details.


## **Conclusion**
This study shows the significant impact of weather conditions and and departure time on travel duration and stress levels as travel durations affect stress levels.
	- Peak hours which are set to be the commute times and rainy weather conditions.

The project highlights the significance of analyzing personal travel data to make data-informed decisions for better time management and stress management. As we expand the dataset and improve how we gather information, future research can provide more about what shapes our day-to-day travel experiences.


  
  	  	 
  	  

  

 


     



    
   
