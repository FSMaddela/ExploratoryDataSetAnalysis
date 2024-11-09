
# Exploratory Data Set

Hi! This is a project that shows my mastery of data wrangling and analysis using PANDAS. NUMPY, SEABORN, and MATPLOTLIB. It involves the use of several basic and advanced python programming techniques that I've accumulated throughout the first semester.

## Table of Contents
- [Part I - Overview](#part-i---data-set-overview)
- [Part II - Basic Descriptive Statistics](#part-ii---basic-descriptive-statistics)
- [Part III - Top Performers](#part-iii---top-performers)
- [Part IV - Temporal Trends](#part-iv---temporal-trends)
- [Part V - Genre and Music Characteristics](#part-v---genre-and-music-characteristics)
- [Part VI - Platform Popularity](#part-vi---platform-popularity)
- [Part VII - Advanced Analysis](#part-vii---advanced-analysis)

# Part I - Data Set Overview
In the first part of the data analysis, we go through the overview of the data set. By simply calling our data set using `pd.read_csv` we can already see the dimensions of the data frame. In which case it is 953 rows long and 24 columns wide.

Next we need to find any missing values, this is also fairly simple as python has a built in function for finding NaN variables within a given data. We just need to utilize the `isna()` function which returns a data frame where missing variables are set to True while filled variables are set to False.

Given that we now have a data frame with only boolean values (True and False) and since these two values are simply 1s and 0s, we can find the sum of each column to see how many missing variables we have.

# Part II - Basic Descriptive Statistics
For the second part, we are tasked to find the mean, median, and standard deviation of the `streams` column from the data set.

This is easily done using the built in functions for the mean, median, and standard deviation. These being `mean()`, `median()`, and `std()`. One problem I had encountered however, was that the values in the `streams` column weren't numeric but strings. And these functions would only take numeric values which meant that I had to convert the string values into numeric data types.

Through the use of `pd.to_numeric` I was able to easily change the data type of the values which allowed me to find the mean, median, and standard deviation of the `streams` column.

Next, we needed to find if there are any noticeable trends and outliers for the artist count and release year. To do this I opted to create a line plot using SEABORN which shows me how many artists are involved on the release of tracks per year. This showed that 4 artist groups where mainly prominent during the 1970s and during the 2000s it was a mixed bag averaging out to 2 artists.

# Part III - Top Performers
The third part involves finding the top 5 most streamed songs on the data set and the 5 most frequent artist appearing on the data set.

To find the top 5 most streamed songs I only had to sort the data set from most streams using `.sort_values(ascending=False, by=['streams'])`, what this does is sort the streams from descending order. After sorting the data, I then used the `.head()` function to show the first 5 values on the sorted data set. This is convenient since if I wanted to show more than 5 values I can just change the number inside the parentheses to the amount I needed.

Next, to find the 5 most frequent artist on the data set, I had to use the function `value_counts()`, this counts how many times a specific variable had appeared on the data set and sorts them by the most number of times they've appeared. After sorting the data set, I then used the `.head()` function one again to show the first 5 values.

# Part IV - Temporal Trends
The fourth part required the analysis of trends over time. I decided to use a line plot once again as I thought that it would be the best graph to visualize trends over a given time period. Using SEABORN once again, I was able to create a line plot of the number of tracks (y-axis) and the years (x-axis) from which we can see that during the 2020s there was a massive spike in the number of tracks made.

The second part of the analysis requires a comparison between the number of tracks (y-axis) and the months ( x-axis). For this one I had to change the plot a bit since the x-axis would only show values in increments of 2. To remedy this I manually changed the values of the x-axis with numbers from 1-12 representing each month of the year. 

Interestingly, there was a common trend regarding the release month of a track and whether it appears on the top charts. Tracks made on January and May made it into the charts more often than others, while tracks made in August barely made it in the charts. 

# Part V - Genre and Music Characteristics
The fifth part needed an analysis of the correlation between streams and specific characteristics of the tracks. I had to use the `.corr` function here and create a correlation matrix as that was the only option I had found that would be able to represent the correlation between multiple variables.

From the correlation matrix I was able to find that all of the characteristics did not contribute to higher streams, with some such as danceability having an inderect correlation. This could be due to how people have different tastes in music. 

However, there were correlations between other characteristics, an example being danceability and energy, where I found that danceability correlated to energy. Other characteristics were too insignificant to conclude anything.

# Part VI - Platform Popularity
The sixth part involved checking which platform was the most popular. To do this I obtained the sum of all variables from each platform then compared them from each other. Although it seemed like such a simple way of doing it I found that it represented how many users have added the song to which playlist. After comparing the sums, I concluded that the most popular was spotify playlist beating out other platforms by millions.

# Part VII - Advanced Analysis
The seventh and final part of the analysis required checking for trends within keys and modes to the number of streams. To accomplish this, I had to group each keys and modes using the `.groupby()` function, then find the mean of the grouped keys and modes. 

I then sorted the results in descending order and found that songs that are in the key of C# were streamed more times than other keys and songs that are in the mode of Major were streamed more than songs in Minor.

# Conclusion
In this project I was able to brush up on my programming skills and learn more syntax as well. I was able to use functions that I had found no use for before and even some that I've rarely ever used. Data analysis and Wrangling is an important skill that has many real world applications, this much was apparent. If I were to look into the data one variable to another, it would take me ages just to find trends, outliers, or correlations between them. Knowing how to program makes it a lot easier to analyze sheets of raw data. This project shows just how powerful data analysis is in discovering patterns and trends in large data sets.

