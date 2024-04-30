# Baseball: On the Clock

## Analyzing the effects of the implementation of the pitch clock on pither's performance.

In 2023, Major League Baseball implemented a pitch clock in an effort to speed up the pace of play of games. 
There has been ample research on how this improved the length of games and its effect on the fan experience, 
but there has not been much public research into the pitch clock’s effect on the performance of pitchers. 
Using data from the advanced statistical website Baseball Savant, I researched some trends in the correlation 
of pitcher tempo to performance over the last several seasons and how this changed during the 2023 season with 
the implementation of the pitch clock. I have used a few different tests to assess the statistical differences 
in pitcher tempo and performance from the pre clock and clock eras and will use this to assess how the clock 
has effected pitchers.

Baseball Savant tracks pitchers pace with a metric called tempo. Tempo is measured by the median seconds a pitcher
takes between pitches while the bases are empty. Using data from Baseball Savant, I compiled a dataset of pitch clock
data and performance metrics from 2015 through 2023, excluding the Covid shortened 2020 season. I also calculated
the difference in ERA, Strikeout percentage, and Tempo and added those to my dataset.

Once I had my dataset, my first step was to make a linear model with the data. I created a linear model for both
ERA difference vs empo difference and strikeout percentage difference vs tempo difference. Neither of these models
had strong correlations as indicated by their correlation coefficients of -.1383 and .1754 respectively. Thus, 
there was no correlation between a change in tempo and a change in ERA or strikeout percentage between the 2022
and 2023 seasons. 

In an effort to confirm my results from the linear model, I decided to next perform a bootstrap test. For my bootstrap
tests, I simulated 3000 test statistics. This was significantly more than the number of events in my linear model. 
I graphed my statistics from the bootstrap tests, and the results were as expected. The actual median from both 
distributions fell right in the middle of my simulated distributions. Thus, we can expect our results to occur repeatedly. 

To further confirm my initial results, I conducted a permutation test. My null hypothesis was that the tempos from 2022 
and 2023 were the same, my alternate hypothesis was that the tempos from 2022 and 2023 were different. I took all the 
measured tempos from the two seasons and mixed them up. I took one tempo from the first half of the tempos and one from
the second half and calculated the difference between the two for the tempo difference. I simulated this result 3000 times.
I graphed the distribution of simulated statistics. The result was that the actual median tempo difference from 2022 to 2023
was way outside of the 95% confidence interval. Thus, we reject the null hypothesis that the tempos from 2022 and 2023 are 
the same. This is what we expected to see with the implementation of the pitch clock.

In conclusion, the implementation of the pitch clock was a very contreversial event that received a lot of push back several
pitchers. However, it did not have a significant impact on the performance of pitchers across MLB. There are a few performance 
outliers in the dataset that could have been due to the clock, but there is no way to know for sure. With the benefits of the
pitch clock on pace of play already well documented, the implementation of the pitch clock in 2023 appears to have little 
negative effect on the game.
