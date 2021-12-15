# COVID-19 Pandemic Time Series Modeling
Created by Anushna Prakash  
DATA 512 - Human-Centered Data Science  

During the last two years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families.  
One aspect that has been hard to miss in the last two years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society. To be honest, we are actually at the very beginning of understanding and comprehending these impacts.  
During our Course Project we are going to begin taking a look at some of the social aspects of the pandemic by conducting a human centered data science analysis of some available COVID-19 data.  
My specific assignment was on the below county:

| County | State | Area_km^2| Area_mi^2 | Population_2020_Census | Population_Increase_from_2010 | County Seat |  
| ------ | ----- | -------- | --------- | ---------------------- | ----------------------------- | ----------- |  
| Orange | California | 2,047.56 | 790.57 | 3,186,989 | 176,757 | Santa Ana |  


## Structure
The folder is structured as shown below.  
```
.
├── README.md
├── data_clean
│   ├── oc_cases-births-deaths.csv
│   ├── oc_seasonally-adjusted_covid-cases-deaths_births_deaths.csv
│   ├── orange-county_CA_covid-cases_mask-adoption_mandates.csv
│   └── us_covid_cases-deaths.csv
├── data_raw
│   ├── RAW_us_confirmed_cases.csv
│   │   └── RAW_us_confirmed_cases.csv
│   ├── RAW_us_deaths.csv
│   └── U.S._State_and_Territorial_Public_Mask_Mandates_From_April_10__2020_through_August_15__2021_by_County_by_Day.csv
├── results
│   ├── births_seasonal-adjustment.jpg
│   ├── deaths_seasonal-adjustment.jpg
│   ├── oc_accidents-suicides.jpg
│   ├── oc_adjusted_fertility-non-covid-deaths.jpg
│   ├── oc_sa_accidents-suicide.jpg
│   ├── oc_unadjusted_fertility-all-deaths.jpg
│   ├── oc_unadjusted_fertility-non-covid-deaths.jpg
│   ├── orange-county_CA_daily-cases.jpg
│   ├── orange-county_CA_daily-infection-rate-smoothed.jpg
│   └── orange-county_CA_daily-infection-rate.jpg
├── src
│   ├── mortality_fertility_analysis.ipynb
│   └── oc_analysis.ipynb
└── submissions
    ├── A5 - Extension.pdf
    ├── A7 - Written Report.pdf
    ├── a4-reflection.md
    └── oc_county_mortality_fertility.pptx
```

The submissions folder contains the files submitted to for grading.

## Raw Data
The data is downloaded from the below sources:
- The RAW_us_confirmed_cases.csv file from the [Kaggle repository of John Hopkins University COVID-19 data.](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv)  
- The RAW_us_deaths.csv file from the [Kaggle repository of John Hopkins University COVID-19 data.](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_deaths.csv)  
The data is structured as below for both data sets, with multiple columns for each additional day of data (wide format):  

| Province_State | Admin2 | UID | iso2 | iso3 | code3 | FIPS | Country_Region | Lat | Long | Combined_Key |
| -------------- | ------ | --- | ---- | ---- | ----- | ---- | -------------- | --- | ---- | ------------ |  
| The province or state | County name | unique identifier | unused geography code | unused geography code | unused geography code | 5-digit Unique county identifier | Unused geography code | Latitude | Longitude | unused geography code |  

- The [CDC dataset](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) of masking mandates by county. **THIS DATA IS NOT INCLUDED IN THIS REPOSITORY AS THE FILESIZE WAS TOO LARGE. PLEASE DOWNLOAD IT DIRECTLY FROM THE LINK LOCALLY**  

| State_Tribe_Territory | County_Name | FIPS_State | FIPS_County | date | order_code | Face_Masks_Required_in_Public | Source_of_Action | URL | Citation |
| -------------- | ------ | --- | ---- | ---- | ----- | ---- | -------------- | --- | ---- |  
| The tribe or state | County name | unique identifier for state | unique identifier for county | YYYY-MM-DD date | Type of mandate order | Boolean identifier | Authority | URL | Citation |  

- The New York Times mask compliance [survey data.](https://github.com/nytimes/covid-19-data/tree/master/mask-use)  
- Deaths from [California Health & Human Services Department](https://data.chhs.ca.gov/dataset/death-profiles-by-county/resource/2e546f88-bba8-4d77-846a-7fb77846cac6)  
- Births from [California Health & Human Services Department](https://data.chhs.ca.gov/dataset/live-birth-profiles-by-county/resource/94a186da-7184-427b-b0b5-224bb0a05cd8)  
## Cleaned Data
There are several cleaned data files available under the `data_clean` folder. 

## Licensing
WIP