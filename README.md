# Title

**Authors**: Student1, Student2

## Overview

A one-paragraph overview of the project, including the business problem, data, methods, results and recommendations.

The aim of this report is derive insights on what makes a movie successful (and is not) from data ranging between IMDB, Rotten Tomatoes, Box Office Mojo, TheMovieDB.org and the-numbers.com. These data insights / analyses on the movie industry are intended to help Microsoft stakeholders make informed decisions on how to make an entryway into the movie industry. By exploring, and analyzing the trends, and categories of successful and not successful movies in the industry, the takeaway for our Microsoft stakeholders is to empower them with data these insights to strategically position themselves to create their own movie studio. The method to observe successful movies throughout our movie database was through analyzing the profits of movies at different budget levels and genres. Profits are defined as X times the original production budget -- "how many X times in domestic and worldwide gross did a movie make over their production budget. It was observed that while the genres Action, Adventure, Comedy, Drama, Thriller generate the most revenue in domestic and worldwide gross, the most profitable movie genres are Horror, Mystery, Documentary, Sport and Romance. To dial down further examining the average rating for the most profitable genres -- Horror and Romance 1 & 2 respectively for the higher rated movies with documentaries having the widest spread. As a result, it would be recommended as a start to consider a movie in these genre classes and as a follow-up investigate an appropriate movie director to reach out to for Microsoft's first movie.

## Business Problem

Summary of the business problem you are trying to solve, and the data questions that you plan to answer in order to solve them.

***
Questions to consider:
* What are the business's pain points related to this project?
* How did you pick the data analysis question(s) that you did?
* Why are these questions important from a business perspective?
***
The current and largest pain point of Microsofts entryway into the movie industry is understanding the movie industry overall. If Microsoft wants to make a good first impression, one would need to understand the characteristics and footsteps of a successful movie. Although the opinion and path to producing a successful movie is subjective, to simplify our use case, we will use profits as the key performance indicator for a movie -- that is, how many more times in revenue did a movie produce worldwide and domestically over its original production budget. The amount in revenue a movie makes appears as a natural indicator for a successful movie as it can set the precedence, and budget for future movie production. 

## Data

Describe the data being used for this project.

***
Questions to consider:
* Where did the data come from, and how do they relate to the data analysis questions?
* What do the data represent? Who is in the sample and what variables are included?
* What is the target variable?
* What are the properties of the variables you intend to use?
***

The data pulled, queried, and scraped for this analysis range between IMDB, Rotten Tomatoes, Box Office Mojo, TheMovieDB.org and the-numbers.com. The data from these sources are relevant because they contain data points such as production budget, domestic and worldwide gross, IMDB ratings, Rotten Tomatoes ratings, directors, and genres -- all of which are essential to help dissect the characteristics of successful and unsuccessful movies. Specifically for the scope of this analysis, I intend to initially use the variables -- production budget, domestic and worldwide gross, and IMDB ratings. With these numeric variables, I aim observe how they trend against procured categories such as low, medium and high production budgets, and lastly how do they breakdown genre-to-genre. From these data points, I aim to understand a starting point in production budget and genre that will provide highest chance of a first successful movie from Microsoft Studios. 

## Methods

Describe the process for analyzing or modeling the data. For Phase 1, this will be descriptive analysis.

***
Questions to consider:
* How did you prepare, analyze or model the data?
* Why is this approach appropriate given the data and the business problem?
***

The main tables used in this analysis were imdb_title_basics, tn_movie_budgets, bom_movie_gross, tmdb_movies, and imdb_title_ratings. Since there are no unique keys that already exist between these tables, I created a key combination of movie title + year to join these tables through. However, this method assumes that no two movies of the same name are produced in the same year. Moreover, after joining the tables on this generated key -- the essential data points to consider include:
* production_budget
* domestic_gross
* worldwide_gross
* averagerating (imdb)
* popularity

The categorical variables to consider are 
* production budget binned between low, medium and high
* genre_label

Between production_budget, domestic_gross, and worldwide gross, these data points were combined to generate a profit ratio -- that is:
* domestic_gross_budget_ratio = domestic_gross / production budget
* worldwide_gross_budget_ratio = worldwide_gross / production_budget

The two generated metrics above are used as the starting point in determining successful movies -- which production budget class is a good starting point to position Microsoft for high profits, also how much profits are they looking to gain? Based on these answers, which genres of movies are best to first delve into and explore, thus set up next steps on finding the appropriate director, given the budget.

## Results

Present your key results. For Phase 1, this will be findings from your descriptive analysis.

***
Questions to consider:
* How do you interpret the results?
* How confident are you that your results would generalize beyond the data you have?
***

Here is an example of how to embed images from your sub-folder:

### Visual 1
![graph1](./images/domestic_gross.jpg)

### Visual 2
![graph2](./images/median_domestic_gross_ratio_bar.jpg)

### Visual 3
![graph3](./images/worldwide_gross_bar.jpg)

### Visual 4
![graph4](./images/median_worldwide_gross_ratio_bar.jpg)

### Visual 5
![graph5](./images/ProductionBudgetClassvsWorldwideGross.jpg)

### Visual 6
![graph6](./images/ProductionBudgetClassvsWorldwideGrossRatio.jpg)

### Visual 7
![graph7](./images/MovieGenreWorldwideProfits_LowBudget.jpg)

### Visual 8
![graph8](./images/MedianLowBudgetWorldwideGross-BudgetRatiobyGenre.jpg)

### Visual 9
![graph9](./images/MovieGenreWorldwideProfits_MedBudget.png)

### Visual 10
![graph10](./images/MedianMedBudgetWorldwideGross-BudgetRatiobyGenre.jpg)

### Visual 11
![graph11](./images/MovieGenreWorldwideProfits_HighBudget.png)

### Visual 12
![graph12](./images/MedianHighBudgetWorldwideGross-BudgetRatiobyGenre.jpg)

### Visual 13
![graph13](./images/GenreWorldwideGross-BudgetComparison.jpg)

### Visual 14
![graph14](./images/GenreAvgRatingComparison.jpg)

### Visual 15
![graph15](./images/GenrePopularityRatingComparison.jpg)

## Conclusions

Provide your conclusions about the work you've done, including any limitations or next steps.

***
Questions to consider:
* What would you recommend the business do as a result of this work?
* What are some reasons why your analysis might not fully solve the business problem?
* What else could you do in the future to improve this project?
***

What I would recommend is for first the Microsoft stakeholders to question what is their expected production budget? Based on the trends, should they invest between $600,000 and $1,800,000, they can perhaps break even or 1.5 - 2 times that investment. However, should they invest less than $600,000, it is possible to double or quadruple that amount. The less money, the likelier they can multiply that investment.

Once broken down into budgets, Microsoft can then decide which genre of movie to initially explore. Based on the three paramaters of gross_budget ratio, average ratings, and popularity -- Horror and Mystery are the genres that stand out the most.

Nonetheless, based on the presented analysis, these results may not fully solve the business problem as it leaves to be desired the amount of marketing involved, region specific analyses should a smaller specific release be considered. With the movie going on hold during the pandemic, what does an the avenue of online streaming look like? Lastly, the directors and production teams that best fit the Horror and Mystery genre recommendations.

In the future, I would like to further add the data in rotten tomatoes as another dimension -- ratings from audience, critics, and perhaps create a sentiment analysis using the text data. Another direction is to understand the avenue of online streaming, and profits to be made there vs in-person movie going.

## For More Information

Please review our full analysis in [our Jupyter Notebook](./dsc-phase1-project-template.ipynb) or our [presentation](./DS_Project_Presentation.pdf).

For any additional questions, please contact **name & email, name & email**

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
