---
title: "The Trend of New York City Cabs, Year of 2017"
date : 2018-06-13
tags: [Time Series]
#header:
#  image: "/images/NYCTaxi.jpg"
excerpt: "Time Series, NYC Taxi Caps, Data Science, R Shiny, User-Friendly Dashboards, Data Visualization"
---
<img src="{{ site.url }}{{ site.baseurl }}/images/NYCTaxi.jpg" alt="linearly separable data">

## Introduction
The goal of this project is to find several taxi trip trends in the city of New York in 2017: number of trips and trip duration. It is built in shiny application format which gives users an ability to choose pick up and drop off locations along with month and day of the week.

## Data Overview
* Year of 2017 dataset for both green and yellow taxis, provided by the City of New York
* Over 200 million data observations

## Data Manipulation
* The dataset is aggregated to the maximum level to build the plots to increase the loading speed for the application
* The date column includes year, month, day, and time. It was necessary to separate the date column in order to aggregate the data accordingly
* There are some NA values and observations. NA values are deleted and 95 quantile observations are selected

# ShinyApp
[link](https://heojstats.shinyapps.io/nyc_taxi_cab_app/)
