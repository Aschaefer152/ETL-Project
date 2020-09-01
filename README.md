# ETL-Project

ETL Project Proposal:

We found a csv file on https://catalog.data.gov/dataset/ncdc-storm-events-database that breaks down historical Storm events, showing key statistics on past Strom Events. We have filtered out the data without lat and long to clean the dataset.  

Utilizing the MeteoStat API we will use our Storm Events dataset’s lat and long variables as primary key’s in order to find the nearest weather station ID from the MeteoStat API. Here we are limiting the results to 1 in order to find the top results for the nearest Station (or Station ID) as well as defining the radius within 100 KM from the Station. We chose this specific radius limit in order to locate only one Station ID, which will be the closest to provide the most accurate temperature information.

Now that we have successfully added the Station ID, we are able to utilize the Historical Daily Weather Data API which will return the average temperature and date. Average temperature is as a float in degrees© and Date a date string. 

Now that we have the Data and Average Temperature from the Historical Daily Weather Data API we can now merge our Strom Events.date and Historical Daily Weather Data API.date to link our data.

Now that we have combined all necessary variables, we are able to find the Temperature of the Storm Event and add that to our merged dataset. 
