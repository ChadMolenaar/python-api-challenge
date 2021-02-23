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

After each pair of plots explain what the linear regression is modeling such as any relationships you notice and any other analysis you may have. The dataset, is not 'wrong' it is simply biased to the natural differences between the Northern and Southern Hemispheres at a given point in time. So a date analysis is required - however, this is not I used for part 2. Vacation Py.

These are noted, with a code and general summary within the WeatherPy jupyter notebook. As an example of the differential explained in the WeatherPy part of this assighnment I have made a quick example: - 

refer .png testfig13 (this showed the desparity in the data).


Part 2. VacationPy

For the second part of this project (VacationPy), using the data for future ideal locations for a future vacation. Using gmaps and the Google Places API (g_key) to create a heatmap that displays the humidity for every city from part one. I have taken notice of the instructions but narrowed down the list of cities to find the ideal weather conditions, as per the instructions:-

* A max temperature lower than 80 degrees but higher than 70.
* Wind speed less than 10 mph.
* Zero cloudiness.
* Drop any rows that didn't contain all three conditions. But that is not what I am looking for.

My code below shows what I am looking for....

narrowed_city_df = narrowed_city_df[narrowed_city_df['Max Temp'] >= 0]
narrowed_city_df = narrowed_city_df[narrowed_city_df['Max Temp'] <= 60]  
narrowed_city_df = narrowed_city_df[narrowed_city_df['Wind Speed'] >= 20]
narrowed_city_df = narrowed_city_df[narrowed_city_df['Cloudiness'] >= 30]
narrowed_city_df = narrowed_city_df[narrowed_city_df['Humidity'] <= 70]
narrowed_city_df = narrowed_city_df.dropna()


Note: Given my desired vacation requirements, I added humidity and changed the initial three requirements. I like the cold, and loweer humidity. However, humidity has a different feeling between the cold and heat - as i wanted a cold place to vacation - I had to increse the humidity level given the dataset provided.

Observations and Insights

The dataset is a data point taken in a particular time. In this instance, I have had a result of two places I would like to visit.

Naturally I used the previous mentioned tools (i.e. OpenwethearPy etc) and then Google Places API to find the first hotel for each city located within 5000 meters of the coordinates. Finally, hotels were plotted on top of the heatmap with each pin containing the hotel name, city, and country. which, gave me the places I'd like to go. Canada. But the data has not given me this as where google did:

Using a different dataset, you can see how it can become a problem. A google search shows: https://www.google.com/search?gs_ssp=eJzj4tTP1TcwNS4yMDJg9OIrykxKzSxKVEgvSsxLSQUAZ1QIQw&q=ribeira+grande&rlz=1C1FHFK_en-GBAU927AU927&oq=Ribeira+Grande&aqs=chrome.1.0i355j46j0l8.2956j0j15&sourceid=chrome&ie=UTF-8 or

https://www.google.com/search?rlz=1C1FHFK_en-GBAU927AU927&sxsrf=ALeKk02-BtT7lPfZ7nns05_SfUsaRU6HpA%3A1614056017224&ei=UYo0YLyYDfaN4-EPv6ebyAQ&q=R%C3%ADo+Gallegos&oq=R%C3%ADo+Gallegos&gs_lcp=Cgdnd3Mtd2l6EAwyBQguEJMCMgIIADICCAAyBggAEBYQHjIGCAAQFhAeMgYIABAWEB4yBggAEBYQHjIGCAAQFhAeMgYIABAWEB4yBggAEBYQHjoKCC4QsAMQQxCTAjoHCC4QsAMQQzoHCAAQsAMQQ1CfjC9Yn4wvYJqzL2gBcAJ4AIAB5gGIAYkDkgEFMC4xLjGYAQCgAQKgAQGqAQdnd3Mtd2l6yAEKwAEB&sclient=gws-wiz&ved=0ahUKEwj8hLecm__uAhX2xjgGHb_TBkkQ4dUDCA0

Both have been created out of this mess of a dataset that I, myself, would love to visit. So not too bad all in all!


Jupyter Notebook VacatonPy, is not too dismilar to Part 1. The tools utilised are a simple function through expansion on the original dataset.

Python
Pandas library
Jupyter Notebook
Matplotlib library
Citipy
OpenWeatherMap API
Google Places API
gmaps
API Keys

At the end of the day - it did not matter the randomness - or the fact that the Northern Hemispher was colder and fit my parameters, it still worked for what I wanted out of it - it showed both a Northern, and Southern Hemisphere representation. And it has still shown an unexpected result.