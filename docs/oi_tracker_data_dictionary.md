<body>
<header>
<h1 class="title"><div style="white-space: pre-line;">Opportunity Insights Economic Tracker
Data Dictionary</div></h1>
<p class="subtitle">last updated on 2021-03-03</p>
</header>
<p><a href="https://raw.githubusercontent.com/OpportunityInsights/EconomicTracker/main/docs/oi_tracker_data_dictionary.pdf"><img src="pdf-icon.svg" alt="PDF Download" width="50" style="display:inline;"/> <img src="null.png" alt="Click here to download a PDF version of this document" /></a></p>
<h2 id="overview">Overview</h2>
<p>Each data source and level of aggregation has a separate CSV, named using the following convention: <em>Data source</em> – <em>Geographic Level of Aggregation</em> – <em>Temporal Level of Aggregation</em></p>
<p>Additionally, we have three files, <strong>GeoIDs – State</strong> and <strong>GeoIDs – County</strong> and <strong>GeoIDs – City</strong>, that provide information on geographic crosswalks and aggregation. These can be merged to any file sharing the same geographic level of aggregation using the geographic identifier. Additionally, <strong>GeoIDs – County</strong> indicates the commuting zone (CZ) and state that each county belongs to. The City-level data (listed under &quot;Metro&quot; on the tracker site) associates the largest cities in the United States with a representative county one-to-one (except in the case of New York City which includes the 5 boroughs).</p>
<p>Finally, we have gathered a collection of key state-level policy dates relevant for changes in other series trends and values. These are contained in the <strong>Policy Milestones – State</strong> file.</p>
<p>A description of the columns in each file follows.</p>
<h2 id="geoid-file-descriptions">GeoID File Descriptions</h2>
<h3 id="geoids---state.csv">GeoIDs - State.csv</h3>
<p>Geographic identifier: <code>statefips</code></p>
<ul>
<li><code>statename</code>: The name of the state.</li>
<li><code>stateabbrev</code>: The 2-letter state abbreviation.</li>
<li><code>state_pop2019</code>: The population of the state in 2019, from Census Bureau estimates.</li>
</ul>
<h3 id="geoids---county.csv">GeoIDs - County.csv</h3>
<p>Geographic identifier: <code>countyfips</code></p>
<ul>
<li><code>countyname</code>: The name of the county.</li>
<li><code>cityid</code>: The city identifier that the county is assigned to.</li>
<li><code>cityname</code>: The name of the city that the county is assigned to.</li>
<li><code>cz</code>: The numeric identifier of the commuting zone (CZ) in which the county is contained.</li>
<li><code>czname</code>: The name of the commuting zone (CZ) in which the county is contained.</li>
<li><code>statename</code>: The name of the state in which the county is contained.</li>
<li><code>statefips</code>: The FIPS code of the state in which the county is contained.</li>
<li><code>stateabbrev</code>: The 2-letter abbreviation of the state in which the county is contained.</li>
<li><code>county_pop2019</code>: The population of the county in 2019 according to Census Bureau estimates.</li>
</ul>
<h3 id="geoids---city.csv">GeoIDs - City.csv</h3>
<p>Geographic identifier: <code>cityid</code></p>
<ul>
<li><code>cityname</code>: The name of the city.</li>
<li><code>stateabbrev</code>: The 2-letter abbreviation of the primary state in which the city is contained.</li>
<li><code>statename</code>: The name of the primary state in which the city is contained.</li>
<li><code>statefips</code>: The FIPS code of the primary state in which the city is contained.</li>
<li><code>lat</code>: Latitude of the city.</li>
<li><code>lon</code>: Longitude of the city.</li>
<li><code>city_pop2019</code>: The population of the city in 2019 according to Census Bureau estimates, calculated as population of the county or counties assigned to the city.</li>
</ul>
<h2 id="data-file-descriptions">Data File Descriptions</h2>
<h3 id="affinity">Affinity</h3>
<p>Spending data from <a href="https://www.affinity.solutions">Affinity Solutions</a>.</p>
<ul>
<li><code>spend_all</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_acf</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in accomodation and food service (ACF) MCCs, 7 day moving average, 7 day moving average.</li>
<li><code>spend_aer</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in arts, entertainment, and recreation (AER) MCCs, 7 day moving average.</li>
<li><code>spend_apg</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in general merchandise stores (GEN) and apparel and accessories (AAP) MCCs, 7 day moving average.</li>
<li><code>spend_grf</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in grocery and food store (GRF) MCCs, 7 day moving average.</li>
<li><code>spend_hcs</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in health care and social assistance (HCS) MCCs, 7 day moving average.</li>
<li><code>spend_tws</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in transportation and warehousing (TWS) MCCs, 7 day moving average.</li>
<li><code>spend_all_inchigh</code>: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with high (top quartile) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_all_incmiddle</code>: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with middle (middle two quartiles) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_all_inclow</code>: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes with low (bottom quartiles) median income, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_all_q2</code>: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes in the second quartile (i.e. second lowest) of median incomes, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_all_q3</code>: Seasonally adjusted credit/debit card spending by consumers living in ZIP codes in the third quartile (i.e. second highest) of median incomes, relative to January 4-31 2020 in all merchant category codes (MCC), 7 day moving average.</li>
<li><code>spend_retail_w_grocery</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in retail (AAP, CEC, GEN, GRF, HIC, ETC, SGH) MCCs including grocery spending, 7 day moving average.</li>
<li><code>spend_retail_no_grocery</code>: Seasonally adjusted credit/debit card spending relative to January 4-31 2020 in retail (AAP, CEC, GEN, HIC, ETC, SGH) MCCs excluding grocery spending, 7 day moving average.</li>
<li><code>provisional</code>: Indicator to mark that the date is within the most recent three weeks of data and is subject to non-negligible changes as new data is posted.</li>
<li><code>freq</code>: Marks whether the data represents a daily (&quot;d&quot;) or weekly (&quot;w&quot;) value.</li>
</ul>
<h3 id="burning-glass">Burning Glass</h3>
<p>Job postings data from <a href="https://www.burning-glass.com/">Burning Glass Technologies</a>.</p>
<ul>
<li><code>bg_posts</code>: Average level of job postings relative to January 4-31 2020.</li>
<li><code>bg_posts_ss30</code>: Average level of job postings relative to January 4-31 2020 in manufacturing (NAICS supersector 30).</li>
<li><code>bg_posts_ss55</code>: Average level of job postings relative to January 4-31 2020 in financial activities (NAICS supersector 55).</li>
<li><code>bg_posts_ss60</code>: Average level of job postings relative to January 4-31 2020 in professional and business services (NAICS supersector 60).</li>
<li><code>bg_posts_ss65</code>: Average level of job postings relative to January 4-31 2020 in education and health services (NAICS supersector 65).</li>
<li><code>bg_posts_ss70</code>: Average level of job postings relative to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).</li>
<li><code>bg_posts_jz1</code>: Average level of job postings relative to January 4-31 2020 requiring little/no preparation (ONET jobzone level 1).</li>
<li><code>bg_posts_jz2</code>: Average level of job postings relative to January 4-31 2020 requiring some preparation (ONET jobzone level 2).</li>
<li><code>bg_posts_jz3</code>: Average level of job postings relative to January 4-31 2020 requiring medium preparation (ONET jobzone level 3).</li>
<li><code>bg_posts_jz4</code>: Average level of job postings relative to January 4-31 2020 requiring considerable preparation (ONET jobzone level 4).</li>
<li><code>bg_posts_jz5</code>: Average level of job postings relative to January 4-31 2020 requiring extensive preparation (ONET jobzone level 5).</li>
<li><code>bg_posts_jzgrp12</code>: Average level of job postings relative to January 4-31 2020 requiring low preparation (ONET jobzone levels 1 and 2).</li>
<li><code>bg_posts_jzgrp345</code>: Average level of job postings relative to January 4-31 2020 requiring high preparation (ONET jobzone levels 3, 4 and 5).</li>
</ul>
<h3 id="covid">COVID</h3>
<p>COVID case numbers and death numbers from the <a href="https://github.com/nytimes/covid-19-data">New York Times COVID-19 repository</a>. COVID test numbers from the <a href="https://covidtracking.com/">COVID Tracking Project</a>.</p>
<ul>
<li><code>case_rate</code>: Confirmed COVID-19 cases per 100,000 people, seven day moving average.
<ul>
<li><code>case_count</code>: Confirmed COVID-19 cases, seven day moving average.</li>
</ul></li>
<li><code>new_case_rate</code>: New confirmed COVID-19 cases per 100,000 people, seven day moving average.
<ul>
<li><code>new_case_count</code>: New confirmed COVID-19 cases, seven day moving average.</li>
</ul></li>
<li><code>death_rate</code>: Confirmed COVID-19 deaths per 100,000 people, seven day moving average.
<ul>
<li><code>death_count</code>: Confirmed COVID-19 deaths, seven day moving average.</li>
</ul></li>
<li><code>new_death_rate</code>: New confirmed COVID-19 deaths per 100,000 people, seven day moving average.
<ul>
<li><code>new_death_count</code>: New confirmed COVID-19 deaths, seven day moving average.</li>
</ul></li>
<li><code>test_rate</code>: Confirmed COVID-19 tests per 100,000 people, seven day moving average.
<ul>
<li><code>test_count</code>: Confirmed COVID-19 tests, seven day moving average.</li>
</ul></li>
<li><code>new_test_rate</code>: New confirmed COVID-19 tests per 100,000 people, seven day moving average.
<ul>
<li><code>new_test_count</code>: New confirmed COVID-19 tests, seven day moving average.</li>
</ul></li>
</ul>
<h3 id="google-mobility">Google Mobility</h3>
<p>GPS mobility data indexed to Jan 3-Feb 6 2020 from <a href="https://www.google.com/covid19/mobility/">Google COVID-19 Community Mobility Reports</a>.</p>
<ul>
<li><code>gps_away_from_home</code>: Time spent outside of residential locations.</li>
<li><code>gps_retail_and_recreation</code>: Time spent at retail and recreation locations.</li>
<li><code>gps_grocery_and_pharmacy</code>: Time spent at grocery and pharmacy locations.</li>
<li><code>gps_parks</code>: Time spent at parks.</li>
<li><code>gps_transit_stations</code>: Time at inside transit stations.</li>
<li><code>gps_workplaces</code>: Time spent at work places.</li>
<li><code>gps_residential</code>: Time spent at residential locations.</li>
</ul>
<h3 id="employment">Employment</h3>
<p>Employment levels relative to Jan 4-31 from <a href="https://www.paychex.com/">Paychex</a>, <a href="https://www.intuit.com/">Intuit</a>, <a href="https://www.earnin.com/">Earnin</a> and <a href="https://www.kronos.com/">Kronos</a>.</p>
<ul>
<li><code>emp_combined</code>: Employment level for all workers.</li>
<li><code>emp_combined_inclow</code>: Employment level for workers in the bottom quartile of the income distribution (incomes approximately under $27,000).</li>
<li><code>emp_combined_incmiddle</code>: Employment level for workers in the middle two quartiles of the income distribution (incomes approximately $27,000 to $60,000).</li>
<li><code>emp_combined_inchigh</code>: Employment level for workers in the top quartile of the income distribution (incomes approximately over $60,000).</li>
<li><code>emp_combined_ss40</code>: Employment level for workers in trade, transportation and utilities (NAICS supersector 40).</li>
<li><code>emp_combined_ss60</code>: Employment level for workers in professional and business services (NAICS supersector 60).</li>
<li><code>emp_combined_ss65</code>: Employment level for workers in education and health services (NAICS supersector 65).</li>
<li><code>emp_combined_ss70</code>: Employment level for workers in leisure and hospitality (NAICS supersector 70).</li>
<li><code>emp_combined_retail</code>: Employment level for workers in retail (NAICS sector 44-45).</li>
<li><code>emp_combined_retail_inclow</code>: Employment level for workers in retail (NAICS sector 44-45) and in the bottom quartile of the income distribution (incomes approximately under $27,000).</li>
<li><code>emp_combined_retail_incmiddle</code>: Employment level for workers in retail (NAICS sector 44-45) and in the middle two quartiles of the income distribution (incomes approximately $27,000 to $60,000).</li>
<li><code>emp_combined_retail_inchigh</code>: Employment level for workers in retail (NAICS sector 44-45) and in the top quartile of the income distribution (incomes approximately over $60,000).</li>
<li><code>emp_combined_advance</code>: Indicator (0 or 1) for whether employment data is a forecasted employment level based on timecard data from Kronos and employees on weekly paycycles from Paychex.</li>
</ul>
<h3 id="ui-claims">UI Claims</h3>
<p>Unemployment insurance claims data from the <a href="https://oui.doleta.gov/unemploy/DataDashboard.asp">Department of Labor</a> (national and state-level) and numerous individual state agencies (county-level).</p>
<ul>
<li><code>initclaims_rate_regular</code>: Number of initial claims per 100 people in the 2019 labor force, Regular UI only
<ul>
<li><code>initclaims_count_regular</code>: Count of initial claims, Regular UI only</li>
</ul></li>
<li><code>initclaims_rate_pua</code>: Number of initial claims per 100 people in the 2019 labor force, PUA (Pandemic Unemployment Assistance) only
<ul>
<li><code>initclaims_count_pua</code>: Count of initial claims, PUA (Pandemic Unemployment Assistance) only</li>
</ul></li>
<li><code>initclaims_rate_combined</code>: Number of initial claims per 100 people in the 2019 labor force, combining Regular and PUA claims
<ul>
<li><code>initclaims_count_combined</code>: Count of initial claims, combining Regular and PUA claims</li>
</ul></li>
<li><code>contclaims_rate_regular</code>: Number of continued claims per 100 people in the 2019 labor force, Regular UI only
<ul>
<li><code>contclaims_count_regular</code>: Count of continued claims, Regular UI only</li>
</ul></li>
<li><code>contclaims_rate_pua</code>: Number of continued claims per 100 people in the 2019 labor force, PUA (Pandemic Unemployment Assistance) only
<ul>
<li><code>contclaims_count_pua</code>: Count of continued claims, PUA (Pandemic Unemployment Assistance) only</li>
</ul></li>
<li><code>contclaims_rate_peuc</code>: Number of continued claims per 100 people in the 2019 labor force, PEUC (Pandemic Emergency Unemployment Compensation) only
<ul>
<li><code>contclaims_count_peuc</code>: Count of continued claims, PEUC (Pandemic Emergency Unemployment Compensation) only</li>
</ul></li>
<li><code>contclaims_rate_combined</code>: Number of continued claims per 100 people in the 2019 labor force, combining Regular, PUA and PEUC claims
<ul>
<li><code>contclaims_count_combined</code>: Count of continued claims, combining Regular, PUA and PEUC claims</li>
</ul></li>
</ul>
<h3 id="womply">Womply</h3>
<p>Small business openings and revenue data from <a href="https://www.womply.com/">Womply</a>.</p>
<ul>
<li><code>merchants_all</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020.</li>
<li><code>merchants_inchigh</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in high income (quartile 4 of median income) ZIP codes.</li>
<li><code>merchants_incmiddle</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in middle income (quartiles 2 &amp; 3 of median income) ZIP codes.</li>
<li><code>merchants_inclow</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in low income (quartile 1 of median income) ZIP codes.</li>
<li><code>merchants_ss40</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in transportation (NAICS supersector 40).</li>
<li><code>merchants_ss60</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).</li>
<li><code>merchants_ss65</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).</li>
<li><code>merchants_ss70</code>: Percent change in number of small businesses open calculated as a seven-day moving average seasonally adjusted and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).</li>
<li><code>merchants_retail</code>: Percent change in number of small businesses open, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in retail businesses (NAICS 2-digit codes 44-45).</li>
<li><code>merchants_food_accommodation</code>: Percent change in number of small businesses open, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in food and accommodation businesses (NAICS 2-digit code 72)</li>
<li><code>revenue_all</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020.</li>
<li><code>revenue_inchigh</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in high income (quartile 4 of median income) zipcodes.</li>
<li><code>revenue_incmiddle</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in middle income (quartiles 2 &amp; 3 of median income) zipcodes.</li>
<li><code>revenue_inclow</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in low income (quartile 1 of median income) zipcodes.</li>
<li><code>revenue_ss40</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in transportation (NAICS supersector 40).</li>
<li><code>revenue_ss60</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in professional and business services (NAICS supersector 60).</li>
<li><code>revenue_ss65</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in education and health services (NAICS supersector 65).</li>
<li><code>revenue_ss70</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31 2020 in leisure and hospitality (NAICS supersector 70).</li>
<li><code>revenue_retail</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in retail businesses (NAICS 2-digit codes 44-45).</li>
<li><code>revenue_food_accommodation</code>: Percent change in net revenue for small businesses, calculated as a seven-day moving average, seasonally adjusted, and indexed to January 4-31, 2020 in food and accommodation businesses (NAICS 2-digit code 72).</li>
</ul>
<h3 id="zearn">Zearn</h3>
<p>Online math learning data from <a href="https://www.zearn.org/">Zearn</a>.</p>
<ul>
<li><code>engagement</code>: Average level of students using platform relative to January 6-February 21 2020.</li>
<li><code>engagement_inclow</code>: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.</li>
<li><code>engagement_incmiddle</code>: Average level of students using platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.</li>
<li><code>engagement_inchigh</code>: Average level of students using platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income.</li>
<li><code>badges</code>: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020.</li>
<li><code>badges_inclow</code>: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the lowest median income.</li>
<li><code>badges_incmiddle</code>: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in ZIP codes with median income between the 25th and 75th percentiles.</li>
<li><code>badges_inchigh</code>: Average level of students achievements earned (badges) on platform relative to January 6-February 21 2020 for schools in the 25% of ZIP codes with the highest median income. <!-- List additional variables in comments so they are detected by `verify-csv-columns.py`
- `break_engagement`:
- `break_badges`:
- `break_engagement_inchigh`:
- `break_badges_inchigh`:
- `break_engagement_inclow`:
- `break_badges_inclow`:
- `break_engagement_incmiddle`:
- `break_badges_incmiddle`:
- `imputed_from_cz`:
--></li>
</ul>
<p>Note that for every variable listed here, there is a corresponding variable with the prefix <code>break_</code> (for example, <code>break_engagement</code>). During the period in which schools are on summer or winter break, we record the outcomes in these <code>break_</code> variables instead of the usual variables. These numbers are not displayed on the <a href="https://tracktherecovery.org">Economic Tracker</a> because they do not reliably measure differences in student learning across geography and income groups when many schools are on break.</p>
<p>To ensure privacy, the results for some counties are masked. Where possible, masked county levels values are replaced by commuting zone means, as indicated by the <code>imputed_from_cz</code> variable. The masking criteria are explained in further detail in our <a href="https://github.com/OpportunityInsights/EconomicTracker/blob/main/docs/oi_tracker_data_documentation.md#online-math-participation">data documentation</a>.</p>
<h2 id="policy-milestones">Policy Milestones</h2>
<p>Key state-level policy dates relevant for changes in other series trends and values.</p>
<ul>
<li><code>statename</code>: The name of the U.S. state</li>
<li><code>statefips</code>: 2-digit FIPS code of the U.S. state</li>
<li><code>schools_closed</code>: The date at which the state ordered all public K-12 schools statewide to physically close</li>
<li><code>nonessential_biz_closed</code>: The date on which the state government ordered all nonessential businesses to close</li>
<li><code>stayathome_start</code>: The date on which the state government told residents to stay home, save for excepted activities</li>
<li><code>regional_stayathome_end</code>: The date on which the state’s order telling residents to stay home expired, was lifted, or relaxed for one or more regions in the state</li>
<li><code>statewide_stayathome_end</code>: The date on which the state’s order telling residents to stay home expired, was lifted, or changed from mandatory to recommended. Either for the entire state all at once, or for the very last locality with a remaining stay at home order.</li>
<li><code>regional_biz_opened</code>: The date on which the state began reopening significant businesses (typically in-store retail or non-essential manufacturing) for one or more regions in the state</li>
<li><code>statewide_biz_opened</code>: The date on which the state began reopening significant businesses (typically in-store retail or non-essential manufacturing). Either for the entire state all at once, or for the very last locality which hadn’t yet reopened any businesses.</li>
<li><code>regional_biz_reclosed</code>: The date on which the state began reclosing businesses (of any sector) that had been reopened previously for one or more regions in the state</li>
<li><code>statewide_biz_reclosed</code>: The date on which the state began reclosing businesses (of any sector) that had been reopened previously. Either for the entire state all at once, or for the very last locality which hadn’t yet reclosed any businesses.</li>
<li><code>state_milestone#</code>: The dates on which the state enacted significant new policy milestones that go beyond the existing policy dates tracked. Examples include, ending a reclosure, enacting a new regional reopening system, or issuing a stay-at-home advisory, or enacting an additional reclosure after a state's first. The column name suffix indicates both the chronological order of the milestones within the particular state and corresponds to the particular milestone type as indicated in the description# column.</li>
<li><code>description#</code>: A description of the policy action represented by the state_milestone# column with the same suffix number. For instance state_milestone1 is described in description1.</li>
</ul>
</body>
