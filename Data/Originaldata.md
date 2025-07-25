# Our world in COVID-19 data.

The primary dataset originates from Our World in Data, encompassing COVID-19 case counts, deaths, testing rates, vaccination data, GDP, healthcare capacity, and population demographics across 200+ countries and territories.

The data can be accessed using the following link: [our data](https://covid.ourworldindata.org/data/owid-covid-data.xlsx)

The data spans from the beginning of the pandemic through multiple waves of the pandemic.

The dataset consists of over **430,000** records and **67** variables. The variables can be classified based on the following thematic areas:
Identification and Geography

1.Epidemiological data

2. Hospitalization and ICU data

3. Testing data and vaccination data.

4. Policy and stringency

5. Demographics and Population data

6. Socioeconomic indicators

7. Health infrastructure and Risk factors

8. Excess mortality


The data contains daily records of COVID-19 in different parts of the world from **31/12/2019** to **04/08/2024.**

From the original dataset, we created a subset of 7 countries from each continent that had the least percentage of missing data. The table below shows the percentages of missing data in the included variables for the whole dataset: 

| VARIABLE | MISSING PERCENTAGES|
|-------|--------|
|Iso code | 0.00|
|Continent|0.00|
|Location|0.00|
|Date|0.00|
|Total cases|4.11|
|New cases|4.49|
|New cases smoothed|4.78|
|Total deaths|4.11|
|New deaths|4.38|
|New deaths smoothed|4.67|
|Total cases per million|4.11|
|New cases per million|4.49|
|New cases smoothed per million|4.78|
|Total deaths per million|4.11|
|New deaths per million|4.38|
|New deaths smoothed per million|4.67|
|Reproduction rate|56.96|
|ICU Patients|90.89|
|ICU patients per million|90.89|
|Hospital patients|90.53|
|Hospital patients per million|90.53|
|Weekly ICU admissions|97.44|
|Weekly ICU admissions per million|97.44|
|Weekly hospital admissions|94.30|
|Weekly hospital admissions per million|94.30|
|Total tests|81.51|
|New tests|82.44|
|Total tests per thousand|81.51|
|New tests per thousand|82.44|
|New tests smoothed|75.79|
|New tests smoothed per thousand|75.79|
|Positive rate|77.66|
|Tests per case|78.03|
|Tests units|0.00|
|Total vaccinations|80.11|
|People vaccinated|81.11|
|People fully vaccinated|81.82|
|Total boosters|87.52|
|New vaccinations|83.47|
|New vaccinations smoothed|54.58|
|Total vaccinations per hundred|80.11|
|People vaccinated per hundred|81.11|
|People fully vaccinated per hundred|81.82|
|Total boosters per hundred|87.52|
|New vaccinations smoothed per million|54.58|
|New people vaccinated smoothed|55.25|
|New people vaccinated smoothed per hundred| 55.25|
|Stringency index|54.31|
|Population density|16.05|
|Median age| 22.07|
|Aged 65 older|24.72|
|Aged 70 older|22.85|
|GDP per capita|23.55|
|Extreme poverty|50.63|
|Cardiovscualr death rate|23.42|
|Diabetes prevalence| 19.45|
|Female smokers|42.44|
|Male smokers|43.22|
|Handwashing facilities|62.34|
|Hospital beds per thousand|32.31|
|Life expectancy|9.11|
|Human development index|25.69|
|Population|0.00|
|Excess mortality cumulative absolute|96.88|
|Excess mortality cumulative|96.88|
|Excess mortality|96.88|
|Excess mortality cumulative per million|96.88|

The table below shows the countries included in the subset.
| CONTINENT|LOCATION|TOTAL COUNT/ENTRIES|DATE FIRST CASE WAS REPORTED|
|------|----|----|------|
|Africa| South Africa|3348|5/03/2020|
|Asia|Malaysia|1684|25/01/2020|
|Europe|Czechia|1682|12/03/2020|
||Italy|1677|12/02/2020|
|North America|Canada|1674|05/03/2020|
|South America|Chile|1674|01/03/2020|
|Oceania|Australia|1674|25/05/2025|

In the dataset, we observed trends in some of the variables that were being reported on a 7 day rolling average. New cases, new deaths, new cases smoothed per million, new deaths smoothed per million were imputed from the trends observed and zero cases reported during the start of the pandemic in the different countries.

The subset data with and without imputations have been attached in the Data folder. 

