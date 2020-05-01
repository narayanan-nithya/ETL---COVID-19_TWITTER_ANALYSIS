# ETL---COVID-19_TWITTER_ANALYSIS

<p align="center">
  <img width="800" height="300" src="https://github.com/narayanan-nithya/ETL---COVID-19_TWITTER_ANALYSIS/blob/master/globe-covid19-scaled.jpeg">
</p>
https://github.com/narayanan-nithya/ETL---COVID-19_TWITTER_ANALYSIS/blob/master/globe-covid19-scaled.jpeg
## Final Report

The sources that we extracted data from were:

    https://covid19api.com/
    https://api.twitter.com/labs/2/tweets/search


We transformed the data by importing CSV and JSON files into a jupyter notebook, and using python and pandas, we joined the two data frames by Country. We did this with the aim of comparing the number of tweets per country, per number of deaths per country, and dropped any rows with null values in either of the two data frames. In doing so, we essentially filtered out any of the countries with either low number of deaths, or low number of tweets. 

After we joined both dataframes, we pushed the data to MongoDB. Once doing so, we then extracted the data, filtered by the top 5 countries with the highest amount of deaths, and exported a separate CSV with the filtered data, to plot and analyze. 

We chose to use MongoDB compass, a non-relational database, so that our collection could hold different documents, and the number of fields and content can differ from one document to the other. With this capability, we can query the data in whatever way we choose, without running into errors when different sources of data don't line up. This worked for us due to the fact that the twitter api output is continually changing, which wouldn't work for a relational database. 

The final collections we used in the production database are the countries with the highest amount of COVID-19 related deaths, which we then directly compared to the twitter api collection of data, where we queried for COVID-19 related tweets per country. 

## Observation

Based on the top 5 severely affected countries by COVID-19, we found that the number of deaths does not correlate to the twitter activity of the population in that country (tweets related to COVID-19). In fact, we noticed that in countries with highrer COVID-19 related deaths, the tweets were relatiovely less compared to the countries that had lower number of deaths. This shows that countries less severely affected are the ones that are most anxious about the pandemic. Countries that are most affected don't want to talk about it socially. 
<p align="center">
  <img width="500" height="500" src="https://github.com/narayanan-nithya/ETL---COVID-19_TWITTER_ANALYSIS/blob/master/covid_twitter_plot.png">
</p>
