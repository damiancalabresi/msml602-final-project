# MSML602 \- Principles of Data Science Final Project \- Proposal  Damian Calabresi

# **Summary**

The purpose of this study is to examine how the erosion of democratic governance and values contributes to the diminishment of women’s rights and gender equality.

Across the globe, the decline of democracy has been accompanied by a marked regression in women’s rights, along with a broader reduction in human rights protections. Far-right political movements have gained traction, fueling a conservative ideological resurgence that challenges gender equality and often portrays feminist policies as threats to traditional societal structures. This ideological backslash affects  not only women’s rights but also the human rights framework that promotes equality and justice for all.

On the other side, left-leaning governments, mostly formed during socialist and communist revolutions, implement profound changes in societal structures, human right policies, and public government access.

This relationship between democracy and human rights, especially women's rights, must be investigated while considering each country's cultural, religious, and economic values.

# **Background**

The second half of the 20th century saw significant progress in women’s rights, alongside the broader defense of human rights (Behr, Perrint, Hyland, & Trumbic, 2024). Over time, various achievements in different parts of the world led to both advances and setbacks in areas such as abortion rights, women’s suffrage and government representation, workplace equality, and seeking justice in cases of violence against women .

Some of the rights secured by feminist movements include mobility, freedom, and travel independence; anti-harassment and anti-discrimination protections in the workplace; equal pay for work of equal value; participation in the industrial workforce; equality in marriage and divorce laws; condemnation of domestic violence; maternity leave and protections for pregnant workers; access to credit and business participation; equal inheritance and administrative authority; recognition of non-monetary household contributions; access to pensions and retirement programs; and childcare benefits.

These achievements have often been realized in a select group of countries, typically those aligned with democratic and progressive values. Progress is neither linear nor guaranteed. The feminist movement has encountered setbacks during periods of cultural shifts, economic downturns, or a return to conservative governments.

The presence of checks and balances (Ortiz, Allen, Nagel, & Smith, 2023\) among government branches is an important tool to protect human rights and promote equality in a civic society.

Over the last decade, a resurgence of conservative ideologies and authoritarian, populist leaders—predominantly from far-right backgrounds—has compromised these checks and balances while targeting feminist movements and women’s rights as part of broader campaigns against democratic principles and human rights protections (Grzebalska & Pető, 2018). This backlash manifests through:

* **Rhetorical Attacks**: Public discourse that undermines gender equality policies, often framing them as threats to traditional gender roles and family structures.  
* **Policy Regression**: Rollback of provisions related to gender equality, reproductive rights, and mechanisms safeguarding women against violence.  
* **Political Marginalization**: Attempts to diminish women’s political participation by promoting narratives that confine women to subordinate societal roles.

Throughout history, women’s rights have been closely tied to democratic stability, human rights protections, and the rule of law. On the other hand, the systemic erosion of these rights frequently signals broader democratic backsliding. While no democratic regime is entirely free from gender-based restrictions, the systematic regression of women’s rights under authoritarian rule stands as a critical indicator of democratic decline.

# **Objectives**

The goal of this study is to examine the correlation between the adoption of women’s rights and democracy indexes across different countries. The objective is to determine whether autocracies lead to the deterioration of women’s rights, whether the reverse is true, or if other societal factors contribute to both the emergence of autocracies and the erosion of human rights.

The objective is to assess whether this relationship is one of correlation or causation, considering additional variables such as dominant religions, levels of religiosity, economic growth, human development, and workforce composition.

This research will also investigate exceptions to the trend, including the rise of Asian countries like Singapore and the emergence of left-leaning populist governments, which have demonstrated lower democracy index scores while simultaneously advancing protections for minorities and women’s rights.

# **Methodology**

To fulfill its objectives, this study will analyze the following datasets (See References for more details):

* World Bank Group \- Women, Business and the Law 1.0 Data for 1971-2024 (1)  
* World Bank Group \- DataBank \- Gender Statistics (2)  
* Georgetown Institute for Women, Peace and Security \- Women Peace and Security Index (3)  
* Center for Systemic Peace \- The Polity Project (4)  
* Freedom House \- Freedom in the World (5)  
* Autocratic Regime Data (6)  
* Harvard Dataverse \- Lexical Index of Electoral Democracy (LIED) (7)  
* Harvard Dataverse \- Boix-Miller-Rosato Dichotomous Coding of Democracy (8)  
* Esri Canada Education and Research \- World Religions (9)  
* World Religion Project \- Global Religion Dataset (10)  
* Secular Policy Institute \- Religiosity by Country (11)  
* Pew Research Center \- Religious Diversity Index (RDI) Table (12)

The analysis process will follow these steps:

### **Data Cleanup and Exploratory Data Analysis**

Download the datasets, clean the inconsistent data and standardize the format between all the data sources.

Initial EDA. Identify qualitative and quantitative predictors. Drop unnecessary columns and review significance of each dataset for the purpose of this study.

### **Identify Scope**

Define which countries and time periods will be studied based on the information available. (Expected to cover from 1980 to 2022\)

### **Comprehensive Analysis of Democracy Indexes**

Analyze the selected democracy indexes and calculate the correlation between teams. Decide which index will be the most significant for these studies.

Decide if qualitative or quantitative indexes will be correlated, as some datasets are dichotomy indexes while others are democracy coefficients.

Investigate over the components used to calculate each of these democracy indexes, and identify if some of them are already related to women rights, as they would lead to bias in the data.

### **Cleanup and Merge Datasets**

Do research over the religion datasets and merge them with the democracy-related data. These datasets are included in the study as they have a strong correlation with gender equality and women's role in a society.

Cleanup and merge the datasets containing gender statistics and women security indexes.

### **Linear and Logistic Regression**

Use linear and logistic regression methodologies to analyze the prediction of democracy indexes using the women rights data as predictors. Investigate the correlation between them taking into consideration the potential collinearity with religion and economic related information.

### **SVM and Clustering**

Use Support Vector Machines to classify autocracies and democracies with the women information as the axis.

Apply clustering techniques to group countries based on the democracy data as well as the gender equality data and compare the results.

### **Identify Outliers**

Identify outliers and complete a qualitative analysis of the data and potential correlation with and without these outliers.

### **Analyze impact of global events**

Study the women rights progression over the years and analyze how the may have been impacted in specific countries or regions after the occurrence of specific global events like: The end of Cold War; Taliban revolution in Afghanistan, US Civil Rights Act, Iranian revolution, Latin-american dictatorships, Emergence of Arab oil countries, Japanese Boom and Stagnation, China growth, Singapore emergence, Vietnam war, South African Apartheid, Balkan Conflicts, Arab Spring

# **Timeline**

* Week 1 (03/13): Dataset extraction and research  
* Week 2 (03/20): Data cleanup and EDA  
* Week 3 (03/27): Identify scope. Comprehensive Analysis of Democracy Indexes  
* Week 4 (04/03): Cleanup and Merge Datasets  
* Week 5 (04/10): Linear and Logistic Regression  
* Week 6 (04/17): SVM and Clustering  
* Week 7 (04/24): Identify Outliers  
* Week 8 (05/01): Analyze impact of global events  
* Week 9 (05/08): Draft paper  
* Week 10 (05/15): Redact paper and review

# **Importance**

In recent years, the world has witnessed a resurgence of conservative ideologies and the rise of authoritarian, populist leaders, predominantly from far-right backgrounds. These political shifts have weakened essential democratic mechanisms, such as checks and balances, which play a crucial role in promoting equality.

Feminist movements and women’s rights have increasingly become targets in broader campaigns aimed at dismantling democratic principles and human rights protections. In many cases, governments have portrayed gender equality initiatives as unnecessary expenditures, arguing that they divert public funds from economic development.

It is now more critical than ever to analyze the impact of these political transformations on societal progress, particularly concerning women’s rights. This study aims to highlight how the erosion of democracy correlates with setbacks in gender equality. Furthermore, it underscores the reality that rights, once granted, are not always permanent and can be rescinded under shifting political landscapes.

# **References**

## **Data Sources**

(1) World Bank Group. (2024). Women, Business and the Law 1.0 Data for 1971-2024. Retrieved from https://wbl.worldbank.org/en/wbl-data

(2) World Bank Group. (2024). DataBank \- Gender Statistics. Retrieved from https://databank.worldbank.org/source/gender-statistics

(3) Georgetown Institute for Women, Peace and Security. (2024). Women Peace and Security Index. Retrieved from https://giwps.georgetown.edu/the-index/

(4) Center for Systemic Peace. (2024). The Polity Project. Retrieved from https://www.systemicpeace.org/polityproject.html

(5) Freedom House. (2024). Freedom in the World. Retrieved from https://freedomhouse.org/report/freedom-world

(6) Pennsylvania State University. (2024). Autocratic Regime Data. Retrieved from https://sites.psu.edu/dictators/

(7) Harvard Dataverse. (2024). Lexical Index of Electoral Democracy (LIED). Retrieved from https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/WPKNIT

(8) Harvard Dataverse. (2024). Boix-Miller-Rosato Dichotomous Coding of Democracy. Retrieved from https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/FENWWR

(9) Esri Canada Education and Research. (2024). World Religions Dataset. Retrieved from https://edu.hub.arcgis.com/datasets/world-religions/explore?showTable=true

(10) World Religion Project. (2024). Global Religion Dataset. Retrieved from https://www.thearda.com/data-archive?fid=WRPGLOBL

(11) Secular Policy Institute. (2024). Religiosity by Country. Retrieved from https://secularpolicyinstitute.net/wp-content/uploads/2015/03/secular-demographics-by-country.pdf

(12) Pew Research Center. (2024). Religious Diversity Index (RDI) Table. Retrieved from https://www.pewresearch.org/religion/2014/04/04/religious-diversity-index-scores-by-country/

## **Academic Sources**

Grzebalska, W., & Pető, A. (2018). The gendered modus operandi of the illiberal transformation in Hungary and Poland. Women's Studies International Forum, 68, 164-172. ISSN 0277-5395. https://doi.org/10.1016/j.wsif.2017.12.001

Behr, D. M., Perrint, C., Hyland, M., & Trumbic, T. (2024). *Empowering Change: Assessing the Role of Democracy, Civil Society, and Women’s Rights Groups in Advancing Legal Gender Equality*. World Bank Group. Retrieved from https://www.worldbank.org

Ortiz, E., Allen, J., Nagel, R. U., & Smith, J. M. (2023). Exploring the Links between Women’s Status and Democracy. Washington, DC: Georgetown Institute for Women, Peace and Security. https://giwps. georgetown. ed u/wp-content/uploads/2023/03/Exploring-the-Links-betwee n-Womens-Status-and-Democracy.pdf.

## **Background and Context**

(1) Human Rights Watch. (2023). The Fight for Women’s Rights is a Fight Against Authoritarianism. Retrieved from https://www.hrw.org/news/2023/01/04/fight-womens-rights-fight-against-authoritarianism