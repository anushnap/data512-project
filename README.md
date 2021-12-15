# COVID-19 Pandemic Time Series Modeling
Created by Anushna Prakash  

During the last two years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families.  

One aspect that has been hard to miss in the last two years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society. To be honest, we are actually at the very beginning of understanding and comprehending these impacts.  

During our Course Project we are going to begin taking a look at some of the social aspects of the pandemic by conducting a human centered data science analysis of some available COVID-19 data. My specific assignment was on the below county:

| County | State | Area_km^2| Area_mi^2 | Population_2020_Census | Population_Increase_from_2010 | County Seat |  
| ------ | ----- | -------- | --------- | ---------------------- | ----------------------------- | ----------- |  
| Orange | California | 2,047.56 | 790.57 | 3,186,989 | 176,757 | Santa Ana |  

Of this data, I ask:
- How did mask mandates affect daily confirmed coronavirus cases in Orange county?  
- How did the pandemic affect average non-COVID-related deaths?  
- How did the pandemic affect the number of accident-related deaths?  
- How did the pandemic affect the number of suicide-related deaths?  
- How did the pandemic affect the number births?  

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

| Column name | Description |  
| ----------- | ----------- |  
| Province_State | Province or state |  
| Admin2 | Country |  
| UID | Unique identifier |  
| iso2 | Unused geography code |  
| iso3 | Unused geography code |  
| code3 | Unused geography code |  
| FIPS | Unique 5-digit identifier |  
| Lat | Latitude |  
| Long_ | Longitude |  

- The [CDC dataset](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) of masking mandates by county. **THIS DATA IS NOT INCLUDED IN THIS REPOSITORY AS THE FILESIZE WAS TOO LARGE. PLEASE DOWNLOAD IT DIRECTLY FROM THE LINK LOCALLY**  

| Column name | Description |  
| ----------- | ----------- |  
| State_Tribe_Territory | State or tribe name |  
| County_Name | County name |  
| FIPS_State | Numeric state identifier |  
| FIPS_County | Numeric county identifier |  
| date | YYYY-MM-DD format |  
| order_code | Order type |  
| Face_Masks_Required_in_Public | Boolean identifier |  
| Source_of_Action | Authority |  
| URL | URL |  
| Citation | Citation |  

- The New York Times mask compliance [survey data.](https://github.com/nytimes/covid-19-data/tree/master/mask-use)  

| Column name | Description |  
| ----------- | ----------- |  
| COUNTYFP | Numeric state and county identifier |  
| NEVER | Percentage of respondants responding "never" wearing masks |  
| RARELY | Percentage of respondants responding "rarely" wearing masks |  
| SOMETIMES | Percentage of respondants responding "sometimes" wearing masks |  
| FREQUENTLY | Percentage of respondants responding "frequently" wearing masks |  
| ALWAYS | Percentage of respondants responding "always" wearing masks |  

- Deaths from [California Health & Human Services Department](https://data.chhs.ca.gov/dataset/death-profiles-by-county/resource/2e546f88-bba8-4d77-846a-7fb77846cac6)  
- Births from [California Health & Human Services Department](https://data.chhs.ca.gov/dataset/live-birth-profiles-by-county/resource/94a186da-7184-427b-b0b5-224bb0a05cd8)  
Both tables follow the below column format:  

| Column name | Description |  
| ----------- | ----------- |  
| County | County name |  
| Year | YYYY year format |  
| Month | MM month format |  
| Strata | The intersectional cut of data, for example "all" or "Black" |  
| Cause (DEATHS) | The intersectional cut of deahts, for example "Accidents" |  
| Count | Count of incidents |  


## Results  

From this analysis, I discovered that there is evidence for:  
- Higher non-COVID-related deaths  
- Lower births  
- Higher accidents  

And that there is not enough evidence to support any change in in the number of suicides.  

Do these results surprise you? They surprised me too! Take a look at my code to reproduce the results or to complete the same analysis on a different county. Do you find the same trends?  

## Licensing
- The Johns Hopkins data is available under the [creative commons license](https://creativecommons.org/licenses/by/4.0/) which means the data is available with proper attribution.  
- The CDC data is available under the below citation:  
CDC, COVID-19 Community Intervention & Critical Populations Task Force, Monitoring & Evaluation Team, Mitigation Policy Analysis Unit, the CDC, Center for State, Tribal, Local, and Territorial Support, Public Health Law Program, and Max Gakh, Assistant Professor, School of Public Health, University of Nevada, Las Vegas, “U.S. State and Territorial Orders Requiring Masks in Public,” (August 15, 2021).  
- The New York Times mask data is available under this [permissive license](https://github.com/nytimes/covid-19-data/blob/master/LICENSE) which is highly permissive with proper attribution.  
- The CHHS data is available under [license](https://data.chhs.ca.gov/pages/terms) with attribution.  