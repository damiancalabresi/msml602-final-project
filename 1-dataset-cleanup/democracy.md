# Democracy

## Polity5

[The Polity Project](https://www.systemicpeace.org/polityproject.html)

### Indicators

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

### Processing Files

See Jupyter Notebook for processing files.

### Data Range

Countries: 166

Years: 1941 - 2018

## Freedom in the World

[Freedom House](https://freedomhouse.org/reports/freedom-world)

### Indicators

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

### Processing Files

See Jupyter Notebook for processing files.

### Data Range

Countries: 195

Years: 2013 - 2025

## Autocratic Regime Data

This source contains two datasets:
- GWF: Geddes et al. (2012) 
- CGV: Cheibub et al. (2010)

The primary data set (“GWF Autocratic Regimes.xls”, “GWFcases.dta”, “GWFtscs.dta”, and “GWFtscs.txt”) is time series-cross section data that contains the Start and End dates of the autocratic regimes as well as the regime type and variables that code different dimensions of how autocratic regimes fail.

The file "GWF All Political Regimes Case List.xls" contains a summary of the autocracy cases as well as the disagreements between the GWF and CGV.

The file "GWF Autocratic Regimes.xlsx" contains the GWF dataset and will be used for the analysis.

### Indicators

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

#### Type of Subsequent Regime

- 0: The regime has not ended by 2010.
- 1: The regime that follows the last year of the regime being coded is democratic.
- 2: The regime in the year following the last year of the regime being coded is autocratic, that is, included in our autocratic data set.
- 3: The regime is followed by a period that is neither autocratic nor democratic (Periods when the country has no government or has multiple governments or when foreign troops occupy the country)

#### How the Regime Ended

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

#### Violence

- 0: The regime had not ended by 2010.
- 1: Non-violent, defined as involving no deaths.
- 2: A few deaths occurred during the transition. If numbers are available, ‘a few’ means 1-25.
- 3: Many deaths occurred during the transition. If numbers are available, ‘many’ means more than 25 but less than 1000.
- 4: More than 1000 deaths occurred.

#### Regime Type

- Party-based regimes: party, party-based, party-military, party-personal, party-personal-military, oligarchy
- Military regimes: indirect military, military, military-personal
- Personalist regimes: personal
- Monarchical regimes: monarchy

### Processing Files

See Jupyter Notebook for processing files.

### Data Range

Countries: 120
Years: 1946 - 2010

## Boix-Miller-Rosato Dichotomous Coding of Democracy

[Boix-Miller-Rosato Dichotomous Coding of Democracy](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/FENWWR)

This data set provides a dichotomous coding of democracy for every country in the world (222 total) from 1800 to 2020.

### Indicators

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

### Processing Files

See Jupyter Notebook for processing files.

### Data Range

Countries: 203
Years: 1800 - 2020

## Lexical Index of Electoral Democracy (LIED)

[Lexical Index of Electoral Democracy (LIED)](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/WPKNIT)

LIED covers all independent countries and most semi-sovereign polities and overseas colonies, protectorates, etc. within the 1789 to 2020 timespan. Scores for each indicator reflect the status of a country on the last day of the calendar year (31 December).

The dataset consists of 14 original indicators and original two indices. The indicators are used to construct two indices, i.e., the Lexical Index of Electoral Democracy (lexical_index) and an extended version called Lexical Index of Electoral Democracy+ (lexical_index_plus).

### Indicators

- **countryn**: Name of the polity.
- **cow**: Correlates of War country ID.
- **vdem**: Varieties of Democracy country ID.
- **year**: Year.
- **male_suffrage**: All male citizens are allowed to vote in national elections (1=present, 0=absent).
- **female_suffrage**: All female citizens are allowed to vote in national elections (1=present, 0=absent).
- **executive_elections**: Chief executive is either directly or indirectly elected (1=present, 0=absent).
- **legislative_elections**: Legislative body, issues at least some laws and does not perform executive functions. The lower house (or unicameral chamber) of the legislature is at least partly elected. The legislature has not been closed (1=present, 0=absent).
- **multi_party_legislative_elections**: The lower house of the legislature is elected by voters facing more than one choice (1=present, 0=absent).
- **competitive_elections**: Elections are, in principle, sufficiently free to enable the opposition to gain power if they were to attract sufficient support from the electorate (1=present, 0=absent).
- **lexical_index**: Original index of democracy (Score 0 to 6).
- **political_liberties**: Freedom of expression, freedom of assembly, and freedom of association are respected. (1=present, 0=absent).
- **lexical_index_plus**: The meaning of the scores from 0 to 5 are identical to LIED, whereas 6 and 7 refer to the other indicator values.
- **democratic_transition**: Democratic transition took place in a given year as signified by a change in the competitive_elections indicator (1=present, 0=absent).
- **transition_type**: For years with democratic transitions, mode of transition
- **democratic_breakdown**: A democratic breakdown took place in a given year as signified by a change in competitive_elections indicator from 1 in the previous year to 0 in the current year (1=present, 0=absent).
- **breakdown_type**: For years with democratic transitions, mode of transition
- **turnover_period**: Indicates whether a particular country-year is part of a period between an initial electoral government alternation (as indicated by a turnover event, see below) in a multi-party electoral regime and an interruption of the same multi-party electoral regime (as indicated by a score
of 0 on executive elections or multi-party_legislative_elections, see above). If another turnover event happens later in the same polity, a new turnover period begins (1=present, 0=absent).
- **turnover_event**: Partisan control over government power alternated from an elected chief executive to another party/coalition/candidate representing the opposition as a consequence of a multi-party election (1=present,0=absent).
- **two_turnover_period**: Year is part of a period between a second electoral government alternation. If two turnover events happens later in the same polity under a new multi_party electoral regime, a new two-turnover period begins (1=present, 0=absent).
- **sovereign**: Indicates whether a polity/country is a separate unit in the international system of states (1) or subjected to foreign colonization or occupation with formal loss of autonomy (0).

### Lexical Index

- 0: legislative_election=0 & executive_elections=0 (regime type: non-electoral autocracies)
- 1: legislative_elections=1 or executive_elections=1 & multi-party_legislative_elections=0 (regime type: one-party autocracies, few cases where executive elections are on track but there is no functioning elected parliament)
- 2: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=0 (regime type: multiparty autocracies without elected executive – generally because a monarch influences government appointment and removal or foreign powers dominate political decision-making or has significant veto powers)
- 3: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 & competitive_elections=0 (regime type: multiparty autocracies)
- 4: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 &
- 5: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 & competitive_elections=1 & male_suffrage=1 & female_suffrage=0 (regime type: male democracies)
- 6: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 & competitive_elections=1 & male_suffrage=1 & female_suffrage=1 (regime type: electoral democracies)

### Lexical Index Plus

This index, LIED+, adds an extra layer to the upper-end of LIED in the form of political liberties. This is done to distinguish between electoral democracies and polyarchies.

The meaning of the scores from 0 to 5 are identical to LIED, whereas 6 and 7 refer to the following configurations of indicator values:

- 6: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 & competitive_elections=1 & male_suffrage=1 & female_suffrage=1 & political_liberties=0 (regime type: electoral democracies)
- 7: legislative_elections=1 & multi-party_legislative_elections=1 & executive_elections=1 & competitive_elections=1 & male_suffrage=1 & female_suffrage=1 & political_liberties=1 (regime type: polyarchies)

### Transition Type

- 1: conversion (incumbent-led)
- 2: cooperative (pact between incumbents and opposition/balanced influence)
- 3: collapse (opposition-led)
- 4: foreign supervision (imposition by foreign power based on intervention or highly asymmetrical – partial or full – decolonization)
- 5: foreign liberalization (democracy reemerges after occupational power has lost war to foreign powers)
- 0: Country-years without democratic transitions are scored 0

### Breakdown Type

- 1: implicit regression induced by incumbents
- 2: military coup
- 3: foreign occupation
- 4: self-coup (incumbents close down parliament unduly and take full political control)
- 5: coup or civil conflict headed by opposition party/movement
- 6: coup headed by monarch
- 0: Country-years without democratic breakdowns are scored 0

### Processing Files

See Jupyter Notebook for processing files.

### Data Range

Countries: 235
Years: 1789 - 2023


