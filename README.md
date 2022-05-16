# Surfs Up Weather Analysis
## Overview
The purpose of this assignment was to analyze weather data on in Oahu, Hawaii. Using data storage and retrieval tools, we were able to analyze the data for an investor to determine if this location is optimal to open a surf and ice cream business. With our assistance, the investor wants to determine if his investment is well spent on this prospective business in hopes that it can operate year-round.

---

## Data Analysis

*Deliverable 1: June Temp Data*

![June_Histogram.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/June%20Hist.png)![June_Temp_Description.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/June%20Temp.png)

This small table offers a lot of information regarding the temperature trends in June for this area. We can determine from 1,700 data entries that the average temp is 74.94 degrees Fahrenheit. This is an optimal temperature for enjoying Ice Cream on the beach and looking at the rest of the table we can also determine that there is not a large deviation from the average with the minimum and maximum temperatures. Even the coldest temperature in June only went down to 64 degrees. The chart below is a histogram that displays the frequency of the temperatures.

The histogram displays that most frequent temperatures can be seen just under 75 degrees and just below 80 degrees, with the minimum and maximum temperatures only being hit on rare occasion.

*Deliverable 2: December Temp Data*

![December Histogram.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/Dec%20Hist.png)![December_Temp_Description.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/Dec%20Temp.png)

December temperatures display a similar set of data when compared to June temperatures. While most temperate climates would expect winter months to be colder, Hawaii being a tropical climate often has similar temperatures all year round with more of a hot season and a cool season. The average temperature is only 3 degrees cooler than that of June's average temp, while the spread of temperatures shows there is a higher frequency of temperatures below 70 and rarely a temperature that hits 80. All that to say, these tropical temperatures still offer an optimal experience to enjoy ice cream, as the temperatures are still mild enough to enjoy the beach.

The spread of data in the histogram is very similar in shape to the June temperature while being shifted down a few degrees. The most frequent temperatures are from the high 60's to low 70's while outliers like 60 and low 80's are rarely reached.

### Additional Queries

**JUNE DATA**

```
# Additional Query: June Precipitation
june_precipitation = session.query(Measurement.tobs,Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
june_precipitation_df = pd.DataFrame(june_precipitation, columns = ['Temperature', 'Precipitation'])
june_precipitation_df.describe()
```

![June_Temp Precip.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/June_Temp_Precip.png)

**DECEMBER DATA**

```
# Additional Query: December Precipitation
december_precipitation = session.query(Measurement.tobs,Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
dec_precip_df = pd.DataFrame(december_precipitation, columns = ['Temperature', 'Precipitation'])
dec_precip_df.describe()
```

![Dec_temp_precip.png](https://github.com/RyanJL18/surfs_up/blob/main/Resources/December_Temp_Precip.png)

## Conclusion

In summary, the temperatures across the year in Oahu offer very little change. Additional queries below offer details on the precipitation to see if there is any cause for concern regarding rainfall in the area.

As you can see, there is very little cause for concern related to precipitation in this area at these given times. The average rainfall is very low, and the min/max recordings only differ slightly. I would argue that potentially looking at this same data at monsoon season would offer more insight as to whether there is an extremely rainy season or not. However, given the data we have analyzed, the Surf and Shake shop would do extremely well in this area. Trends seem to suggest that there would rarely be a time of year that would *not* offer an optimal weather experience. 
