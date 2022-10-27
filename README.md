# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

### Problem Statement

We are a team of data scientists tasked by the California Department of Education to explore and identify factors and gaps that contribute to ACT, SAT participation rates with the aim of increasing participation rate in California.
In this project, I will be focusing on the relationship of GDP per capita, household income and poverty level to ACT and SAT tests participation rate.

### Datasets

This project analysis is based on the following data sets: 

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

#### Additional Data

* [`states_data_1997_2021.csv`](./data/states_data_1997_2021.csv): 2017-2019 GDP data by State ([source](https://apps.bea.gov/regional/downloadzip.cfm))
* [`states_income.csv`](./data/states_income.csv): 2017-2019 Median household income by State ([source](https://nces.ed.gov/programs/digest/d20/tables/dt20_102.30.asp))
* [`states_poverty.csv`](./data/states_poverty.csv): Percentage of people in poverty by State using 3-Year average (2017-2019) ([source](https://www.census.gov/data/tables/2020/demo/income-poverty/p60-270.html))
* [`population.csv`](./data/population.csv): 2019 Population by State ([source](https://www.census.gov/data/tables/time-series/demo/popest/2010s-state-total.html))

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|obj|STATES DATA|State names|
|act17_part|float64|STATES DATA|Statewide ACT Participation Rate, 2017|
|sat17_part|float64|STATES DATA|Statewide SAT Participation Rate, 2017|
|act18_part|float64|STATES DATA|Statewide ACT Participation Rate, 2018|
|sat18_part|float64|STATES DATA|Statewide SAT Participation Rate, 2018|
|act19_part|float64|STATES DATA|Statewide ACT Participation Rate, 2019|
|sat19_part|float64|STATES DATA|Statewide SAT Participation Rate, 2019|
|pop19|int64|STATES DATA|States population for 2019|
|poverty_pct|float64|STATES DATA|3-year average percentage of people in poverty, 2017-2019|
|income_2017|float64|STATES DATA|Median household income for 2017|
|income_2018|float64|STATES DATA|Median household income for 2018|
|income_2019|float64|STATES DATA|Median household income for 2019|
|gdp_2017|float64|STATES DATA|Current-dollar GDP for 2017|
|gdp_2018|float64|STATES DATA|Current-dollar GDP for 2018|
|gdp_2019|float64|STATES DATA|Current-dollar GDP for 2019|
|gdp19_percap|float64|STATES DATA|2019 GDP per capita GDP|

### Executive Summary

This project examines data covering participation rates for students taking the SAT and ACT college entrance exam. The data are organized at the state level and contain 2017, 2018 and 2019 participation rates. This allows for a state-by-state comparison of participation rates for each test. In addition, a second data set consisting of state-level GDP per capita, median household income and poverty level data is used to explore relationships with the tests participation rate.

From 2017 to 2019, ACT participation rates by state has been decreasing, while SAT participation rates has been increasing on average. This suggests that some states are beginning to adopt SAT test over the ACT test.

A moderately strong negative relationship between poverty level by state and SAT test participation is found. This means that states with lower SAT participation rates are associated with higher poverty level. 

A moderately strong positive relationship between GDP per capita and household income by state, and SAT participation is found. In other words, higher SAT participation rates are associated with higher GDP per capita and income. And since ACT and SAT participation rates are negatively correlated, the reverse is found for ACT participation rates.

### Conclusions and Recommendations

Across US, the ACT and SAT participation rates are inversely correlated to each other, with states tending to prefer one test or the other. ACT shows a large group of states with 100% participation, and a higher baseline participation nationwide. SAT shows a larger group of states with 50-80% particpation.

From the data, we know that states with a relatively low GDP per capita, low household income and high poverty level tend to have higher ACT participation rate on average. The opposite is true for states with high GDP per capita, high household income and low poverty level.

California, with its high GDP per capita, high household income and above average poverty level, seems to suggest that there is some social inequality in the state that impact the tests participation rates. ([source](https://www.ppic.org/publication/poverty-in-california/#:~:text=According%20to%20the%20CPM%2C%2016.4,to%20severely%20constrained%20employment%20opportunity.))

Based on both an examination of the data and a review of state college entrance exam testing policy, it is clear that participation in such tests is heavily influenced by state policy towards testing. Currently, 29 states require that high school students take either the SAT or the ACT with no state requiring students take both. ([source](https://testive.com/state-sat-act/))

To increase participation, California can consider making one of the two tests a mandatory high school graduation requirement. This policy provides several benefits to education systems and to students. One benefit is that it provides a college-level standardized test that can be used to benchmark students and to measure the efficacy of high-school educational systems. Integrating the test into the high school curriculum can also remove barriers to test taking such as the cost or the need to do it on a weekend.

To tackle any social inequality, the California Department of Education can work with the related departments or parties to promote high quality jobs and to raise standards of living in all counties, instead of just Rural or Suburban counties across California.
