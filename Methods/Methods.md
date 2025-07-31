### DATA LOADING
We got our data from Our World In Data website; described in the data  folder.

### DATA PREPROCESSING/ EDA
##### Data Inspection and Quality Assessment
The original dataset contained 67 variables and approximately 430000 entries from 255 countries worldwide. The average percentage of missing data across all countries in the dataset was approximately 49%. Considering the variables, missing data ranged from 97% to 4%. We subset our data to 7 countries that had the least percentage of missing data (<35% missing data) from each continent, that we used in the subsequent steps. 

In the new dataset, we selected variables that only had raw entries, excluding calculated and standardized variables in an effort to prevent redundancy and reduce multicollinearity effect.
Variables selected and included for further analysis were:  
- continent
- date
- location
- new cases
- new deaths
- stringecy index
- new vaccinations
- new tests
- people fully vaccinated
- total boosters
- hospital patients
- icu patients
- population
- population density
- median age
- percentage of population aged 65 years and above
- percentage of poplation aged 70 years and older
- gdp per capita
- extreme poverty
- cardiovascular death rate
- diabetes prevalence
- female smokers
- male smokers
- hospital bed per thousand
- life expectancy
- human development index

All the variables included were numerical data types apart from the identifiers and date variable.

#### Data Cleaning
We observed a pattern in some of the variables. New cases and new deaths were recorded on a weekly basis, while new vaccinations, new tests, people fully vaccinated, total boosters, hospital patients, ICU patients recorded in inconsistent days, and some variables having static values (population, population density, median age, aged 65 and older, aged 70 and older, GDP per capita, extreme poverty, cardiovascular death rate, diabetes prevalence, female smokers, male smokers, hospital beds per thousand, life expectancy, human development index). 
The date column was converted to datetime format to facilitate time series analysis. We dropped duplicates for each location-date pair (repeated entries in individual countries).

We created a subset of the data, including only weekly inputs or a sum of the weekly inputs in the different countries. For the static entries, we forward filled and extracted only entries recorded on Sundays. For entries recorded on a daily basis or at intervals, we summed up and extracted the entries for the whole week. 
From this, we had 26 variables, and 1686 weekly entries from the 7 countries. 
 
### STATISTICAL ANALYSIS
##### Correlation Analysis and Hypothesis Testing
- *Correlation matrix showing pairwise correlation coefficients*
  
We plotted a correlation heatmap with 23 variables, testing whether the correlations observed are statistically signifcant using *p* values. We used Pearson Correlation test that returns a correlation coefficient and a p value. The correlation coefficient shows how strong a relationship is while the *p* value shows whether the relationship is statistically significant and not due to chance. Our hypotheses in this case were: 

  **Null hypothesis**: There is no linear correlation between the features and new cases and new deaths
  **Alternate Hypothesis**: There is a linear relationship between the features and new cases and new deaths.

### FEATURE SELECTION
We explored different options for feature selection; 
1. Filter method- From the correlation matrix and hypothesis testing, we identified the top 10 features that were highly correlated with Infection and Mortality rates.
2. Lasso model feature selection
   
Target variables input for this model were New cases and new deaths.
From this model, features that had non-zero coefficients were identified.
For new cases, the features selected were stringency index, new vaccinations, new tests, people fully vaccinated, total boosters, hospital patients, ICU patients, population, population density, female smokers.
For new deaths, selected features included stringency index, new vaccinations, new tests, people fully vaccinated, total boosters, hospital patients, ICU patients, population density, extreme poverty.

#### Data Visualization
##### Time Series Analysis; Progression of cases and deaths over time
Location, continent, date, new cases and new deaths variables were used to plot time series analysis for the seven countries selected. The trends for each country and were plotted using line graphs.
##### Bar graphs and line graphs
We created a bar graph showing the top leading countries with the biggest percentage of older population >65 years old and the average new cases in each of the countries, relating to the population demographics in terms of the age. 

### PREDICTIVE MODELLING
- *Classification model*
- *Regression model*
  - Evaluating the models using MAE,RMSE and R<sup>2</sup>
- *Compare model perfomance*
- *Visualize predicted vs Actual values*
### Model Improvement and Evaluation
Added 13 countries to the model
