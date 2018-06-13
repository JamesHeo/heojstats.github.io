---
title: "The Trend of New York City Cabs, Year of 2017"
date : 2018-06-13
tags: [Time Series]
#header:
#  image: "/images/NYCTaxi.jpg"
excerpt: "Time Series, NYC Taxi Caps, Data Science, R Shiny, User-Friendly Dashboards, Data Visualization"
---



## Introduction
New York City is one of the most popular and famous city in the US. When a person visits the US, it might be a must place to go. It indicates that since there is a lot of travelers in the city, there must be high number of taxis in the city. In this project, it simply shows the trend of taxi trips: number of trips and taxi duration. It is built in shiny application format which gives users an ability to choose pick up and drop off locations along with month and day of the week.

<br>

## Data Overview
* Year of 2017 dataset for both green and yellow taxis, provided by the City of New York
* Over 200 million data observations


## Data Manipulation
* Since the entire dataset is large, the dataset is aggregated to the maximum level to build the plots to increase the loading speed for the application
* The date column includes year, month, day, and time. It was necessary to separate the date column in order to aggregate the data accordingly
* There are some NA values and observations that showed as abnormal. NA values are deleted and 95 quantile observations are selected


ShinyApp: [link](https://heojstats.shinyapps.io/nyc_taxi_cab_app/)
