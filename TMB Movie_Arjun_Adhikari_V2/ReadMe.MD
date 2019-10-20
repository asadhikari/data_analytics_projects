## Project Summary 

__In this analysis I determined what attributes make a movie successful.__ 

<img src="Images/Movie_Genre_WordCloud.png" width=400>

### Data Cleanup 
1. The data was cleaned up to drop any missing values, non-necessary columns and any budget or revenue values that contained zero. This dropped down the number of movies from >10,000 down to 3853. 
    1. Though this resulted in loss of >50% of the original data, there dataset is significantly large enough to analyze. 
    2. Further cleaning was done on one outlier, the movie "The Warrior's Way". The budget of the movie was reported incorrectly, and this was corrected (Budget for a warrior's way https://en.wikipedia.org/wiki/The_Warrior%27s_Way)
    3. The profit for the movies was calculated using the budget_adj and revenue_adj. The profit is the correct metric (compared to the revenue to judge the box office success of a movie). __Also, it is essential to realize that the _adjusted budget and revenue_ should be used for analysis, because these take inflation into account.__
    
### Analysis and limitation 
1. __Pandas hist() function, and seaborn pairplots()__ were utilized to see any obvious correlations, and were used as the basis of further investigation. 
    1. The revenue has a positive correlation with budget, vote_average, vote_count, and popularity. 
    2. The release year also seems to be correlated to the budget, vote count and popularity. 
    3. __Limitation__ - Though these plots are good for cursory analysis, they do not provide many quantitative insights and other methods need to be used. 

2. __The number of movies made per decade have increased with time.__

3. __Budget, profit, vote count and popularity of the movies were investigated as a function of time using seaborn barplots and boxplots__
    1. __Adjusted budget vs time__:  We see that after 1960s, there was a fall in the average budget for the next two decades, but the recent decades have seen a higher average spending. Looking at the box plot that has all the data, this is primarily due to the rise in high budget movies in recent years. _Conclusion: Increase in the number of high budget movies in the recent years is leading to an increased average budget_

    2. __Profit vs time__: Here we see that the average profit was higher in the 60's and 70's. However, if we look at the box plot, we see that we have a lot of outliers for the recent decades, suggesting that there are more movies that are making really big profits. 
        1. To confirm this, I looked at the number of movies making >500M. When we plot this data, we can clearly see that over time, the number of highly profitable movie increases. 
        2. _Conclusion: Though the average profit may have gone down over the decades, we are getting more and more movies that are highly profitable._
    
    3. __Vote count and vote average vs time__: Here from both the box and bar plots we see that the count of votes increase over time. However, the average vote (or rating) of the movie doesn't change. _Conclusion: There is an increase number of votes, possibly due to the increase in internet usage and social media, but the average perceived quality of the movies have not changed_. 

    4. __Popularity vs time__: We see that there is a significant increase in the 2010's, and this is mostly due to some really popular movies in this time (Boxplot), which skew the mean. _Conclusion: There have been more really popular movies in 2010's compared to the rest of the decades_. 
    5. __Limitations of analysis__: 
        1. Even though the boxplot gives use the whole data, it is sometimes hard to interpret data with a large number of outliers, because the axis are squeezed. 
        2. The barplot gives only the average, and singular events maybe lost. 
        3. IMPORTANT: A combination of box and bar plots should be used to better analyze both, the means of the data, and the spread of the data. 

4. __Relationship between profit and vote_count, popularity, budget, vote_average__
    1. Popularity, budget, vote_count and vote_average are positively correlated to profit
    2. The year does not correlate with profit 
    3. __Limitations__:  Although the correlation is positive, but the R squared value is on the order of 0.5, which is not a very strong correlation. This will be the case with such large datasets, and sometimes it's hard to find very quantitative relationships. Therefor for this analysis, we cannot say that "_if a movie's budget was x, then the profit would be y_", we can only draw qualitative correlations. 
    
5. __Effect of month on the success of movie__
    1. An analysis of profit and popularity shows that June and Decemeber are the best months to release a movie 
    2. This is probably because these coincide with vacations and holidays 
    
6. __Non-quantitative attributes of a successful movie__
    1. For this analysis, only box-office hit movies (profit >500M) were considered. 
        1. Steven Spielberg is the most successful director, with 10 movies with 500M+ profit 
        2. Adventure and Action are the most popular genre for successful movies. 
             1. __Limitation__: This is not the most popular genre of movies. However, the aim of this project is to find out what are the attributes of successful movies, not just movies. 

7. Challenges: The biggest challenge was the data cleanup, and dealing with columns, such as genre, that had multiple values, and getting them to a more analytical friendly form. 

8. __Additional data__: As we progress into the digital age, it was be interesting to analyze
    1. The age group of the viewers
    2. Release channels: Theaters, Netflix, Amazon
    3. Most frequent media channel (Theaters, Netflix, Amazon) used to watch the movie, and associated revenue. 
    4. Number of viewers in the movie theaters, and the total number of viewers. 

