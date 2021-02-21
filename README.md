# python-api-challenge

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. This project uses Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

## Part I - WeatherPy

Creaed a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. Utilized a [Python library](https://pypi.python.org/pypi/citipy), and the [OpenWeatherMap API](https://openweathermap.org/api) to create a representative model of weather across world cities.

Created a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude


Ran linear regression on each relationship. 
Then separated the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

The notebook:

* Randomly selects at least 500 unique (non-repeat) cities based on latitude and longitude.
* Performs a weather check on each of the cities using a series of successive API calls.
* Includes a print log of each city as it's being processed with the city number and city name.
* Saves a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Uses jupyter-gmaps and the Google Places API for this part.

* Created a heat map that displays the humidity for every city from Part I.

* Narrows down the DataFrame to the following weather condition:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

* Uses Google Places API to find the first hotel for each city located within 5000 meters of the coordinates.

* Plots the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

Uses:

* Jupyter notebook.
* Matplotlib or Pandas plotting libraries.

### Copyright

Trilogy Education Services © 2020. All Rights Reserved.
