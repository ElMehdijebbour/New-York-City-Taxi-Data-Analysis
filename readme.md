# New York City Taxi Data Analysis

## Overview
This project aims to analyze a dataset containing New York City taxi ride information. The main goal is to compute the utilization of each taxi, understand the time it takes for a taxi to find its next passenger based on the borough of drop-off, and understand the intra-borough and inter-borough trips.

## Table of Contents
- [New York City Taxi Data Analysis](#new-york-city-taxi-data-analysis)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Project Setup](#project-setup)
  - [Dataset Overview](#dataset-overview)
  - [Methodology](#methodology)
  - [Project Steps](#project-steps)
  - [How to Run](#how-to-run)

## Project Overview
This project aims to analyze a dataset containing New York City taxi ride information. The main goal is to compute the utilization of each taxi, understand the time it takes for a taxi to find its next passenger based on the borough of drop-off, and understand the intra-borough and inter-borough trips.


## Project Setup
To set up the project environment using Docker:
1. Ensure you have Docker installed on your system.
2. If you need a reference for setting up the Docker environment, you can refer to this repository: [Spark Practice Configuration](https://github.com/riccardotommasini/spark-practice).
3. Once you have your Docker configuration ready, navigate to the directory containing  `docker-compose.yml` file.
4. Start the Docker environment by running:
   ```bash
   docker-compose up
    ```
## Dataset Overview
The dataset, available at [NYC Taxi Dataset](http://www.andresmh.com/nyctaxitrips/).
Each row in the dataset represents a single taxi ride in CSV format. The dataset provides:
- Unique ID for the taxi (license)
- Pick-up location (latitude and longitude)
- Pick-up time
- Drop-off location (latitude and longitude)
- Drop-off time

Additionally, the dataset includes a .geojson file with the geographical boundaries of the various NYC boroughs to identify and associate each ride with a specific borough.


## Methodology
The project involves several key steps:
- Enriching the dataset with borough information.
- Handling temporal and geospatial data.
- Implementing Spark's window operator for temporal analysis.
  
## Project Steps
The analysis includes several key steps, each crucial to understanding the dynamics of taxi usage in NYC:
- **Initialize PySpark Session**
- **Data Loading**: Read the CSV file with schema inference and immediately select the necessary columns. Cache the data for performance.
- **Data Enrichment**: Convert the date columns to Unix timestamps, calculate the duration in minutes between pickup and dropoff.
- **Data Cleaning**: Ensure data integrity by filtering out unreasonable values, focusing on duration, latitude, and longitude.
- **Query 1: Utilization**: Compute how effectively taxis are utilized in NYC.
- **Query 2: Average Time to Next Fare**: Assess the time it takes for taxis to find their next passenger based on the borough of drop-off.
- **Query 3: Intra-Borough Trips**: Analyze trips that start and end within the same borough.
- **Query 4: Inter-Borough Trips**: Study the trips that occur between different boroughs.



## How to Run
To execute the analysis, run the following command:
```bash
jupyter notebook
