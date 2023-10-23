## Google Data Analytics Capstone - Cyclistic Case Study 

### Introduction 
Cyclistic is a bike-share company in Chicago, where customers can use one of 5,824 bicycles around a network of 692 stations across the city. Cyclistic tries to reach a broader audience with flexibility in pricing and having a variety of different bikes. The company offers single-ride passes, full-day passes, and annual memberships. The director of marketing believes that the company's future lies in the annual memberships, for the finance analysts concluded that annual members are more profitable than casual riders (those who use single-ride or full-day passes).  

### Ask 
The director of marketing wants the following question to be answered:

*How do annual members and casual riders use Cyclistic bikes differently?*

By answering this question, new marketing strategies can be implemented to maximize the number of annual members. 

### Prepare
To think about what can be done in the future, the past should be reflected on first. Cyclistic's historical trip data is used in this project to identify trends and patterns between how casual riders and annual members use bikes. Cyclistic's data, which is public, can be found at https://divvy-tripdata.s3.amazonaws.com/index.html . This data is deemed reliable and relevant for this project. To reach a non-outdated conclusion, the most recent year of data (August 2022 - July 2023) was used. After this data was downloaded, it can be cleaned, sorted, and filtered using R Studio. 

### Process 
RStudio was used to clean, sort, and filter the data for this study. SQL and Excel could have also been used, but for the sake of ease, RStudio was the move. 

#### Importing the Data 
Importing the data was a very smooth process. Using readcsv, each csv file for the months were loaded into RStudio. The data type for the columns started_at and ended_at had to be changed from doubles to DateTime with the format %Y-%m-%d %H:%M:%S. All of the monthly tables had the same 13 columns: *ride_id*, *rideable_type*, *started_at*, *ended_at*, *start_station_name*, *start_station_id*, *end_station_name*, *end_station_id*, *start_lat*, *start_lng*, *end_lat*, *end_lng*, and *member_casual*. Because the columns were uniform throughout all 12 of the monthly tables, rbind was used to simply add all of the tables into one big yearly table. 

#### Cleaning the Data
The columns *ride_id*, *start_station_id*, *end_station_id*, *start_lat*, *start_lng*, *end_lat*, and *end_lng* were removed from the yearly table because these columns were extraneous information, and would not prove helpful for the purposes of this case study. Then, using the dates from the started_at column, each aspect of the date was made into its own column to help with finding trends. At this point, there were 11 columns: *rideable_type*, *started_at*, *ended_at*, *start_station_name*, *end_station_name*, *member_casual*, *date*, *month*, *day*, *year*, and *day_of_week*. Using the *started_at* and *ended_at* columns, a new column *ride_length* was created, with the unit being minutes. After that, the bad data was removed. This included ride lengths which were negative (which shouldn't be possible), trips with the *start_station_name* HQ QR, as those were quality checked bikes, rows of data in which there were empty pieces of data, and duplicate data. After that, the data was good to analyze. 

### Analyze
To get a better sense of how the cleaned data looks, aggregated charts were made to get quick snapshots of how the data looks. 

<img width="627" alt="Screenshot 2023-10-22 at 9 03 06 PM" src="https://github.com/imyrie/Cyclistic/assets/97645125/84422760-6f7d-449f-ac9e-63bc89bd341b">

Median Ride Lengths by Payment Plan 

<img width="616" alt="Screenshot 2023-10-22 at 9 03 26 PM" src="https://github.com/imyrie/Cyclistic/assets/97645125/a2c61923-57e7-4702-8168-55e848c054fe">

Average Ride Length by Payment Plan 

<img width="829" alt="Screenshot 2023-10-22 at 9 03 44 PM" src="https://github.com/imyrie/Cyclistic/assets/97645125/1dbd557d-046e-4a8e-a1b7-faa1b539e48e">

Average Ride Length by Weekday, Separated by Payment Plan 

<img width="789" alt="Screenshot 2023-10-22 at 9 04 48 PM" src="https://github.com/imyrie/Cyclistic/assets/97645125/ef3e1bdf-aad6-4f67-ab0a-44acc2f4c3a6">

Average Ride Length by Month, Separated by Month 

<img width="971" alt="Screenshot 2023-10-23 at 12 14 29 AM" src="https://github.com/imyrie/Cyclistic/assets/97645125/23e76d47-fa35-4a98-ae8e-32f3570fac2a">

<img width="855" alt="Screenshot 2023-10-23 at 12 22 50 AM" src="https://github.com/imyrie/Cyclistic/assets/97645125/07577b8b-7a4a-4886-8abc-62dae9946a6b">

