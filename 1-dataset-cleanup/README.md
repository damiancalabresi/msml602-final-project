# Dataset Cleanup

## Catalog

Area | Source | Name | Type | Description
--- | --- | --- | --- | ---
Democracy | Center for Systemic Peace | Polity5 | Time Series | Quantitative measures of political regime characteristics and transitions, assessing democracy and autocracy levels globally from 1776 onwards
Democracy | Freedom House | Freedom in the World | Time Series | Annual global assessment of political rights and civil liberties
Democracy | Pennsylvania State University | Autocratic Regime Data | Tabular | Autocratic regimes: start/end dates, regime types, level of violence during regime failure event, categorization of regime failure events
Democracy | Harvard Dataverse | Lexical Index of Electoral Democracy (LIED) | Tabular | Metrics on governance quality, rule of law, and political stability
Democracy | Harvard Dataverse | Boix-Miller-Rosato Dichotomous Coding of Democracy | Tabular | Dichotomous coding of democracy
Women Rights | World Bank | Gender Statistics | Tabular | Key indicators on gender including education, employment, health, and political participation
Religion | Pew Research | Religious Demographics | Tabular | Global religious composition and trends

## Cleanup Process

### Democracy

#### Polity5

[The Polity Project](https://www.systemicpeace.org/polityproject.html)

##### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
democ | Institutionalized Democracy Index | 0-10
autoc | Institutionalized Autocracy Index | 0-10
polity | Combined Polity Score | +10 (strongly democratic) to -10 (strongly autocratic)
polity2 | Revised Combined Polity Score (p5) | Softens the Polity score for time-series analysis
durable | Regime Durability Index | Number of years since the most recent regime change
xrreg | Regulation of Chief Executive Recruitment | 1- Unregulated; 2 - Designational/Transitional; 3 - Regulated; -66 - Interruption; -77 - Interregnum; -88 - Transition period
xrcomp | Competitiveness of Executive Recruitment | 1 - Selection; 2 - Dual/Transitional; 3 - Election; -66 - Interruption; -77 - Interregnum; -88 - Transition period
xropen | Openness of Executive Recruitment | 1 - Closed; 2 - Dual Executive-Designation; 3 - Dual Executive-Election; 4- Open; -66 - Interruption; -77 - Interregnum; -88 - Transition period
xconst | Executive Constraints (Decision Rules) | 1 - Unlimited Authority; 2 - Intermediate Category; 3 - Slight to Moderate Limitation on Executive Authority; 4 - Intermediate Category; 5 - Substantial Limitations on Executive Authority; 6 - Intermediate Category; 7 - Executive Parity or Subordination; -66 - Interruption; -77 - Interregnum; -88 - Transition period
parreg | Regulation of Participation | 1- Unregulated; 2 - Multiple Identity; 3 - Sectarian; 4 - Restricted; 5 - Regulated; -66 - Interruption; -77 - Interregnum; -88 - Transition period
parcomp | The Competitiveness of Participation | 0 - Not Applicable; 1 - Repressed; 2 - Suppressed; 3 - Factional; 4 - Transitional; 5 - Competitive; -66 - Interruption; -77 - Interregnum; -88 - Transition period
exrec | Executive Recruitment Concept | 1 - Unconstrained; 2 - Dual/Transitional; 3 - Constrained; -66 - Interruption; -77 - Interregnum; -88 - Transition period
exconst | Executive Constraints Concept | Same as xconst
polcomp | Political Competition Concept | Combination of parreg and parcomp

##### Processing Files

See Jupyter Notebook for processing files.

##### Data Range

Countries: 166
Years: 1776 - 2018

#### Freedom in the World

[Freedom House](https://freedomhouse.org/reports/freedom-world)

##### Indicators

Indicator ID | Indicator Name | Value Range
--- | --- | ---
status | Status | F=Free, PF=Partly Free, NF=Not Free
pr_rating | Political Rights Rating | 1-7
cl_rating | Civil Liberties Rating | 1-7
a1 | Head of government elected through free and fair elections | 1-10
a2 | Legislative representatives elected through free and fair elections | 1-10
a3 | Are the electoral laws and framework fair and equitable | 1-10
a | Electoral Process (Aggregated) | 1-30
b1 | Right to organize in different political parties or other competitive political groupings of their choice | 1-10
b2 | Opportunity for the opposition to increase its support | 1-10
b3 | Political choices free from domination by forces that are external to the political sphere | 1-10
b4 | Various segments of the population have full political rights | 1-10
b | Political Pluralism and Participation (Aggregated) | 1-40
c1 | Elected head of government and national legislative representatives determine the policies of the government | 1-10
c2 | Safeguards against official corruption | 1-10
c3 | Government operates with openness and transparency | 1-10
c | Functioning of Government (Aggregated) | 1-30
d1 | Free and independent media | 1-10
d2 | Individuals free to practice and express their religious faith or nonbelief | 1-10
d3 | academic freedom | 1-10
d4 | individuals free to express their personal views  | 1-40
d | Freedom of Expression & Belief | 1-30
e1 | freedom of assembly | 1-10
e2  | freedom for nongovernmental organizations | 1-10
e3 | freedom for trade unions and similar professional or labor organizations | 1-10
e | Associational & Organizational Rights (Aggregated) | 1-30
f1 | independent judiciary | 1-10
f2 | due process prevail in civil and criminal matters | 1-10
f3 | protection from the illegitimate use of physical force | 1-10
f4 | laws, policies, and practices guarantee equal treatment | 1-10
f | Rule of Law (Aggregated) | 1-40
g1 | freedom of movement | 1-10
g2 | right to own property and establish private businesses | 1-10
g3 | social freedoms, including choice of marriage partner and size of family | 1-10
g4 | equality of opportunity and freedom from economic exploitation | 1-10
g | Personal Autonomy & Individual Rights (Aggregated) | 1-40
total | Total Score | 1-100

##### Processing Files

See Jupyter Notebook for processing files.

##### Data Range

Countries: 195
Years: 2013 - 2025

#### Autocratic Regime Data

This source contains two datasets:
- GWF: Geddes et al. (2012) 
- CGV: Cheibub et al. (2010)

The primary data set (“GWF Autocratic Regimes.xls”, “GWFcases.dta”, “GWFtscs.dta”, and “GWFtscs.txt”) is time series-cross section data that contains the Start and End dates of the autocratic regimes as well as the regime type and variables that code different dimensions of how autocratic regimes fail.

The file "GWF All Political Regimes Case List.xls" contains a summary of the autocracy cases as well as the disagreements between the GWF and CGV.

The file "GWF Autocratic Regimes.xlsx" contains the GWF dataset and will be used for the analysis.

##### Indicators

**Case List**

The **Autocratic Regime Case List** sheet contains the following columns:

- **gwf_country**: Country name
- **gwf_casename**: The name of the autocratic regime (Usually the country name and years)
- **gwf_startdate**: Start date on day/month/year format
- **gwf_enddate**: End date on day/month/year format
- **gwf_startyr**: Start year
- **gwf_endyr**: End year
- **gwf_subsreg**: Type of subsequent regime
- **gwf_howend**: How the regime ended
- **gwf_violent**: Whether the regime change was violent
- **gwf_regimetype**: Type of regime

**TSCS Data**

The **TSCS Data** sheet contains the following columns:

- **cow**: Correlates of War (CoW) country code
- **year**: Calendar year
- **gwf_country**: Country name
- **gwf_casename**: Autocratic regime case name (country name and years)
- **gwf_startdate**: Day-Month-Year for the calendar date of the autocratic regime start event
- **gwf_enddate**: Day-Month-Year for the calendar date of the autocratic regime failure event
- **gwf_spell**: Time-invariant duration of autocratic regime
- **gwf_duration**: Time-varying duration of autocratic regime up to time t
- **gwf_failure**: Binary indicator of autocratic regime failure
- **gwf_fail_subs**: Categorical variable marking the subsequent regime type
- **gwf_fail_type**: Categorical variable marking how the autocratic regime ends
- **gwf_fail_violent**: Categorical variable marking the level of violence during the autocratic regime failure event
- **gwf_regimetype**: Autocratic regime type
- **gwf_party**: Binary indicator of party regime type (groups party-based, party-personal, party-military, party-personal-military, oligarchy, and Iran 1979-2010)
- **gwf_personal**: Binary indicator of personalist regime type
- **gwf_military**: Binary indicator of military regime type (groups military, military-personal, indirect military)
- **gwf_monarchy**: Binary indicator of monarchy regime type

The **Autocratic Regime Case List** sheet contains one row per autocratic regime, the **TSCS Data** sheet contains one row per year.

###### Type of Subsequent Regime

- 0: The regime has not ended by 2010.
- 1: The regime that follows the last year of the regime being coded is democratic.
- 2: The regime in the year following the last year of the regime being coded is autocratic, that is, included in our autocratic data set.
- 3: The regime is followed by a period that is neither autocratic nor democratic (Periods when the country has no government or has multiple governments or when foreign troops occupy the country)

###### How the Regime Ended

- 0: The regime had not ended by 2010.
- 1: Regime insiders changed the rules for choosing leaders and policies, or the executive was removed by elite actors other than the military.
- 2: The incumbent, or a party, coalition, or candidate supported by the incumbent, lost an election and allowed the candidate or party that won to take oﬃce.
- 3: A regime held a competitive election in which no major candidate or party supported by the incumbent ran, as a means of choosing the next government, and allowed the winner of the election to take oﬃce.
- 4: The regime was ousted by popular uprising.
- 5: The regime was overthrown by military coup (defined as ouster by the military of the regime in power).
- 6: Regime is ousted by insurgents, revolutionaries, or combatants fighting a civil war.
- 7: Regime changed through foreign imposition or invasion
- 8: A new leader chosen in a regular autocratic succession changed the formal and informal rules defining the regime after his accession to power while himself remaining in power.
- 9: Regime ends because the state’s existence ends or the government’s control of most of its territory ends

###### Violence

- 0: The regime had not ended by 2010.
- 1: Non-violent, defined as involving no deaths.
- 2: A few deaths occurred during the transition. If numbers are available, ‘a few’ means 1-25.
- 3: Many deaths occurred during the transition. If numbers are available, ‘many’ means more than 25 but less than 1000.
- 4: More than 1000 deaths occurred.

###### Regime Type

- Party-based regimes: party, party-based, party-military, party-personal, party-personal-military, oligarchy
- Military regimes: indirect military, military, military-personal
- Personalist regimes: personal
- Monarchical regimes: monarchy

##### Processing Files

See Jupyter Notebook for processing files.

##### Data Range

Countries: 120
Years: 1946 - 2010











