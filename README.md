# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Exploring climate data of Singapore


### Problem Statement

Singapore is an island city-state surrounded by water, situated near the equator and has a tropical climate. Our geographical location makes us susceptible to infectious diseases caused by bacteria, viruses, fungi or even parasites due to the high humidity and rainfall. The project aims to study the relationship between the climate in Singapore and the number of locally reported Typhoid cases to develop effective public health interventions.

---

### Outside Research
There was a study done to understand the relationship between typhoid cases and the climate in Bangladesh, which has similar climate conditions as Singapore with high humidity and high rainfall. In that study, "clear periodicity was found in the timing of case occurrences, with most cases occurring in the monsoon season." The study also found out that "typhoid incidence was seen to increase with temperature, rainfall and river level". While the period of study occured more than a decade ago from 2005 to 2009, it is still relevant in our study to find out whether the different types of monsoon that Singapore encounters have an impact on the locally reported Typhoid cases.

Source: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3554574/

---

### Datasets used

The datasets used include the following:

1) **WeeklyInfectiousDiseaseBulletinCases.csv**: Weekly publication of statistics on local infectious disease situation. Each epidemiological week begins on a Sunday and ends on Saturday.The weekly data is available from Jan 2012 to Dec 2022.

2) **SurfaceAirTemperatureMonthlyMean.csv**: The monthly mean air temperature recorded in degree celsius from Jan 1982 to May 2023.

3) **RainfallMonthlyNumberofRainDays.csv**: The number of rain days (day with rainfall amount of 0.2mm or more) in a month from Jan 1982 to Jun 2023.

4) **SunshineDurationMonthlyMeanDailyDuration.csv**: The monthly mean sunshine hours in a day recorded from Jan 1982 to Jun 2023.

5) **RainfallMonthlyHighestDailyTotal.csv**: The highest daily total rainfall for the month recorded in mm(millimeters) from Jan 1982 to Jun 2023.

6) **RainfallMonthlyTotal.csv**: The monthly total rain recorded in mm(millimeters) from Jan 1982 to Jun 2023.

7) **RelativeHumidityMonthlyMean.csv**: The monthly mean relative humidity recorded in percentage from Jan 1982 to Jun 2023.

All seven datasets can be found from [data.gov.sg](data.gov.sg).

---

### Data Dictionary


|Feature|Type|Dataset|Description|
|---|---|---|---|
|month|string|RainfallMonthlyTotal|Month and year of the data|
|year|string|RainfallMonthlyTotal|Year of the data|
|month_of_year|string|RainfallMonthlyTotal|Month of the data|
|total_rainfall|float|RainfallMonthlyTotal|Total rainfall in mm| 
|no_of_rainy_days|integer|RainfallMonthlyNumberofRainDays|The number of rain days|
|mean_temp|float|SurfaceAirTemperatureMonthlyMean|The monthly mean air temperature recorded in degree celsius|
|maximum_rainfall_in_a_day|float|RainfallMonthlyHighestDailyTotal|The highest daily total rainfall for the month in mm|
|mean_sunshine_hrs|float|SunshineDurationMonthlyMeanDailyDuration|The monthly mean sunshine hours in a day|
|mean_rh|float|RelativeHumidityMonthlyMean|The monthly mean relative humidity recorded in percentage|
|typhoid|float|WeeklyInfectiousDiseaseBulletinCases|Number of Typhoid cases|
|monsoon_type|string|moonsoon_df|Type of monsoon in Singapore, i.e. Northeast (NE), Southwest (SW), Not applicable (NA)|

---

### Summary of findings

For the total rainfall, the comparison against each decade of data in 1990, 2000, 2010 and 2020 showed that that the there were shifts in the highest month of rainfall over the decades from the second half of the calendar year (i.e. Jul to Dec) to the first half of the year (i.e. Jan to Jun) in the most recent decade of 2020. However, the lowest month of rainfall largely remained largely consistent over the decades and falls on the month of February.

For the number of rainy days, the comparison against each decade of data in 1990, 2000, 2010 and 2020 did not show significant shifts as the highest number of rainy days were all in the second half of the calendar year (i.e. Jul to Dec), and the lowest number of rainy days were all in the first half of the calendar year (i.e. Jan to Jun).

When we look at the climate data from 1982 to 2022, we see that the lowest year of number of rainy days and rainfall were consistent and occured in 1997. However, the highest number of rainy days (i.e. 2022) and rainfall (i.e. 2007) were on different years.

The findings segmented by each available decade of data (i.e. 1990, 2000, 2010 and 2020) as well as monthly data from 1982 to 2022 suggested changes in rainfall pattern of Singapore over the past 40 years. There were also shifts in the period of highest rainfall which occurred in the first half of the year for the most recent decade in 2020. In addition, while the lowest rainfall and lowest number of rainy days happen to be the same year, the year of highest rainfall and highest number of rainy days were not the same year. This suggested that both climate metrics might not have very strong positive correlation which we can be studied further using correlation plots.

Based on the above findings, the more recent years of climate data would be more relevant for our subsequent study. We will be  exploring the climate data from 2018 to 2022 and analyse the relationship betweem the climate in Singapore and the local reported Typhoid cases to develop effective public health interventions.

Based on the heatmap showing the correlation between all the numeric columns of the climate and typhoid cases data (i.e. df_final), we are able to detect the following correlations:

1) There is moderate positive correlation between the total rainfall and the number of rainy days (i.e. correlation of 0.57). This confirms our earlier suspicion that the total rainfall and number of rainy days do not hold strong positive correlation.

2) There also exists slight negative correlation between the average relative humidity and the number of typhoid cases and (i.e. correlation of -0.35). This meant that the higher the average relative humidity, we should see lower number of typhoid cases.

However, based on the current data, we are not able to conclude that there is moderate or strong correlations between typhoid cases with the various climate metrics recorded. We could then consider segmenting the data by the type of monsoon which would have differing climate metrics to see whether there are specific monsoon seasons where the number of typhoid cases has a stronger correlation with the specific climate metrics recorded.

After we segment the data by the Southwest monsoon period, Northeast monsoon period and non-monsoon period, we can see from the heatmaps that during the Southwest monsoon period, there is higher moderate negative correlation of -0.59 between the number of typhoid cases and the average relative humidity, compared to when we plot it against the full data. There is also a higher moderate negative correlation of -0.47 between the number of typhoid cases and the number of rainy days, compared to when we plot it against the full data. 

On the contrary, for the Northeast monsoon period and non monsoon period, there is much weaker negative correlation between the number of typhoid cases and the average relative humidity, compared to when we plot it against the full data.

With the above, we can see that for the months of Jun to Sep of the calendar year which happens to be the Southwest monsoon period, when the average relative humidity decreases during this period, we generally see more typhoid cases reported in Singapore. 

---

### Conclusions and Recommendations

Based on the findings above, we can see that there exists a moderate negative correlation between the number of typhoid cases with the average relative humidity of the environment. This negative correlation is stronger when we segment out the data for the Southwest monsoon period, where the median of the average relative humidity is lower than the other two groups.

While the number of typhoid cases in Singapore has been on a decline since the 1980s due to efforts from the government to improve environmental hygiene and sanitation, we should remain vigilant against such infectious disease. This is because at the earlier stages of contracting such disease the symptoms are similar to common fever, and takes up to two weeks before the more apparent stomach related symptoms and skin rashes show. This disease has also shown resistance against antibiotics, and the carriers of the disease without symptoms can remain contagious.

Based on the findings on the climate conditions in Singapore with the number of locally reported Typhoid cases, we should encourage the public to undergo Typhoid vaccine especially during the Southwest monsoon period, where we see a stronger negative correlation between the average relative humidity during the Southwest monsoon period and the number of typhoid cases reported in Singapore.

Last but not least, although Typhoid vaccine is available in Singapore, it is currently not subsidised for the general public. This may potentially deter the public from taking the Typhoid vaccine due to its higher cost. We should consider revising the list of subsidised vaccinations to include Typhoid vaccine under the subsidised list for the general public, especially during the Southwest monsoon period.

Sources:

1) https://eresources.nlb.gov.sg/infopedia/articles/SIP_2022-08-19_132436.html#:~:text=Subsequently%20from%201990%20to%202009,had%20no%20recent%20travel%20history.

2) https://my.clevelandclinic.org/health/diseases/17730-typhoid-fever

3) https://www.nhgp.com.sg/our-services/other-services/Pages/Vaccination-Clinic.aspx

4) https://www.gavi.org/vaccineswork/global-response-needed-typhoid-evades-antibiotics


