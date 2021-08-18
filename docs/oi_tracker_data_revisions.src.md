---
geometry: margin=1in
fontsize: 11pt
linestretch: 1
colorlinks: true
numbersections: true
title: |
  | Opportunity Insights Economic Tracker
  | Data Revisions
subtitle: last updated on 2021-08-18
documentclass: scrartcl
---  

<a href="https://raw.githubusercontent.com/OpportunityInsights/EconomicTracker/main/docs/oi_tracker_data_revisions.pdf"><img src="pdf-icon.svg" alt="PDF Download" width="50" style="display:inline;"/> <img src="null.png" alt="Click here to download a PDF version of this document" /></a>

# Overview
This document provides a description of major revisions to the data posted by the Opportunity Insights Economic Tracker. The document is organized sequentially by series in the tracker, among series that have had substantive data revisions since June 30th 2021 due to changes in data processing or data sources over time.

This document is updated regularly and the following information is subject to change.

For further information or if you have any questions please feel free to reach out to [info@opportunityinsights.org](mailto:info@opportunityinsights.org) and someone on our team will be in touch.

# Data Series

## Employment

**Revisions on June 30th 2021**

The Employment data was revised on June 30th 2021 due to three independent changes in methodology.

- **Revisions to address end-of-year "churn" in Paychex client base:** over time, some firms enter and exit Paychex's client base. This is especially concentrated at the end of each calendar year, where there is significant churn as firms renew their payroll processing contracts. This creates two sources of error in the tracker series. First, due to this seasonal pattern, the raw Paychex data displays a downwards trend in employment at the end of each calendar year as some clients leave Paychex, followed by an upward trend in employment at the very beginning of each calendar year as new clients join. Second, we take steps to avoid firm entry and exit that are more responsive to firm entry and exit at finer levels of geography, so that we can minimize the number of discontinuous changes in employment. The firm entry and exit occurring due to end-of-year "churn" in Paychex's client base resulted in a discrepancy between the national employment series and the corresponding series at the state level.

  To avoid these sources of error, we have changed the way in which we process employment data around the end of each calendar year. We now adjust for the end-of-year pattern in the Paychex data using data from the end of 2019. For each date between December 10 2020 and January 10 2021, using Paychex data on employment at the national level, we compute the change in employment relative to December 10 2020 at the two-digit NAICS code x income quartile level. We also compute the change in employment between the corresponding day in the previous year and December 10 2019. We divide the change in employment relative to December 10 2020 by the corresponding change in employment the previous year relative to December 10 2019. At the national level, as of June 2021, this change results in an upwards revision of the employment series by between 1 and 3 percentage points from December 2020 through May 2021. We then apply the same adjustment to each two-digit NAICS code x income quartile cell at the state, county and city levels. For this reason, the state, county and city-level series have also been adjusted upwards by between 1 and 3 percentage points from December 2020 through May 2021.

- **Revisions arising from changes to adjustment for firm entry/exit in Paychex data**: over time, the Paychex sample changes as clients begin to use or stop using Paychex’s payroll processing services. We previously adjusted for firm entry and exit separately at the national and state levels; for details on this adjustment, see Appendix D of Chetty, Friedman, Hendren and Stepner (November 2020). This introduced the possibility of discrepancies between the national-level and the (employment-weighted) mean of the state-level employment series. Empirically, these discrepancies were small throughout most of 2020, but began to grow in December 2020 due to increased churn in Paychex’s client base at the end of 2020, as described above. Since the firm entry/exit adjustment was applied retrospectively, this led to discrepancies throughout the series.

  We have changed our approach to adjusting for firm entry/exit to avoid these discrepancies. In each county x industry (two-digit NAICS code) x firm size x income quartile cell, we now compute the change in employment relative to January 4-31 2020, and the change in employment relative to July 1-31 2020. For county x industry x firm size x income quartile cells with over 50 employees at any point between January 2020 and the end of the series, we reduce the weight we place on the series if we observe changes in employment that indicate firm entry or exit. In particular, we compute the weight on the cell for county _c_, industry _i_, firm size _s_, and income quartile _q_ as:

  <img src="https://render.githubusercontent.com/render/math?math=\text{Weight}_{c, i, s, q} = \text{max} \Big\{ 1 - \mathbf{1} \{ \text{Min Normed July}_{c, i, s, q} \leq 50 \} \times (50 - \text{Min Normed July}_{c, i, s, q}) \times 0.02 - \mathbf{1} \{ \text{Max Normed January}_{c, i, s, q} \geq 150 \} \times (\text{Max Normed January}_{c, i, s, q} - 150) \times 0.02, 0 \Big\}">

  \begin{align*}
  \text{Weight}_{c, i, s, q} =& \text{max} \Big\{ 1 - \mathbf{1} \{ \text{Min Normed July}_{c, i, s, q} \leq 50 \} \times (50 - \text{Min Normed July}_{c, i, s, q}) \times 0.02\\
  &- \mathbf{1} \{ \text{Max Normed January}_{c, i, s, q} \geq 150 \} \times (\text{Max Normed January}_{c, i, s, q} - 150) \times 0.02, \\
  &0 \Big\}
  \end{align*}

  where Min Normed July<sub>_c, i, s, q_</sub> is the smallest value of indexed employment we observe at each date relative to its mean level over the period July 1-31 2020, and Max Normed January<sub>_c, i, s, q_</sub> is the largest value of indexed employment we observe at each date relative to its mean level over the period January 4-31 2020.

  That is, we reduce the weight we place on the cell by two percentage points for each percentage point of growth we observe above 150 percentage points relative to January 2020. We then further reduce the weight we place on each cell by two percentage points of its January 2020 level for each percentage point of decline we observe below 50 percentage points relative to July 2020.

  At the national level, this change revises the aggregate employment series between -2 (in October 2020) and +2 (in January 2021) percentage points, as of June 2021. This change also substantially revises the state-level employment series. The mean revision (in absolute value) for aggregate employment at the state level is 5.6 percentage points as of June 2021. This revision is largest in March 2021, when the mean revision (in absolute value) is 9.1 percentage points.

- **Revisions to address changes in minimum wages**: we use hourly wage thresholds when constructing employment by income quartile in the Paychex data. The threshold for the bottom quartile of employment is $13; that is, workers who earn below $13 are assigned to the bottom quartile, whereas workers earning above (or exactly) $13 are allocated to other wage quartiles. On January 1 2021, minimum wage changes came into force in CA, MA, AZ and NY, which caused the minimum wage for some workers to move from below $13 to above $13. This resulted in a decline in employment for workers earning below $13, and a corresponding increase in employment for workers earning above $13, as firms increased workers' wages in response to the minimum wage change. This was reflected in a decrease in low-income employment and an increase in middle-income employment in the tracker data for states in which the minimum wage had increased above $13.

  Though the tracker data for these states accurately represented trends in employment among workers earning below $13, the movement of workers around the minimum wage threshold created difficulties when comparing trends in low-wage employment across states. We have taken four steps to address this problem. First, we have created additional series for below-median-income and above-median-income employment, which can be downloaded from this repository. As the national median wage threshold in the Paychex data is $18.18, the below-median-income series is not affected by the shifting of workers induced by the minimum wage change. Second, we have added annotations to the tracker data indicating minimum wage changes in the relevant states. Third, we have suppressed series cut by income quartile in these states after December 1 2020, to avoid displaying series that are substantially affected by minimum wage changes. Finally, the impacts of the minimum wage on low-income employment in these states also affected trends at the national level: as workers' wages increased above the $13 threshold, national employment fell. When computing the national-level trend in employment, we now exclude trends in CA, MA, AZ and NY between December 10 2020 and February 10 2021. We continue to use trends in these states when computing national-level employment from February 11 2021 forward.

After making these changes, the (population-weighted) RMSE (root mean square error) of the state-level employment series relative to the CPS is 4.55 percentage points as of April 2021, after removing public sector and furloughed workers and expressing employment in seasonally-unadjusted terms relative to January 2020. Though we will continue to assess our series relative to the CPS, users should note that some amount of noise remains in both our state-level series estimates and in the CPS estimates. Particularly in instances where these two measures of employment differ, users may consider both the Opportunity Insights series and the CPS as helpful inputs in identifying local patterns.

## Unemployment Claims

**Revisions on July 29th 2021**

The unemployment data was revised on July 29th 2021 to correct a data processing error. Previously we assigned continued PEUC and PUA claims to the end of week date indicated by the Report Date rather than the Reflect Date in the [Department of Labor data](https://oui.doleta.gov/unemploy/docs/weekly_pandemic_claims.xlsx). Effectively, this meant continued PEUC and PUA claims were offset by one week into the future in our data. We've corrected this, and claims now align to the appropriate week.

## COVID-19 Infections

**Revisions on March 17th 2021**

Previously we pulled reported cases and deaths from the New York Times' [COVID-19 database](https://github.com/nytimes/covid-19-data) and reported tests from the [COVID Tracking Project](https://covidtracking.com/). At the conclusion of the COVID Tracking Project's efforts in order to collect testing data we instead began pulling reported cases, deaths, and tests at the county level from the Centers For Disease Control and Prevention's [COVID Data Tracker](https://covid.cdc.gov/covid-data-tracker/#datatracker-home) and aggregated to other geographies.

**Revisions on August 4th 2021**

Previously we pulled reported cases, deaths, and tests at the county level from the Centers For Disease Control and Prevention's COVID Data Tracker and aggregated to other geographies. On July 17th the Centers For Disease Control and Prevention began suppressing reported cases and deaths making aggregations across counties no longer feasible and we began to instead pull reported cases and deaths from the New York Times' [COVID-19 database](https://github.com/nytimes/covid-19-data), state level reported tests from the Johns Hopkins Coronavirus Resource Center's [U.S. testing database](https://github.com/govex/COVID-19/tree/master/data_tables/testing_data), and county level reported tests from [The Centers for Disease Control and Prevention](https://covid.cdc.gov/covid-data-tracker/#datatracker-home).    
