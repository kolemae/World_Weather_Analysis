# Weather Analysis for Vacation Planning
Project using Pandas, APIs, and Jupyter Notebook to call, analyze, format, and display weather and gmaps data for the PlanMyTrip app.

### Resources
- Data source: OpenWeatherMap API, Google APIs, WeatherPy_Database.csv, WeatherPy_vacation.csv
- Software: Anaconda 2021.11, Python 3.7.11, Jupyter Notebook

## Overview of Project
For [WeatherPy_Database](Weather%20Database/WeatherPy_Database.ipynb) we used `np.random.uniform` to generate random latitudes and longitudes:
- `lats = np.random.uniform(low=-90.000, high=90.000, size=2000)`
- `lngs = np.random.uniform(low=-180.000, high=180.000, size=2000)`

then used `citipy` to find the nearest cities to get the following from the OpenWeatherMap API:
1. City and Country
2. Max Temperature
3. Humidity
4. Cloudiness
5. Wind Speed
6. Weather Description

We then created [Vacation_Search](Vacation%20Search/Vacation_Search.ipynb) with [WeatherPy_Database.csv](Weather%20Database/WeatherPy_Database.csv). After adding input statements that allow users to enter minimum and maximum temperature criteria for their vacation we:
1. Used the `loc` method to filter for temperature criteria
2. Cleaned the filtered results
3. Used Google APIs to find nearby hotels and added this info to a DataFrame
4. Used `gmaps` to create a map with location markers showing:
   - Hotel name
   - City
   - Country
   - Current weather description
   - Maximum Temperature

![Vacation_Search_Map_Markers](/Vacation%20Search/WeatherPy_vacation_map_markers.png)

As a last step we created an example travel itinerary in [Vacation_Itinerary](Vacation%20Itinerary/Vacation_Itinerary.ipynb):
1. Imported [WeatherPy_vacation.csv](Vacation%20Search/WeatherPy_vacation.csv)
2. Created identical marker map from above
3. Chose four cities from that map that were:
   - Close together
   - In the same country
   - Worked with gmaps `travel_mode` "DRIVING", "BICYCLING", or "WALKING"
4. Created a directions layer map and added markers for the itinerary

<p align="center">
  <img src="https://github.com/kolemae/World_Weather_Analysis/blob/main/Vacation%20Itinerary/WeatherPy_travel_map.png">
</p>
