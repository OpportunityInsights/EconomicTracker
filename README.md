# Opportunity Insights Economic Tracker Data Downloads

The Opportunity Insights Economic Tracker (https://tracktherecovery.org) combines anonymized data from leading private companies – from credit card processors to payroll firms – to provide a real-time picture of indicators such as employment rates, consumer spending, and job postings across counties, industries, and income groups.

All of the data displayed on the Economic Tracker can be downloaded here. In collaboration with our data partners, we are making this data freely available in order to assist in efforts to inform the public, policymakers, and researchers about the real-time state of the economy and the effects of COVID-19.

Anyone is welcome to use this data; we simply we ask that you attribute our work by citing or linking to [the accompanying paper](https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf) and the Economic Tracker at https://tracktherecovery.org.

> "How Did COVID-19 and Stabilization Policies Aﬀect Spending and Employment? A New Real-Time Economic Tracker Based on Private Sector Data", by Raj Chetty, John Friedman, Nathaniel Hendren, Michael Stepner, and the Opportunity Insights Team. June 2020. Available at: https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf

# Data Dictionary

### Overview 

Each data source and level of aggregation has a separate CSV, named using the following convention: *Data source* — *Geographic Level of Aggregation* — *Temporal Level of Aggregation*

Additionally, we have three files, **GeoIDs – State** and **GeoIDs – County** and **GeoIDs - City**, that provide information on geographic crosswalks and aggregation. These can be merged to any file sharing the same geographic level of aggregation using the geographic identifier. Additionally, **GeoIDs – County** indicates the commuting zone (CZ) and state that each county belongs to. The City-level data (listed under "Metro" on the tracker site) associates the largest cities in the United States with a representative county one-to-one (except in the case of New York City which includes the 5 boroughs).

A description of the columns in each file follows.

### GeoID File Descriptions

#### GeoIDs - State.csv

Geographic identifier: `statefips`

- `statename`: The name of the state.
- `stateabbrev`: The 2-letter state abbreviation.
- `state_pop2019`: The population of the state in 2019, from Census Bureau estimates.

#### GeoIDs - County.csv

Geographic identifier: `countyfips`

- `countyname`: The name of the county.
- `cz`: The numeric identifier of the commuting zone (CZ) in which the county is contained.
- `czname`: The name of the commuting zone (CZ) in which the county is contained.
- `statename`: The name of the state in which the county is contained.
- `statefips`: The fips code of the state in which the county is contained.
- `stateabbrev`: The 2-letter abbreviation of the state in which the county is contained.
- `county_pop2019`: The population of the county in 2019, from Census Bureau estimates.

#### GeoIDs - City.csv

Geographic identifier: `cityid`

- `cityname`: The name of the city.
- `stateabbrev`: The 2-letter abbreviation of the state in which the city is contained.
- `statename`: The name of the state in which the city is contained.
- `statefips`: The fips code of the state in which the city is contained.
- `city_pop2019`: The population of the city in 2019.

### File Descriptions


#### Affinity

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

#### Burning Glass

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

#### COVID Cases

COVID case rates from the [New York Times COVID-19 repository](https://github.com/nytimes/covid-19-data).

- `case_rate`: Confirmed COVID-19 cases per 100,000 people, seven day moving average.
- `new_case_rate`: New confirmed COVID-19 cases per 100,000 people, seven day moving average.

#### COVID Deaths

COVID death rates from the [New York Times COVID-19 repository](https://github.com/nytimes/covid-19-data).

- `death_rate`: Confirmed COVID-19 deaths per 100,000 people, seven day moving average.
- `new_death_rate`: New confirmed COVID-19 deaths per 100,000 people, seven day moving average.

#### COVID Tests

COVID test rates from the [COVID Tracking Project](https://covidtracking.com/).

- `test_rate`: Confirmed COVID-19 tests per 100,000 people, seven day moving average.
- `new_test_rate`: New confirmed COVID-19 tests per 100,000 people, seven day moving average.

#### Google Mobility

GPS mobility data indexed to Jan 3-Feb 6 2020 from [Google COVID-19 Community Mobility Reports](https://www.google.com/covid19/mobility/).

- `gps_away_from_home`: Time spent outside of residential locations.
- `gps_retail_and_recreation`: Time spent at retail and recreation locations.
- `gps_grocery_and_pharmacy`: Time spent at grocery and pharmacy locations. 
- `gps_parks`: Time spent at parks.
- `gps_transit_stations`: Time at inside transit stations.
- `gps_workplaces`: Time spent at work places.
- `gps_residential`: Time spent at residential locations.

#### Low Inc Earnings All Businesses / Low Inc Earnings Small Businesses

Earnings data relative to Jan 4-31 for low-income workers from [Earnin](https://www.earnin.com/) and [Homebase](https://joinhomebase.com/).

- `pay`: Earnings received by low-income workers.
- `pay31_33`: Earnings received by low-income workers in Sector 31-33: Manufacturing.
- `pay44_45`: Earnings received by low-income workers in Sector 44-45: Retail Trade.
- `pay48_49`: Earnings received by low-income workers in Sector 48-49: Transportation and Warehousing.
- `pay62`: Earnings received by low-income workers in Sector 62: Health Care and Social Assistance.
- `pay72`: Earnings received by low-income workers in Sector 72: Accommodation and Food Services. 
- `pay_inclow`: Earnings received by low-income employees working in ZIP codes in the bottom quartile of national median income.
- `pay_incmiddle`: Earnings received by low-income employees working in ZIP codes in the middle two quartile of national median income.
- `pay_inchigh`: Earnings received by low-income employees working in ZIP codes in the top quartile of national median income.

#### Low Inc Emp All Businesses / Low Inc Emp Small Businesses

Employment data relative to Jan 4-31 for low-income workers from [Earnin](https://www.earnin.com/) and [Homebase](https://joinhomebase.com/).

- `emp`: Employment level for low-income workers.
- `emp31_33`: Employment level for low-income workers in Sector 31-33: Manufacturing.
- `emp44_45`: Employment level for low-income workers in Sector 44-45: Retail Trade.
- `emp48_49`: Employment level for low-income workers in Sector 48-49: Transportation and Warehousing.
- `emp62`: Employment level for low-income workers in Sector 62: Health Care and Social Assistance.
- `emp72`: Employment level for low-income workers in Sector 72: Accommodation and Food Services. 
- `emp_inclow`: Employment level for low-income employees working in ZIP codes in the bottom quartile of national median income.
- `emp_incmiddle`: Employment level for low-income employees working in ZIP codes in the middle two quartile of national median income.
- `emp_inchigh`: Employment level for low-income employees working in ZIP codes in the top quartile of national median income.

#### UI Claims

Unemployment insurance claims data from the [Department of Labor](https://oui.doleta.gov/unemploy/DataDashboard.asp) (national and state-level) and numerous individual state agencies (county-level).

- `initial_claims`: Count of newly requested claims to begin a period of unemployment insurance eligibility.
- `initial_claims_rate`: Initial claims per 100 people in the 2019 labor force.
- `total_claims`: Count of initial claims plus the count of continuing claims from people continuing to receive unemployment insurance benefits.
- `total_claims_rate`: Total claims per 100 people in the 2019 labor force.

#### Womply Merchants

Small business openings data from [Womply](https://www.womply.com/).

- `merchants_all`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020. 
- `merchants_inchigh`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in high income (quartile 4 of median income) ZIP codes.
- `merchants_incmiddle`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in middle income (quartiles 2 & 3 of median income) ZIP codes.
- `merchants_inclow`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in low income (quartile 1 of median income) ZIP codes.
- `merchants_ss40`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in transportation (NAICS supersector 40).
- `merchants_ss60`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).
- `merchants_ss65`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).
- `merchants_ss70`: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).

#### Womply Revenue

Small business revenue data from [Womply](https://www.womply.com/).

- `revenue_all`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020.
- `revenue_inchigh`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in high income (quartile 4 of median income) zipcodes.
- `revenue_inclow`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in low income (quartile 1 of median income) zipcodes.
- `revenue_incmiddle`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in middle income (quartiles 2 & 3 of median income) zipcodes.
- `revenue_ss40`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in transportation (NAICS supersector 40).
- `revenue_ss60`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).
- `revenue_ss65`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).
- `revenue_ss70`: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).


#### Zearn

Online math learning data from [Zearn](https://www.zearn.org/).

- `engagement`: Average level of students using platform relative to January 6-February 21 2020.
- `engagement_inclow`: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.
- `engagement_incmiddle`: Average level of students using platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.
- `engagement_inchigh`: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income.
- `badges`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020.
- `badges_inclow`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.
- `badges_incmiddle`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.
- `badges_inchigh`: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income.


# Privacy and Integrity Statement

Opportunity Insights is committed to the rigorous protection of individual and business privacy and fidelity to academic integrity through independent, non-partisan research and policy analysis.

The data reflected in the Opportunity Insights Economic Tracker are aggregated, de-identified, and do not reveal information about specific individuals, transactions, or businesses. Opportunity Insights is a leader in ​[developing privacy protection tools](https://opportunityinsights.org/paper/differential-privacy/)​ and methods, and all data releases follow rigorous protocols to protect individual privacy.

Each external organization that has contributed data to the Economic Tracker has done so with the explicit understanding that Opportunity Insights will use the contributed data in the Economic Tracker without precondition, subject to the data privacy standards set by data providers and any associated regulatory protections.

The Opportunity Insights Economic Tracker is a freely available public good. Opportunity Insights will never sell or monetize data and will not share the underlying data from the Economic Tracker with any third party (including any Opportunity Insights​​ [funder](https://opportunityinsights.org/team/)​).
