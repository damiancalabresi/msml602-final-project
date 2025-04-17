# Exploratory Data Analysis

In this stage I will perform a comprehensive analysis of the datasets.

## Steps

The EDA stage includes some of the following steps:

### Review Predictors, Ranges, and Missing Values
The data cleanup process implied going through each dataset reference documentation to understand the meaning of each predictor, review the ranges, complete empty values, and leave empty records out.

### Review Correlation between variables

Each dataset provides a key index (E.g.: Polity5, RDI, WPS Index, etc.) as a measurement of democracy or women rights. In almost every case, these indexes are calculated based on the predictors of the dataset. This calculation is precise and documented in the dataset reference documentation. For this reason, it's not valuable to measure this correlation.

### Principal Component Analysis

Most of the indexes present in the datasets are based on a fixed calculation from the predictors. This reduces the variance and richness of the dataset to one linear variable.

Doing PCA we can study which predictors are more important to understand the difference between the countries.

### Compare dataset indexes

Multiple datasets are provided to evaluate the same concept. To be more precise, 5 democracy, 2 religion, and 2 women rights datasets are studied.

## Democracy

### Polity5

For more details see [pca-polity5.ipynb](pca-polity5.ipynb)

Did a PCA with the columns that aren't calculated from another predictors. They are: 'exrec', 'parcomp', 'parreg', 'polcomp', 'xconst', 'xrcomp', 'xropen', 'xrreg'.

- exrec: Executive Recruitment Concept
- parcomp: The Competitiveness of Participation
- parreg: Regulation of Participation
- polcomp: Political Competition Concept
- xconst: Executive Constraints (Decision Rules)
- xrcomp: Competitiveness of Executive Recruitment
- xropen: Openness of Executive Recruitment
- xrreg: Regulation of Chief Executive Recruitment

The PCA was done over all the years and only taking a snapshot of each country for the last year.

The purpose of the PCA is to understand which predictors are more important to understand the difference between the countries. Based on the analysis, all of them are significant except for 'parreg'. 'xrreg' and 'xropen' aren't as important as the others.

### Freedom in the World

For more details see [pca-freedom-in-the-world.ipynb](pca-freedom-in-the-world.ipynb)

Did a PCA over all the predictors that were not calculated from another predictors. They were all similarly significant and very highly correlated.

From this analysis I understand that no predictor adds more value to differentiate countries than the total score or the aggregated indexes. When correlating this dataset to others, comparing only the total score should give us enough information.

### Autocratic Regime Data

This dataset contains a list of autocratic regimes and the dates they started and ended. The analysis of these dates has already been done during the dataset cleanup.

### Boix-Miller-Rosato Dichotomous Coding of Democracy

This dataset describes, for each country and year, if a country is democratic or not. There aren't more predictors than this. The dataset has already been analyzed during the cleanup.

This dichotomous index will have to be compared to the other indexes to see if it's a good proxy for democracy.

### Lexical Index of Electoral Democracy

For more details see [pca-lied.ipynb](pca-lied.ipynb)

This dataset describes, for each country and year, the level of democracy based on a series of boolean indicators. Boolean predictors are not ideal for PCA but I made the analysis. It shows that having or not executive or legislative elections, as well as male and female suffrage, are the most important predictors to differentiate the democracy between countries.

The correlation matrix gives us more information about this dataset:
- We see a high correlation between countries with executive and legislative elections. Most countries with legislative elections also have multi-party legislative elections. While they're outliers, the indicator of having elections is already a good differentiation factor.
- Not many of the countries with executive or legislative elections have real competitive elections, less than that have enough political liberties.
- Something that calls my attention is that female suffrage is not thightly correlated with a country policital liberties or competitive elections. This doesn't support the premise of our investigation.
- A country being sovereign doesn't seem to be correlated with anything related to suffrage and democracy. I would say these predictors about sovereignty are not important for our analysis.

## Religion

### Pew Research Center - Global Religious Diversity

For more details see [pca-global-religious-diversity.ipynb](pca-global-religious-diversity.ipynb)

Each predictor is a percentage of a religion in a country. There is no correlation to analyze between them.

The "Religious Diversity Index" is calculated using the Herfindahl-Hirschman Index so the correlation is fixed.

I created a linear regression model to see if the religious diversity is correlated with countries were a given religion is the dominant one. I found that:
- Countries with Christian or Muslim majority have lower religious diversity and this is statistically significant.
- Countries with an unaffiliated majority or folks religion majority have higher religious diversity.

### National Religion Dataset

For more details see [pca-national-religion-dataset.ipynb](pca-national-religion-dataset.ipynb)

This dataset provides a time series of the percentage of each religion in a country. The religion indicators are more detailed, differentiating between different christian, muslim denominations, and other religions.

The information provided by this dataset isn't as reliable as the one from the Pew Research Center.

I added a column to the dataset to calculate which religion is the majority in a country.

## Women's Rights

### Georgetown Institute for Women, Peace and Security - Women Peace and Security Index

For more details see [pca-georgetown.ipynb](pca-georgetown.ipynb)

This is a tabular dataset based on surveys and reports done in different countries. It evaluates several predictors related to women's rights and safety and calculates an index for each country.

The dataset has already been cleaned.

I did a PCA as well as a regression to see which predictors are more important to understand the difference between the countries. These predictors seems to be the most significant:

- Education
- Financial Inclusion
- Maternal Mortality Ratio
- Intimate Partner Violence
- Proximity to Conflict
- Cell Phone Use
- Access to Justice

### World Bank Group - Women, Business and the Law Historical Data

For more details see [pca-world-bank.ipynb](pca-world-bank.ipynb)

This is a time series dataset which provides a series of boolean predictors for each country and year. Those predictors are grouped in categories and a score is calculated for each category based on the percentage of boolean predictors that are true.

I did a PCA over the entire dataset, then took a snapshot of the last year (2024) and followed the same process.

When looking at the entire dataset it looks like every predictor is equally important for the variance of the dataset. This means there are two dimensions: countries and years. The dataset has a lot of variance in general, without a clear pattern definition.

When looking at just the last year, the dataset keeps having a lot of variance but the score in the marriage category has somewhat more importance to differentiate between the women situation in the countries.

## EDA Summary

In almost every dataset I did a PCA using the original predictors (Not the calculated indexes). This shows a 2D visualization of the dataset and it's variance. It looks like every dataset has a lot of variance, without a clear pattern definition.

This predicts that the correlation between the democracy and women rights indexes will be low or not precise. I'll discover this in the next phase.

# Scope Definition

## Time Series Snapshot

Through the EDA, for the time series datasets, I took a snapshot of the information for each country on the last year of the dataset and I saved those as new datasets.

## Define Countries

For more details see [scope-definition.ipynb](scope-definition.ipynb)

I imported all the tabular datasets (Including the snapshots from the time series datasets) and I defined the countries that I'll use for the analysis.

When comparing names or codes a lot of countries were excluded given that their names didn't match. I had to use the `CountryConverter` to get the ISO3 codes for each country and added a new column named "iso3" to each dataset.

The list of 154 countries that are present in all datasets is:

Afghanistan, Angola, Albania, United Arab Emirates, Argentina, Armenia, Australia, Austria, Azerbaijan, Burundi, Belgium, Benin, Burkina Faso, Bangladesh, Bulgaria, Bahrain, Belarus, Bolivia, Plurinational State of, Brazil, Bhutan, Botswana, Central African Republic, Canada, Switzerland, Chile, China, Côte d'Ivoire, Cameroon, Congo, Colombia, Comoros, Cabo Verde, Costa Rica, Cyprus, Czechia, Germany, Djibouti, Denmark, Dominican Republic, Algeria, Ecuador, Egypt, Spain, Estonia, Ethiopia, Finland, Fiji, France, Gabon, United Kingdom, Georgia, Ghana, Guinea, Gambia, Guinea-Bissau, Equatorial Guinea, Greece, Guatemala, Guyana, Honduras, Croatia, Haiti, Hungary, Indonesia, India, Ireland, Iran, Islamic Republic of, Iraq, Israel, Italy, Jamaica, Jordan, Japan, Kazakhstan, Kenya, Kyrgyzstan, Cambodia, Korea, Republic of, Kuwait, Lao People's Democratic Republic, Lebanon, Liberia, Sri Lanka, Lesotho, Lithuania, Luxembourg, Latvia, Morocco, Moldova, Republic of, Madagascar, Mexico, North Macedonia, Mali, Myanmar, Mongolia, Mozambique, Mauritania, Mauritius, Malawi, Malaysia, Namibia, Niger, Nigeria, Nicaragua, Netherlands, Norway, Nepal, New Zealand, Oman, Pakistan, Panama, Peru, Philippines, Papua New Guinea, Poland, Portugal, Paraguay, Qatar, Romania, Russian Federation, Rwanda, Saudi Arabia, Senegal, Singapore, Solomon Islands, Sierra Leone, El Salvador, Somalia, Suriname, Slovakia, Slovenia, Sweden, Eswatini, Syrian Arab Republic, Chad, Togo, Thailand, Tajikistan, Timor-Leste, Trinidad and Tobago, Tunisia, Türkiye, Taiwan, Province of China, Tanzania, United Republic of, Uganda, Ukraine, Uruguay, United States, Uzbekistan, Venezuela, Bolivarian Republic of, Viet Nam, South Africa, Zambia, Zimbabwe.

**Polity5** dataset is the most restrictive one and is excluding multiple countries out of the analysis. When comparing specific datasets, specially when Polity5 is not involved, I'll use all the countries included in the two datasets.