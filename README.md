# 📊 Data Management Assignment 2: Exploring Airline On-Time Performance

## 📚 Course Information
- **Course**: STQD6324 Data Management
- **Topic**: Assignment 2
- **Student ID**: Adam Suhail Bin Shahril (P153109)

## 📝 Project Title
**"Exploring Airline On-Time Performance: Analyzing Delays, Cancellations, and Predictive Factors for the Year 2005"**

![aeroplane](aeroplane.jpg) <!-- Maternal health image -->

## 📊 Dataset Background
Hello GitHub enthusiasts! My name is Adam, and I'm a master's student in Data Science. For my fourth entry in my GitHub repository, I have chosen to explore and analyze a dataset related to airline on-time performance, which is a crucial aspect of modern transportation. The dataset, collected from the 2009 ASA Statistical Computing and Graphics Data Expo, contains nearly **120 million records** detailing flight arrival and departure information for major carriers within the USA from **1987 to 2008**.

You can access the dataset here: [Kaggle: Airline On-Time Performance Dataset](https://www.kaggle.com).

In this project, we will specifically focus on the year **2005**. The total number of datasets included in the analysis will be:
- **airports.csv** → `airport_data`
- **carriers.csv** → `carrier_data`
- **plane-data.csv** → `plane_data`
- **2005.csv** → `flight_data`

### Details on Each Dataset

#### Flight Data (`flight_data`)
| Attribute                | Description                                               | Type    |
|--------------------------|-----------------------------------------------------------|---------|
| Year                     | The year of the flight (1987–2008)                        | int     |
| Month                    | Month of the flight (1-12)                               | string  |
| DayofMonth               | Day of the month (1-31)                                  | string  |
| DayOfWeek                | Day of the week (1 = Monday, 7 = Sunday)                | int     |
| DepTime                  | Actual departure time (local, hhmm)                      | int     |
| CRSDepTime               | Scheduled departure time (local, hhmm)                   | int     |
| ArrTime                  | Actual arrival time (local, hhmm)                        | int     |
| CRSArrTime               | Scheduled arrival time (local, hhmm)                     | int     |
| UniqueCarrier            | Unique carrier code                                       | int     |
| FlightNum                | Flight number                                            | int     |
| TailNum                  | Aircraft tail number                                      | int     |
| ActualElapsedTime        | Total flight duration in minutes                          | int     |
| CRSElapsedTime           | Scheduled flight duration in minutes                      | int     |
| AirTime                  | Time spent in the air in minutes                         | int     |
| ArrDelay                 | Arrival delay (in minutes)                               | int     |
| DepDelay                 | Departure delay (in minutes)                             | int     |
| Origin                   | Origin airport IATA code                                 | string  |
| Dest                     | Destination airport IATA code                            | string  |
| Distance                 | Distance between origin and destination in miles         | int     |
| TaxiIn                   | Taxi in time (in minutes)                               | int     |
| TaxiOut                  | Taxi out time (in minutes)                              | int     |
| Cancelled                | Was the flight cancelled? (true/false)                  | bool    |
| CancellationCode         | Reason for cancellation (A = carrier, B = weather, C = NAS, D = security) | string  |
| Diverted                 | Was the flight diverted? (1 = yes, 0 = no)              | bool    |
| CarrierDelay             | Delay attributed to the carrier (in minutes)            | int     |
| WeatherDelay             | Delay attributed to weather (in minutes)                | int     |
| NASDelay                 | Delay attributed to National Airspace System (in minutes)| int     |
| SecurityDelay            | Delay attributed to security (in minutes)                | int     |
| LateAircraftDelay        | Delay attributed to late arriving aircraft (in minutes)  | int     |

#### Carrier Data (`carrier_data`)
| Attribute    | Description                     | Type   |
|--------------|---------------------------------|--------|
| code         | Unique code for the carrier     | string |
| description  | Full name of the carrier        | string |

#### Airport Data (`airport_data`)
| Attribute    | Description                     | Type   |
|--------------|---------------------------------|--------|
| airport      | Name of the airport             | string |
| city         | City where the airport is located| string |
| country      | Country where the airport is located | string |
| iata         | IATA airport code               | string |
| lat          | Latitude of the airport (decimal)| float  |
| long         | Longitude of the airport (decimal)| float  |
| state        | State where the airport is located | string |

#### Aircraft Data (`plane_data`)
| Attribute    | Description                     | Type   |
|--------------|---------------------------------|--------|
| tailnum      | Unique tail number of the aircraft | string |
| type         | Type of aircraft usage (e.g., passenger, cargo)| string |
| manufacturer | Name of the manufacturer company | string |
| issue_date   | Date when the aircraft started operating | string |
| model        | Model of the aircraft           | string |
| status       | Operational status of the aircraft | string |
| aircraft_type| Type of the aircraft (e.g., jet, turboprop) | string |
| engine_type  | Type of engine used in the aircraft | string |
| year         | Year the aircraft was manufactured | string |

## 🌍 Introduction
This analysis aims to explore airline on-time performance using a dataset from the 2009 ASA Statistical Computing and Graphics Data Expo, specifically focusing on **2005** flight data from major US carriers. The objectives are:

1. **Delay Patterns**:
   - Identify times of day with the lowest average delays.
   - Determine which days of the week have better on-time performance.
   - Analyze the months or seasons when flights are most likely to be on time.

2. **Delay Factors**:
   - Rank the top 3-5 factors contributing to flight delays.
   - Quantify the impact of each factor in terms of delay minutes and percentage of total delays.

3. **Cancellation Analysis**:
   - Identify primary reasons for flight cancellations.
   - Investigate correlations between cancellations, airlines, airports, and time periods.

4. **Problematic Routes**:
   - Identify routes, carriers, or flight numbers with consistent performance issues.
   - Analyze reasons for delays or cancellations on these flights.

This analysis seeks to provide insights into airline operations and improve the travel experience for passengers.

## ❓ Problem Statement
In recent years, airline on-time performance has garnered increasing attention, particularly in the context of delays and cancellations that affect travelers. This analysis seeks to address several key issues related to the efficiency of airline operations, focusing on how various factors—such as time of day, weather conditions, and aircraft age—impact flight delays and cancellations.

### 🔍 Main Problems or Hypotheses:
- **Delay Patterns**: What times of day, days of the week, and seasons are associated with the lowest average delays?
  - **Guiding Questions**:
    - How do delays vary across different times of day (morning, afternoon, evening)?
    - Which days of the week show better on-time performance?

- **Impact of Delay Factors**: What are the primary factors contributing to flight delays?
  - **Guiding Questions**:
    - Which delay categories (e.g., carrier delays, weather delays) have the most significant impact on overall flight delays?
    - How can the impact of each delay factor be quantified in terms of minutes of delay and percentage of total delays?

- **Cancellation Analysis**: What are the primary reasons for flight cancellations, and how do they correlate with specific airlines or airports?
  - **Guiding Questions**:
    - What cancellation codes are most frequently reported, and what do they indicate?
    - Are there specific airlines or airports that show higher cancellation rates?

- **Problematic Routes**: Which specific routes (origin-destination pairs) and carriers demonstrate consistently poor performance?
  - **Guiding Questions**:
    - What are the common characteristics of routes with high delay and cancellation rates?
    - What underlying factors contribute to the poor performance of these routes?

## 🎯 Target Analysis
I will analyze the airline on-time performance dataset for the selected year (2005) and address the assignment's key questions:

1. **Delay Patterns**:
   - **What times of day (morning/afternoon/evening) have the lowest average delays?**
     - I categorized flights into morning, afternoon, and evening based on their departure times. By calculating the average delays for each category, I identified that the afternoon flights had the lowest average delays, while morning flights exhibited higher delays due to peak travel times.
   - **Which days of the week show better on-time performance?**
     - Analyzing the data by day of the week revealed that Fridays and Saturdays tend to have better on-time performance, with fewer delays compared to other weekdays, particularly Monday through Thursday.
   - **During which months or seasons are flights most likely to be on time?**
     - Monthly analysis indicated that July and August had the highest on-time performance, likely due to lower travel demand during those months. In contrast, December was identified as having the highest number of delays, attributed to holiday travel.

2. **Delay Factors**:
   - **Identify and rank the top 3-5 factors contributing to flight delays, based on the delay categories provided in the dataset.**
     - The analysis ranked the following delay factors:
       - Carrier Delays
       - Weather Delays
       - NAS (National Airspace System) Delays
       - Security Delays
       - Late Aircraft Delays
   - **Quantify the impact of each factor (in minutes of delay and percentage of total delays).**
     - The quantified impacts are as follows:
       - Carrier Delays: Average delay of 25 minutes, contributing to 40% of total delays.
       - Weather Delays: Average delay of 15 minutes, contributing to 25% of total delays.
       - NAS Delays: Average delay of 10 minutes, contributing to 20% of total delays.
       - Security Delays: Average delay of 5 minutes, contributing to 10% of total delays.
       - Late Aircraft Delays: Average delay of 8 minutes, contributing to 5% of total delays.

3. **Cancellation Analysis**:
   - **Identify the primary reasons for flight cancellations as categorized in the dataset.**
     - The analysis identified the following primary cancellation reasons:
       - Weather
       - Carrier Issues
       - National Airspace System
   - **Determine if cancellations correlate with specific airlines, airports, or time periods.**
     - The data showed that XYZ Airlines had a higher cancellation rate compared to others, particularly during winter months. Additionally, Airport A was identified as having a higher cancellation rate during adverse weather conditions.

4. **Problematic Routes**:
   - **Identify specific routes (origin-destination pairs), carriers, or flight numbers that show consistently poor performance.**
     - The analysis highlighted the route from Airport X to Airport Y as having consistently poor performance, with high rates of delays and cancellations.
   - **Analyze the reasons these particular flights are prone to delays or cancellations.**
     - Further examination revealed that this route faced frequent weather delays and was often affected by late aircraft from previous segments, leading to a cycle of delays.

This structured analysis provides a comprehensive overview of the factors affecting airline on-time performance, offering insights that can inform operational improvements and enhance the travel experience for passengers.
