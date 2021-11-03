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
The folder is approximately structured as shown below. The specific contents will change as more is added to the project.
```
.
├── README.md
├── data_clean
│   └── orange-county_CA_covid-cases_mask-adoption_mandates.csv
├── data_raw
│   ├── RAW_us_confirmed_cases.csv
│   │   └── RAW_us_confirmed_cases.csv
│   └── U.S._State_and_Territorial_Public_Mask_Mandates_From_April_10__2020_through_August_15__2021_by_County_by_Day.csv
├── results
│   └── orange-county_CA_daily-cases.jpg
├── src
│   └── oc_analysis.ipynb
└── submissions
    └── a4-relection.md
```

The submissions folder contains the files submitted to for grading.

## Raw Data
The data is downloaded from the below sources:
- The RAW_us_confirmed_cases.csv file from the [Kaggle repository of John Hopkins University COVID-19 data.](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv)  
- The [CDC dataset](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) of masking mandates by county. **THIS DATA IS NOT INCLUDED IN THIS REPOSITORY AS THE FILESIZE WAS TOO LARGE. PLEASE DOWNLOAD IT DIRECTLY FROM THE LINK LOCALLY**  
- The New York Times mask compliance [survey data.](https://github.com/nytimes/covid-19-data/tree/master/mask-use)  

## Cleaned Data
WIP

## Licensing
WIP