<body>
<header id="title-block-header">
<h1 class="title"><div class="line-block">Opportunity Insights Economic Tracker<br />
Data Documentation</div></h1>
<p class="subtitle">last updated on 2022-01-18</p>
</header>
<p><a href="https://raw.githubusercontent.com/OpportunityInsights/EconomicTracker/main/docs/oi_tracker_data_documentation.pdf"><img src="pdf-icon.svg" alt="PDF Download" width="50" style="display:inline;"/> Click here to download a PDF version of this document</a></p>
<h1 id="overview">Overview</h1>
<p>This document provides an overview of the sources and processing applied to each data series within the <a href="https://tracktherecovery.org">Opportunity Insights Economic Tracker</a>. The documentation is organized sequentially by series in the tracker, then broken down into categories of information describing each series, its source data, and our processing steps.</p>
<p>You can refer to additional documentation published by Opportunity Insights for complementary information:</p>
<ul>
<li>The Economic Tracker’s <strong><a href="https://github.com/OpportunityInsights/EconomicTracker/blob/main/docs/oi_tracker_data_dictionary.md">Data Dictionary</a></strong> lists each data file and variable available for public use, with short descriptions of the contents of each variable.</li>
<li>The <strong><a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">accompanying paper</a></strong> provides detailed information about the methodology used to construct the series.</li>
</ul>
<p>Please note that both the data and this data documentation is updated regularly and that the following information is subject to change.</p>
<h1 id="data-series">Data Series</h1>
<h2 id="consumer-spending">Consumer Spending</h2>
<p><strong>Summary:</strong> Aggregated and anonymized purchase data from consumer credit and debit card spending. Spending is reported based on the ZIP code where the cardholder lives, not the ZIP code where transactions occurred.</p>
<p><strong>Data Source:</strong> <a href="https://www.affinity.solutions/dataforgood">Affinity Solutions</a></p>
<p><strong>Update Frequency:</strong> Weekly</p>
<p><strong>Date Range:</strong> January 13th until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Data is daily until the final two weeks of the series, and the daily data is presented as a 7 day lookback moving average. For the final two weeks of the series, the data is weekly and presented as weekly data points.</p>
<p><strong>Index Period:</strong> January 4th - January 31st</p>
<p><strong>Indexing Type:</strong> Seasonally adjusted change since January 2020. Data is indexed in 2019 and 2020 as the change relative to the January index period. We then seasonally adjust by dividing year-over-year, which represents the difference between the change since January observed in 2020 compared to the change since January observed since 2019. We account for differences in the dates of federal holidays between 2019 and 2020 by shifting the 2019 reference data to align the holidays before performing the year-over-year division.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>By Industry</em>. Industries are constructed by grouping merchant codes that are used by Affinity Solutions to identify the category of merchant and merchant activity.</p>
<ul>
<li>Apparel and General Merchandise</li>
<li>Entertainment and Recreation</li>
<li>Grocery</li>
<li>Health Care</li>
<li>Resturants and Hotels</li>
<li>Transportation</li>
</ul></li>
<li><p><em>By Consumer Zip Code Income</em>. Transactions are linked to zip codes where the consumer lives and zip codes are classified into income categories based on measurements of median household income and population provided by the American Community Survey (2014 - 2018).</p>
<ul>
<li>High Income (median household income greater than $78,000 per year)</li>
<li>Middle Income (median household income between $46,000 per year and $78,000 per year)</li>
<li>Low Income (median household income less than $46,000 per year)</li>
</ul></li>
</ul>
<p><strong>Data masking:</strong> For the state-level breakdowns by income quartile and the county-level data, we mask locations with average daily spending &lt; $70,000 in January 2019. The raw data contains discontinuous breaks caused by entry or exit of credit card providers from the sample: counties with multiple structural breaks are dropped from the sample. Additionally, Affinity Solutions suppresses any cut of the data with fewer than five transactions. For more details refer to the accompanying <a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">paper</a>.</p>
<p><strong>Notes:</strong> We require at least 3 weeks of data in order to reliably identify and correct discontinuous breaks caused by entry or exit of credit card providers from the sample. The most recent 3 weeks of data are therefore marked ‘provisional’ and are subject to non-negligible changes as new data is posted. For breaks found prior to the last 3 weeks, we correct for it using a method outlined in the <a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">paper</a>. Otherwise we substitute the national mean for more recent breaks while we gather enough data to implement the corrections outlined in the <a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">paper</a>. We typically only allow series to have one significant break, however, in the case of areas with large populations (e.g. Louisville KY) we relax this rule. In these cases, we subtract out the level change but keep the post-break variation.</p>
<h2 id="small-business-revenue">Small Business Revenue</h2>
<p><strong>Summary:</strong> Small business transactions and revenue data aggregated from several credit card processors. Transactions and revenue are reported based on the ZIP code where the business is located.</p>
<p><strong>Data Source:</strong> <a href="https://www.womply.com">Womply</a></p>
<p><strong>Update Frequency:</strong> Weekly</p>
<p><strong>Date Range:</strong> January 15th until the most recent date available.</p>
<p><strong>Data Frequency:</strong></p>
<ul>
<li><em>National, State, Metro</em>: Daily, presented as a 7-day moving average</li>
<li><em>County</em>: Weekly, presented as a 6-day average Monday through Saturday, omitting Sunday</li>
</ul>
<p><strong>Indexing Period:</strong> January 4th - January 31st</p>
<p><strong>Indexing Type:</strong> Seasonally adjusted change since January 2020. Data is indexed in 2019 and 2020 as the change relative to the January index period. We then seasonally adjust by dividing year-over-year, which represents the difference between the change since January observed in 2020 compared to the change since January observed since 2019. We account for differences in the dates of federal holidays between 2019 and 2020 by shifting the 2019 reference data to align the holidays before performing the year-over-year division. For series at the weekly frequency, we define weeks to run from Monday through Saturday and drop Sunday data. (See the Data Masking section below.) Weeks that span the end of the year are treated as the first week of the later year.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>Industry</em>, by <a href="https://www.bls.gov/sae/additional-resources/naics-supersectors-for-ces-program.htm">NAICS supersector</a>.</p>
<ul>
<li>Education and Health Services</li>
<li>Leisure and Hospitality</li>
<li>Professional &amp; Business Services</li>
<li>Retail and Transportation</li>
</ul></li>
<li><p><em>Business Zip Code Income</em>. Transactions are linked to ZIP codes where the business is located and ZIP codes are classified into income categories based on measurements of median household income and population provided by the American Community Survey (2014 - 2018).</p>
<ul>
<li>High Income (median household income greater than $78,000 per year)</li>
<li>Middle Income (median household income between $46,000 per year and $78,000 per year)</li>
<li>Low Income (median household income less than $46,000 per year)</li>
</ul></li>
</ul>
<p><strong>Data Masking:</strong> The sample is restricted to firms with 30 or more transactions in a quarter and more than one transaction in 2 out of the 3 months. To reduce the influence of outliers, Womply excludes firms outside twice the interquartile range of annual firm revenue calculated within the sample. To preserve the privacy of firms, Womply imputes values for cells that contain fewer than 3 merchants.</p>
<p>For the county series, which is measured with a weekly frequency, we reduce the influence of imputation by dropping all data from Sundays (which are disproportionately likely to contain imputations). We drop any County x Week cell that contains imputed data within Monday-Saturday and we drop counties entirely if over 25% of their weeks contain imputed data.</p>
<p>We also exclude counties with a total average revenue of less than $250,000 or an average revenue of less than $10,000 during the indexing period (January 4-31, 2020). Additionally we omit spending categories for a small number of geographies that are extreme positive outliers, and we cap a small number of extreme negative outliers at 0 revenue.</p>
<p><strong>Notes:</strong></p>
<p>Small businesses are defined as those with annual revenue below the Small Business Administration’s <a href="https://www.sba.gov/document/support--table-size-standards">thresholds</a>. Thresholds vary by 6 digit NAICS code ranging from a maximum number of employees between 100 to 1500 to be considered a small business depending on the industry.</p>
<p>County-level and metro-level data and breakdowns by High/Middle/Low income ZIP codes have been temporarily removed since the August 21st 2020 update due to revisions in the structure of the raw data we receive. We hope to add them back to the OI Economic Tracker soon.</p>
<h2 id="small-businesses-open">Small Businesses Open</h2>
<p><strong>Summary:</strong> Number of small businesses open, as defined by having had at least one transaction in the previous 3 days.</p>
<p><strong>Data Source:</strong> <a href="https://www.womply.com">Womply</a></p>
<p><strong>Update Frequency:</strong> Weekly</p>
<p><strong>Date Range:</strong> January 15th until the most recent date available.</p>
<p><strong>Data Frequency:</strong></p>
<ul>
<li><em>National, State, Metro</em>: Daily, presented as a 7-day moving average</li>
<li><em>County</em>: Weekly, presented as a 6-day average Monday through Saturday, omitting Sunday</li>
</ul>
<p><strong>Indexing Period:</strong> January 4th - January 31st</p>
<p><strong>Indexing Type:</strong> Seasonally adjusted change since January 2020. Data is indexed in 2019 and 2020 as the change relative to the January index period. We then seasonally adjust by dividing year-over-year, which represents the difference between the change since January observed in 2020 compared to the change since January observed since 2019. We account for differences in the dates of federal holidays between 2019 and 2020 by shifting the 2019 reference data to align the holidays before performing the year-over-year division. For series at the weekly frequency, we define weeks to run from Monday through Saturday and drop Sunday data. (See the Data Masking section below.) Weeks that span the end of the year are treated as the first week of the later year.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>Industry</em>, by <a href="https://www.bls.gov/sae/additional-resources/naics-supersectors-for-ces-program.htm">NAICS supersector</a>.</p>
<ul>
<li>Education and Health Services</li>
<li>Leisure and Hospitality</li>
<li>Professional &amp; Business Services</li>
<li>Retail and Transportation</li>
</ul></li>
<li><p><em>Business Zip Code Income</em>. Transactions are linked to ZIP codes where the business is located and ZIP codes are classified into income categories based on measurements of median household income and population provided by the American Community Survey (2014 - 2018).</p>
<ul>
<li>High Income (median household income greater than $78,000 per year)</li>
<li>Middle Income (median household income between $46,000 per year and $78,000 per year)</li>
<li>Low Income (median household income less than $46,000 per year)</li>
</ul></li>
</ul>
<p><strong>Data Masking:</strong> The sample is restricted to firms with 30 or more transactions in a quarter and more than one transaction in 2 out of the 3 months. To reduce the influence of outliers, Womply excludes firms outside twice the interquartile range of annual firm revenue calculated within the sample. To preserve the privacy of firms, Womply imputes values for cells that contain fewer than 3 merchants.</p>
<p>For the county series, which is measured with a weekly frequency, we reduce the influence of imputation by dropping all data from Sundays (which are disproportionately likely to contain imputations). We drop any County x Week cell that contains imputed data within Monday-Saturday and we drop counties entirely if over 25% of their weeks contain imputed data.</p>
<p>We also exclude counties with a total average revenue of less than $250,000 or an average revenue of less than $10,000 during the indexing period (January 4-31, 2020). Additionally we omit spending categories for a small number of geographies that are extreme positive outliers, and we cap a small number of extreme negative outliers at 0 revenue.</p>
<p><strong>Notes:</strong> Small businesses are defined as those with annual revenue below the Small Business Administration’s <a href="https://www.sba.gov/document/support--table-size-standards">thresholds</a>. Thresholds vary by 6 digit NAICS code ranging from a maximum number of employees between 100 to 1500 to be considered a small business depending on the industry.</p>
<p>County-level and metro-level data and breakdowns by High/Middle/Low income ZIP codes have been temporarily removed since the August 21st 2020 update due to revisions in the structure of the raw data we receive. We hope to add them back to the OI Economic Tracker soon.</p>
<h2 id="job-postings">Job Postings</h2>
<p><strong>Summary:</strong> Weekly count of new job postings, sourced from over 40,000 online job boards. New job postings are defined as those that have not had a duplicate posting for at least 60 days prior.</p>
<p><strong>Data Source:</strong> <a href="https://www.burning-glass.com">Burning Glass Technologies</a></p>
<p><strong>Update Frequency:</strong> Weekly</p>
<p><strong>Date Range:</strong> January 17th until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Weekly data points, with each week ending on Friday.</p>
<p><strong>Indexing Period:</strong> January 4th - January 31st</p>
<p><strong>Indexing Type:</strong> Change relative to the January 2020 index period, not seasonally adjusted.</p>
<p><strong>Geographies:</strong> National, State, Metro.</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>Industry</em>, by <a href="https://www.bls.gov/sae/additional-resources/naics-supersectors-for-ces-program.htm">NAICS supersector</a>.</p>
<ul>
<li>Educational and Health Services</li>
<li>Financial Activities and Services</li>
<li>Leisure and Hospitality</li>
<li>Manufactoring</li>
<li>Professional and Business Services</li>
</ul></li>
<li><p><em>Education Requirement</em>, by <a href="https://www.onetonline.org/help/online/zones">ONET Jobzone’s Education Requirement Classification</a>.</p>
<ul>
<li>Minimal - Jobzone 1</li>
<li>Some - Jobzone 2</li>
<li>Moderate - Jobzone 3</li>
<li>Considerable - Jobzone 4</li>
<li>Extensive - Jobzone 5</li>
</ul></li>
</ul>
<p><strong>Data Masking:</strong> In order to avoid extreme outliers, we calculate a cutoff of one standard deviation above the 97th percentile of the state-level data for each variable and mask values that exceed this threshold.</p>
<h2 id="employment">Employment</h2>
<p><strong>Summary:</strong> Number of active employees, aggregating information from multiple data providers. This series is based on firm-level payroll data from Paychex and Intuit, worker-level data on employment and earnings from Earnin, and firm-level timesheet data from Kronos.</p>
<p><strong>Data Source:</strong> <a href="https://www.paychex.com/">Paychex</a>, <a href="https://www.intuit.com/">Intuit</a>, <a href="https://www.earnin.com/">Earnin</a>, <a href="https://www.kronos.com/">Kronos</a></p>
<p><strong>Update Frequency:</strong> Weekly</p>
<p><strong>Date Range:</strong> January 15th 2020 until the most recent date available. The most recent date available for the full series depends on the combination of Paychex, Intuit and Earnin data. We extend the national trend of aggregate employment and employment by income quartile by using Kronos timecard data and Paychex data for workers paid on a weekly paycycle to forecast beyond the end of the Paychex, Intuit and Earnin data.</p>
<p><strong>Data Frequency:</strong> Daily, presented as a 7-day moving average</p>
<p><strong>Indexing Period:</strong> January 4th - January 31st</p>
<p><strong>Indexing Type:</strong> Change relative to the January 2020 index period, not seasonally adjusted.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p>To prevent the introduction of new Paychex clients from artificially creating noise in the employment series overtime, in the underlying raw data we suppress county x quartile x industry x firm size cells that both (i) experience a large anomalous change in employment and (ii) made up a large share of given wage quartile’s total employment at any point in a county in the current year. For more details on the specifics of these thresholds see the appendix of the <a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">accompanying paper</a>.</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>Wage</em>.</p>
<ul>
<li>High Income (top wage quartile, annualized income greater than ~$60,000 per year)</li>
<li>Middle Income (middle wage quartiles, annualized income between ~$27,000 per year and ~$60,000 per year)</li>
<li>Low Income (bottom wage quartile, annualized income less than ~$27,000 per year)</li>
<li>Above Median (annualized income greater than ~$37,000 per year)</li>
<li>Below Median (annualized income less than ~$37,000 per year)</li>
</ul></li>
<li><p><em>Industry</em>, by <a href="https://www.bls.gov/sae/additional-resources/naics-supersectors-for-ces-program.htm">NAICS supersector</a>.</p>
<ul>
<li>Professional and Business Services</li>
<li>Education and Health Services</li>
<li>Retail and Transportation</li>
<li>Leisure and Hospitality</li>
</ul></li>
<li><p><em>Industry</em>, by <a href="https://www.census.gov/programs-surveys/economic-census/guidance/understanding-naics.html">NAICS sector</a>.</p>
<ul>
<li>Retail</li>
</ul></li>
</ul>
<p><strong>Data masking:</strong> As the employment series is a composite series, each of its component series have their own masking standards that in aggregate determine masking for the series. Additionally for states where the minimum wage was raised to $13 dollars per hour or higher, we suppress the breakdowns that split out the first quartile from the second quartile as the minimum wage increase pushes a number of workers from the first into the second quartile.</p>
<p><em>In the Paychex series</em>, we reduce the weight of cells in which we detect firm entry/exit over time. In each county x industry (two-digit NAICS code) x firm size x income quartile cell, we compute the change in employment relative to January 4-31 2020, and the change in employment relative to July 1-31 2020. For county x industry x firm size x income quartile cells with over 50 employees at any point between January 2020 and the end of the series, we reduce the weight we place on the series if we observe changes in employment that indicate firm entry or exit. In particular, we reduce the weight we place on the cell by two percentage points for each percentage point of growth we observe above 150 percentage points relative to January 2020. We then further reduce the weight we place on each cell by two percentage points of its January 2020 level for each percentage point of decline we observe below 50 percentage points relative to July 2020.</p>
<p><em>In the Earnin series</em>, we restrict the sample to workers who are active Earnin users with non-missing earnings and hours worked over the last 28 days and we exclude workers whose reported income over the prior 28 days is greater than $50,000/13 (corresponding to an income of greater than $50,000 annually).</p>
<p><em>In the Kronos and Intuit series</em>, we do not make any sample restrictions.</p>
<p><em>In the combined series</em>, we mask the series in two additional ways:</p>
<ul>
<li><p>We do not report changes in employment among low-income or middle-income workers around the date of minimum wage changes. We use hourly wage thresholds when constructing employment by income quartile in the Paychex data. The threshold for the bottom quartile of employment is $13; that is, workers who earn below $13 are assigned to the bottom quartile, whereas workers earning above (or exactly) $13 are allocated to other wage quartiles. On January 1 2021, minimum wage changes came into force in CA, MA, AZ and NY, which caused the minimum wage for some workers to move from below $13 to above $13. This results in a decline in employment for workers earning below $13, and a corresponding increase in employment for workers earning above $13, as firms increased workers’ wages in response to the minimum wage change. As these trends are driven by the legislative change in minimum wages, rather than by underlying economic conditions, we suppress the low-income and middle-income series in these states. Instead, the below-median-income and above-median-income series we have made available can be used to describe trends in employment by income in these states. (As the median wage in the Paychex data is $18.18, the assignment of workers to below-median or above-median income is substantially unaffected by wage changes caused by minimum wage laws.)</p></li>
<li><p>We do not report employment trends in Washington, DC or South Dakota, where our analysis sample is small.</p></li>
</ul>
<p><strong>Notes:</strong></p>
<ul>
<li><p>For low income workers, the change in employment is calculated using Paychex and Earnin data. For medium and high income workers, the change in employment is calculated using Paychex and Intuit data.</p></li>
<li><p>In order to provide closer to real time data, we forecast the most recent employment measures beyond those available in the combined Earnin, Intuit, and Paychex dataset alone. To do so, we leverage two sources of higher frequency data: Kronos timestamp data and the Paychex weekly pay cycle sample. Using this higher frequency data we forecast more recent changes in employment using a distributed lag model, constructed by regressing a given week’s employment measure on the corresponding week’s Kronos measure, as well as its current and 3 previous lagged weeks’ Paychex weekly pay cycle measure. For more details, please refer to the appendix of the accompanying <a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">paper</a>.</p></li>
</ul>
<h2 id="unemployment-claims">Unemployment Claims</h2>
<p><strong>Summary:</strong> Weekly unemployment insurance claims counts and rates (as a share of the 2019 labor force) for all states, as well as initial unemployment insurance claims for select counties where the data is publicly available.</p>
<p><strong>Data Source:</strong> State-level and national statistics are reported by the U.S. Department of Labor.</p>
<p>The county-level series is only available for states whose respective state agencies publish county level data:</p>
<ul>
<li>Alabama: Alabama Department of Labor</li>
<li>Arizona: Arizona Commerce Authority</li>
<li>California: Employment Development Department of California</li>
<li>Colorado: Colorado Department of Labor and Employment</li>
<li>Georgia: Georgia Department of Labor</li>
<li>Hawaii: Hawaii Department of Labor</li>
<li>Idaho: Idaho Department of Labor</li>
<li>Illinois: Illinois Department of Employment Security</li>
<li>Indiana: Indiana Department of Workforce Development</li>
<li>Iowa: State of Iowa</li>
<li>Kentucky: Kentucky Center for Statistics</li>
<li>Maryland: Maryland Department of Labor</li>
<li>Massachusetts: Massachusetts Department of Unemployment Assistance</li>
<li>Missouri: State of Missouri</li>
<li>Nebraska: NEworks (Government of Nebraska)</li>
<li>Nevada: Nevada Department of Employment; Training and Rehabilitation</li>
<li>New York: New York State Department of Labor</li>
<li>Ohio: Ohio Department of Job and Family Services</li>
<li>Pennsylvania: Government of Pennsylvania</li>
<li>Washington: Washington State Employment Security Department</li>
<li>Wisconsin: Wisconsin Department of Workforce Development</li>
<li>Wyoming: Wyoming Department of Workforce Services</li>
</ul>
<p><strong>Update Frequency:</strong> Weekly (where available, in the case of county-level data)</p>
<p><strong>Date Range:</strong> January 18th until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Weekly data points, with each week ending on Saturday.</p>
<p>Note that county-level claims in California, Georgia, Kentucky, and Illinois are reported at the monthly level and imputed to weekly data points for the county-level series. For more information about the imputation methodology, see the <strong><a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">accompanying paper</a></strong></p>
<p><strong>Indexing Period:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Indexing Type:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Geographies:</strong> National, State, County, Metro.</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>Initial Claims</em></p>
<ul>
<li>Regular Claims</li>
<li>PUA Claims</li>
<li>Combined Claims</li>
</ul></li>
<li><p><em>Continued Claims</em></p>
<ul>
<li>Regular Claims</li>
<li>PUA Claims</li>
<li>PEUC Claims</li>
<li>Combined Claims</li>
</ul></li>
</ul>
<p><strong>Data masking:</strong> No masking is performed by Opportunity Insights, but county-level data is subject to varying masking rules implemented by the state agencies that release the data. For more details, check with the relevant state agency for that state’s particular masking rules.</p>
<p><strong>Notes:</strong> Unemployment claims rates are calculated by dividing unemployment claims counts by the Bureau of Labor Statistics labor force estimates from 2019.</p>
<p>Under the CARES Act, all states provide 13 additional weeks of federally funded Pandemic Emergency Unemployment Assistance (PEUC) benefits to people who exhaust their regular state benefits. Under the Act, through the end of 2020, some people who exhaust all these benefits, and others who have lost their jobs for reasons arising from the pandemic but who are not normally eligible for UI in their state, are eligible for Pandemic Unemployment Assistance (PUA). “Combined Claims” are defined as the sum of regular, PUA and PEUC unemployment benefit claims.</p>
<p>National totals for all programs’ unemployment benefit claims are the sum of the claims counts for all states and DC and exclude other territories such as Puerto Rico and the U.S. Virgin Islands.</p>
<h2 id="online-math-participation">Online Math Participation</h2>
<p><strong>Summary:</strong> Number of students using Zearn Math, a curriculum from the non-profit Zearn, among schools that already used Zearn Math in course instruction before the pandemic.</p>
<p><strong>Data Source:</strong> <a href="https://about.zearn.org">Zearn</a></p>
<p><strong>Update Frequency:</strong> Weekly, except during summer and winter school breaks.</p>
<p><strong>Date Range:</strong> January 6th to May 3rd 2020. The data series is not being updated during the summer. Updates will resume during the fall semester.</p>
<p><strong>Data Frequency:</strong> Weekly data points, with each week ending on Sunday.</p>
<p><strong>Indexing Period:</strong> January 6th - February 7th</p>
<p><strong>Indexing Type:</strong> Change relative to the January 2020 index period, not seasonally adjusted.</p>
<p><strong>Geographies:</strong> National, States, County, Metro</p>
<p>To ensure privacy, the data we obtain are masked such that any county with fewer than two districts, fewer than three schools, or fewer than 50 students on average using Zearn Math is excluded. Where possible, masked county levels values are replaced by commuting zone means.</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>School Income</em>. Schools are classified by income based on the share of students in the school eligible for free and reduced lunch based on data provided by Zearn.</p>
<ul>
<li>High Income (35.7% students are free and reduced lunch eligible)</li>
<li>Middle Income (56.9% students are free and reduced lunch eligible)</li>
<li>Low Income (80.4% students are free and reduced lunch eligible)</li>
</ul></li>
</ul>
<p><strong>Data masking:</strong> Data is masked such that any county with fewer than two districts, fewer than three schools, or fewer than 50 students on average using Zearn Math during the period between January 6 and February 7 is excluded. Masked county level data is replaced with the commuting zone average so long as there are more than two school districts in the commuting zone or at least three schools in the commuting zone. If these condition are not met the county-level data remains masked. Additionally we exclude schools who did not have at least 5 students using Zearn Math for at least one week from January 6 to February 7.</p>
<h2 id="student-progress-in-math">Student Progress in Math</h2>
<p><strong>Summary:</strong> Number of lessons completed by students each week using Zearn Math, among schools that already used Zearn Math in course instruction before the pandemic.</p>
<p><strong>Data Source:</strong> <a href="https://about.zearn.org">Zearn</a></p>
<p><strong>Update Frequency:</strong> Weekly, except during summer and winter school breaks.</p>
<p><strong>Date Range:</strong> January 6th to May 3rd 2020. The data series is not being updated during the summer. Updates will resume during the fall semester.</p>
<p><strong>Data Frequency:</strong> Weekly data points, with each week ending on Sunday.</p>
<p><strong>Indexing Period:</strong> January 6th - February 7th</p>
<p><strong>Indexing Type:</strong> Change relative to the January 2020 index period, not seasonally adjusted.</p>
<p><strong>Geographies:</strong> National, States, County, Metro</p>
<p>To ensure privacy, the data we obtain are masked such that any county with fewer than two districts, fewer than three schools, or fewer than 50 students on average using Zearn Math is excluded. Where possible, masked county levels values are replaced by commuting zone means.</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><p><em>School Income</em>. Schools are classified by income based on the share of students in the school eligible for free and reduced lunch based on data provided by Zearn.</p>
<ul>
<li>High Income (35.7% students are free and reduced lunch eligible)</li>
<li>Middle Income (56.9% students are free and reduced lunch eligible)</li>
<li>Low Income (80.4% students are free and reduced lunch eligible)</li>
</ul></li>
</ul>
<p><strong>Data masking:</strong> Data is masked such that any county with fewer than two districts, fewer than three schools, or fewer than 50 students on average using Zearn Math during the period between January 6 and February 7 is excluded. Masked county level data is replaced with the commuting zone average so long as there are more than two school districts in the commuting zone or at least three schools in the commuting zone. If these condition are not met the county-level data remains masked. Additionally we exclude schools who did not have at least 5 students using Zearn Math for at least one week from January 6 to February 7.</p>
<h2 id="covid-19-infections">COVID-19 Infections</h2>
<p><strong>Summary:</strong> The daily count and rate per 100,000 people of confirmed COVID-19 cases, deaths, hospitalizations, or tests performed.</p>
<p><strong>Data Source:</strong> <a href="https://github.com/nytimes/covid-19-data">The New York Times</a>, <a href="https://github.com/govex/COVID-19/tree/master/data_tables/testing_data">The Johns Hopkins Coronavirus Resource Center</a>, <a href="https://covid.cdc.gov/covid-data-tracker/#datatracker-home">The Centers for Disease Control and Prevention</a>, <a href="https://beta.healthdata.gov/Hospital/COVID-19-Reported-Patient-Impact-and-Hospital-Capa/g62h-syeh">U.S. Department of Health &amp; Human Services</a></p>
<p><strong>Update Frequency:</strong> Daily</p>
<p><strong>Date Range:</strong> January 22th until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Daily, presented as a 7-day moving average</p>
<p><strong>Indexing Period:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Indexing Type:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Geographies:</strong> National, State, Country, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><em>New</em> Cases, Deaths, or Tests (presented as a 7-day moving average)</li>
<li><em>Total</em> Cases, Deaths, or Tests</li>
<li><em>Other</em> Hospitalized</li>
</ul>
<p><strong>Data masking:</strong> No masking is performed by Opportunity Insights.</p>
<h2 id="covid-19-vaccinations">COVID-19 Vaccinations</h2>
<p><strong>Summary:</strong> Percentage of the population who have received one or more doses of any COVID-19 vaccine, completed a COVID-19 vaccination series, or received a COVID-19 booster or additional dose.</p>
<p><strong>Data Source:</strong> <a href="https://covid.cdc.gov/covid-data-tracker/#datatracker-home">The Centers for Disease Control and Prevention</a></p>
<p><strong>Update Frequency:</strong> Daily</p>
<p><strong>Date Range:</strong> February 24th 2021 until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Daily, presented as a 7-day moving average for new vaccinations</p>
<p><strong>Indexing Period:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Indexing Type:</strong> No indexing applied, the published numbers directly report quantities.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li><em>New Vaccinations</em>. Percent of population newly vaccinated with at least one vaccine dose</li>
<li><em>Total Vaccinations</em>. Percent of population in total vaccinated with at least one vaccine dose</li>
<li><em>New Completed Vaccinations</em>. Percent of population newly having completed a vaccine series</li>
<li><em>Total Completed Vaccinations</em>. Percent of population in total having completed a vaccine series</li>
<li><em>New Boosters</em>. Percent of population newly vaccinated with a booster (or additional) dose</li>
<li><em>Total Boosters</em>. Percent of population in total vaccinated with a booster (or additional) dose</li>
</ul>
<p><strong>Data masking:</strong> No masking is performed by Opportunity Insights.</p>
<p><strong>Notes:</strong> CDC data published prior to the 24th of February 2021 used a different methodology to assign vaccinations to the state where they were administered, producing numbers that are not directly comparable to those published after February 24th.</p>
<h2 id="time-outside-home">Time Outside Home</h2>
<p><strong>Summary:</strong> Time spent away from home, estimated using cellphone location data from Google users who have enabled the Location History setting.</p>
<p><strong>Data Source:</strong> <a href="https://www.google.com/covid19/mobility/">Google COVID-19 Community Mobility Reports</a>, <a href="https://www.bls.gov/tus/">American Time Use Survey</a></p>
<p><strong>Update Frequency:</strong> When released by Google, typically every 4-7 days.</p>
<p><strong>Date Range:</strong> February 24th until the most recent date available.</p>
<p><strong>Data Frequency:</strong> Daily</p>
<p><strong>Indexing Period:</strong> January 3rd to February 5th</p>
<p><strong>Indexing Type:</strong> Change relative to the January 2020 index period, not seasonally adjusted.</p>
<p><strong>Geographies:</strong> National, State, County, Metro</p>
<p><strong>Breakdowns:</strong></p>
<ul>
<li>Time Away From Home</li>
<li>Retail and Restaurants</li>
<li>Transit</li>
<li>Parks</li>
<li>Grocery</li>
<li>Workplace</li>
</ul>
<p><strong>Data masking:</strong> Google does not release data for geographies where their <a href="https://www.google.com/covid19/mobility/data_documentation.html?hl=en#about-this-data">internal quality and privacy thresholds</a> are not met. Therefore some geographic areas are omitted from the series for certain breakdowns and certain dates.</p>
<p><strong>Notes:</strong> When data is missing for 1 or 2 consecutive days we linearly interpolate the missing values and construct the 7 day moving average including these interpolated values. If data is missing for 3 or more consecutive days, the corresponding 7 day moving average is also recorded as missing whenever it overlaps with the missing data.</p>
<p>Time Away From Home is calculated by multiplying the mean time spent inside home from the American Time Use Survey by the percent change in time spent at residential locations reported by Google. For more information about this imputation, see the <strong><a href="https://opportunityinsights.org/wp-content/uploads/2020/05/tracker_paper.pdf">accompanying paper</a></strong>.</p>
<h2 id="policy-milestones">Policy Milestones</h2>
<p><strong>Summary:</strong> Key state-level policy dates relevant for changes in other series trends and values. Includes start and end of stay at home order dates, public school closure dates, and non-essential business closure and re-opening dates.</p>
<p><strong>Data Source(s):</strong> New York Times, MCH Strategic Data, the Institute for Health Metrics and Evaluation, and local news and government sources.</p>
<p><strong>Update Frequency:</strong> Monthly</p>
<p><strong>Geographies:</strong> State</p>
</body>
