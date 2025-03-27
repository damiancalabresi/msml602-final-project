# MSML 602 - Principles of Data Science - Final Project - Project Status Report \#1

# Table of Contents

1. [Github Repository](#github-repository)
2. [Dataset Extraction and Cleanup](#dataset-extraction-and-cleanup)
   1. [Democracy Datasets](#democracy-datasets)
      - [Polity5](#polity5)
      - [Freedom in the World](#freedom-in-the-world)
      - [Autocratic Regime Data](#autocratic-regime-data)
      - [Boix-Miller-Rosato Dichotomous Coding of Democracy](#boix-miller-rosato-dichotomous-coding-of-democracy)
      - [Lexical Index of Electoral Democracy (LIED)](#lexical-index-of-electoral-democracy-lied)
   2. [Religiosity Datasets](#religiosity-datasets)
      - [Pew Research Center - Global Religious Diversity](#pew-research-center---global-religious-diversity)
      - [World Religion Project - National Religion Dataset](#association-of-religion-data-archives---national-religion-dataset)
   3. [Women Rights Datasets](#women-rights-datasets)
      - [Georgetown Institute for Women, Peace and Security - Women Peace and Security Index](#georgetown-institute-for-women-peace-and-security---women-peace-and-security-index)
      - [World Bank Group - Women, Business and the Law Historical Data](#world-bank-group---women-business-and-the-law-historical-data)
3. [Next Steps](#next-steps)
4. [Status](#status)

# Github Repository

I've created a Github repository that will contain the Jupyter Notebooks containing the code executed to clean, extract, and analyze the data.

The repository is public and most of the progress will also be documented in markdown within this code.

[Github - damiancalabresi - msml602-final-project](https://github.com/damiancalabresi/msml602-final-project/)

# Dataset Extraction and Cleanup

The code and markdown documentation can be found here:

[https://github.com/damiancalabresi/msml602-final-project/tree/main/1-dataset-cleanup](https://github.com/damiancalabresi/msml602-final-project/tree/main/1-dataset-cleanup)

## Democracy Datasets

### Polity5

- Downloaded dataset from [The Polity Project](https://www.systemicpeace.org/polityproject.html)
- Renamed and dropped empty columns
- Analyzed the [Polity5 Codebook](https://github.com/damiancalabresi/msml602-final-project/blob/main/datasets/processed/democracy/polity/p5manualv2018.pdf)
- Transposed the dataset: Years were columns and predictors were rows. Country-Year is the identifier
- Verified that Year is an integer
- Verified that predictors don't have missing values
- Analyzed "durable" predictor. It has a lot of missing values, even for recent years. It didn't add much value either. Dropped it.
- "polity2" predictor is built from "polity", just to add continuity to years with interrupted data. The predictor is not set in many cases and cannot be recalculated. Dropped it. The years with interruptions will be filtered when a quantitative analysis over the "polity" predictor is performed.
- The predictors "polcomp" and "exrec" contain many missing rows but, when filtering from 1940 onwards, they are complete. We know that our analysis will start on 1940 or later, based on the other datasets, so I filtered the dataset and kept those predictors.
- Verified all the columns are numeric and the minimum or maximum values are plausible.
- Saved the cleaned dataset as a CSV file.

Countries: 166

Years: 1941 - 2018

These are the indicators of the Polity5 dataset:

Indicator ID | Indicator Name | Value Range
--- | --- | ---
autoc | Composite Autocracy Index | 0-10 (-77 -88 -66 for special cases)
democ | Composite Democracy Index | 0-10 (-77 -88 -66 for special cases)
exconst | Executive Constraints Concept | Same as xconst
exrec | Executive Recruitment Concept | 0-10 (-77 -88 -66 for special cases)
parcomp | The Competitiveness of Participation | 0 - Not Applicable; 1 - Repressed; 2 - Suppressed; 3 - Factional; 4 - Transitional; 5 - Competitive (-77 -88 -66 for special cases)
parreg | Regulation of Participation | 1- Unregulated; 2 - Multiple Identity; 3 - Sectarian; 4 - Restricted; 5 - Regulated (-77 -88 -66 for special cases)
polcomp | Political Competition Concept | Combination of parreg and parcomp (1-10)
polity | Combined Polity Score | +10 (strongly democratic) to -10 (strongly autocratic)
xconst | Executive Constraints (Decision Rules) | 1 - Unlimited Authority; 2 - Intermediate Category; 3 - Slight to Moderate Limitation on Executive Authority; 4 - Intermediate Category; 5 - Substantial Limitations on Executive Authority; 6 - Intermediate Category; 7 - Executive Parity or Subordination (-77 -88 -66 for special cases)
xrcomp | Competitiveness of Executive Recruitment | 0 - xrreg is Unregulated; 1 - Selection; 2 - Dual/Transitional; 3 - Election (-77 -88 -66 for special cases)
xropen | Openness of Executive Recruitment | 0 - xrreg is Unregulated; 1 - Closed; 2 - Dual Executive-Designation; 3 - Dual Executive-Election; 4- Open (-77 -88 -66 for special cases)
xrreg | Regulation of Chief Executive Recruitment | 1 - Unregulated; 2 - Designational/Transitional; 3 - Regulated (-77 -88 -66 for special cases)

**Special Cases**

- -77: Interregnum
- -88: Transition period
- -66: Interruption

### Freedom in the World

- Downloaded dataset from [Freedom House](https://freedomhouse.org/reports/freedom-world)
- Metadata is in the same Excel file as the dataset
- Renamed columns and drop unrelated columns (Region, Add Q, Add A)
- Some rows are territories and not countries. Dropped them
- Renamed columns to be consistent with the naming convention
- Verify that all predictors are numeric and don't have missing values
- Saved the cleaned dataset as a CSV file

Countries: 195

Years: 2013 - 2025

These are the indicators of the Freedom in the World dataset:

Indicator ID | Indicator Name | Value Range
--- | --- | ---
status | Status | F=Free, PF=Partly Free, NF=Not Free
pr_rating | Political Rights Rating | 1-7
cl_rating | Civil Liberties Rating | 1-7
a1 | Head of government elected through free and fair elections | 0-4
a2 | Legislative representatives elected through free and fair elections | 0-4
a3 | Are the electoral laws and framework fair and equitable | 0-4
a | Electoral Process (Aggregated) | 0-12
b1 | Right to organize in different political parties or other competitive political groupings of their choice | 0-4
b2 | Opportunity for the opposition to increase its support | 0-4
b3 | Political choices free from domination by forces that are external to the political sphere | 0-4
b4 | Various segments of the population have full political rights | 0-4
b | Political Pluralism and Participation (Aggregated) | 0-16
c1 | Elected head of government and national legislative representatives determine the policies of the government | 0-4
c2 | Safeguards against official corruption | 0-4
c3 | Government operates with openness and transparency | 0-4
c | Functioning of Government (Aggregated) | 0-12
d1 | Free and independent media | 0-4
d2 | Individuals free to practice and express their religious faith or nonbelief | 0-4
d3 | academic freedom | 0-4
d4 | individuals free to express their personal views  | 0-4
d | Freedom of Expression & Belief | 0-16
e1 | freedom of assembly | 0-4
e2  | freedom for nongovernmental organizations | 0-4
e3 | freedom for trade unions and similar professional or labor organizations | 0-4
e | Associational & Organizational Rights (Aggregated) | 0-11
f1 | independent judiciary | 0-4
f2 | due process prevail in civil and criminal matters | 0-4
f3 | protection from the illegitimate use of physical force | 0-4
f4 | laws, policies, and practices guarantee equal treatment | 0-4
f | Rule of Law (Aggregated) | 0-16
g1 | freedom of movement | 0-4
g2 | right to own property and establish private businesses | 0-4
g3 | social freedoms, including choice of marriage partner and size of family | 0-4
g4 | equality of opportunity and freedom from economic exploitation | 0-4
g | Personal Autonomy & Individual Rights (Aggregated) | 0-16
total | Total Score | 0-100

### Autocratic Regime Data

This source contains two datasets:
- GWF: Geddes et al. (2012) 
- CGV: Cheibub et al. (2010)

The primary data set ("GWF Autocratic Regimes.xlsx") is a time series data set that contains the Start and End dates of the autocratic regimes as well as the regime type and variables that code different dimensions of how autocratic regimes fail.

The file "GWF All Political Regimes Case List.xls" contains a summary of the autocracy cases as well as the disagreements between the GWF and CGV. I didn't use this data set.

The file "GWF Autocratic Regimes.xlsx" contains two sheets:
- TSCS Data: Country-Year data for the autocratic regimes
- Autocratic Regimes Case List: List of autocratic regimes, with start and end date. One row per regime case

Work done:
- Load the Autocratic Regime Case List
- Review rows with missing values
- Analyze case of Iran 79, which cannot be classified. Left it as it is as I don't want to exclude this case.
- Set End Year to -1 when the regime is still ongoing
- Transform start and end date format
- Verified all predictors are integers

#### Indicators

**Autocratic Regime Case List**

Indicator ID | Indicator Name | Value Range
--- | --- | ---
gwf_country | Country name
gwf_casename | The name of the autocratic regime (Usually the country name and years)
gwf_startdate | Start date on day/month/year format
gwf_enddate | End date on day/month/year format
gwf_startyr | Start year
gwf_endyr | End year
gwf_subsreg | Type of subsequent regime | 0 to 3 (See Codebook)
gwf_howend | How the regime ended | 0 to 9 (See Codebook)
gwf_violent | Whether the regime change was violent | 0 to 4 (See Codebook)
gwf_regimetype | Type of regime | Party-based, Military, Personalist, Monarchical (See Codebook)

**TSCS Data**

Indicator ID | Indicator Name | Value Range
--- | --- | ---
cow | Correlates of War (CoW) country code | 
year | Calendar year | 
gwf_country | Country name | 
gwf_casename | Autocratic regime case name (country name and years) | 
gwf_startdate | Day-Month-Year for the calendar date of the autocratic regime start event | 
gwf_enddate | Day-Month-Year for the calendar date of the autocratic regime failure event | 
gwf_spell | Total number of years of the autocratic regime | 
gwf_duration | Duration of the autocratic regime until the current year | 
gwf_failure | Binary indicator of autocratic regime failure | 0-1
gwf_fail_subs | Categorical variable marking the subsequent regime type | 0 to 3
gwf_fail_type | Categorical variable marking how the autocratic regime ends | 0 to 9
gwf_fail_violent | Categorical variable marking the level of violence during the autocratic regime failure event | 0 to 4
gwf_regimetype | Autocratic regime type | Party-based, Military, Personalist, Monarchical (See Codebook)
gwf_party | Binary indicator of party regime type | 0-1
gwf_personal | Binary indicator of personalist regime type | 0-1
gwf_military | Binary indicator of military regime type | 0-1
gwf_monarchy | Binary indicator of monarchy regime type | 0-1

### Boix-Miller-Rosato Dichotomous Coding of Democracy

- Downloaded dataset from [Boix-Miller-Rosato Dichotomous Coding of Democracy](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/FENWWR)
- Review Codebook to understand predictors
- Remove records which are not valid countries or countries with NA values in the democracy predictor
- Review NA values
- Set empty democracy_omitteddata to -1 for missing records

This data set provides a dichotomous coding of democracy for every country in the world (222 total) from 1800 to 2020.

Countries: 203

Years: 1800 - 2020

#### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
country | Country name
ccode | COW country code
abbreviation | World Bank 3-letter code
abbreviation_ucdp | UCDP 3-letter code
year | Year | 1800 to 2020
democracy | Dichotomous democracy measure | 1 = Democratic, 0 = Non-Democratic (For occupied countries the value is continued from previous years)
democracy_trans | Democratic transition in the current year | -1 = Democratic breakdown, 0 = No change, 1 = Transition (current year)
democracy_breakdowns | Country's total number of democratic breakdowns (up through current year) | > 0
democracy_duration | Consecutive years of current regime type | > 0
democracy_omitteddata | This is the same measure as democracy, except it records an -1 for countries occupied during an international war or experiencing state collapse during a civil war. The democracy variable instead fills in these years as continuations of the same regime type. | 0, 1, -1
democracy_femalesuffrage | This adjusts democracy by also requiring that at least half of adult women have the right to vote. | 0, 1

### Lexical Index of Electoral Democracy (LIED)

- Downloaded dataset from [Lexical Index of Electoral Democracy (LIED)](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/WPKNIT)
- Review Codebook to understand predictors
- Drop Region which is not part of the v6.4 codebook
- Remove records which are not countries (vdem is NA)
- Fx rows with invalid characters in the "year" column
- Verify all the fields are parsed as integers


LIED covers all independent countries and most semi-sovereign polities and overseas colonies, protectorates, etc. within the 1789 to 2020 timespan. Scores for each indicator reflect the status of a country on the last day of the calendar year (31 December).

The dataset consists of 14 original indicators and original two indices. The indicators are used to construct two indices, i.e., the Lexical Index of Electoral Democracy (lexical_index) and an extended version called Lexical Index of Electoral Democracy+ (lexical_index_plus).

#### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
countryn | Name of the country |
cow | Correlates of War country ID
vdem | VDEM dataset country ID
year | Year | 1789 to 2023
male_suffrage | Male citizens are allowed to vote | 1=present, 0=absent
female_suffrage | Female citizens are allowed to vote | 1=present, 0=absent
executive_elections | Chief executive is either directly or indirectly elected | 1=present, 0=absent
legislative_elections | Legislative body, issues at least some laws and does not perform executive functions. The lower house (or unicameral chamber) of the legislature is at least partly elected. The legislature has not been closed | 1=present, 0=absent
multi_party_legislative_elections | The lower house of the legislature is elected by voters facing more than one choice | 1=present, 0=absent
competitive_elections | Elections are, in principle, sufficiently free to enable the opposition to gain power if they were to attract sufficient support from the electorate | 1=present, 0=absent
lexical_index | Original index of democracy | Score 0 to 6
political_liberties | Freedom of expression, freedom of assembly, and freedom of association are respected | 1=present, 0=absent
lexical_index_plus | The meaning of the scores from 0 to 5 are identical to LIED, whereas 6 and 7 refer to the other indicator values | Score 0 to 7
democratic_transition | Democratic transition took place in a given year as signified by a change in the competitive_elections indicator | 1=present, 0=absent
transition_type | For years with democratic transitions, mode of transition | See later
democratic_breakdown | A democratic breakdown took place in a given year as signified by a change in competitive_elections indicator from 1 in the previous year to 0 in the current year | 1=present, 0=absent
breakdown_type | For years with democratic transitions, mode of transition | See later
turnover_period | Indicates whether a particular country-year is part of a period between an initial electoral government alternation (as indicated by a turnover event, see below) in a multi-party electoral regime and an interruption of the same multi-party electoral regime (as indicated by a score
of 0 on executive elections or multi-party_legislative_elections, see above). If another turnover event happens later in the same polity, a new turnover period begins | 1=present, 0=absent
turnover_event | Partisan control over government power alternated from an elected chief executive to another party/coalition/candidate representing the opposition as a consequence of a multi-party election | 1=present, 0=absent
two_turnover_period | Year is part of a period between a second electoral government alternation. If two turnover events happens later in the same polity under a new multi_party electoral regime, a new two-turnover period begins | 1=present, 0=absent
sovereign | Country is a separate unit in the international system of states (1) or subjected to foreign colonization or occupation | 1 - 0

**Transition Type**

- 0: no transition
- 1: conversion (incumbent-led)
- 2: cooperative (pact between incumbents and opposition/balanced influence)
- 3: collapse (opposition-led)
- 4: foreign supervision (imposition by foreign power based on intervention or highly asymmetrical – partial or full – decolonization)
- 5: foreign liberalization (democracy reemerges after occupational power has lost war to foreign powers)

**Breakdown Type**

- 0: No breakdowns
- 1: implicit regression induced by incumbents
- 2: military coup
- 3: foreign occupation
- 4: self-coup (incumbents close down parliament unduly and take full political control)
- 5: coup or civil conflict headed by opposition party/movement
- 6: coup headed by monarch

## Religiosity Datasets

### Pew Research Center - Global Religious Diversity

This study calculates Religious Diversity Index (RDI) scores for countries, regions and the world based on the shares of eight major world religions (Buddhism, Christianity, folk or traditional religions, Hinduism, Islam, Judaism, and other religions).

[Pew Research Center - Global Religious Diversity](https://www.pewforum.org/datasets/global-religious-diversity/)

- Obtained data set from [Religious Diversity Index Scores by Country](https://www.pewresearch.org/religion/2014/04/04/religious-diversity-index-scores-by-country/)
- Understand Religious Diversity Index (RDI) calculation [methodology](https://www.pewresearch.org/religion/2014/04/04/methodology-2-5/)
- Transform population to integer and resolves cases with invalid characters
- Transform percentages to float

Notes:
- When the percentage of a given religion is too low, the data set contains "< 0.1%", I set it to 0
- When the population is too low the data set contains "< 10,000", I set it to "10000"
- The information represents a snapshot taken in the year 2010

#### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
country | Country name | 
population | Population | 
rdi | Religious Diversity Index | 0 - 10
christian | Percentage of Christians | 0 - 1
muslim | Percentage of Muslims | 0 - 1
unaffiliated | Percentage of unaffiliated | 0 - 1
hindu | Percentage of Hindus | 0 - 1
buddhist | Percentage of Buddhists | 0 - 1
folk | Percentage of Folk or Traditional Religions | 0 - 1
jewish | Percentage of Jews | 0 - 1
other | Percentage of Other Religions | 0 - 1

### Association of Religion Data Archives - National Religion Dataset

The World Religion Dataset is maintained by The Association of Religion Data Archives (The ARDA)

- Review Codebook
- Review missing and null values
- Remove countries that don't exist anymore (E.g.: Yugoslavia, Federated Republic of Germany). Their datasets are not reliable anyway
- Review reliability of sources

#### Indicators

- Religion indicators: The meaning of each column (E.g.: "chrstcat" is Christianity - Roman Catholics) is described in the Table 2 of the Codebook. They are: chrsprot, chrcat, chrsorth, chrsang, chrsothr, chrsgen, judorth, jdcons, judref, judothr, judgen, islmsun, islmshi, islmibd, islmnat, islmalw, islmahm, islmothr, islmgen, budmah, budthr, budothr, budgen, zorogen, hindgen, sikhgen, shntgen, bahgen, taogen, jaingen, confgen, syncgen, anmgen, nonrelig, othrgen
- pop: The population of the country
- Percentage indicatos: For each religion, the percentage is also calculated. These columns are: chprtpct, chcatpct, chortpct, changpct, chothpct, chgenpct, jdorpct, jdcnpct, jdrfpct, jdotpct, jdgenpct, issunpct, isshipct, isibdpct, isnatpct, isalapct, isahmpct, islotpct, isgenpct, bumahpct, buthrpct, buothpct, bugenpct, zogenpct, higenpct, sigenpct, shgenpct, bagenpct, tagenpct, jagenpct, cogenpct, sygenpct, angenpct, norelpct, otgenpct
- dualrelig: If the country information allows for multiple religions per person (1 = Yes, 0 = No)
- datatype: Data source type for the country information
- recreliab: Reliability of the data source (1 to 35, 1 is the highest reliability)
- reliablev: Level of reliability of the data source (1 = Low, 2 = Medium, 3 = High)

**Note:** "reliablev" will be used to filter the most reliable countries when doing the analysis.

## Women Rights Datasets

### Georgetown Institute for Women, Peace and Security - Women Peace and Security Index

The Women Peace and Security Index (WPS Index) is a composite index created by the Georgetown Institute for Women, Peace and Security. This index shows that countries where women are doing well are also more peaceful, democratic, prosperous.

This index is based on surveys conducted over the years 2018 to 2023.

For more information, see: [Georgetown University - Women Peace and Security Index](https://giwps.georgetown.edu/the-index/)

- Review documentation
- Clean spreadsheets to obtain a single dataset
- Transform column names to lower case
- Verify missing and empty values

#### Indicators

Measurements belong to the dimensions: Inclusion, Justice, and Security.

- Inclusion: Education, Employment, Financial Inclusion, Cell Phone Use, Parliamentary Representation
- Justice: Absence of legal discrimination, Access to justice, Maternal mortality ratio, Son bias
- Security: Intimate partner violence, Community safety, Political violence targeting women, Proximity to conflict

Indicator ID | Indicator Name | Value Range
--- | --- | ---
women_peace_and_security_index | Women Peace and Security Index | 0 - 100
education | Average number of years of education of women ages 25 and older | 0 to 15
employment | The number of employed women and girls, ages 25 - 64, expressed as a percent of the total of female population in that age group | 0 - 100
financial_inclusion | Women ages 15 and older who report having an account at a bank | 0 - 100
cell_phone_use | Percentage of women and girls ages 15 and older who report having a mobile phone | 0 - 100
parliamentary_representation | Percentage of seats held by women in lower and upper houses of the national parliament | 0 - 100
absence_of_legal_discrimination | The extent (0–100) to which laws and regulations differentiate between women and men, or protect women's opportunities | 0 - 100
access_to_justice | The extentto which women are able to exercise justice by bringing cases before the court without risk to their personal safety | 0 - 4
maternal_mortality_ratio | Number of deaths due to pregnancy-related causes per 100,000 live births | 0 - 1000
son_bias | Number of boys born per 100 girls | 100 - 114
intimate_partner_violence | Percentage of ever-partnered women who experienced physical or sexual violence committed by their intimate partner in the 12 months preceding the survey | 0 - 100
community_safety | Percentage of women who report feeling safe walking alone at night in their community | 0 - 100
political_violence_targeting_women | Percentage of women who report being victims of political violence | 0 - 100
proximity_to_conflict | Number of civilian targeting events in which women and/or girls are the 'target' of the violence. It is expressed as the number of events per 100,000 women | 0 - 1.2

### World Bank Group - Women, Business and the Law Historical Data

The World Bank Group Women, Business and the Law (WBL) dataset is a comprehensive historical dataset that provides detailed information on the legal framework governing women's economic opportunities and rights.

The dataset defines a series of questions which are answered with YES or NO based on the country's legal framework. Those questions are grouped in the categories: Mobility, Workplace, Pay, Marriage, Parenthood, Entrepreneurship, Assets, and Pension.

For each of the categories a score from 0 to 100 is calculated (Based on the percentage of questions answered with YES). Based on these scores, the WBL Index is calculated as the average of the scores of the categories.

For more information, see: [World Bank Group - Women, Business and the Law Historical Data](https://www.worldbank.org/en/research/wbl)

- Review documentation
- Classify quantitative columns and transform qualitative columns to 0 and 1
- Transform column names to lower case

### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
wbl_index | Women, Business and the Law Index | 0 - 100
mobility | Mobility | 0 - 100
workplace | Workplace | 0 - 100
pay | Pay | 0 - 100
marriage | Marriage | 0 - 100
parenthood | Parenthood | 0 - 100
entrepreneurship | Entrepreneurship | 0 - 100

# Scope Definition



#  Next Steps

# Status

* Week 1 (03/13): Dataset extraction and research - DONE  
* Week 2 (03/20): Data cleanup and EDA - IN PROGRESS  
* Week 3 (03/27): Identify scope. Comprehensive Analysis of Democracy Indexes - PENDING  
* Week 4 (04/03): Cleanup and Merge Datasets - PENDING  
* Week 5 (04/10): Linear and Logistic Regression - PENDING  
* Week 6 (04/17): SVM and Clustering - PENDING  
* Week 7 (04/24): Identify Outliers - PENDING  
* Week 8 (05/01): Analyze impact of global events - PENDING  
* Week 9 (05/08): Draft paper - PENDING  
* Week 10 (05/15): Redact paper and review - PENDING