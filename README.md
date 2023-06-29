# SQLAlchemy and Flask Homework Solution: Analysis of the climate in Hawaii

## Background

To help with the trip planning for a long holiday vacation in Honolulu, Hawaii, I decided to do a climate analysis about the area.
In Part 1 of the analysis I used SQLAlchemy ORM queries, Pandas, and Matplotlib. 
In Part 2 of the analysis I designed a Flask API based on the queries developed in Part 1.

### Before reading the homework csv data files and coding in sql

1. I created a new repository in GitHub for this project called `sqlalchemy`. 
2. Inside the new repository I cloned the new repository to my computer.
3. Inside my local Git repository, I created a directory/folder for the assignment and named it SurfsUp.
4. Then added the Jupter notebook climate_starter.ipynb with starter script and hawaii.sqlite, as well as the Resources folder that contains the 2 data files, for Part 1.  For Part 2 the downloaded app.py was used.
  
### Files including data used 

* SurfsUp/Resources/hawaii_measurements.csv - information about the precipitation and temperature observations at each station from 1/1/2010-8/23/2016
* SurfsUp/Resources/hawaii_stations.csv - information about the name, lat/long, and elevation of each of the 9 stations

## Part 1 - Analysis and Exploration of the Climate Data

1. Used the provided files (climate_starter.ipynb and hawaii.sqlite) to complete the climate analysis and data exploration.
2. Used the SQLAlchemy create_engine() function to connect to the SQLite database.
3. Used the SQLAlchemy automap_base() function to reflect the tables into classes, and then saved references to the classes named station and measurement.
4. Linked Python to the database by creating a SQLAlchemy session.
5. Performed a precipitation analysis and then a station analysis by completing the steps in the following two subsections.

   ### Precipitation Analysis

    1. Found the most recent date in the dataset.
    2. Using that date, got the previous 12 months of precipitation data by querying the previous 12 months of data. (Did not pass the date as a variable to the query.)
    3. Selected only the "date" and "prcp" values.
    4. Loaded the query results into a Pandas DataFrame. Explicitly set the column names.
    5. Sorted the DataFrame values by "date".
    6. Plotted the results by using the DataFrame plot method, as shown in Hawaii_12_months_precipitation.png.
    7. Used Pandas to print the summary statistics for the precipitation data. 
    8. Closed the session.
       
   ### Station Analysis

    1. Designed a query to calculate the total number of stations int the dataset.
    2. Designed a query to find the most-active stations (that is, the stations that have the most rows). To do so, completed the following steps:
       - Listed the stations and observation counts in descending order.
       - Answered the following question: which station id has the greatest number of observations.
    3. Designed a query that calculated the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.
    4. Designed a query to get the previous 12 months of temperature observation (TOBS) data. To do so, completed the following steps:
       - Filtered by the station that has the greatest number of observations.
       - Queried the previous 12 months of TOBS data for that station.
       - Plotted the results as a histogram with bins=12, as shown in Observed_Temps_USC00519281.png
    5. Closed the session.
    
 ## Part 2 - Design of the Climate App

Desgined a Flask API based on the queires developed in Part 1.
1. Started the homepage and listed all the avialble routes.
2. /api/v1.0/precipitation
    - Converted the query results from the precipitation analysis (i.e. retrieved only the last 12 months of data) to a dictionary using date as the key and prcp as the           value.
    - Returned the JSON representation of the dictionary.
3. /api/v1.0/stations
    - Returned a JSON list of stations from the dataset.
4. /api/v1.0/tobs
    - Queried the dates and temperature observations of the most-active station for the previous year of data.
    - Returned a JSON list of temperature observations for the previous year.
5. /api/v1.0/start and /api/v1.0/start/end
    - Returned a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.
    - For a specified start, calculated TMIN, TAVG, and TMAX for all the dates greater than or equal to the start date.
    - For a specified start date and end date, calculated TMIN, TAVG, and TMAX for the dates from the start date to the end date, inclusive.
    - Joined the station and measurement tables for some of the queries.
    - Used the Flask jsonify function to convert the API data to a valid JSON response object.
