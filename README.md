# TMDb-analysis
# Project: TMDb Movie Data

## Table of Contents
<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#wrangling">Data Wrangling</a></li>
<li><a href="#eda">Exploratory Data Analysis</a></li>
<li><a href="#limitations">Limitations</a></li>
<li><a href="#conclusions">Conclusions</a></li>
</ul>
<a id='intro'></a>

## Introduction

> This project outlines the data analysis process with the selected data set: TMDb Movie Data. This data set contains almost 10,000 movies collected from The Movie Database, with information such as popularity, budget/revenue, genre, release year, and user ratings. 
>
> After wrangling and cleaning the data, I will explore the data with regard to two main questions:
>> 1) Which genres are most popular? Which genres are most popular over time?
>
>> 2) Are there any strong relationships associated with the adjusted revenue?

<a id='wrangling'></a>
## Data Wrangling
> In the data wrangling process, I looked at various metrics to get a quick sense of the data and what needed to be cleaned. For instance, there were columns such as id, tagline, overview, homepage, and others which were not necessary for my analysis so I removed them. 

<a id='eda'></a>
## Exploratory Data Analysis

> The exploratory data analysis process involved asking multiple questions to take a deeper dive into the data.

### Question 1: Which genres are most popular? Which genres are more popular over time?
**Part 1: Which genres are most popular?**

**Part 2: Which genres are more popular over time?**

### Question 1 Summary: 

**Part 1**: After simplifying the "Genres" column to show only the first genre when more than one was listed, and removing genre categories that had less than 100 movies, the genres that appear to have the highest popularity are "Adventure" and "Science Fiction".

**Part 2**: After categorizes the movies into two time periods based on the median release_year (pre_2005 and post_2005), and plotting the genres and popularty next to each other, the pre_2005 and post_2005 most popular genre appears to be "Adventure".

### Question 2: Are there any strong relationships associated with the adjusted revenue?

### Question 2 Summary: 

The strongest correlations with revenue_adj that can be deduced from the plots and from the correlation matrix are:
    
    vote_count (0.66)
    
    budget_adj (0.59)
    
    popularity (0.56)
    
This method, however, is not conclusive enough to assume causation. They simply show some association.

<a id='limitations'></a>
## Limitations

> 1) For Question 1, **Which genres are most popular? Which genres are most popular over time?**, because there were genres that were discarded due to small sizes and therefore potentially inaccurate data, it is not enough to conclude that Adventure and Science Fiction are the most popular genres without looking at all genres available. Additionally, there were many movies that had more than one genre listed, and my analysis involved only looking at the first one, therefore there might be some debate about which genres are actually appropriate for each title. Lastly, my decision to use the median release_year of 2005 as the point in which to split the data to look at how genre popularity has changed over time could be considered an arbitrary selection might not actually reflect the true changes over time.
>
> 2) For Question 2,  **Are there any strong relationships associated with the adjusted revenue?** dropping 5,022 rows where revenue_adj was zero, is a significant amount to discard. Given that revenue information was either not available or was inaccurate to begin with, this will likely have a large impact on the results of the analysis. I believe that this way is a better way to handle the missing data rather than attribute values that I am not able to accurately predict. Given these limitations, it is difficult to find accurate correlations.

<a id='conclusions'></a>
## Conclusions

> After working through the data analysis process of wrangling and exploring, and taking the limitations above into consideration, the following conclusions can be made regarding The Movie Database data set:

>> 1) The most popular genres of the total dataset appear to be Adventure and Science Fiction. When looking at the genre popularity over time, Adventure appeared to be the most popular pre-2005 and post-2005 genre.
>
>> 2) A higher Adjusted Revenue is correlated with Vote Count, Adjusted Budget, and Popularity. This however does not indicate causation by any of these variables, as there are limitations with only looking at scatterplots and correlation matrixes.
