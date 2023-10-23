# Google Data Analytics Capstone - Cyclistic Case Study 

## Introduction 
Cyclistic is a bike-share company in Chicago, where customers can use one of 5,824 bicycles around a network of 692 stations across the city. Cyclistic tries to reach a broader audience with flexibility in pricing and having a variety of different bikes. The company offers single-ride passes, full-day passes, and annual memberships. The director of marketing believes that the company's future lies in the annual memberships, for the finance analysts concluded that annual members are more profitable than casual riders (those who use single-ride or full-day passes).  

## Ask 
The director of marketing wants the following question to be answered:

_How do annual members and casual riders use Cyclistic bikes differently? _

By answering this question, new marketing strategies can be implemented to maximize the number of annual members. 

## Prepare
To think about what can be done in the future, the past should be reflected on first. Cyclistic's historical trip data is used in this project to identify trends and patterns between how casual riders and annual members use bikes. Cyclistic's data, which is public, can be found at https://divvy-tripdata.s3.amazonaws.com/index.html . This data is deemed reliable and relevant for this project. To reach a non-outdated conclusion, the most recent year of data (August 2022 - July 2023) was used. After this data was downloaded, it can be cleaned, sorted, and filtered using R Studio. 

## Process 
RStudio was used to clean, sort, and filter the data for this study. SQL and Excel could have also been used, but for the sake of ease, RStudio was the move. 

### R Studio
#### Importing the Data 
Importing the data was a very smooth process. After unzipping the files, I went into RStudio and loaded readr. For each month, I used readcsv in order to load the csv files into RStudio, and I changed the data type for the columns started_at and ended_at from doubles to DateTime with the format %Y-%m-%d %H:%M:%S. Then, when I looked through the data for each month, I saw that they all had the same 13 columns: ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng, and member_casual. Because the columns were uniform throughout all 12 of the monthly datasets, I was able to use rbind to simply add all of the tables into one big yearly table. 
#### Cleaning the Data

