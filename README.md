# Global Life Expectancy Data Analysis

<img src="https://github.com/user-attachments/assets/cfa45bed-ad3b-4cff-bb3f-e5ae281e2a30" width="800">

An exploratory data analysis of what predicts how long people live across 179 countries, with a focus on how those factors differ in Africa.
Project was completed in 2024.

 [https://g5lila.github.io/life-expectancy-analysis/EDA_FACTORS_LIFEEXP.html](https://g5lila.github.io/life-expectancy-analysis/EDA_FACTORS_LIFEEXP.html)

## Overview

My family in East Africa faces health challenges ranging from limited healthcare access to malnutrition and infectious disease. That made me curious about the bigger picture: what actually determines life expectancy, and does the answer change in Africa? In my report, I compare how socioeconomic factors like GDP and schooling stack up against health factors like immunization and disease, both globally and in Africa. Key findings include a 16-year gap in median life expectancy between Africa and the rest of the world, with schooling as the strongest global correlate (r ≈ 0.73). In Africa, however, health factors like immunization and HIV incidence matter as much as or more than schooling and GDP, which are much weaker predictors there. 

## Methods & Tools

- **Languages & tools:** R, Quarto, RStudio, with packages like ggplot, psych, knitr, etc. 

- **Data:** [Life Expectancy (WHO) Updated](https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated/data) from Kaggle, covering 179 countries from 2000 to 2015. It was compiled from the WHO Global Health Observatory, the World Bank, UN Data, and Our World in Data.


`EDA_FACTORS_LIFEEXP.qmd` - Quarto source code for full analysis 
`EDA_FACTORS_LIFEEXP.html` - Rendered report 
`data/Life-Expectancy-Data-Updated.csv` - Dataset used in my analysis

## Next Steps

These findings are correlations, not causal effects. To go further, I plan to 1. run a multiple regression to find which factors stay significant when considered together and 2. address multicollinearity among the economic variables (GDP per capita, GDP category, economy status)

**Gelila Yimtatu** · B.S. Data Science, William & Mary
