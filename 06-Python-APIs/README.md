##Python API Challenge

Introduction:

Understanding the initial question of this project - "What's the weather like as we approach the equator?" is a classic switch on the old "Well, of course it's hotter closer to the equator". The larger and more potenent question revealed later is: - If you had to take a holiday - where would you go?

As per the instructions for this project, I used Python requests, APIs, and JSON as well as the following for the first intial part of this assignment:

-pandas as pd
-numpy as np
-citipy
-from config import api_key
-matplotlib.pyplot as plt
-scipy.stats as st
-and from scipy.stats import linregress

There were two parts to this project and hence my repository corresponds to the two parts: - Firstly:

Part 1. WeatherPy

Utilising the tools for this project (WeatherPy), I first utilised Python with a maximum of 2,000 cities across the world of varying distances from the equator. Then, numpy generated a random set of 500 latitude and longitude coordinates. Citipy was then used to locate the nearest city for each latitude and longitude. The OpenWeatherMap API was utilised to then, take the next step of retrieving weather data for each of the cities. This was then saved, as per the instructioins, into a .csv file.

Instructions: The first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot add a sentence or too explaining what the code is and analyzing.

The second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots explain what the linear regression is modeling such as any relationships you notice and any other analysis you may have.

These are noted, with a code and general summary within the WeatherPy jupyter notebook.


Part 2. VacationPy

For the second part of this project (VacationPy), I used the weather data gathered from part one to help plan for future vacations. Specifically, I used jupyter-gmaps and the Google Places API to create a heatmap that displays the humidity for every city from part one. I then narrowed down the list of cities to find the ideal weather conditions, including:

* A max temperature lower than 80 degrees but higher than 70.
* Wind speed less than 10 mph.
* Zero cloudiness.
* Drop any rows that didn't contain all three conditions.

Note: Given my desired vacation requirements, I added humidity and changed the initial three requirements.

I then used the Google Places API to find the first hotel for each city located within 5000 meters of the coordinates. Finally, I plotted the hotels on top of the humidity heatmap with each pin containing the hotel name, city, and country.

Observations and Insights
From part one (WeatherPy), here are some observations and insights that can be made from the data:

There is a strong, negative correlation between a city's latitude and maximum temperature in the northern hemisphere. That is, as you go farther away from the equator (latitude increases), a city's maximum temperature will generally be lower than cities closer to the equator in the northern hemisphere. This is what I expected to see - for example, it's a lot colder in Minnesota (farther north) than it is in Mexico.

There is a very weak, positive correlation between cloudiness and a city's latitude for both the northern and southern hemispheres. This is represented in the scatter plots in this notebook for those two factors as the data points being scattered across the graph. As a result, we can conclude that a city's latitude has little to no influence on how cloudy a city is.

There is a very weak, positive correlation for the northern hemisphere between a city's latitude and wind speed (mph), and there is a very weak, negative correlation for the southern hemisphere for those same two factors. I think the fact that the southern hemisphere has a negative correlation and the northern hemisphere has a positive correlation has to have something to do with the northern hemisphere and southern hemisphere being in opposite seasons from each other. Overall, for both hemispheres, latitude has a small influence on wind speed but not very much. However, it is important to note that the correlation between these two factors for the southern hemisphere is stronger than the correlation between these two factors for the northern hemisphere.

Jupyter Notebook
For this project, I used jupyter notebook to render and display the results of this analysis. There are two notebook files. One for part one (WeatherPy) and another for part two (VacationPy) of this project.


Technologies Used
Python
Pandas library
Jupyter Notebook
Matplotlib library
Citipy
OpenWeatherMap API
Google Places API
gmaps
API Keys

