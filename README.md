# etl-project

## Extract

Initially we were unable to puse.com/usdot/flight-delays#airlines.csv due to the limit. To read in all 12 csv files at once created a foh the 1st Kaggle file to our github repo. We found out that github has a file limit. As a work around we created 12 csv files out of the main airline.csv https://www.kagglr loop and set the files to a variable called "filepaths".

For our second dataset we used the city_attributes.csv related to historical hourly weather data https://www.kaggle.com/selfishgene/historical-hourly-weather-data#city_attributes.csv. The goal of this project was to potentially find any reasoning for flight delays or cancellations for the cities that were available in this dataset.

## Transform

The initial step completed was to filter out any cities within our city attributes data file that was outside of the United States. After we only had the cities, we wanted to include we needed to convert the cities into a list. Created the cities variable to convert the "city" column from airports.csv into a list. We combined/filtered the airports dataframe and cities list to only filter in cities that are a match in our list. Followed this same logic we used for cities to convert the airport codes to a list. We found that the dataframe.isin() function was extremely helpful due to being able to filter in or out of our dataframe to only see airports that matched any city destination or origin that was in our list. The function works similarly to SQL's in and not in function, thinking of it as a for loop. We next merged the two dataframes that we utilized the isin/~isin function with.

Now that we have the data, we want the way we wanted it we narrowed down the columns we wanted to include within our dataframe. We moved back into the extraction process for the next few steps only because we wanted to start the process of finding out the potential reasoning as to why a flight is delayed or cancelled. The csv added in included temperature, wind speed, weather description, and wind speed. Now that we have the files added as well as the airport cities, we can now begin to research reasoning as to what caused disruptions in the flights.

## Load

Postgres was used to load our data in a SQL database. The function used within pandas was "to_sql". The purpose of using this function was to write our dataframes to SQL and not have to manually add each table and upload the data to postgres.

We next could in theory analyze all of our data to draw conclusions as to why flights in 2015 were delayed or cancelled.

Contributors
Jeremiah Herberg, Chris Suchite, Jenniffer Lockwood, Celina Akwo, Richard Hamilton
