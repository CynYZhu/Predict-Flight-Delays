# Airline Partner Recommendation to Electronic Arts

## Introduction
Accurate prediction of flight delay is crucial for airlines and their customers because of the cascading consequences of any given flight anomaly on both the carriers and the passengers. Our motivation for creating models to predict flight delays is that we are a data science consultancy hired by Electronic Arts, a large corporation operating in the gaming industry to identify and recommend airline carriers to partner with for an exclusivity agreement. We aim to predict flight delays in advance so that we can help EA avoid missed opportunities company wide by anticipating and making sound decisions when these situations arise.

## Data
The datasets that we will leverage to develop predictive flight delay models include the following:

- Airline data from the US Department of Transportation containing flight information like flight number, origin airport, destination airport, time of flight, and delay status between 2015 and 2020.
- Weather data from the National Oceanic and Atmospheric Administration (NOAA) Integrated Surface Database from 2015 to 2020 containing sensor readings on wind speed, visibility, temperature, and dew point.
- A table of NOAA weather station locations that will be the key to joining both the weather and airline datasets

## Models
We experimented with decision tree (baseline model), logistic regression, random forest, XGBoost, and Gradient Boost, and adopted various methods to improve performance, such as rolling window cross validation, gridsearch, etc. We compared the performance of 4 models and decided to choose XGBoost as our champion model considering the balance between precision and recall. More details on model performance can be found in the report.ipynb. 

## Novel approach
Thinking about real life scenarios, one major reason flight delays is that the previous flight operated by the same aircraft was delayed, resulting in the subsequent flights not being operated as scheduled. We utilized the motif finding function in GraphFrame library to find the potential consecutive flights operated by the same aircraft. With additional features of the source airport, such as weather data at two time points and airport evaluation scores, we built Gradient Boost model to see if we could improve recall of predictions. Even thought the accuracy and recall is comparable to the model what without connection flight features, we leveraged novel network algorithm created new features for 80M records in this process. 

## Summary
The top 5 airline carriers recommended for exclusivity agreements with EA are the following:

1. AA - American Airlines
2. UA - United Airlines
3. WN - Southwest Airlines
4. OO - Skywest Airlines
5. DL - Delta Airlines

