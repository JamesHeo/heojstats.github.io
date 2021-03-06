---
title: "The Trend of New York City Cabs, Year of 2017"
date : 2018-06-13
tags: [Time Series]
#header:
#  image: "/images/NYCTaxi.jpg"
excerpt: "Time Series, NYC Taxi Caps, Data Science, R Shiny, User-Friendly Dashboards, Data Visualization"

---
<img src="{{ site.url }}{{ site.baseurl }}/images/NYCTaxi.jpg" alt="NYC with taxi">

### Introduction
<small>The goal of this project is to find several taxi trip trends in the city of New York in 2017: number of trips and trip duration. It is built in shiny application format which gives users an ability to choose pick up and drop off locations along with month and day of the week. It also includes a few static visualizations for more details.</small>


### Data Overview
<small>Year of 2017 dataset for both green and yellow taxis, provided by the City of New York.</small><br>
<small>Over 200 million data observations.</small><br>

### Data Manipulation
<small>The date column includes year, month, day, and time. It is necessary to separate the date column in order to aggregate the data accordingly.</small><br>
<small>There are some NA values and observations. NA values are deleted and 95 quantile observations are selected.</small><br>
<small>Beforehand, the dataset is aggregated to the maximum level to increase the loading speed for the application. The dataset is dropped down to 263 observations.</small><br>

### Hourly Trend
<small>To look at the plots, please click the link provided below.</small><br>
<small>Please wait until the pickup and dropoff selections pop up.</small><br>
<small>Please click the submit button.</small><br>

[ShinyApp](https://heojstats.shinyapps.io/nyc_taxi_cab_app/)
<br>
<small>JFK airport is selected as a pickup location and times square is selected as a dropoff location to give an example insight. In general, the trend of the average trip duration follows the trend of number of trips. It indicates that, when there is a high traffic, the average trip duration increases. Additionally, the line plot shows that the average trip duration is the highest between 7AM and 8AM which is the morning rush hour. The number of taxi trip is relatively high in the afternoon.</small>

<small>Please, feel free to play with the app.</small>

### Close look of December 2017 Data
![alt]({{ site.url }}{{ site.baseurl }}/images/NYCTaxi/LineChart.png)
<small>The line chart above shows the hourly trend of the taxi trip in New York City in December 2017. It shows that the number of taxi trips rapidly increases during the morning rush hour: between 7AM and 9AM. There are more customers who pay with their credit cards in the morning. On the other hand, there are more customers who pay with cash in the afternoon. The taxi trips increases and reaches the peak at 6PM. The number of taxi trips keep decreasing until 5AM.</small>

<img src="{{ site.url }}{{ site.baseurl }}/images/NYCTaxi/BarChart.png" alt="bar chart">
<small>The bar chart above shows the daily trend of the taxi trip in New York City in December 2017. It shows that the number of the taxi trip is high on Fridays and Saturdays. However, the number is low when it is Sunday or during the holiday season.</small>

### For more insights
<small>We have found that from December 2017 data that there are relatively more number of taxi trips on Fridays and Saturdays between 5:00PM and 7:00PM. Based on my personal experience when I was traveling, I have talked to few Uber drivers and a lot of them drive as their second job. Here, I would like to get some more insights for them so that they can spend their limited driving time more efficiently. The trend indicates that it is more efficient to drive on Fridays and Saturdays at between 5:00PM and 7:00PM. I have wrote a basic SQL query to answer a business question: Under the circumstance, which area shows the highest number of pick-ups?</small>

```r
sqldf("
SELECT pu_zone as 'Pick Up Zone' , SUM(trip_count_tot) as 'Number of Trips'
FROM new_combined
WHERE month = 'Dec'
and day in ('Fri','Sat')
and hr in (17,18,19)
GROUP BY pu_zone
ORDER BY 2 desc
      ")
```

<small>The result table shows that "upper east side north and south" in New York City Area has the highest number of pick-ups on Friday and Saturdays between 5:00PM and 7:00PM in December 2017. This insight would be significantly helpful for taxi or Uber drivers who would like to make their driving time more efficient.</small>

<img src="{{ site.url }}{{ site.baseurl }}/images/NYCTaxi/num_trips.jpg" alt="tripsummary">
