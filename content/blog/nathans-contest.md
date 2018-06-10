---
author: "Soethiha Soe"
date: 2018-06-04
title: Nathans Hot Dog Eating Contest
---

### Overview
In this exercise we plot the number of hot-dogs and buns (HDB) eaten by the winner of Nathan's Hot Dog Eating Contest for each year of competition. The dataset 'Hot Dog Contest with Affiliation' contains the records of Nathan's Hot Dog Eating Contest results from 1981 to 2017.  Each data entry contains the year of the contest, name of the winning contestant, and number of HDB consumed total and per minute by the winner.  The extended version of the dataset also captures whether the winning contestant was affiliated with Major League Eating (MLE) & International Federation of Competitive Eating (IFOCE).   A glimpse of the data is shown below:

### Graph description
We used a column graph to show the number of hot-dogs and buns (HDB) consumed by the winner of Nathan's Hot Dog Eating Contest for each year between 1981 and 2017.  The competition year is on the x-axis, and the number of HDB consumed by the winner for the year is on the y-axis.  Our initial graph is shown in Figure-1. 
![plot of chunk original plot](/img/nathans_hdb_original.png)
Figure-1: Column graph of HDB consumed

### Improved graph
To help reduce the effort required to map the competition year with HDB consumed for that year, we increased the number of ticks on the x-axis interval.  We used the scale_x_XX function in R to modify the number of breaks. The improved plot is shown in Figure-2.  
![plot of chunk original plot](/img/nathans_hdb_improved.png)
Figure-2: Graph with increased number of x-axis lable ticks

### Description of the audience we're aiming for
The audiences are sports writers or researchers examining the history of competitive eating, or individuals who plan to participate in the competition.  The graph is designed to help the viewer quickly find the number of HDB consumed by the winner for each competition year, as well as discover a general trend in the number of HDB consumed.    

### How I created it:  
The provided dataset was preprocessed  with variables (such as year of competition and HDB consumed) defined in columns and values assigned to rows.  We load the dataset into a R dataframe and filtered the dataset for entries recorded after 1980, and only for the records of male contenstant.  The reason why we filtered the dataset this way is that it gives us a consisten YoY record of HDM consume. We then used ggplot to create a geom_col() of the data.  On the x-axis is the year of the competition, and on the y-axis is the number of HDB consumed by the winning contestant for that year.  We selected to use black and white plot since there was only one dependent variable (HDB consumed).  For the improved plot, we changed the x-axis label interval. 

### What are we trying to tell and how to read it
We are showing the number of HDB consumed by Nathan's eating contest winner between 1981-2017.  The audience can look at a particular competition year on the x-axis then read out the number of HDB eaten in the y-axis.  The audience may notice the ~2x increase in number of HDB consumed between 2000 and 2001, and may be prompted to do further investigation.  Extending their exploratory data analyis, they would find that the reason for the abrupt increase is due to a longer time allotment given to the competitors (as the competition became affiliated with ICOFE/MLE).  The audience could also interpolate the the number of HDB consumed in the competition is increasing.

### Presentation tips
We could use annotation to overlay information that would be more useful in interpreting the results.  For example, we could include (encoded in color) the amount of time the competitors were given to eat HDB for each of the competition years.  Additional, we can include the name of the winner along the x-axis (repeat champions?), and show if the winner for a particular year was afficiliate with ICOFE/MLE.  These exercises were completed in Lab01.

### Potential variations of the plot
We could use a scatter plot to show the number of HDB consumed.  We could simply replace the column(bar) graph with geom_point() while keeping the y-axis and x-axis variables identical. However, since the x-axis values can only take on whole integers and there is only one y-value for each x-value, a bar graph is easier to read.
