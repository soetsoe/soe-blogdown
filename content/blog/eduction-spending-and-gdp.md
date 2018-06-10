---
author: "Soethiha Soe"
date: 2018-06-02
title: "Public Spending on Education and GDP in Africa"
---

### Overview
The data used in this visualization is a subset of the [Africa Developer Indicator](https://datacatalog.worldbank.org/dataset/africa-development-indicators) dataset collected by the World Bank, compiled from officially recognized international sources.  With this dataset, we examined the trends in public spending on education and GDP per capita for African nations between the years 1970 and 2012.  Before importing the data into R, the original dataset was filtered to only include entries that contain records of both public spending on education and GDP per capita for a given country and year. 

### Graph description
We employed a weighted scatter plot for visualizing the dataset.  On the x-axis is the year of record, and on the y-axis is the public spending on education as a percetage of GDP.  The weights of the plots represent the GDP per capita.  Our initial plot of the data is shown in Figure-1. 
![plot of chunk original plot](/img/original plot-1.png)
Figure-1: Original plot of public spending on education and GDP

### Improved graph
To help us communicate with a wider audience, we replaced the color pallete used in the original plot with a color-blind friendly palette.  The improved plot is shown in Figure-2.  
![plot of chunk improved plot](/img/improved plot-1.png)
Figure-2: Color blind friendly plot

### Description of the audience we're aiming for
The plot is targeted at policy makers, NGOs, and economists examining probable relationship between public investment in education and GDP at the national level.  This particular case with the ADI dataset could help researchers test their theories against a geographical backdrop that is undergoing significant social, political, and economic transition.  

### How I created it:  
Partly inspired by the Gapminder dataset on GDP and mortality rates, we searched for another dataset to explore probable relationships between different social, political, and economic indicators for a set of countries sharing a geographical backdrop.  We selected the Africa Developer Indicator (ADI) dataset for this study, as it allowed us to explore a broad set of social and economic indicators over a 40 year period for the countries of Africa.  During the initial exploratory data analysis, we identified a handful of indicators that could be considered as 'hidden' factors for GDP health and growth.  We further condensed the list of indicators to a few with sufficient records across countries and over a longer time period so that a relatively dense graph can be constructed for extracting probable trends and relationships.  The selected variables were Year, Public Spending on Education, and GDP per Capita.  

The original ADI dataset was processed into a format friendlier for manipulation in R.  We used the ggplot2 package in R to construct our graph.  Before settling on a scatter plot to visualize our data, we also looked at using a bar (column) graph and a line plot.  We found that the bar graph is not well suited for depicting datasets with more than one continous variable, and can be a visual clutter when the data contains a large number of categories.  We also discovered that adding a trend line (straight or smooth) of educational spending over time for each country did not help bring out new information in our scatter plot.  With the use of symbol size, the GDP values were already readily discernible between the datapoints above and below the 5% educational spending line.  We sustain that any additional trend lines or annotation would have only required more effort on the part of the viewer to interpret the data.

We read in a previously formatted ADI dataset and group the data points by country.  Since we can only make use of row entries that have both GDP per cap and educational spending entries populated, we filter the dataset with these two column values greater than 0.

### What are we trying to tell and how to read it
The graph is intended to show that there is correclation between public investment in education above a certain threshold (~5% of GDP) and higher GDP per capita for 15 African countries.  What we cannot tell from this graph is whether higher GDP per capita (which anectodally suggests greater political and social stability) was the driver for higher public spending in education, or if the investment in education lead to higher GDP per capita.  The viewer can read the graph starting form the left side and making her way to the right, all the while scanning from top to bottom to interpret whether the size of the points are larger or smaller with increase in y-axis value.  This also helps the viewer build a heurisitc for uncovering whether trends changed over time.  Our interpretation of the plot is one that suggests that high GDP per capita and public spending on education are a virtuous cycle for those countries with favorable conditions.  

### Presentation tips
As an extension, we could include annotation highlighting the y-axis threshold (~5%) where there appears to be 1.5x or more average GDP per capita gap for countries investing above and below the level.  We could group all the datapoints below $2000 GDP per cap into one bucket, and all the datapoints above $3000 GDP per cap into another category, then calculate the mean and variance for educational spending for the two groups.  This could help use derive a more accurate estimate of the dividing line.  In terms of the plot layout, we're generally happy with the x and y-axis unit intervals and the densitiy of the data points.

### Potential variations of the plot
A 3-dimensional scatter plot with GDP per capita on the z-axis is a suitable alternative for exploring correlations between educational spending and GDP over time.  This could be a substitute for using point symbol size as a way to encore GDP value.  Using height on the z-axis instead of symbol size to convey the GDP value would make it easier to interpret the absolute GDP value.  However, we believe a relative comparison of GDP (using point symbol size) as a function of educational spending is sufficient for extracting the right level of information from the graph.  A 3D scatter plot adds the disadvantage of requiring the user to visualize depth from a 2D image.     
