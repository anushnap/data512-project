Anushna Prakash  
DATA 512 - Human-Centered Data Science  
November 4, 2021  
# A4 - Common Analysis Reflection

![Orange County, CA Case counts](../results/orange-county_CA_daily-cases.jpg)
![Orange County, CA smoothed infection rates](../results/orange-county_CA_daily-infection-rate-smoothed.jpg)

## Explanation of the Visualizations  
The visualizations for this assignment shows the daily new confirmed cases of COVID-19, the estimated daily counts if mask mandates were not in place and enforced, and the smoothed infection rates with the mask mandates in place and estimated figures without from the February 1, 2020 through October 15, 2021 during the COVID-19 pandemic. Those dates are in the x-axis of both figures. Though the axes labels continue forward into November 2021 for continuity, the data is intentionally truncated at October 15, 2021. The confirmed cases are represented in the y-axis in the representative unit in the top image in blue bars, with the darkness of the bar indicating whether or not a mandate was being enforced. An estimation of the number of cases and infection rate if mask mandates were not enforced is shown in the orange dotted lines in both figures. This assumes that all individuals wear a cloth mask, which has been shown to be 67% effective at limiting the transmission of COVID-19.  

In the bottom image, the x-axis represents the infection rate as a percentage. To reduce the noise from daily case counts being affected by weekends and holidays, the infection rates use the seven-day rolling average of actual daily case counts or calculated daily case counts assuming a mask mandate is not enforced. The infection rate is calculated as the daily case count divided by the total population at-risk. No deaths from COVID-19 are built into the model, so the population at risk is only affected by the 10 day cumulative sum of infected individuals. Additionally, the population is static throughout the 18-month series and is calculated using 2020 Census Bureau figures.  

We can tell from these two graphs that mask mandates did have an impact in reducing the number of total cases. This is seen by the gap between the blue bars in the upper graph and the orange dotted line. Without a mask mandate, it is possible that daily case counts may have been much higher. The peak of daily cases is on December 29, 2020, where the potential cases without a mask mandate is estimated to be over 2,500 infections higher. By translating this into a daily infection rate, we can see the trend play out a bit clearer, where smoothed infection rates assuming no mask mandate are higher than the infection rates were with a mask mandate. At the peak of COVID-19 smoothed infection rates on 2021-01-08, the infection rate is estimated ot be 0.18% unmasked, but is only 0.12% with masks. From these graphs it is clear that mask mandates did have an impact on the spread of COVID-19.  

In total, the assumptions that were made for this analysis are below:  
- The time period is limited from Feb 1, 2020 to Oct 15, 2021.  
- The location is limited to Orange County, CA.  
- Confirmed COVID-19 cases are as a result of a positive COVID-19 test result. There is no assumption around asymptomatic spreaders or false negatives.  
- A rolling 7 day average is used that takes into account the prior 6 periods and the current period in its calculation. This accounts for any variation caused by people not getting tested over weekends and holidays.  
- The population is assumed by the 2020 Census Bureau figure.  
- The population-at-risk is defined by the current population - total infections over the prior 10 days. No deaths are assumed to reduce the population at this time. The population is static over the 18 month series.  
- All individuals wear a cloth mask, which reduces transmission by 67%. Case counts are inflated by 1.49 to estimate cases without a mask mandate.  

Second, we would like to understand what you got out of the collaborative activities in this assignment. You should write a reflection statement that highlights one or two specific things that you learned from answering the research question posed in this assignment. Your reflection statement should include specific attributions for any/all code, methods and techniques that you reused. Your reflection statement should be no more than 2 written pages.  