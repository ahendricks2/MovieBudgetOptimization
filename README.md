# Movie Budget Optimization Project

October 2023

Andrew Hendricks (AndrewHHendricks@gmail.com)

Links to Notebooks and Documents:

Analysis Notebook
Random Sampling Notebook 1
Random Sampling Notebook 2
Random Sampling Notebook 3
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



## Results and Conclusion

“If I had said yes to all the projects I turned down, and no to all the other ones I took, it would have worked out about the same.”

–David Picker, former president and CEO of Paramount, Lorimar, and Columbia Pictures







High-budget films have the best odds of reaching profitability and the best median outcomes, but the mean for low-budget films is through the roof. The mean is more influenced by outliers, so maybe a few highly successful low-budget films are skewing that measure?

Also, Mlodinow’s coin flip analogy is looking downright generous after seeing that chart. Our best odds come from high-budget films, which give us a 56% chance of success. Low-budget and mid-budget films are both worse than 50–50. That should give us some pause about the role of skill in picking which films will succeed on a film to film basis.

Note: If you are a movie executive who would like to hire me as a consultant, you are almost certainly the skillful exception.

Let’s dig a little deeper.

How big are the gains when films from each budget category do succeed and how bad are the failures when they fail?


This may help explain the difference between the median and mean that we found before. It wasn’t just a few outliers pulling the mean upwards: low-budget films may have the lowest odds of succeeding, but when they do, they tend to crush it. Their failures are also the worst of the three budget categories, but because their wins tend to be so much bigger than their losses, they may be a pretty good investment.

Now, for the last step.

We have been studying films on a one-to-one basis so far, but remember: we can afford to make a whole lot of low-budget films for the cost of one high-budget film. The one-to-one comparison between low-budget and high-budget films does not account for the remaining budget we have if we choose the low-budget film, so let’s move on to a comparison based on normalized budgets instead.

We can use the calculations we have made in the previous steps to multiply the median number of successes and failures for each budget group by the median gross to budget ratios to determine the median outcome for each $80 million investment. Let’s see what happens.


If you originally chose to invest in the low-budget films, you can give yourself a pat on the back.

Based on median outcomes, investing in a higher volume of low-budget films was easily the best investment.

Let’s take this a step further, though.

Remember, this analysis relied on defining success as gross doubling profit, which was just an estimate. Our analysis also treated everything as a median outcome. In real life, the median outcome doesn’t occur every time; things are messier.

Let’s test this out for a second time but in a different way.

Imagine a movie studio has three executives. All of them are purists who only select movies in the budget category they prefer. Also, they value work life balance, so they make all their decisions randomly.

First, Holly Highbudget picks a high-budget movie to greenlight. Then Melinda Midbudget and Lisette Lowbudget can make as many movies as they want within their budget category as long as the overall budget of their projects falls within $10 million of Holly’s budget.

During the few hours they spend in the office, they compete to see who can pick the movies with the best gross to budget ratio.

Let’s see how they do!

We will give each of them 30 opportunities to try their luck.


Lisette, you’re a genius!

The median outcome of picking the high volume of low-budget films was that the films collectively grossed a colossal 519% of their overall budget.

There are some interesting differences between the two analyses. Even though they were the best choice based on both methods, low-budget films performed substantially better in the second analysis than they did in the first. Also, mid-budget films moved from the third place to second as we shifted from analysis one to analysis two.

Some of these discrepancies can be attributed to the estimates we used for profitability.

We also noticed that the median was far more pessimistic about low-budget films than the mean was. Using the median as the basis of our analysis still worked out better than using the mean would have, but maybe the median was underrating low-budget films in the first analysis.

By the way, why were the median and the mean so different? Let’s take a look at the distribution of the GTB data.


It’s not exactly a linear relationship. The median reduced the impact of all those very high values in the lowest budget films. The mean didn’t.

There are also a number of limitations to this analysis.

Two of the biggest ones are that it is based on only 5,782 movies, and it does not account for marketing expenses, distribution shares, or the maximum number of films a studio can produce at a time.

The size of the data set leads to a third problem: after cleaning, there was an insufficient number of films remaining to analyze whether things like the genre or run time of low-budget films could impact the odds of success or median outcomes. It would be nice to try to do better than random picking even though that did work out pretty nicely.

If I were going to do a follow up analysis to this study, I would want to address these limitations by investing in a more robust data source.

Still, based on this data, there are some pretty strong takeaways.

First, movie executives should think probabilistically. High-budget films had the highest odds of success, and that was only 56%. Stick to the Mlodinow Principle: picking whether an individual film will be profitable is about the same as calling heads or tails. Don’t overrate skill.

Second, investing in more lower-budget films tends to work better than investing in fewer higher-budget films. The median outcomes come out better, but the strategy also allows you to diversify your investment and protect against the variability inherent in the business. In my sample test, high budget films failed to gross double their budget 43% of the time, almost exactly the same as the 44% fail rate that the median outcomes predicted. Low-budget films failed to reach that threshold just once, or 3% of the time. There’s a reason why Netflix is doing this.

Finally, give your data people the budget to get the good data behind the paywall.

And give them a raise while you’re at it.
