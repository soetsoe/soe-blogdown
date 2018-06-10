+++
author = "Soethiha Soe"
title = "Children and Animal Sounds"
date = "2018-06-02"
+++


### Overview
The dataset 'Animal Sounds Summary' contains the results of a study that examined how well children in different age groups can understand or reproduce an animal sound.  Three animal sounds were used in the study: "cockadoodledoo", "meow", and "woof woof".  More than 2000 children between the ages 8 through 18 participated in the study that documented the proportion of the children (by age group) that can either understand or reproduce each of the animal sounds.  In this exercise, we plot the proportion of children per age group that can understand an animal sound.

### Graph description
We used scatter plots with facet wrapping for each type of animal sound used in the testing.  Each facet box represents an animal sound.  The age of the children are on the x-axis, and the proportion of children participated in the study who can recognize the animal sound is on the y-axis.  Our initial plot of the data is shown in Figure-1. 
![plot of chunk original plot](/img/animal_sounds_original.png)
Figure-1: Proportion of Children Recognizing Animal Sounds

### Improved graph
To improve the interpretability of the graph, we increased the size of the points in the plot and used color encoding for the different animal sound categories
![plot of chunk original plot](/img/animal_sounds_improved.png)
Figure-2: Improved Plot

### Description of the audience we're aiming for
The targeted audience is a child developmental psychologist or a researcher in the field of auditory processing that may be interested in analyzing the developmental trends in the understanding or reproduciton of sounds.  

### How I created it
The entries in the dataset were grouped by children age and type of animal sound, with each row containing a record of response values.  We used ggplot to create a scatter plot of the data.  On the x-axis is the age of the children, and on the y-axis is the proportion of children for the age group that can understand an animal sound.  We use a facet wrapper to create individual windows for each type of animal sound. The original plot was created with default point size and color.  We improved the visualization by increasing the size of geom_point() and assigning color coding to the animal sounds.  

### What are we trying to tell and how to read it
We are showing the proportion of children in each age group (8 through 18) that can understand the animal sounds "cockadoodledoo", "meow", and "woof woof".  The viewer can start with the left-most window containing the data entries for "cockadoodle". As she looks at the graph from left to right, she should discover a relatively linear trend in the proportion of children that can understand the "cockadoodledoo" sound as a function of age. Similarly, as she examines the second and third plots, she once again discovers a linear increase in proportion of children that can understand the animial sound with age.  She might also find that children generally recognize the sounds "meow" and "woof woof" before they recognize "cockadooledoo".

### Presentation tips
We could use annotation to point out that children generally learn to understand the sounds "meow" and "woof woof" before they can understand "cockadoodledoo".  We could also include a linear fit line to show that the proportion of children that understands an animal sound improves linearly with age. 

### Potential variations of the plot
We could use a column(bar) graph to show the proportion of children that understand animal sounds by age group.  We could simply replace the scatter plots with columns while keeping the y-axis and x-axis variables identical.  We could also use a facet wrapper to continue grouping the datapoints by animila point.  The column graph, however, would require more effort on the part of the viewer to interpolate the linear trend.
