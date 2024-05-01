# Baseball: On the Clock

## Analyzing the effects of the implementation of the pitch clock on pitcher's performance.

In 2023, Major League Baseball (MLB) implemented a pitch clock in an effort to speed up the pace of play during 
games. There has been ample research on how this improved the length of games and its effect on the fan experience, 
but there has not been much public research into the pitch clock’s effect on the performance of pitchers. 
Using data from the advanced statistical website Baseball Savant, I researched trends in the correlation 
of pitcher tempo to performance over the last several seasons and how this changed during the 2023 season with 
the implementation of the pitch clock. I used a few different tests to assess the statistical differences 
in pitcher tempo and performance from the pre-clock and clock eras and will use this to assess how the clock 
has affected pitchers.

Baseball Savant tracks pitchers' pace with a metric called tempo. Tempo is measured by the median seconds a pitcher
takes between pitches while the bases are empty. Using data from Baseball Savant, I compiled pitch clock data and 
performance metrics from 2015 through 2023, excluding the Covid shortened 2020 season. I also calculated the 
difference in Earned Run Average (ERA), strikeout percentage, and tempo and included those in my dataset.

Once I had my dataset, my first step was to make a linear model with the data. I created a linear model for both
ERA difference vs tempo difference and strikeout percentage difference vs tempo difference. Neither of these models
had strong correlations as indicated by their correlation coefficients of -.1383 and .1754 respectively. Thus, 
there was no correlation between a change in tempo and a change in ERA or strikeout percentage between the 2022
and 2023 seasons. 

*You can use the interactive visualization in the notebook to experiment with the correlations between different 
variables in the dataset.* 

![era v tempo final](https://github.com/nathanaelrorie/senior-project/assets/129222776/d721dba4-6d90-464b-8eb2-ab18368bfb96)
![k v tempo final](https://github.com/nathanaelrorie/senior-project/assets/129222776/47a8a73d-7af6-49a9-be50-bd64bf1b4f20)

In an effort to validate my results from the linear model, I next performed a bootstrap test. I simulated 3000 test 
statistics, which was significantly more than the number of events in my linear model. I graphed my statistics from 
the bootstrap tests, and the results were as expected. The actual median from both distributions fell right in the 
middle of my simulated distributions. Thus, we can expect our results to occur repeatedly. 

![2023 bootstrap final](https://github.com/nathanaelrorie/senior-project/assets/129222776/df1f7ffe-53e0-453b-97d5-871c254fdd24)
![diff bootstrap final](https://github.com/nathanaelrorie/senior-project/assets/129222776/dcbe08c2-7e83-422f-a959-b02b65ad2739)

To further validate my initial results, I conducted a permutation test. My null hypothesis was that the tempos from 2022 
and 2023 were the same, my alternate hypothesis was that the tempos from 2022 and 2023 were different. I took all the 
measured tempos from the two seasons and shuffled them. I took one tempo from the first half of the tempos and one from
the second half and calculated the difference between the two for the tempo difference. I simulated this result 3000 times 
and graphed the distribution of the simulated statistics. The result was that the actual median tempo difference from 2022 
to 2023 was substantially outside of the 95% confidence interval. Thus, we reject the null hypothesis that the tempos from 
2022 and 2023 are the same. This is what we expected to see with the results of our previous tests.

![perm test final](https://github.com/nathanaelrorie/senior-project/assets/129222776/2593cf04-9ee9-48ec-b394-20fac65eed08)

In conclusion, the implementation of the pitch clock was a very controversial event that received push back from several
pitchers. However, it did not have a statistically significant impact on the performance of pitchers across MLB. There are 
a few performance outliers in the dataset that could have been attributed to the clock, but with a large enough population,
they were not impactful. With the benefits of the pitch clock on pace of play already well documented, the implementation 
in 2023 appears to have little negative effect on the game from a pitcher performance perspective.


***Note*** There are several code blocks toward the end of the notebook that seemingly don't create anything. I am in the 
process of working on a dashboard, but have yet to get all the pieces together. Feel free to try and put them together
yourself or to create your own dashboard with the data.
