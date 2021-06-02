---
geometry: margin=1in
fontsize: 11pt
linestretch: 1
colorlinks: true
numbersections: true
title: |
  | Opportunity Insights Economic Tracker
  | Data Dictionary
subtitle: last updated on 2021-06-02
documentclass: scrartcl
---  

<a href="https://raw.githubusercontent.com/OpportunityInsights/EconomicTracker/main/docs/oi_tracker_data_dictionary.pdf"><img src="pdf-icon.svg" alt="PDF Download" width="50" style="display:inline;"/> <img src="null.png" alt="Click here to download a PDF version of this document" /></a>

\renewcommand{\thesubsection}{\arabic{subsection}}

## Overview

Each data source and level of aggregation has a separate CSV, named using the following convention: *Data source* – *Geographic Level of Aggregation* – *Temporal Level of Aggregation*

Additionally, we have three files, **GeoIDs – State** and **GeoIDs – County** and **GeoIDs – City**, that provide information on geographic crosswalks and aggregation. These can be merged to any file sharing the same geographic level of aggregation using the geographic identifier. Additionally, **GeoIDs – County** indicates the commuting zone (CZ) and state that each county belongs to. The City-level data (listed under "Metro" on the tracker site) associates the largest cities in the United States with a representative county one-to-one (except in the case of New York City which includes the 5 boroughs).

Finally, we have gathered a collection of key state-level policy dates relevant for changes in other series trends and values. These are contained in the **Policy Milestones – State** file.

A description of the columns in each file follows.

## GeoID File Descriptions

### GeoIDs - State.csv

Geographic identifier: `statefips`

- `statename`: The name of the state.
- `stateabbrev`: The 2-letter state abbreviation.
- `state_pop2019`: The population of the state in 2019, from Census Bureau estimates.

### GeoIDs - County.csv

Geographic identifier: `countyfips`

- `countyname`: The name of the county.
- `cityid`: The city identifier that the county is assigned to.
- `cityname`: The name of the city that the county is assigned to.
- `cz`: The numeric identifier of the commuting zone (CZ) in which the county is contained.
- `czname`: The name of the commuting zone (CZ) in which the county is contained.
- `statename`: The name of the state in which the county is contained.
- `statefips`: The FIPS code of the state in which the county is contained.
- `stateabbrev`: The 2-letter abbreviation of the state in which the county is contained.
- `county_pop2019`: The population of the county in 2019 according to Census Bureau estimates.

### GeoIDs - City.csv

Geographic identifier: `cityid`

- `cityname`: The name of the city.
- `stateabbrev`: The 2-letter abbreviation of the primary state in which the city is contained.
- `statename`: The name of the primary state in which the city is contained.
- `statefips`: The FIPS code of the primary state in which the city is contained.
- `lat`: Latitude of the city.
- `lon`: Longitude of the city.
- `city_pop2019`: The population of the city in 2019 according to Census Bureau estimates, calculated as population of the county or counties assigned to the city.

## Data File Descriptions

### Affinity

Spending data from [Affinity Solutions](https://www.affinity.solutions).

- `spend_all`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_acf`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in accomodation and food service (ACF) MCCs, 7 day moving average, 7 day moving average.
- `spend_aer`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in arts, entertainment, and recreation (AER) MCCs, 7 day moving average.
- `spend_apg`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in general merchandise stores (GEN) and apparel and accessories (AAP) MCCs, 7 day moving average.
- `spend_grf`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in grocery and food store (GRF) MCCs, 7 day moving average.
- `spend_hcs`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in health care and social assistance (HCS) MCCs, 7 day moving average.
- `spend_tws`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in transportation and warehousing (TWS) MCCs, 7 day moving average.
- `spend_all_inchigh`: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with high (top quartile) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_all_incmiddle`: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with middle (middle two quartiles) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_all_inclow`: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with low (bottom quartiles) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_all_q2`: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes in the second quartile (i.e. second lowest) of median incomes, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_all_q3`: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes in the third quartile (i.e. second highest) of median incomes, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.
- `spend_retail_w_grocery`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in retail (AAP, CEC, GEN, GRF, HIC, SGH, ETC) MCCs including grocery spending, 7 day moving average.
- `spend_retail_no_grocery`: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in retail (AAP, CEC, GEN, HIC, SGH, ETC) MCCs excluding grocery spending, 7 day moving average.
- `provisional`: Indicator to mark that the date is within the most recent three weeks of data and is subject to non-negligible changes as new data is posted.
- `freq`: Marks whether the data represents a daily ("d") or weekly ("w") value.

The merchant category codes (MCC) making up the retail spending measures are: AAP apparel and accessories, CEC consumer electronics, GEN general merchandise stores, GRF groceries, HIC home improvement centers, SGH sporting goods and hobby, ETC miscellaneous.

### Burning Glass

Job postings data from [Burning Glass Technologies](https://www.burning-glass.com/).

- `bg_posts`: Average level of job postings relative to January 4-31 2020.
- `bg_posts_ss30`: Average level of job postings relative to January 4-31 2020 in manufacturing (NAICS supersector 30).
- `bg_posts_ss55`: Average level of job postings relative to January 4-31 2020 in financial activities (NAICS supersector 55).
- `bg_posts_ss60`: Average level of job postings relative to January 4-31 2020 in professional and business services (NAICS supersector 60).
- `bg_posts_ss65`: Average level of job postings relative to January 4-31 2020 in education and health services (NAICS supersector 65).
- `bg_posts_ss70`: Average level of job postings relative to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).
- `bg_posts_jz1`: Average level of job postings relative to January 4-31 2020 requiring little/no preparation (ONET jobzone level 1).
- `bg_posts_jz2`: Average level of job postings relative to January 4-31 2020 requiring some preparation (ONET jobzone level 2).
- `bg_posts_jz3`: Average level of job postings relative to January 4-31 2020 requiring medium preparation (ONET jobzone level 3).
- `bg_posts_jz4`: Average level of job postings relative to January 4-31 2020 requiring considerable preparation (ONET jobzone level 4).
- `bg_posts_jz5`: Average level of job postings relative to January 4-31 2020 requiring extensive preparation (ONET jobzone level 5).
- `bg_posts_jzgrp12`: Average level of job postings relative to January 4-31 2020 requiring low preparation (ONET jobzone levels 1 and 2).
- `bg_posts_jzgrp345`: Average level of job postings relative to January 4-31 2020 requiring high preparation (ONET jobzone levels 3, 4 and 5).

### COVID

COVID cases, deaths, tests, and vaccination numbers are from the [CDC](https://covid.cdc.gov/covid-data-tracker/#datatracker-home).

- `case_rate`: Confirmed COVID-19 cases per 100,000 people, seven day moving average.
    - `case_count`: Confirmed COVID-19 cases, seven day moving average.
- `new_case_rate`: New confirmed COVID-19 cases per 100,000 people, seven day moving average.
    - `new_case_count`: New confirmed COVID-19 cases, seven day moving average.
- `death_rate`: Confirmed COVID-19 deaths per 100,000 people, seven day moving average.
    - `death_count`: Confirmed COVID-19 deaths, seven day moving average.
- `new_death_rate`: New confirmed COVID-19 deaths per 100,000 people, seven day moving average.
    - `new_death_count`: New confirmed COVID-19 deaths, seven day moving average.
- `test_rate`: Confirmed COVID-19 tests per 100,000 people, seven day moving average.
    - `test_count`: Confirmed COVID-19 tests, seven day moving average.
- `new_test_rate`: New confirmed COVID-19 tests per 100,000 people, seven day moving average.
    - `new_test_count`: New confirmed COVID-19 tests, seven day moving average.
- `vaccine_rate`: First vaccine doses administered per 100 people.
    - `vaccine_count`: First vaccine doses administered.
- `new_vaccine_rate`: New first vaccine doses administered per 100 people, seven day moving average.
    - `new_vaccine_count`: New first vaccine doses administered, seven day moving average.

### Google Mobility

GPS mobility data indexed to Jan 3-Feb 6 2020 from [Google COVID-19 Community Mobility Reports](https://www.google.com/covid19/mobility/).

- `gps_away_from_home`: Time spent outside of residential locations.
- `gps_retail_and_recreation`: Time spent at retail and recreation locations.
- `gps_grocery_and_pharmacy`: Time spent at grocery and pharmacy locations.
- `gps_parks`: Time spent at parks.
- `gps_transit_stations`: Time at inside transit stations.
- `gps_workplaces`: Time spent at work places.
- `gps_residential`: Time spent at residential locations.

### Employment

Employment levels relative to Jan 4-31 2020 from [Paychex](https://www.paychex.com/), [Intuit](https://www.intuit.com/), [Earnin](https://www.earnin.com/) and [Kronos](https://www.kronos.com/).

- `emp_combined`: Employment level for all workers.
- `emp_combined_inclow`: Employment level for workers in the bottom quartile of the income distribution (incomes approximately under $27,000).
- `emp_combined_incq2`: Employment level for workers in the second quartile of the income distribution (incomes approximately $27,000 to $37,000).
- `emp_combined_incmiddle`: Employment level for workers in the middle two quartiles of the income distribution (incomes approximately $27,000 to $60,000).
- `emp_combined_incq3`: Employment level for workers in the third quartile of the income distribution (incomes approximately $37,000 to $60,000).
- `emp_combined_inchigh`: Employment level for workers in the top quartile of the income distribution (incomes approximately over $60,000).
- `emp_combined_incbelowmed`: Employment level for workers in the bottom half of the income distribution (incomes approximately under $37,000).
- `emp_combined_incabovemed`: Employment level for workers in the top half of the income distribution (incomes approximately over $37,000).
- `emp_combined_ss40`: Employment level for workers in trade, transportation and utilities (NAICS supersector 40).
- `emp_combined_ss60`: Employment level for workers in professional and business services (NAICS supersector 60).
- `emp_combined_ss65`: Employment level for workers in education and health services (NAICS supersector 65).
- `emp_combined_ss70`: Employment level for workers in leisure and hospitality (NAICS supersector 70).
- `emp_combined_retail`: Employment level for workers in retail (NAICS sector 44-45).
- `emp_combined_retail_inclow`: Employment level for workers in retail (NAICS sector 44-45) and in the bottom quartile of the income distribution (incomes approximately under $27,000).
- `emp_combined_retail_incmiddle`: Employment level for workers in retail (NAICS sector 44-45) and in the middle two quartiles of the income distribution (incomes approximately $27,000 to $60,000).
- `emp_combined_retail_inchigh`: Employment level for workers in retail (NAICS sector 44-45) and in the top quartile of the income distribution (incomes approximately over $60,000).
- `emp_combined_advance`: Indicator (0 or 1) for whether employment data is a forecasted employment level based on timecard data from Kronos and employees on weekly paycycles from Paychex.

### UI Claims

Unemployment insurance claims data from the [Department of Labor](https://oui.doleta.gov/unemploy/DataDashboard.asp) (national and state-level) and numerous individual state agencies (county-level).

- `initclaims_rate_regular`: Number of initial claims per 100 people in the 2019 labor force, Regular UI only
    - `initclaims_count_regular`: Count of initial claims, Regular UI only
- `initclaims_rate_pua`: Number of initial claims per 100 people in the 2019 labor force, PUA (Pandemic Unemployment Assistance) only
    - `initclaims_count_pua`: Count of initial claims, PUA (Pandemic Unemployment Assistance) only
- `initclaims_rate_combined`: Number of initial claims per 100 people in the 2019 labor force, combining Regular and PUA claims
    - `initclaims_count_combined`: Count of initial claims, combining Regular and PUA claims
- `contclaims_rate_regular`: Number of continued claims per 100 people in the 2019 labor force, Regular UI only
    - `contclaims_count_regular`: Count of continued claims, Regular UI only
- `contclaims_rate_pua`: Number of continued claims per 100 people in the 2019 labor force, PUA (Pandemic Unemployment Assistance) only
    - `contclaims_count_pua`: Count of continued claims, PUA (Pandemic Unemployment Assistance) only
- `contclaims_rate_peuc`: Number of continued claims per 100 people in the 2019 labor force, PEUC (Pandemic Emergency Unemployment Compensation) only
    - `contclaims_count_peuc`: Count of continued claims, PEUC (Pandemic Emergency Unemployment Compensation) only
- `contclaims_rate_combined`: Number of continued claims per 100 people in the 2019 labor force, combining Regular, PUA and PEUC claims
    - `contclaims_count_combined`: Count of continued claims, combining Regular, PUA and PEUC claims

### Womply

Small business openings and revenue data from [Womply](https://www.womply.com/).

- `merchants_all`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020.
- `merchants_inchigh`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in high income (quartile 4 of median income) ZIP codes.
- `merchants_incmiddle`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in middle income (quartiles 2 & 3 of median income) ZIP codes.
- `merchants_inclow`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in low income (quartile 1 of median income) ZIP codes.
- `merchants_ss40`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in transportation (NAICS supersector 40).
- `merchants_ss60`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).
- `merchants_ss65`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).
- `merchants_ss70`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).
- `merchants_retail`: Percent change in number of small businesses open, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in retail businesses (NAICS 2-digit codes 44-45).
- `merchants_food_accommodation`: Percent change in number of small businesses open, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in food and accommodation businesses (NAICS 2-digit code 72)
- `revenue_all`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020.
- `revenue_inchigh`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in high income (quartile 4 of median income) zipcodes.
- `revenue_incmiddle`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in middle income (quartiles 2 & 3 of median income) zipcodes.
- `revenue_inclow`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in low income (quartile 1 of median income) zipcodes.
- `revenue_ss40`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in transportation (NAICS supersector 40).
- `revenue_ss60`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).
- `revenue_ss65`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).
- `revenue_ss70`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).
- `revenue_retail`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in retail businesses (NAICS 2-digit codes 44-45).
- `revenue_food_accommodation`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in food and accommodation businesses (NAICS 2-digit code 72).

Note at the County level, these variables are calculated on a weekly basis as a 6-day average of days Monday through Saturday. Omitting Sunday reduces the influence of imputations in small geographic areas, as discussed in the [data documentation](https://github.com/OpportunityInsights/EconomicTracker/blob/main/docs/oi_tracker_data_documentation.md).

### Zearn

Online math learning data from [Zearn](https://www.zearn.org/).

- `engagement`: Average level of students using platform relative to January 6-February 21 2020.
- `engagement_inclow`: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.
- `engagement_incmiddle`: Average level of students using platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.
- `engagement_inchigh`: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income.
- `badges`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020.
- `badges_inclow`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.
- `badges_incmiddle`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.
- `badges_inchigh`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income.
<!-- List additional variables in comments so they are detected by `verify-csv-columns.py`
- `break_engagement`:
- `break_badges`:
- `break_engagement_inchigh`:
- `break_badges_inchigh`:
- `break_engagement_inclow`:
- `break_badges_inclow`:
- `break_engagement_incmiddle`:
- `break_badges_incmiddle`:
- `imputed_from_cz`:
-->

Note that for every variable listed here, there is a corresponding variable with the prefix `break_` (for example, `break_engagement`). During the period in which schools are on summer or winter break, we record the outcomes in these `break_` variables instead of the usual variables. These numbers are not displayed on the [Economic Tracker](https://tracktherecovery.org) because they do not reliably measure differences in student learning across geography and income groups when many schools are on break.

To ensure privacy, the results for some counties are masked. Where possible, masked county levels values are replaced by commuting zone means, as indicated by the `imputed_from_cz` variable. The masking criteria are explained in further detail in our [data documentation](https://github.com/OpportunityInsights/EconomicTracker/blob/main/docs/oi_tracker_data_documentation.md#online-math-participation).

## Policy Milestones

Key state-level policy dates relevant for changes in other series trends and values.

- `statename`: The name of the U.S. state
- `statefips`: 2-digit FIPS code of the U.S. state
- `schools_closed`: The date at which the state ordered all public K-12 schools statewide to physically close
- `nonessential_biz_closed`: The date on which the state government ordered all nonessential businesses to close
- `stayathome_start`: The date on which the state government told residents to stay home, save for excepted activities
- `regional_stayathome_end`: The date on which the state’s order telling residents to stay home expired, was lifted, or relaxed for one or more regions in the state
- `statewide_stayathome_end`: The date on which the state’s order telling residents to stay home expired, was lifted, or changed from mandatory to recommended. Either for the entire state all at once, or for the very last locality with a remaining stay at home order.
- `regional_biz_opened`: The date on which the state began reopening significant businesses (typically in-store retail or non-essential manufacturing) for one or more regions in the state
- `statewide_biz_opened`: The date on which the state began reopening significant businesses (typically in-store retail or non-essential manufacturing). Either for the entire state all at once, or for the very last locality which hadn’t yet reopened any businesses.
- `regional_biz_reclosed`: The date on which the state began reclosing businesses (of any sector) that had been reopened previously for one or more regions in the state
- `statewide_biz_reclosed`: The date on which the state began reclosing businesses (of any sector) that had been reopened previously. Either for the entire state all at once, or for the very last locality which hadn’t yet reclosed any businesses.
- `state_milestone#`: The dates on which the state enacted significant new policy milestones that go beyond the existing policy dates tracked. Examples include, ending a reclosure, enacting a new regional reopening system, or issuing a stay-at-home advisory, or enacting an additional reclosure after a state's first. The column name suffix indicates both the chronological order of the milestones within the particular state and corresponds to the particular milestone type as indicated in the description&#35; column.
- `description#`: A description of the policy action represented by the state_milestone&#35; column with the same suffix number. For instance state_milestone1 is described in description1.
