# Dataset Cleanup

## Catalog

Area | Source | Name | Type | Description
--- | --- | --- | --- | ---
Democracy | Center for Systemic Peace | Polity5 | Tabular | Annual global assessment of political rights and civil liberties
Democracy | Freedom House | Freedom in the World | Tabular | Annual global assessment of political rights and civil liberties
Democracy | V-Dem Institute | Democracy Index | Tabular | Comprehensive data measuring different aspects of democracy worldwide
Democracy | World Bank | Governance Indicators | Tabular | Metrics on governance quality, rule of law, and political stability
Women Rights | World Bank | Gender Statistics | Tabular | Key indicators on gender including education, employment, health, and political participation
Women Rights | UN Women | Violence Against Women | Tabular | Statistics on domestic violence, sexual harassment, and gender-based crimes
Women Rights | OECD | Gender Wage Gap | Tabular | Data on pay differences between men and women across countries
Religion | Pew Research | Religious Demographics | Tabular | Global religious composition and trends
Religion | World Religion Database | Religious Freedom Index | Tabular | Data on religious restrictions and persecution
Religion | UN | Religious Sites Protection | Tabular | Information on preservation of religious and cultural sites

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

