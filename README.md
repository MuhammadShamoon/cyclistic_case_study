# Cyclistic Customer Analysis

### Project Overview

In this case study, we will work for Cyclistic, a fictional bike-share company in Chicago. The customers who purchase single-ride or full-day passes are called casual riders and customers who purchase annual memberships are Cyclistic annual members. The marketing director believes the company’s future success depends on maximizing the number of annual memberships. He has set a clear goal to Design marketing strategies to convert casual riders into annual members. However, the marketing analyst team needs to understand better how annual members and casual riders differ.

### Data Sources

Cyclistic’s historical trip data: The primary dataset used for this analysis is the "Divvy_Trips_2020_Q1.csv" file, made available by Motivate International Inc. to analyze and identify trends within one quarter of a year. This public data can be used to explore how different customer types are using Cyclistic bikes.

### Tools

- Excel - Data cleaning
- BigQuery - Data analysis
- Tableau - Creating visualizations

### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:
- Data loading and inspection.
- Added Column “trip_length_min” to track the duration of each ride in minutes.
- Added Column “day_of_week” to analyze customers' behaviour on weekdays and weekends. 
- Handling missing values.
- Data cleaning and formatting.

### Data Analysis

- Following SQL code investigate the number of rides across each day in a week for both categories of users.

```sql
SELECT 
  member_casual
  ,day_of_week
  ,COUNT(ride_id) AS ride_count

FROM 
  `casestudy-416218.bike_share.Q1` 

GROUP BY
  member_casual
  ,day_of_week

ORDER BY 
  day_of_week
  ,member_casual
```

- Following SQL code helps to explore when most users use bikes during the day.

```sql
SELECT  
  FORMAT_DATETIME('%H',started_at) AS start_time
  ,member_casual
  ,COUNT(ride_id) AS ride_count

FROM 
  `casestudy-416218.bike_share.Q1` 
  
GROUP BY 
  start_time
  ,member_casual  

ORDER BY 
  member_casual 
  ,start_time
```

### Results

The analysis results are summarized as follows:

1. The average trip length of casual riders is approximately four times of annual members.

![trip length comparison](https://github.com/MuhammadShamoon/cyclistic_case_study/assets/52103515/cf941372-5a5a-4891-92f0-808945ca85f8)

2. During weekends, the annual members use bikes from afternoon to evening, but during weekdays they mostly use them at 8 am and 5 pm to commute to work.

![Annual members](https://github.com/MuhammadShamoon/cyclistic_case_study/assets/52103515/9ed02246-bd2d-40bc-ab4a-ce18b9bd704b)

3. The number of Casual riders reached its peak value around 2 pm and performed a bell-shaped pattern. They are more likely to ride for leisure.

![Casual Riders Population](https://github.com/MuhammadShamoon/cyclistic_case_study/assets/52103515/154e52dd-ef2e-40d4-8ead-83b337f44604)

### Recommendations

Based on the analysis, we recommend the following actions:

-
-
-

### Limitations



