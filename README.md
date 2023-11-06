# Movie Budget Optimization Project

October 2023

Andrew Hendricks (AndrewHHendricks@gmail.com)

Links to Notebooks and Documents:

[Final Analysis Notebook](https://github.com/ahendricks2/MovieBudgetOptimization/blob/master/Final_Analysis_Notebook.ipynb)
[Random Sampling Notebook 1](https://github.com/ahendricks2/MovieBudgetOptimization/blob/master/BudgetOptimizationTests1-10.ipynb)
[Random Sampling Notebook 2](https://github.com/ahendricks2/MovieBudgetOptimization/blob/master/BudgetOptimizationTests11-20.ipynb)
[Random Sampling Notebook 3](https://github.com/ahendricks2/MovieBudgetOptimization/blob/master/BudgetOptimizationTests21-30.ipynb)
[Calclulations for Median Outcomes](https://docs.google.com/spreadsheets/d/1o0E2XP9nXAZeYJsLwtY1qCmxErmuV-2pQQFe5gnHqN4/edit?usp=sharing)
[Random Sampling Records and Calculations](https://docs.google.com/spreadsheets/d/1bQ4EyUhBwGWAohoMwtb9CEcr09r8X9TA_IXWM1Hd8Io/edit?usp=sharing)


## Overview and Business Understanding

For our second project in the Flatiron Data Science Bootcamp, my classmates and I took on the hypothetical role of consultants for a company that was opening a new movie studio and wanted to get a sense of how to make the most money in the movie business.

My overall approach to determining what types of movies would be most profitable was to address the question as a budget optimization problem. I categorized all of the films in the database as low-budget, mid-budget, or high-budget based on definitions I found online (links to sources embedded below). I then sought to answer the question of whether it would be more profitable for a studio to invest a given budget in one high-budget film or in multiple low-budget or mid-budget films. Before normalizing for budget, I used the ratio of the worldwide gross to the production budget as my main metric for profitability. After normalizing for budget, I used worldwide gross as the main profitability metric.

To do this, I used significance testing, mean and median outcomes, and random sampling; the results of the random sampling are recorded in the other notebooks in this repository as well as here.

## Data Understanding

To complete the project, I primarily used budgetary data from The Numbers, which included information about almost 6,000 films. I supplemented this data with information from IMDB to investigate the relationship between genre and profitability. I also used data from IMDB, which provided information about genres and other movie characteristics.

First, I defined budget categories based on information I found online. I defined low-budget as a budget below $5 million, high-budget as a budget above $50 million, and mid-budget as everything in between. By those definitions, the data set included 1382 low-budget films, 3192 mid-budget films, and 1208 high-budget films.

Next, because production budgets don’t include expenses like marketing or the share of revenues that goes to movie theaters or streaming services, I estimated that a movie needed to gross double its budget to be profitable based on what I could find online. I only relied on this estimate for my analysis of mean and median outcomes-- I did not rely on it when I used random sampling with replacement. By that definition, we had 526 low-budget successes, 1423 mid-budget successes, and 671 high-budget successes.


## Analysis 

A single high-budget film had the strongest median outcome in terms of gross to budget ratio, but a single low-budget film had the highest mean outcome.

![0_C4bfWySStygvlK9F](https://github.com/ahendricks2/MovieBudgetOptimization/assets/141271148/a8104d19-4fa4-4102-9d64-ac58e79f5187)

Based on those results, I investigated further to find out why the mean and median outcomes were so different and to see whether a few extremely high grossing low-budget films were skewing the mean higher. I broke down the budget categories into successes and failures based on the definitions above.

![0_7vmXNJ1jh270vol0](https://github.com/ahendricks2/MovieBudgetOptimization/assets/141271148/318506dd-52db-470b-9220-8dd0665a1fd3)

Looking at only the successes in each categories, the median outcomes now heavily favored low-budget films. While the median outcomes for failures were also the worst, the strength of the successes substantialy outweighed the strength of the failures.

I then left my analysis of individual films and returned to the original question of whether it would be better to invest in a single high-budget film, multiple mid-budget films, or a large amount of low-budget films by using the success and failure rates and the median outcomes of the successes and failures for films in each category.

![0_X7eUAVGgUO_J1Zhf](https://github.com/ahendricks2/MovieBudgetOptimization/assets/141271148/9017597b-67a5-4c0b-848b-2453da73fd10)

From this analysis, the movie student would optimize a given budget by investing in a high volume of low-budget films.

To further explore, I did a second round of analysis using random sampling with replacement. I started by selecting a random high-budget film from the data set. Then, I selected a random number of mid-budget and low-budget films so that the overall budgets of each project were within $5 million of one another. For each trial, I compared how each budget investment strategy compared to the others; in the end I compared the median outcome of each strategy.

<img width="511" alt="Screenshot 2023-11-05 195625" src="https://github.com/ahendricks2/MovieBudgetOptimization/assets/141271148/c6e5e084-32d9-483d-b6d6-ae601f1cf110">

## Results and Conclusion

“If I had said yes to all the projects I turned down, and no to all the other ones I took, it would have worked out about the same.”

–David Picker, former president and CEO of Paramount, Lorimar, and Columbia Pictures

In Leonard Mlodinow’s The Drunkard’s Walk, Mlodinow wrote about how picking whether an individual movie will be a success or a failure has about the same success rate as calling a coin flip, and he used the above quote, which he attributed to William Goldman’s Adventures in Screen and Trade, to illustrate his point.

The results of this analysis support that thinking. High-budget films had the highest odds of success, and that was only 56%. Skill is probably overrated when it comes to picking the most profitable movies.

The analysis also showed that investing in a higher volume of low-budget films, was the best investment strategy. Even by choosing films at random from a pool that contained mostly failures, the median outcome for investing a normalized budget in a high volume of low-budget films was to gross over 5x the budget.

For next steps, I would want to use a higher volume of data and to get access to a larger database of movie characteristics to do a deeper investigation into the kinds of low-budget films that would be most profitable.
