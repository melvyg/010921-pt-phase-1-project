# A Movie Success Story - An In-Depth Analysis on Successful Movies by Budgets & Genres

**Author**: Melvin Garcia

## Overview

The aim of this report is derive insights on what makes a movie successful (and is not) from data ranging between IMDB, Rotten Tomatoes, Box Office Mojo, TheMovieDB.org and the-numbers.com. These data insights / analyses on the movie industry are intended to help Microsoft stakeholders make informed decisions on different approaches to make an entryway into the movie industry. The method to observe successful movies throughout our movie database was through analyzing the profits of movies at different budget levels and genres. Profits are defined as X times the original production budget -- "how many X times in domestic and worldwide gross did a movie make over their production budget. It was observed that while the genres Action, Adventure, Comedy, Drama, and Animation generate the most revenue in worldwide gross, the most profitable movie genres are Horror, Mystery, Music, Musical and Animation. To dial down further examining the average rating for the most profitable genres -- Biography and Animation are ranked 1 & 2 respectively for the higher rated movies with the Music genre having the widest spread. As a result, it would be recommended as a start to consider a movie in these genre classes and as a follow-up investigate an appropriate movie director to reach out to for Microsoft's first movie.

## Business Problem

The current and largest pain point of Microsofts entryway into the movie industry is understanding the industry overall. If Microsoft wants to make a good first impression, one would need to understand the characteristics and blueprint of a successful movie. Although the opinion and path to producing a successful movie is subjective, to simplify our use case, we will use profits as the key performance indicator for a movie -- that is, how many more times in revenue did a movie produce worldwide and domestically over its original production budget. The amount in revenue a movie makes appears as a natural indicator for a successful movie as it can set the precedence, and budget for future movie production. 

## Data

The data pulled, queried, and scraped for this analysis range between IMDB, Rotten Tomatoes, Box Office Mojo, TheMovieDB.org and the-numbers.com. The data from these sources are relevant because they contain data points such as production budget, domestic and worldwide gross, IMDB ratings, Rotten Tomatoes ratings, directors, and genres. Specifically for the scope of this analysis, I intend to initially use the variables -- production budget, domestic and worldwide gross, and IMDB ratings. With these characteristics, I aim to observe how they trend against procured categories such as low, medium and high production budgets, and lastly how do they breakdown genre-to-genre. From these data points, I aim to understand a starting point in production budget and genre that will provide highest chance of a first successful movie from Microsoft Studios. 

## Methods

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

The two generated metrics above are used as the starting point in determining successful movies. Some questions to consider include:
1. Which production budget class is a good starting point to position Microsoft for high profits?
2. How much profits are they looking to gain? 

Based on these answers, I aim to examine which genres of movies are best to first delve into and explore.

## Results

### Visual 1
![graph5](./images/ProductionBudgetClassvsWorldwideGross.jpg)
The above is a scatter plot observing the relationship between Production Budget ($) and Worldwide gross. At the same time, the scatter plot is divided by production budget class -- Low, Medium, and High indicated by the color hue. Notably, there is a positive linear relationship between the two variables stating, the higher the production budget, the more there is generated in worldwide gross ($).

### Visual 2
![graph6](./images/ProductionBudgetClassvsWorldwideGrossRatio.jpg)
In comparison to Visual 1, the chart above examines the relationship between production budget ($) and worldwide gross-budget ratio. It can be seen between medium and high budget movies, the return on investment (ROI) ranges between 1X - 5X, with low budget movies having a range of 1X - 30X. There are two observations to be made with the low budget movies: 1. They comprise of roughly 3/4 of all movies in this analysis and 2. while low budget movies have such a large range on ROI, the majority of movies have an ROI between 1X - 10X.

### Visual 3
![graph8](./images/MedianLowBudgetWorldwideGross-BudgetRatiobyGenre.jpg)
This bar chart examines the rank of movie genres in the low budget class by their median worldwide gross-budget ratio. For the remainder of the analysis, I will focus on the top 5 genres of each budget class. In this case, the top 5 genres in the low budget class are: Mystery, History, Horrow, Music, and Thriller.

### Visual 4
![graph10](./images/MedianMedBudgetWorldwideGross-BudgetRatiobyGenre.jpg)
This bar chart examines the rank of movie genres in the medium budget class by their median worldwide gross-budget ratio. The top 5 genres in the medium budget class are: Musical, Music, Western, Biography, and Animation.

### Visual 5
![graph12](./images/MedianHighBudgetWorldwideGross-BudgetRatiobyGenre.jpg)
This bar chart examines the rank of movie genres in the high budget class by their median worldwide gross-budget ratio. The top 5 genres in the high budget class are: Crime, Biography, Animation, Adventure, and Comedy.

### Visual 6
![graph13](./images/GenreWorldwideGross-BudgetComparison.jpg)
In the visual above, five genres were selected that were common within the top 5 of median worldwide gross-budget between the budget classes. Afterwards, the genres were bootstrapped to generate a distribution over their worldwide gross-budget ratio to provide a comparison of the most profitable genres in the movie industry. The top 2 most profitable genres are Horror and Music, 1 and 2 respectively.

### Visual 7
![graph14](./images/GenreAvgRatingComparison.jpg)
Similar to visual 6, in the chart above, a similar bootstrap sampling method was employed between the top 5 genres to provide a comparison on average rating. The top 2 genres with the highest ratings are Biography and Animation, with Music having the highest spread.

## Conclusions

What I would recommend to the Microsoft stakeholders is to first question what is their expected production budget? Based on the trends, should they invest between $600,000 and $1,800,000, they can perhaps break even or 1.5 - 2 times that investment. However, should they invest less than $600,000, it is possible to double or quadruple that amount. The less money, the likelier they can multiply that investment.

Once broken down into budgets, Microsoft can then decide which genre of movie to initially explore. Based on the three paramaters of gross_budget ratio, average ratings, and popularity -- Horror and Mystery are the genres that stand out the most.

## Next Steps

Nonetheless, based on the presented analysis, these results may not fully solve the business problem as it leaves to be desired the amount of marketing involved, region specific analyses should a smaller specific release be considered. With the movie going on hold during the pandemic, what does an the avenue of online streaming look like? Lastly, the directors and production teams that best fit the Horror and Mystery genre recommendations.

In the future, I would like to further add the data in rotten tomatoes as another dimension -- ratings from audience, critics, and perhaps create a sentiment analysis using the text data. Another direction is to understand the avenue of online streaming, and profits to be made there vs in-person movie going.

## For More Information

Please review our full analysis in [our Jupyter Notebook](./0-Microsoft-Movie-Analysis.ipynb) or our [presentation](./MicrosoftMovieAnalysis_Flatiron_Presentation_MG.pdf).

For any additional questions, please contact **Melvin Garcia garciamelvin4@gmail.com**

## Repository Structure

```
├── README.md                           
├── 0-Microsoft-Movie-Analysis.ipynb  
├── MicrosoftMovieAnalysis_Flatiron_Presentation_MG.pdf
├── data
└── images
```
