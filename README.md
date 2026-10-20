# Global Life Expectancy Data Analysis

<img src="https://github.com/user-attachments/assets/cfa45bed-ad3b-4cff-bb3f-e5ae281e2a30" width="800">

An exploratory data analysis of what predicts how long people live across 179 countries, with a focus on how those factors differ in Africa! My project answers this in two parts: an exploratory data analysis followed by a regression model that tests which ones still matter when considered together. 

## Data

[Life Expectancy (WHO) Updated](https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated/data) from Kaggle, covering 179 countries from 2000 to 2015. It was compiled from the WHO Global Health Observatory, the World Bank, UN Data, and Our World in Data.

## Part 1: Overview of [my EDA Analysis](https://g5lila.github.io/life-expectancy-analysis/eda_report/EDA_FACTORS_LIFEEXP.html)

   My family in East Africa faces lots of health challenges, and so I decided to explore the bigger picture: what actually determines life expectancy, and does the answer change in Africa? In my report, I compare how socioeconomic factors like GDP and schooling stack up against health factors like immunization and disease, both globally and in Africa.

   Some takeaways include that median life expectancy in Africa is 16 years lower than in the rest of the world. Globally, schooling is the strongest correlate of life expectancy (r ≈ 0.73), but in Africa that relationship is much weaker (r ≈ 0.37), and GDP follows the same pattern. Instead, health factors like immunization and HIV incidence matter as much as or more than schooling and GDP in Africa. The most extreme adult mortality in the dataset was concentrated in Zimbabwe, Lesotho, and Eswatini between 2000 and 2007.

## Methods & Tools

- R, Quarto, RStudio, with packages like ggplot, psych, and knitr

- **Files:** 

  - `EDA_FACTORS_LIFEEXP.qmd` - Quarto source code for full analysis 

  - `EDA_FACTORS_LIFEEXP.html` - Rendered report 

  - `data/Life-Expectancy-Data-Updated.csv` - Dataset used in my analysis

## Next Steps

These findings are correlations, not causal effects. To go further, I plan to 1. run a multiple regression to find which factors stay significant when considered together and 2. address multicollinearity among the economic variables (GDP per capita, GDP category, economy status)

## Part 2: Overview of Life Expectancy Prediction with Regression 

   Previously, I explored which factors are actually associated. Now, I build a regression model to test which factors still predict life expectancy when they are all considered together. We first used a variance inflation factor (VIF) test to address multicollinearity, which flagged infant deaths, under-five deaths, Diphtheria, and Polio (VIF > 10), so we removed them. Our first-order model with the remaining 10 predictors was statistically useful (global F-test, p < 2.2e-16), and forward and backward stepwise regression both removed alcohol consumption (p = 0.78). That left nine predictors: Hepatitis B, Measles, BMI, HIV incidence, GDP per capita, population, thinness among children aged 5–9 and adolescents aged 10–19, and schooling.

   We then compared four models using nested F-tests: a first-order model, a second-order model with only interaction terms, a second-order model with only squared terms, and a complete second-order model with both. The complete second-order model outperformed every other model (p < 2.2e-16 in each comparison) and explains about 89% of the variation in life expectancy (adjusted R² = 0.891), predicting within about 6 years of the true value. A residual analysis showed the residuals were approximately normal, with mild signs of uneven variance that did not invalidate the model.

## Methods & Tools

- R, RStudio, Variance inflation factor (VIF), multiple linear regression, forward and backward stepwise regression, nested F-tests (ANOVA), residual analysis

- **Files:** 

  - `presentation.pdf` - My presentation slides
    
## Concluding Comments 

   The regression confirmed the main story from Part 1. HIV incidence, schooling, GDP per capita, BMI, thinness, and immunization all stayed in the final model, so the factors that looked important in the exploratory analysis held up when tested together. The regression also helped explain a pattern that Part 1 could only show visually. In Part 1, the relationship between GDP and life expectancy curved and leveled off at higher incomes, and in Part 2, adding squared and interaction terms significantly improved the model, confirming that these factors do not affect life expectancy in a simple straight line and often depend on each other.

   The two parts also differ in an important way. Part 1 focused on how Africa compares to the rest of the world, while the regression model was built on global data. A natural next step would be to fit the model separately for Africa and the rest of the world to test whether the differences found in Part 1 hold up in a full model. Both parts share the same limitation: they show statistical associations, not causal effects, and because each country appears once per year, the observations are not fully independent.
