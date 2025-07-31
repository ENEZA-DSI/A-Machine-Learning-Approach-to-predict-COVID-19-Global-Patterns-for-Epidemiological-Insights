### DATA LOADING
We got our data from Our World In Data website; described in the ['Data/'](../Data/) folder.

### DATA PREPROCESSING/ EDA
##### Data Inspection and Quality Assessment
The original dataset comprised **67 variables** and approximately 430000 entries from **255 countries** globally. The average percentage of missing data across all countries in the dataset was approximately 49%. Considering the variables, missing data ranged from 97% to 4%.

To ensure data quality: 
- We subset the dataset to include 7 countries that had the least percentage of missing data (<35% missing data) from each continent, that we used in the subsequent steps.
- In the new dataset, we excluded derived and standardized variables in an effort to avoid redundancy and reduce multicollinearity effect.
  
Variables selected and included for further analysis were:  
- continent, date, location
- new cases, new deaths, stringency index
- new vaccinations, new tests, people fully vaccinated, total boosters
- hospital patients, ICU patients, hospital beds per thousand
- population, population density, median age
- % population aged 65+, % population aged 70+
- GDP per capita, extreme poverty
- cardiovascualar death rate, diabetes prevalence
- female smokers, male smokers
- life expectancy, human development index


All the variables included were numerical data types apart from the identifiers (location, continent) and date variable.

#### Data Cleaning
We observed a pattern in some of the variables. New cases and new deaths were recorded on a weekly basis, while new vaccinations, new tests, people fully vaccinated, total boosters, hospital patients, ICU patients recorded in inconsistent days, and some variables having static values (population, population density, median age, aged 65 and older, aged 70 and older, GDP per capita, extreme poverty, cardiovascular death rate, diabetes prevalence, female smokers, male smokers, hospital beds per thousand, life expectancy, human development index). 
The date column was converted to datetime format to facilitate time series analysis. We dropped duplicates for each location-date pair (repeated entries in individual countries).

We created a subset of the data, including only weekly inputs or a sum of the weekly inputs in the different countries. For the static entries, we forward filled and extracted only entries recorded on Sundays. For entries recorded on a daily basis or at intervals, we summed up and extracted the entries for the whole week. 
From this, we had 26 variables, and 1686 weekly entries from the 7 countries. 
 
### STATISTICAL ANALYSIS
##### Correlation Analysis and Hypothesis Testing
- *Correlation matrix showing pairwise correlation coefficients*
  
We plotted a correlation heatmap with 23 variables and tested the statistical significane of the relationships using earson corelation test. The correlation coefficient indicates the strength and direction of the relationship, while the *p* value shows whether the relationship is statistically significant and not due to chance. Our hypothesis in this case was: 

  **Null hypothesis**: There is no linear correlation between the features and new cases and new deaths
  
### FEATURE SELECTION
We explored different options for feature selection; 
1. Filter method/ Statistical Feature Selection
   From the **correlation matrix** and **hypothesis testing**, we identified the top 10 features that were highly correlated with Infection and Mortality rates.
2. Neural Networks
3. Lasso model feature selection
   
   Target variables input for this model were New cases and new deaths.
   From this model, features that had non-zero coefficients were identified.
   For **new cases**, the features selected were stringency index, new vaccinations, new tests, people fully        vaccinated, total boosters, hospital patients, ICU patients, population, population density, female          smokers.
   For **new deaths**, selected features included stringency index, new vaccinations, new tests, people fully       vaccinated, total boosters, hospital patients, ICU patients, population density, extreme poverty.

#### Data Visualization
##### Time Series Analysis; Progress of cases and deaths over time
Time trends of new cases and new deaths were plotted for each of the 7 countries. Line graphs were used to observe the infection and mortality trends over time.
##### Bar graphs and line graphs
Bar plots were used to display:
- Countries with the highest percentage of population aged >65 and average new cases. 
- Their corresponding average new case numbers, linking age demogrpahics to infection rates.

### PREDICTIVE MODELLING
#### Model types
- *Classification model*
  
  LightGBM was used to identify contries that had high and low infection rates
  
- *Regression model*
  
  RandomForest Regressor and Ensemble models were used to predict the frequency of new cases and new deaths    in the selected countries.

#### Evaluation metrics
- Models were assessed using Mean Absolute Error (MAE), Root Mean Square Error (RMSE), R<sup>2</sup>, F1 score and accuracy score.
- A confusion matrix was also used to assess the perfomance of the model. 

#### Model Comparison
The perfomance of the diffferent models was compared based on the above metrics.
Visualization included *predicted vs the actual values* plots for perfomance evaluation.

### Model Improvement
To improve model generalizability we expanded the dataset to include additional countries, increasing the geographical diversity and training daa size.

#### Assumptions
When building the model, the following assumptions were made:
- The subset of our data used to train the model might not be a true representation of the global trend.
- Our model did not cater for the differences in the behavior of pandemic within each of the countries. 
