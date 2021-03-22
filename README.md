# python-api-challenge

## Project Description

The goal of this project is to visulaize and analyze weather data versus location in the world to determine if the location correlates with temperature, humidity, cloudiness, or wind speed. The second part of the project places the humidity data on a heatmap and plots the location of hotels near certain cities uing the google API and gmaps. This project uses `Python`, Jupyter notebook, and the following libraries: `pandas`, `requests`, `Matplotlib`, `os`, `numpy`, `time`, `scipy`, `datetime`, and `gmaps`. You will need to acquire an [OpenWeatherMap API](https://openweathermap.org/api) and a [Google API](https://support.google.com/googleapi/answer/6158862?hl=en). 

### Part I - WeatherPy

Creaed a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. Utilized a [Python library](https://pypi.python.org/pypi/citipy), and the [OpenWeatherMap API](https://openweathermap.org/api) to create a representative model of weather across world cities.

Ran linear regression on each relationship and then separated the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Northern%20Hemisphere%20Max%20Temps%20vs.%20Latitude.png)

* Southern Hemisphere - Temperature (F) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Southern%20Hemisphere%20Max%20Temps%20vs.%20Latitude.png)

* Northern Hemisphere - Humidity (%) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Northern%20Hemisphere%20Humidity%20vs.%20Latitude.png)

* Southern Hemisphere - Humidity (%) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Southern%20Hemisphere%20Humidity%20vs.%20Latitude.png)

* Northern Hemisphere - Cloudiness (%) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Northern%20Hemisphere%20Cloudiness%20vs.%20Latitude.png)

* Southern Hemisphere - Cloudiness (%) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Southern%20Hemisphere%20Cloudiness%20vs.%20Latitude.png)

* Northern Hemisphere - Wind Speed (mph) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Northern%20Hemisphere%20Wind%20Speed%20vs.%20Latitude.png)

* Southern Hemisphere - Wind Speed (mph) vs. Latitude

![screenshot](/WeatherPy/Images/LinReg%20Southern%20Hemisphere%20Wind%20Speed%20vs.%20Latitude.png)

The notebook:

* Randomly selects at least 500 unique (non-repeat) cities based on latitude and longitude.
* Performs a weather check on each of the cities using a series of successive API calls.
* Includes a print log of each city as it's being processed with the city number and city name.
* Saves a CSV of all retrieved data and a PNG image for each scatter plot.

#### Conclusion
* As the latitude moves away from the equator, the max temperature decreases and more drastically in the northern hemisphere. The highest max temperatures are at 0 latitude/equator. The regression is not linear but does become linear when the northern and southern hemispheres are split up. The r2 value in the northern hemisphere of 0.76 demonstrates the strong correlation between latitude and max temperature in the northern hemisphere. The southern hemisphere does not correlate as well with an r2 value of 0.31. NOTE: the r2 values will change every time the notebook is ran because it is pulling in 500 random cities every time.
* The humidity does not correlate with latitude. The linear regression with the low r2 value (0.14 and 0.03) for the northern and southern hemisphere demonstrate the low correlation.
* The cloudiness does not correlate with latitude. The linear regression with the low r2 value (0.07 and 0.22) for the northern and southern hemisphere demonstrate the low correlation.
* The wind speed does not correlate with latitude. The linear regression with the low r2 value (0.01 and 0.08) for the northern and southern hemisphere demonstrate the low correlation.


### Part II - VacationPy

Uses jupyter-gmaps and the Google Places API.

* Created a heat map that displays the humidity for every city from Part I.

* Narrows down the DataFrame to the following weather conditions:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

* Uses Google Places API to find the first hotel for each city located within 5000 meters of the coordinates.

* Plots the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

![screenshot](/VacationPy/Images/Heat%20Map%20with%20Markers.png)
