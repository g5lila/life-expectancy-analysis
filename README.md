# Global Life Expectancy Data Analysis
A statistical analysis identifying key predictors of global life expectancy

Life expectancy, the average amount of years a person is expected to live, is crucial to assessing population health. A measure of who we are, how we live, and what shapes a healthy life. In our global health class, we learn about life beyond just being a health metric, as it ties to policy-making, healthcare investment, community/schooling environments, and resource allocation. With this in mind, we wanted to look at all these factors and conduct a statistical analysis on its many factors. 

Most studies undertaken in the past on factors affecting life expectancy considers primarily demographic variables, income composition and mortality rates. This Life Expectancy dataset we have found from WHO (World Health Organization) goes beyond. 
It takes into account factors like the HDI, which is a holistic measure assessing country development (using not only economic growth but also average annual income, education and more). 
Also this dataset includes immunization factors like Polio and Hepatitis B, which is important because 
Plus, most of these studies relied on single-year global data. This dataset spans from 2000 to 2015.
Our data consists of about 179 countries from (as mentioned from) the years 2000-2015. There are originally 21 variables and 2,864 rows to start with.
Our primary question was:  What are the most decisive predictive factors influencing global life expectancy?

We removed four variables: Country, Region, Year, and Economy_status_Developing/Economy_status_Developed. 
While the country or region associated with each data row could be valuable for geographical analysis, these variables do not directly contribute our research question! We want to understand the statistical relationships between key health and socioeconomic factors affecting life expectancy. Categorical variables like this don’t directly influence it.
Logically, adult_mortality was removed as well

To start we began with preliminary data exploration. From plotting one can see that:
Schooling, GDP_per_capita, and Diphtheria-> a positive (ish) correlation with life expectancy, suggesting that higher levels of these factors contribute to longer lives
Some variables, like Population_mln, show weak or inconsistent relationships, indicating they may have limited direct influence on life expectancy.

Then we looked at the correlation of this to double check. Testing the correlation between a few of the variables and Life Expectancy have shown that this dataset will be useful to test the influence of predictive factors on Life Expectancy.
