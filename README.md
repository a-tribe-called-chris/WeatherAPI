# WeatherAPI
A simple Proof of Concept utilizing the weather.gov API


I utilized the weather.gov free API in order to access real time {lat} {long} weather information, particularly around regions featuring my favorite ski reorts.

A blurb about the API is below:

api.weather.gov represents the public face of the next generation of data services from the National Weather Service. It offers public access to a wide range of essential weather data, in a way that modern web developers expect: a REST-style, JSON-based web service.

The API is also being built to provide a powerful and modern platform for data dissemination for both internal and external customers. We’re doing this to help eliminate some internal redundancies, giving you and our own forecasters and developers a one-stop shop for vital data.

https://weather-gov.github.io/api/general-faqs

Use is straight forward, provide a simple {lat} {long} pairing to return JSON data of each location.

Details:

Our current documentation is located at https://www.weather.gov/documentation/services-web-api. Over time we will also be offering this information here as well.

We also provide a service definition in OpenAPI v3.0 (previously known as Swagger) format. You can access this file at https://api.weather.gov/openapi.json (in JSON format) or https://api.weather.gov/openapi.yaml (in YAML format).

Much of the data returned from the API is in GeoJSON (RFC 7946) format. Certain endpoints also offer useful alternative formats, such as OASIS Common Alerting Protocol (CAP) XML for alerts data.

You’ll need to know the latitude and longitude of the location in decimal degrees. (If you want to get really geospatially technical, your location should be a WGS 84 or EPSG 4326 coordinate.)

For our example here, we’ll use the Washington Monument in Washington, D.C. It’s located at 38.8894 latitude, -77.0352 longitude.
Please note that, for efficiency purposes, the API doesn’t support more than four decimal places of precision in coordinates. If you send a more precise coordinate, you’ll receive an error giving you the closest proper coordinate. Four decimal places is about 30 feet (10 meters) over most of the United States, so that should still be close enough!
Once you know the latitude and longitude, it’s an easy three-step process from there. You can follow along in your browser with the links below:

Retrieve the metadata for your location from https://api.weather.gov/points/{lat},{lon}.
For our example the URL will be https://api.weather.gov/points/38.8894,-77.0352
You’ll get back a JSON document. Inside the document, find the properties object, and inside that, find the forecast property. You’ll find another URL there.
For our example this gives us https://api.weather.gov/gridpoints/LWX/96,70/forecast
You can also get the hour-by-hour forecast from the forecastHourly property. For our example it’s https://api.weather.gov/gridpoints/LWX/96,70/forecast/hourly
Retrieve that URL. You’ll get a JSON document containing the forecast for that location. There you go!
We’re still working on documentation for the JSON that API returns, but we think it’s pretty easy to understand if you just look at it. If you need more reference, the forecast JSON very closely aligns with the information you’d see on a web page on forecast.weather.gov. If you still have questions, please see our Reporting Issues page for how to ask.

Overall the goal of this Project was to simply return weather data, which I consider a success. This is a small portion of a future project I hope to work on. 
