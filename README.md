# Global Life Expectancy Data Analysis

<img src="https://github.com/user-attachments/assets/cfa45bed-ad3b-4cff-bb3f-e5ae281e2a30" width="800">

An exploratory data analysis of what predicts how long people live across 179 countries, with a focus on how those factors differ in Africa! My project answers this in two parts: an exploratory data analysis followed by a regression model that tests which ones still matter when considered together. 

### Data

[Life Expectancy (WHO) Updated](https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated/data) from Kaggle, covering 179 countries from 2000 to 2015. It was compiled from the WHO Global Health Observatory, the World Bank, UN Data, and Our World in Data.

## Part 1: Overview of [my EDA Analysis](https://g5lila.github.io/life-expectancy-analysis/)

   My family in East Africa faces lots of health challenges, and so I decided to explore the bigger picture: what actually determines life expectancy, and does the answer change in Africa? In my report, I compare how socioeconomic factors like GDP and schooling stack up against health factors like immunization and disease, both globally and in Africa.

   Some takeaways include that median life expectancy in Africa is 16 years lower than in the rest of the world. Globally, schooling is the strongest correlate of life expectancy (r ≈ 0.73), but in Africa that relationship is much weaker (r ≈ 0.37), and GDP follows the same pattern. Instead, health factors like immunization and HIV incidence matter as much as or more than schooling and GDP in Africa. The most extreme adult mortality in the dataset was concentrated in Zimbabwe, Lesotho, and Eswatini between 2000 and 2007.

### Methods & Tools

- R, Quarto, RStudio, with packages like ggplot, psych, and knitr

- **Files:** 

  - `EDA_FACTORS_LIFEEXP.qmd` - Quarto source code for full analysis 

  - `EDA_FACTORS_LIFEEXP.html` - Rendered report 

  - `data/Life-Expectancy-Data-Updated.csv` - Dataset used in my analysis

### Next Steps

These findings are correlations, not causal effects. To go further, I plan to 1. run a multiple regression to find which factors stay significant when considered together and 2. address multicollinearity among the economic variables (GDP per capita, GDP category, economy status)

## Part 2: Overview of Life Expectancy Prediction with Regression 

   In Part 1, I found which factors are associated with life expectancy. In Part 2, I built a regression model to test which ones still predict it when considered together. After removing highly correlated variables (VIF > 10) and running stepwise regression, nine predictors remained, including HIV incidence, schooling, GDP per capita, BMI, and immunization.

   The best model included both interaction and squared terms. It outperformed simpler models in nested F-tests and explains about 89% of the variation in life expectancy (adjusted R² = 0.891), predicting within about 6 years of the true value. Overall, the extra terms confirmed what my EDA visualizations suggested, which is that these factors do not affect life expectancy in a straight line and often depend on each other.

## Methods & Tools

- R, RStudio, Variance inflation factor (VIF), multiple linear regression, forward and backward stepwise regression, nested F-tests (ANOVA), residual analysis

- **Files:** 

  - `presentation.pdf` - My presentation slides
    
## Concluding Comments 
   
   The regression analysis validated the main message I drew from my EDA, in that education, BMI, GDP per capita, and HIV prevalence were some of the strongest correlations on the global scale in Part 1 and all four remained in the final regression analysis model. The largest discrepancy was in the case of immunizations. In Part 1, Polio and Diphtheria were the most correlated vaccines with life expectancy, but in Part 2, I excluded them due to their high correlation with other explanatory variables, so only Hepatitis B and Measles remained in the model. Both parts show correlation, not causation, and the observations are not fully independent since each country appears once per year. This was a fun project that strengthened my understanding of how exploratory analysis and regression work together, and it gave me a better picture of the health challenges facing Africa!
