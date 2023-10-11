# Cinephiles Phase 2 Project

September 2023
Yasitha De Alwis (ydealwis@gmail.com)
Kendall McNeil (kendallmccneil@gmail.com)
Andrew Hendricks (AndrewHHendricks@gmail.com)


## Overview

Our company has decided to create its own new movie studio and wants to explore what types of movies are doing best at the box office.

Our company asked our team to study which types of movies are doing the best and to translate our findings into actionable insights for the new movie studio head.

## Business Understanding

Our key stakeholder is the head of the new movie studio. The main question we explored was: Which factors have the strongest significance in relation to a movie's return on investment?

## Data Understanding and Analysis

### Source of data

To perform our analysis, our team primarily relied on budgetary data from two sources.  The first source was The Numbers, which provided us with information about runtimes, release date, production budgets, and worldwide gross. The second source was IMDB, which provided us with data about genres and other movie characteristics as well as personnel such as directors, writers, and actors.

### Description of data

The budgetary data from The Numbers included approximately 5,500 records of movies from the past several decades. To perform our analysis of the relationship between factors from the IMDB database and ROI, we merged the data sets and eliminated Nan values as needed.

### Methods

To begin, we decided to calculate a ratio of worldwide gross relative to budget to determine the return on investment for each film.  We used this value as our main measure of profitability.

Next, for each factor we analyzed, we performed chi squared tests to evaluate whether we could reject the hull hypothesis that there was no significant statistical correlation between that factor and return on investment. To do so, we created categories for return on investment based on a normal distribution.

For factors where we could reject the null hypothesis with at least 95% confidence, we then grouped the data by element for that factor and reviewed the median ROI for each element.  When possible, we limited our analysis to data sets with at least 30 records. In certain analyses involving smaller numbers of records, such as analyses of personnel categories, we used the best sample of data we had available.


### Results



## Conclusion

Based on our analysis, we would make the following recommendations to the head of the company's new movie studio:
1. The most profitable genre is horror/mystery/thriller.
2. The most profitable months to release a film are June and July.
3. The most profitable directors are Henry Joost, Ariel Shulman, David F. Sandberg, Pierre Coffin, Christopher Landon, James DeMonaco, M. Night Shyamalan, James Wan, Damien Chazelle, and Jake Kasdan.
4. The most profitable run time is over two hours, specifically from 134-137 minutes.

