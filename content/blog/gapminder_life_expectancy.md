---
author: "Soethiha Soe"
date: 2018-06-03
title: "Life Expectancy by Continent"
best: true
---

### Overview
The data used in this visualization is a subset of the [Gapminder Dataset](https://www.gapminder.org/data/) on world facts that can be used to examine social, political, and economic indicators.  In this exercise we plot the life expectancy distribution for each continent.  

The R code below creates a table and plot of life expectancy distribution. We used the aggregate function to subsample the dataset and generate summary statistics.  The summary statistics were then combined to create a single table tabulating the statisitics by continent.  

```r
#load data and packages
library(gapminder)
library(tidyverse)
library(ggplot2)
library(dplyr)
library(readr)

lifeExpCont <- gapminder %>%
  group_by(continent) %>%
  arrange(continent, lifeExp)

#create a table with mean and variance of lifeExp for each continent
lifeExpMedian <- aggregate(lifeExp ~ continent, gapminder, median)
lifeExpMean <- aggregate(lifeExp ~ continent, gapminder, mean)
lifeExpVar <- aggregate(lifeExp ~ continent, gapminder, var)
lifeExpTable <- cbind(lifeExpMean, lifeExpMedian$lifeExp, lifeExpVar$lifeExp)
colnames(lifeExpTable)<- c("continent","median","mean", "variance")

#show summary table of life expectacy by continent
lifeExpTable
```

```
##   continent   median    mean  variance
## 1    Africa 48.86533 47.7920  83.72635
## 2  Americas 64.65874 67.0480  87.33067
## 3      Asia 60.06490 61.7915 140.76711
## 4    Europe 71.90369 72.2410  29.51942
## 5   Oceania 74.32621 73.6650  14.40666
```

```r
#Companion graph - create boxplot of life expectancy by continent
ggplot(lifeExpCont, aes(x=continent, y=lifeExp))+
  geom_boxplot(outlier.colour = "blue") +
  geom_jitter(position = position_jitter(width = 0.2, height = 0), alpha = 0.25)+
  labs(x = "Continent", y="Life Expectancy Distribution")+
  ggtitle("Distribution of Life Expectancy by Continent")
```

![plot of chunk sad_plot2](/img/gapminder-life-expectancy.png)